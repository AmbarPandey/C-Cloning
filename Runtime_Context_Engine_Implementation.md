# Runtime Context Engine Implementation

**Project:** C-Cloning — Master Runtime Implementation
**Phase:** Phase 4 — Context Engine
**Artifact Type:** Implementation (runtime objects, contracts, interfaces, pipeline)
**Branch:** `feature/master-runtime-implementation`
**Consumes (LOCKED / prior implementation phases, never modified):** Master Runtime Architecture
v1.1; Runtime Engineering Standard; Runtime Configuration System; Runtime Bootstrap Implementation
(Phase 1 → `BootstrapSession`); Runtime Configuration Loader Implementation (Phase 2 →
`ConfigurationSession` / `ConfigurationRegistry`); Runtime Module Engine Implementation
(Phase 3 → `ModuleEngineHandle`).

> This is an **implementation** artifact, not a design or specification. It defines the concrete
> engine that **assembles and exposes** the Runtime Execution Context. It does **not** redesign the
> Runtime Context model. It consumes only prior **implementation-layer** runtime objects and **never
> reads configuration directly** — all configuration is reached through the Phase-2
> `ConfigurationSession`/`ConfigurationRegistry` handles it is given.

---

## 0. Implementation Conventions (inherited from Phases 1–3)

- **Object notation:** typed field lists (`name: Type`) with abstract types (`String`, `Int`, `Bool`,
  `Enum`, `Map<K,V>`, `List<T>`, `Ref<T>`, `Hash`, `Timestamp`). No platform types.
- **Interface notation:** `operation(inputs) -> outputs throws ContextError`.
- **Source access rule:** the Context Engine consumes **only** upstream runtime handles —
  `BootstrapSession`, `ConfigurationSession`, `ModuleEngineHandle`. It **never** opens YAML files and
  **never** re-reads configuration outside the Phase-2 registry surface.
- **Immutability:** objects marked `sealed` are frozen after construction; consumers receive `Ref<T>`.
- **Determinism:** discovery/resolution/expansion order is derived from upstream artifacts
  (module order from the engine, key order from the registry), never from enumeration order. Same
  upstream inputs ⇒ same `ExecutionContext` and same hashes.

### 0.1 Relationship to prior phases
- **Phase 1** → `BootstrapSession` (runtime identity, repository binding, runtime state).
- **Phase 2** → `ConfigurationSession` + `ConfigurationRegistry` (effective config, provenance,
  per-module views).
- **Phase 3** → `ModuleEngineHandle` (module table, module state table, `ModuleExecutor`).
- **Phase 4 (this)** consumes all three and produces the sealed **`ExecutionContext`** — the single
  object Phase 5 executes against. The Context Engine assembles context; it does not define what
  context *means* (that is the locked Runtime Context model).

---

## 1. Context Engine Implementation (component inventory)

| Component | Role (implementation) |
|-----------|-----------------------|
| **ContextEngine** | Top-level façade owning the context runtime. Exposes the sealed `ExecutionContext` to Phase 5. Holds the `ContextRegistry`, the `ContextCache`, and the builder/resolver/expansion components. |
| **ContextBuilder** | Orchestrates the context pipeline (X0–X8); assembles context fragments from upstream sessions; enforces fail-closed behavior; returns exactly one of `ExecutionContextHandle` (success) or `ContextError` (failure). |
| **ContextRegistryAdapter** | Read-only adapter over upstream handles (`BootstrapSession`, `ConfigurationRegistry`, `ModuleEngineHandle`). Translates them into engine-internal `ContextSourceView` objects. Never modifies upstream objects or reads config directly. |
| **ContextResolver** | Resolves context fragments into a coherent, de-duplicated context tree; resolves cross-references between bootstrap/config/module fragments; establishes provenance. |
| **ContextExpansionEngine** | Applies the declared, bounded expansion of context (derived/computed context entries) using only upstream-supplied inputs; enforces expansion limits (Section 7). |
| **ContextValidator** | Runs the ordered context validation rule set; produces a `ContextValidationReport`. |
| **ContextCache** | Stores resolved fragments and the assembled context keyed by content hash; enforces the cache strategy (Section 9). |
| **ContextSession** | The sealed, run-scoped object representing "the execution context for this Runtime session"; boundary object to Phase 5. |

### 1.1 Context Builder (implementation)
```
ContextBuilder.run(bootstrap: BootstrapSession, config: ConfigurationSession, engine: ModuleEngineHandle)
    -> ContextResult                              # ExecutionContextHandle | ContextError
  ctx := new ContextBuildScope(bootstrap, config, engine)
  for stage in ContextExpansionPipeline.stages:   # X0..X8, fixed order
      outcome := stage.execute(ctx)
      if outcome.is_failure:
          err := ContextError.from(stage, outcome, ctx)
          ContextCache.rollback(ctx)              # discard partial cache entries for this run
          return { status: FAILED, error: err }
      ctx.apply(outcome.produced_objects)          # append-only
  engine_ctx := ContextEngine.seal(ctx)            # sealed, immutable façade
  return { status: SUCCESS, handle: engine_ctx.handle() }
```
- Single entry, single result (`ContextResult` tagged union). Fail-closed: first failing stage
  aborts, cache is rolled back, a structured `ContextError` is returned; no partial context escapes.
- Only the builder mutates the build scope, and only by appending sealed stage outputs.

> **Note:** `ContextBuildScope` is the mutable assembly buffer during build; `ExecutionContext` is the
> sealed result. They are distinct objects (assembly vs. identity), mirroring Phase 2/3 conventions.

---

## 2. Context Runtime Objects

### 2.1 `ContextSourceView` (produced by X1 via adapter, sealed per source)
```
ContextSourceView {
  source_kind:  Enum{ BOOTSTRAP, CONFIGURATION, MODULE_ENGINE }
  handle_ref:   Ref<Opaque>        # ref to the upstream session/handle (read-only)
  exposed_keys: List<String>       # the context-relevant keys this source contributes
  source_hash:  Hash               # hash of the upstream object's identity hash (continuity)
}
```
> `ContextSourceView` is a **read projection** over an upstream artifact. It restates no design
> meaning and reads no configuration file directly.

### 2.2 `ContextFragment` (produced by X2, sealed per fragment)
```
ContextFragment {
  fragment_id:  String
  origin:       Enum{ BOOTSTRAP, CONFIGURATION, MODULE_ENGINE }
  entries:      Map<String, ContextEntry>
  fragment_hash:Hash
}
ContextEntry {
  key:          String
  value_ref:    Ref<Any>           # reference to upstream value (never a copy of config content)
  provenance:   ContextProvenance
  derived:      Bool               # true if produced by expansion (X3), else false
}
ContextProvenance { origin: Enum, upstream_key: String, phase: String }
```

### 2.3 `ContextValidationReport` (produced by X4, sealed)
```
ContextValidationReport {
  passed:        Bool
  checks:        List<ContextCheck>   # ordered, deterministic
  first_failure: Optional<String>
}
ContextCheck { id: String, category: Enum{ PRESENCE, PROVENANCE, REFERENCE, CONSISTENCY, EXPANSION_BOUND }, passed: Bool, detail: String }
```

### 2.4 `ExecutionContext` (produced by X5, sealed) — see Section 4.

### 2.5 `ContextRegistryObject` (produced by X5, sealed) — see Section 5.

### 2.6 Object lineage (what produces what)
```
BootstrapSession + ConfigurationSession + ModuleEngineHandle
   └─(X1 Discovery)→ ContextSourceView[BOOTSTRAP, CONFIGURATION, MODULE_ENGINE]
                        └─(X2 Resolution)→ ContextFragment[*] (de-duplicated, provenance-tagged)
                                              └─(X3 Expansion)→ ContextFragment[*] + derived entries (bounded)
                                                                   └─(X4 Validation)→ ContextValidationReport
                                                                                        └─(X5 Construction)→ ExecutionContext + ContextRegistryObject
                                                                                                               └─(X6 Session)→ ContextSession
                                                                                                                                 └─(X7/X8 Expose)→ ExecutionContextHandle → Phase 5
```

---

## 3. Context Runtime Contracts

| Contract ID | Between | Guarantee |
|-------------|---------|-----------|
| **CX-UPSTREAM-ONLY** | Adapter → sources | The engine consumes only `BootstrapSession`, `ConfigurationSession`, `ModuleEngineHandle`; it never reads configuration files directly. |
| **CX-NO-REDESIGN** | Engine → context model | The engine assembles context per the existing model; it defines no new context semantics. |
| **CX-NO-DUP** | Resolver/Registry → config | Context entries hold *references* to upstream values with provenance; config content is never copied or re-authored. |
| **CX-PROVENANCE** | Resolver → entries | Every `ContextEntry` carries a `ContextProvenance` (origin, upstream_key, phase). |
| **CX-BOUNDED-EXPANSION** | Expansion → context | Expansion produces only declared, bounded derived entries from upstream inputs; unbounded/undeclared expansion → fail. |
| **CX-VALIDATE-FIRST** | Validator → construction | `ExecutionContext` is constructed only after `ContextValidationReport.passed == true`. |
| **CX-CONTINUITY** | Engine → prior phases | Source hashes must match upstream session/engine identity hashes; mismatch fails closed. |
| **CX-IMMUTABLE** | Engine → Phase 5 | The exposed `ExecutionContext` is sealed and read-only; there is no mutate surface. |
| **CX-CACHE-COHERENT** | Cache → all | A cached entry is valid only if its content hash matches current inputs; stale entries evicted. |
| **CX-FAILCLOSED** | Builder → all | Any breach → structured `ContextError` + cache rollback; no partial context exposed. |
| **CX-SINGLE-RESULT** | Builder → caller | Exactly one of `ExecutionContextHandle` or `ContextError` is returned. |

---

## 4. Execution Context Model

The **ExecutionContext** is the sealed object Phase 5 executes against. The engine **assembles** it;
it does not redefine its meaning.

```
ExecutionContext {
  session_id:      String                    # inherited from upstream sessions
  bootstrap_ref:   Ref<BootstrapSession>      # read-only
  config_ref:      Ref<ConfigurationSession>  # read-only (registry access surface)
  engine_ref:      Ref<ModuleEngineHandle>    # read-only (module executor + states)
  registry:        Ref<ContextRegistryObject> # queryable context index
  fragments:       Map<String, Ref<ContextFragment>>
  active_mode:     String                     # sourced from config session (not re-read)
  active_version:  String
  context_hash:    Hash                       # deterministic over registry + fragment hashes
}
```
**Rules**
- `ExecutionContext` is **read-only** after seal. There is no `set()`; execution reads context, and
  module invocation happens through the engine's `ModuleExecutor` reachable via `engine_ref`.
- It composes rather than copies: config/module/bootstrap data are reached through references, so the
  authority of the locked artifacts and prior phases is preserved.

---

## 5. Context Registry Model

The **Context Registry** is the sealed, queryable index that Phase 5 uses to read context.

```
ContextRegistryObject {
  index_by_key:    Map<String, Ref<ContextEntry>>       # dotted context key -> entry
  index_by_origin: Map<Enum, List<String>>              # origin -> keys
  derived_keys:    List<String>                          # keys produced by expansion
  registry_hash:   Hash
}
```
**Context registry read interface (query surface for Phase 5):**
```
interface ContextRegistry {
  get(key: String) -> Any throws ContextError            # ContextError{ KEY_NOT_FOUND } if absent
  getOrDefault(key: String, default: Any) -> Any
  provenanceOf(key: String) -> ContextProvenance
  keysByOrigin(origin: Enum) -> List<String>
  isDerived(key: String) -> Bool
  snapshotHash() -> Hash
}
```
**Rules**
- Read-only after seal (no `set()`); context is immutable during a session.
- `get()` on an unknown key fails closed with `ContextError{ KEY_NOT_FOUND }` so downstream execution
  cannot silently proceed on missing context.

---

## 6. Context Interfaces

Behavioral contracts implemented by engine components. Platform bindings deferred to the conformance phase.

```
interface ContextRegistryAdapter {
  views(bootstrap: BootstrapSession, config: ConfigurationSession, engine: ModuleEngineHandle)
      -> List<ContextSourceView> throws ContextError
}

interface ContextResolver {
  resolve(views: List<ContextSourceView>) -> List<ContextFragment> throws ContextError
}

interface ContextExpansionEngine {
  expand(fragments: List<ContextFragment>) -> List<ContextFragment> throws ContextError   # bounded, declared only
}

interface ContextValidator {
  validate(fragments: List<ContextFragment>) -> ContextValidationReport
}

interface ContextCache {
  get(content_hash: Hash) -> Optional<Ref<Any>>
  put(content_hash: Hash, value: Any) -> Unit
  evict(content_hash: Hash) -> Unit
  rollback(scope: ContextBuildScope) -> Unit
}

interface ContextRegistry { ... }              # see Section 5

interface ContextEngine {                       # exposed façade
  handle() -> ExecutionContextHandle
  context() -> Ref<ExecutionContext>
  registry() -> Ref<ContextRegistry>
}
```
**Interface rules**
- Every failable operation throws a `ContextError` (never a platform-native exception escaping the
  engine boundary).
- No interface reads configuration files directly; all config access is via the `ConfigurationSession`
  passed in.

---

## 7. Context Expansion Pipeline

Ordered stages. Each declares **Inputs**, **Consumed Runtime Objects**, **Produced Runtime Objects**,
**Outputs**, and **Failure Behaviour**, matching the required implementation flow
(Bootstrap Session → Configuration Session → Module Engine → Discovery → Resolution → Expansion →
Validation → Execution Context Construction → Expose → Phase 5).

### Stage X0 — Upstream Intake
- **Inputs:** `BootstrapSession`, `ConfigurationSession`, `ModuleEngineHandle`
- **Consumed objects:** the three upstream handles (read-only)
- **Produced objects:** initialized `ContextBuildScope`
- **Failure behaviour:** any upstream handle missing/unexposed → `ContextError{ INTAKE_ERROR }`; abort.

### Stage X1 — Context Discovery
- **Inputs:** upstream handles
- **Consumed objects:** `BootstrapSession` (runtime state), `ConfigurationRegistry` (via config session), `ModuleEngineHandle` (module/state tables)
- **Produced objects:** `ContextSourceView[BOOTSTRAP, CONFIGURATION, MODULE_ENGINE]`
- **Failure behaviour:** source view cannot be built / continuity hash mismatch → `ContextError{ DISCOVERY_ERROR }`; abort.

### Stage X2 — Context Resolution
- **Inputs:** `ContextSourceView[*]`
- **Consumed objects:** source views' exposed keys
- **Produced objects:** `ContextFragment[*]` (de-duplicated, provenance-tagged)
- **Failure behaviour:** unresolved cross-reference / duplicate-key conflict undefinable → `ContextError{ RESOLUTION_ERROR }`; abort.

### Stage X3 — Context Expansion
- **Inputs:** resolved fragments
- **Consumed objects:** fragment entries (upstream-sourced only)
- **Produced objects:** fragments augmented with **bounded, declared** derived entries (`derived=true`)
- **Failure behaviour:** undeclared/unbounded expansion attempted → `ContextError{ EXPANSION_ERROR }`; abort.

### Stage X4 — Context Validation
- **Inputs:** expanded fragments
- **Consumed objects:** fragment provenance + references
- **Produced objects:** `ContextValidationReport`
- **Failure behaviour:** any check fails → `ContextError{ VALIDATION_ERROR, cause = first_failure }`; abort.

### Stage X5 — Execution Context Construction
- **Inputs:** validated fragments, upstream refs
- **Consumed objects:** `BootstrapSession`, `ConfigurationSession`, `ModuleEngineHandle` refs
- **Produced objects:** `ExecutionContext` (sealed), `ContextRegistryObject`
- **Failure behaviour:** construction/seal failure → `ContextError{ CONSTRUCTION_ERROR }`; abort.

### Stage X6 — Context Session Creation
- **Inputs:** sealed execution context
- **Consumed objects:** upstream session ids
- **Produced objects:** `ContextSession` (sealed)
- **Failure behaviour:** seal failure / incomplete scope → `ContextError{ SESSION_ERROR }`; abort.

### Stage X7 — Context Finalization
- **Inputs:** `ContextSession`
- **Consumed objects:** none
- **Produced objects:** finalized engine façade (`ContextEngine`)
- **Failure behaviour:** finalization inconsistency → `ContextError{ FINALIZE_ERROR }`; abort.

### Stage X8 — Expose Execution Context & Pass to Phase 5
- **Inputs:** finalized engine
- **Consumed objects:** `ExecutionContext`, `ContextRegistry`
- **Produced objects:** `ExecutionContextHandle`; context session `lifecycle → EXPOSED`
- **Failure behaviour:** exposure/publish failure → `ContextError{ EXPOSE_ERROR }`; abort + cache rollback.

### Pipeline order (fixed)
```
X0 Intake → X1 Discovery → X2 Resolution → X3 Expansion → X4 Validation →
X5 Construction → X6 Session → X7 Finalization → X8 Expose → Phase 5
```

---

## 8. Context Error Objects

The single structured error returned on any unrecoverable context failure.

```
ContextError {
  error_id:        String
  session_id:      String
  stage_id:        Enum{ X0, X1, X2, X3, X4, X5, X6, X7, X8 }
  origin:          Optional<Enum>          # BOOTSTRAP | CONFIGURATION | MODULE_ENGINE, if applicable
  error_class:     Enum{ INTAKE_ERROR, DISCOVERY_ERROR, RESOLUTION_ERROR, EXPANSION_ERROR,
                          VALIDATION_ERROR, CONSTRUCTION_ERROR, SESSION_ERROR, FINALIZE_ERROR,
                          EXPOSE_ERROR, KEY_NOT_FOUND }
  error_code:      String                  # stable, deterministic per (stage, cause)
  message:         String
  cause_detail:    String                  # e.g. unresolved ref, unbounded expansion, missing key
  produced_before_failure: List<String>    # object ids produced before abort
  cache_rolled_back: Bool
  occurred_at:     Timestamp
  recoverable:     Bool                     # always false within the engine (retry is outer-orchestration only)
}
```
**Failure behaviour (implementation)**
- Built by the builder the instant a stage returns failure or an interface throws.
- Deterministic: identical faulty upstream inputs ⇒ identical `stage_id` + `error_code` across all platforms.
- Triggers `ContextCache.rollback(scope)`, discards the partial build scope, and returns the error.
  No `ExecutionContextHandle` is ever exposed on failure. Upstream sessions/engine are left untouched.

---

## 9. Context Cache Strategy

The cache accelerates context assembly **without ever compromising upstream authority**.

| Aspect | Strategy (implementation) |
|--------|---------------------------|
| **Keying** | Entries keyed by content hash (`fragment_hash`, `context_hash`) or upstream `source_hash`. Never by path or time. |
| **Population** | X2 caches resolved fragments; X5 caches the assembled `ExecutionContext`. |
| **Coherence (CX-CACHE-COHERENT)** | Before serving a cached entry, the engine checks the upstream `source_hash`es still match; on mismatch the entry is evicted and rebuilt. A cached context can never mask changed upstream state. |
| **Scope** | Two tiers: (a) **run-scoped** working cache tied to a `ContextBuildScope`; (b) optional **cross-session** cache keyed by `context_hash`, valid only while all upstream hashes match. |
| **Invalidation** | Eviction triggers: upstream hash change (bootstrap/config/engine), `active_version` change, explicit `evict`. No time-based expiry — validity is content-driven (deterministic). |
| **Rollback** | On any `ContextError`, entries produced during the failing run are evicted (`rollback`); a failed build leaves the cache exactly as before. |
| **Read-through** | `ContextRegistry.get()` reads from the assembled context already in memory; it never re-derives fragments at query time. |
| **Immutability** | Cached values are sealed references; consumers cannot mutate them. |

**Determinism note:** content-hash keys and no time-based expiry mean cache hits never change results —
the same upstream inputs always produce the same `ExecutionContext`.

---

## 10. Implementation Readiness Assessment

| Dimension | What is implemented here | Ready? |
|-----------|--------------------------|--------|
| Build orchestration | `ContextBuilder` + fixed pipeline X0–X8, single result | **Yes** |
| Upstream consumption | Consumes only `BootstrapSession`/`ConfigurationSession`/`ModuleEngineHandle`; no direct config reads | **Yes** |
| Resolution | Fragment resolution with de-duplication + provenance | **Yes** |
| Expansion | Bounded, declared-only expansion (`CX-BOUNDED-EXPANSION`) | **Yes** |
| Validation | Ordered `ContextValidationReport`, validate-before-construct | **Yes** |
| Execution context | Sealed, composed (not copied) `ExecutionContext` for Phase 5 | **Yes** |
| Registry | Sealed, queryable `ContextRegistryObject`; read-only surface | **Yes** |
| Caching | Content-hash keyed, coherence-checked, rollback-safe, deterministic | **Yes** |
| Errors | Single structured `ContextError` + rollback wiring | **Yes** |
| Continuity | Source-hash match binds Phase 4 to Phases 1–3 (`CX-CONTINUITY`) | **Yes** |

**Deferred to later phases (require executable bindings + resolvable upstream objects at runtime):**
1. Binding the interfaces per platform (Claude/OpenAI/Python/LangGraph/n8n) and asserting identical
   `context_hash` / `registry_hash` across all five.
2. Executing resolution/expansion against the *actual* upstream session/engine outputs.
3. Fault-injecting each `error_class` to confirm deterministic codes and clean rollback.

**Verdict:** The Context Engine is **implementation-ready**. Every artifact is concrete, consumes only
prior implementation-layer runtime objects (never configuration directly), does not redesign the
Runtime Context model, and produces the sealed `ExecutionContext` Phase 5 requires.

---

## 11. Internal Quality Review (self-verification)

| Check | Result |
|-------|--------|
| No Runtime Architecture modified | **PASS** — no architecture defined/changed; only context assembly machinery |
| No Runtime Context redesigned | **PASS** — engine assembles per existing model; `CX-NO-REDESIGN`; defines no new context semantics |
| Context Engine consumes only Runtime implementation artifacts | **PASS** — `CX-UPSTREAM-ONLY`; X0/X1 take only the three upstream handles; no direct config reads |
| Execution Context supports downstream execution | **PASS** — sealed `ExecutionContext` + `ContextRegistry` are the Phase 5 read/execute surface (§4, §5) |
| Output is implementation-oriented | **PASS** — components, objects, interfaces, pipeline, cache/error wiring; no design narrative |
| No configuration duplicated | **PASS** — entries hold references with provenance (`CX-NO-DUP`), never copies |
| Single entry, single result; fail-closed | **PASS** — §1.1 (`CX-SINGLE-RESULT`, `CX-FAILCLOSED`) |

**No section resembled a design document; no rewrite required. Approved for commit.**

---

*End of Runtime Context Engine Implementation — Phase 4, Project C-Cloning.*
