# Runtime Configuration Loader Implementation

**Project:** C-Cloning — Master Runtime Implementation
**Phase:** Phase 2 — Configuration Loader
**Artifact Type:** Implementation (runtime objects, contracts, interfaces, pipeline)
**Branch:** `feature/master-runtime-implementation`
**Consumes (LOCKED, never modified):** Runtime Configuration System —
`runtime_manifest.yaml`, `repository_map.yaml`, `module_registry.yaml`, `execution_modes.yaml`,
`runtime_versions.yaml`; Master Runtime Architecture v1.1; Runtime Engineering Standard;
Runtime Bootstrap Implementation (Phase 1).

> This is an **implementation** artifact, not a design or specification. It defines the concrete
> machinery that loads, validates, resolves, caches, and exposes Runtime Configuration during
> execution. The Runtime Configuration System already exists and is authoritative; here we describe
> only **how the implementation consumes and operates on it**.

---

## 0. Implementation Conventions (inherited from Phase 1)

- **Object notation:** typed field lists (`name: Type`) with abstract types (`String`, `Int`, `Bool`,
  `Enum`, `Map<K,V>`, `List<T>`, `Ref<T>`, `Hash`, `Timestamp`). No platform types.
- **Interface notation:** `operation(inputs) -> outputs throws ConfigError`.
- **Config access:** `CFG.<file>.<path>` denotes a **read** of a locked config value. This phase
  **reads only** — it never writes, reorders, or restates the source files.
- **Immutability:** objects marked `sealed` are frozen after construction; consumers receive
  `Ref<T>` handles.
- **Determinism:** ordering (source order, key merge, resolution) is derived from the locked config
  (`CFG.runtime_manifest.config_load_order`), never from filesystem/enumeration order. Same sources
  ⇒ same `EffectiveConfiguration` and same hashes.

### 0.1 Relationship to Phase 1
Phase 1 (Bootstrap) already produced a first-pass `EffectiveConfig` object during startup. **Phase 2
does not re-invent that load.** Instead it implements the *durable, execution-time* Configuration
subsystem that:
1. Accepts the bootstrap-produced config handle as its seed input, and
2. Provides the long-lived **Configuration Registry / Context / Session** used by all later phases.

The Phase 1 `EffectiveConfig` is treated as an input seed; the Phase 2 `EffectiveConfiguration` is
the authoritative execution-time object. They agree by `config_hash` (verified in Stage L3).

---

## 1. Configuration Loader Implementation (component inventory)

| Component | Role (implementation) |
|-----------|-----------------------|
| **ConfigurationLoader** | Reads the five locked files (via the repository binding from Phase 1) into raw source records, in manifest-declared order. Read-only. |
| **ConfigurationValidator** | Runs the ordered validation rule set against the raw + merged config. Produces a `ConfigValidationReport`. |
| **ConfigurationResolver** | Applies precedence merge, resolves references/variables, selects the active execution mode and active version, and produces the sealed `EffectiveConfiguration`. |
| **ConfigurationCache** | Stores parsed source records and the resolved effective config keyed by content hash; enforces the cache strategy (Section 10). |
| **ConfigurationRegistry** | The queryable, sealed index of all effective configuration values and their provenance. The primary read surface for later phases. |
| **ConfigurationContext** | The mutable-during-load assembly buffer owned by the loader controller (never exposed to modules). |
| **ConfigurationSession** | The sealed, run-scoped object representing "the loaded configuration for this Runtime session"; boundary object to Phase 3. |
| **ConfigurationLoaderController** | Orchestrates the loading pipeline (L0–L8), enforces fail-closed behavior, returns exactly one of `ConfigurationSession` or `ConfigError`. |

### 1.1 Loader Controller (implementation)
```
ConfigurationLoaderController.run(seed: EffectiveConfig /*from Phase 1*/, repo: RepositoryBinding)
    -> ConfigLoadResult                          # ConfigurationSession | ConfigError
  ctx := new ConfigurationContext(seed, repo)
  for stage in ConfigurationLoadingPipeline.stages:   # L0..L8, fixed order
      outcome := stage.execute(ctx)
      if outcome.is_failure:
          err := ConfigError.from(stage, outcome, ctx)
          ConfigCache.rollback(ctx)                # discard partial cache entries for this run
          return { status: FAILED, error: err }
      ctx.apply(outcome.produced_objects)          # append-only
  session := ConfigurationSession.seal(ctx)        # sealed, immutable
  return { status: SUCCESS, session }
```
- Single entry, single result (`ConfigLoadResult` tagged union). Fail-closed: first failing stage
  aborts, cache is rolled back, a structured `ConfigError` is returned; no partial session escapes.
- Only the controller mutates the context, and only by appending stage-produced (sealed) objects.

---

## 2. Configuration Runtime Objects

### 2.1 `ConfigSourceRecord` (produced by L1, sealed per source)
```
ConfigSourceRecord {
  source_id:    Enum{ RUNTIME_MANIFEST, REPOSITORY_MAP, MODULE_REGISTRY, EXECUTION_MODES, RUNTIME_VERSIONS }
  path:         String        # canonical repo path of the locked file
  order_index:  Int           # position in CFG.runtime_manifest.config_load_order
  raw_view:     Map           # parsed content (read-only projection of the file)
  content_hash: Hash          # hash of raw bytes; used for cache + integrity
  loaded_at:    Timestamp
}
```

### 2.2 `ConfigValidationReport` (produced by L2, sealed)
```
ConfigValidationReport {
  passed:        Bool
  checks:        List<ConfigCheck>       # ordered, deterministic
  first_failure: Optional<String>        # check_id of first failing check
}
ConfigCheck { id: String, category: Enum{ PRESENCE, SCHEMA, RANGE, CROSS_REF, VERSION, MODE }, passed: Bool, detail: String }
```

### 2.3 `EffectiveConfiguration` (produced by L4, sealed)
```
EffectiveConfiguration {
  merged_view:      Map                  # flattened effective values after precedence merge
  by_source:        Map<Enum, Ref<Map>>  # per-file resolved slice
  active_mode:      Map                  # the single selected mode from execution_modes.yaml
  active_version:   String               # from runtime_versions.yaml
  provenance:       Map<String, ProvenanceRecord>   # key -> which source/precedence won
  source_manifest:  List<ConfigSourceRecord>
  config_hash:      Hash                 # deterministic hash of merged_view + active_mode + active_version
}
ProvenanceRecord { key: String, winning_source: Enum, precedence_rank: Int, overridden_sources: List<Enum> }
```
> `EffectiveConfiguration` is a **read projection + merge result** over the locked files. It restates
> no design meaning; it records *which* value won and *from where* (provenance).

### 2.4 `ConfigModuleView` (produced by L5, per module, sealed)
```
ConfigModuleView {
  module_id:   String                    # module_1 .. module_8, from CFG.module_registry
  slice:       Ref<Map>                  # this module's configuration slice
  version_req: String                    # module version requirement from runtime_versions
  mode_flags:  Map<String, Any>          # mode-derived flags relevant to the module
}
```

### 2.5 `ConfigRegistryObject` (produced by L5, sealed) — see Section 4.

### 2.6 Object lineage (what produces what)
```
seed EffectiveConfig (Phase 1) + RepositoryBinding
   └─(L1 Load)→ List<ConfigSourceRecord>
                   └─(L2 Validate)→ ConfigValidationReport
                                       └─(L3 Integrity)→ (seed.config_hash == recomputed hash)
                                                            └─(L4 Resolve)→ EffectiveConfiguration
                                                                               └─(L5 Registry)→ ConfigRegistryObject + ConfigModuleView[1..8]
                                                                                                   └─(L6 Context)→ ConfigurationContext (finalized)
                                                                                                                      └─(L7 Session)→ ConfigurationSession
                                                                                                                                         └─(L8 Expose)→ Phase 3
```

---

## 3. Configuration Runtime Contracts

| Contract ID | Between | Guarantee |
|-------------|---------|-----------|
| **CC-READONLY** | Loader → locked files | The five YAML files are opened read-only; never written, moved, reordered, or restated. |
| **CC-ORDER** | Loader → sources | Sources are read/merged in `CFG.runtime_manifest.config_load_order`; precedence is total & deterministic. |
| **CC-SEED-MATCH** | Resolver → Phase 1 | Recomputed `config_hash` must equal the Phase-1 seed `config_hash`; mismatch fails closed. |
| **CC-VALIDATE-FIRST** | Validator → Resolver | Resolution runs only after `ConfigValidationReport.passed == true`. |
| **CC-PROVENANCE** | Resolver → Registry | Every effective key carries a `ProvenanceRecord` (which source won, what was overridden). |
| **CC-NO-DUP** | Registry → design | The registry indexes references to source values; it does not copy or re-author config content. |
| **CC-MODULE-SLICE** | Registry → modules | Each module receives only its declared slice from `CFG.module_registry`; no module reshapes config. |
| **CC-CACHE-COHERENT** | Cache → all | A cached entry is valid only if its `content_hash` matches the current source; stale entries are evicted. |
| **CC-SESSION** | Session → Phase 3 | A `ConfigurationSession` exists only if a sealed `EffectiveConfiguration` + `ConfigRegistryObject` exist. |
| **CC-FAILCLOSED** | Controller → all | Any breach → structured `ConfigError` + cache rollback; no partial session is exposed. |
| **CC-SINGLE-RESULT** | Controller → caller | Exactly one of `ConfigurationSession` or `ConfigError` is returned. |

---

## 4. Configuration Registry Model

The **Configuration Registry** is the sealed, queryable index that later phases use to read
configuration. It exposes values by key, by source, and by module — always with provenance.

```
ConfigRegistryObject {
  effective:     Ref<EffectiveConfiguration>     # sealed backing object
  index_by_key:  Map<String, Ref<Any>>           # dotted-key -> resolved value ref
  index_by_source: Map<Enum, Ref<Map>>           # source -> its resolved slice
  module_views:  Map<String, Ref<ConfigModuleView>>   # module_id -> view
  active_mode:   String
  active_version:String
  registry_hash: Hash                            # over effective.config_hash + index shape
}
```
**Registry read interface (query surface for later phases):**
```
interface ConfigurationRegistry {
  get(key: String) -> Any throws ConfigError            # ConfigError{ KEY_NOT_FOUND } if absent
  getOrDefault(key: String, default: Any) -> Any
  provenanceOf(key: String) -> ProvenanceRecord
  moduleView(module_id: String) -> ConfigModuleView throws ConfigError
  activeMode() -> String
  activeVersion() -> String
  snapshotHash() -> Hash
}
```
**Rules**
- The registry is **read-only** after seal. There is no `set()` — configuration is immutable during a
  session (matches the locked Configuration System's authority).
- `get()` on an unknown key fails closed with `ConfigError{ class: KEY_NOT_FOUND }` rather than
  returning null, so downstream phases cannot silently proceed on missing config.

---

## 5. Configuration Context Model

The **ConfigurationContext** is the loader's mutable-during-load assembly buffer (owned by the
controller; never handed to modules).

```
ConfigurationContext {
  seed:          EffectiveConfig                 # from Phase 1 (sealed input)
  repo:          RepositoryBinding               # from Phase 1
  sources:       Optional<List<ConfigSourceRecord>>   # set by L1
  validation:    Optional<ConfigValidationReport>     # set by L2
  effective:     Optional<EffectiveConfiguration>     # set by L4
  registry:      Optional<ConfigRegistryObject>       # set by L5
  stage_cursor:  Int
  trace:         List<ConfigStageTrace>
}
ConfigStageTrace { stage_id: String, inputs_hash: Hash, outputs_hash: Hash, ok: Bool }
```
**Rules**
- Only the controller mutates the context, by appending sealed stage outputs (write-once fields).
- On success the context is frozen into a `ConfigurationSession`, then discarded.
- On failure the context (with partial objects) is passed to cache rollback and discarded; nothing
  partial becomes a session.

---

## 6. Configuration Session Model

The **ConfigurationSession** is the sealed, run-scoped boundary object handed to Phase 3.

```
ConfigurationSession {
  session_id:      String                        # inherited from BootstrapSession
  registry:        Ref<ConfigRegistryObject>     # sealed
  effective:       Ref<EffectiveConfiguration>   # sealed
  bound_bootstrap: Ref<BootstrapSession>         # link back to Phase 1 identity
  created_at:      Timestamp
  lifecycle:       Enum{ SEALED, EXPOSED, CLOSED }
  session_hash:    Hash                           # over session_id + registry_hash + config_hash
}
```
**Rules**
- Created only from a fully-populated context containing a sealed `EffectiveConfiguration` and
  `ConfigRegistryObject`.
- `lifecycle` moves `SEALED → EXPOSED` when Stage L8 publishes the registry to Phase 3.
- `session_hash` binds the config to the bootstrap session so later phases can assert they are
  operating on one coherent Runtime start.

---

## 7. Configuration Interfaces

Behavioral contracts implemented by each component. Platform bindings deferred to the conformance phase.

```
interface ConfigurationLoader {
  loadSources(repo: RepositoryBinding, order: List<Enum>) -> List<ConfigSourceRecord> throws ConfigError
}

interface ConfigurationValidator {
  validate(sources: List<ConfigSourceRecord>) -> ConfigValidationReport
}

interface ConfigurationResolver {
  resolve(sources: List<ConfigSourceRecord>, overrides: Map<String,Any>) -> EffectiveConfiguration throws ConfigError
  selectMode(execution_modes: Map, requested_mode: String) -> Map throws ConfigError
  selectVersion(runtime_versions: Map) -> String throws ConfigError
}

interface ConfigurationCache {
  get(content_hash: Hash) -> Optional<Ref<Any>>
  put(content_hash: Hash, value: Any) -> Unit
  evict(content_hash: Hash) -> Unit
  rollback(ctx: ConfigurationContext) -> Unit
}

interface ConfigurationRegistry { ... }          # see Section 4

interface ConfigurationSessionFactory {
  seal(ctx: ConfigurationContext) -> ConfigurationSession throws ConfigError
  expose(session: ConfigurationSession) -> Ref<ConfigurationRegistry>   # to Phase 3
}
```
**Interface rules**
- Every failable operation throws a `ConfigError` (never a platform-native exception escaping the
  loader boundary).
- `ConfigurationLoader.loadSources` and the resolver are pure reads over the locked files.

---

## 8. Configuration Loading Pipeline

Ordered stages. Each declares **Inputs**, **Consumed Configuration**, **Produced Runtime Objects**,
**Outputs**, and **Failure Behaviour**, matching the required implementation flow
(Bootstrap → Discovery → Loading → Validation → Resolution → Registry → Context → Session → Expose → Phase 3).

### Stage L0 — Bootstrap Intake
- **Inputs:** Phase 1 seed `EffectiveConfig`, `RepositoryBinding`
- **Consumed config:** none (reads Phase-1 objects)
- **Produced objects:** initialized `ConfigurationContext`
- **Outputs:** context ready for discovery
- **Failure behaviour:** missing/invalid seed → `ConfigError{ INTAKE_ERROR }`; abort.

### Stage L1a — Configuration Discovery
- **Inputs:** `RepositoryBinding`
- **Consumed config:** `CFG.runtime_manifest.config_load_order`, `CFG.repository_map` (locations)
- **Produced objects:** ordered source descriptor list (which files, in what order)
- **Outputs:** discovery list on context
- **Failure behaviour:** a declared source is missing/unlocatable → `ConfigError{ SOURCE_MISSING }`; abort.

### Stage L1b — Configuration Loading
- **Inputs:** discovery list
- **Consumed config:** all five files (`runtime_manifest`, `repository_map`, `module_registry`, `execution_modes`, `runtime_versions`)
- **Produced objects:** `List<ConfigSourceRecord>` (parsed, hashed, ordered)
- **Outputs:** source records on context; cache populated by `content_hash`
- **Failure behaviour:** parse error / unreadable file → `ConfigError{ PARSE_ERROR }`; abort.

### Stage L2 — Configuration Validation
- **Inputs:** `List<ConfigSourceRecord>`
- **Consumed config:** `CFG.runtime_versions` (compat matrix), `CFG.module_registry` (expected modules), `CFG.execution_modes` (mode constraints)
- **Produced objects:** `ConfigValidationReport`
- **Outputs:** report on context
- **Failure behaviour:** any check fails → `ConfigError{ VALIDATION_ERROR, cause = first_failure }`; abort.

### Stage L3 — Integrity / Seed Match
- **Inputs:** source records, seed `EffectiveConfig`
- **Consumed config:** none
- **Produced objects:** integrity assertion (recomputed hash == seed hash)
- **Outputs:** verified continuity with Phase 1
- **Failure behaviour:** hash mismatch → `ConfigError{ INTEGRITY_ERROR }`; abort (config changed since bootstrap).

### Stage L4 — Configuration Resolution
- **Inputs:** validated source records, `invocation_overrides`
- **Consumed config:** all five files (merged); `execution_modes` (mode selection); `runtime_versions` (active version)
- **Produced objects:** `EffectiveConfiguration` (merged_view, provenance, active_mode, active_version, config_hash)
- **Outputs:** effective configuration on context
- **Failure behaviour:** unresolved reference / precedence conflict / unknown mode or version → `ConfigError{ RESOLUTION_ERROR }`; abort.

### Stage L5 — Configuration Registry Build
- **Inputs:** `EffectiveConfiguration`
- **Consumed config:** `CFG.module_registry.modules` (to build per-module views)
- **Produced objects:** `ConfigRegistryObject`, `ConfigModuleView[module_1..module_8]`
- **Outputs:** registry on context
- **Failure behaviour:** module set mismatch / slice missing → `ConfigError{ REGISTRY_ERROR }`; abort.

### Stage L6 — Configuration Context Finalization
- **Inputs:** context with all prior objects
- **Consumed config:** none
- **Produced objects:** finalized (complete) `ConfigurationContext`
- **Outputs:** context ready to seal
- **Failure behaviour:** any required object missing → `ConfigError{ CONTEXT_INCOMPLETE }`; abort.

### Stage L7 — Configuration Session Creation
- **Inputs:** finalized context, `BootstrapSession`
- **Consumed config:** none
- **Produced objects:** `ConfigurationSession` (sealed)
- **Outputs:** session ready to expose
- **Failure behaviour:** seal failure → `ConfigError{ SESSION_ERROR }`; abort.

### Stage L8 — Expose Runtime Configuration & Pass to Phase 3
- **Inputs:** `ConfigurationSession`
- **Consumed config:** none
- **Produced objects:** exposed `Ref<ConfigurationRegistry>`; session `lifecycle → EXPOSED`
- **Outputs:** `ConfigLoadResult{ SUCCESS, session }`; control passes to Phase 3
- **Failure behaviour:** exposure/publish failure → `ConfigError{ EXPOSE_ERROR }`; abort + cache rollback.

### Pipeline order (fixed)
```
L0 Intake → L1a Discovery → L1b Loading → L2 Validation → L3 Integrity →
L4 Resolution → L5 Registry → L6 Context → L7 Session → L8 Expose → Phase 3
```

---

## 9. Configuration Error Objects

The single structured error returned on any unrecoverable loader failure.

```
ConfigError {
  error_id:        String
  session_id:      String
  stage_id:        Enum{ L0, L1a, L1b, L2, L3, L4, L5, L6, L7, L8 }
  error_class:     Enum{ INTAKE_ERROR, SOURCE_MISSING, PARSE_ERROR, VALIDATION_ERROR,
                          INTEGRITY_ERROR, RESOLUTION_ERROR, REGISTRY_ERROR,
                          CONTEXT_INCOMPLETE, SESSION_ERROR, EXPOSE_ERROR, KEY_NOT_FOUND }
  error_code:      String        # stable, deterministic per (stage, cause)
  message:         String
  cause_detail:    String        # e.g. failing check id, missing key, conflicting sources, bad mode
  offending_source: Optional<Enum>   # which of the 5 files, if applicable
  produced_before_failure: List<String>   # object ids produced before abort
  cache_rolled_back: Bool
  occurred_at:     Timestamp
  recoverable:     Bool          # always false within the loader (retry is outer-orchestration only)
}
```
**Failure behaviour (implementation)**
- Built by the controller the instant a stage returns failure or an interface throws.
- Deterministic: identical faulty inputs ⇒ identical `stage_id` + `error_code` across all platforms.
- Triggers `ConfigCache.rollback(ctx)` (evict this-run entries), discards the partial context, and
  returns the error. No `ConfigurationSession` is ever exposed on failure.

---

## 10. Configuration Cache Strategy

The cache accelerates re-reads within and across compatible sessions **without ever compromising the
authority of the locked files**.

| Aspect | Strategy (implementation) |
|--------|---------------------------|
| **Keying** | Every entry is keyed by `content_hash` (raw source) or `config_hash` (resolved). Never by path or mtime. |
| **Population** | L1b populates per-source raw entries; L4 populates the resolved `EffectiveConfiguration` entry. |
| **Coherence (CC-CACHE-COHERENT)** | Before serving a cached entry, the loader recomputes the source `content_hash`; on mismatch the entry is evicted and the source re-read. Guarantees the cache can never mask a changed locked file. |
| **Scope** | Two tiers: (a) **run-scoped** working cache tied to a `ConfigurationContext`; (b) optional **cross-session** hash cache keyed by `config_hash`, valid only while all `content_hash`es match. |
| **Invalidation** | Eviction triggers: hash mismatch, `runtime_versions.active` change, or explicit `evict`. There is no time-based expiry — validity is content-driven only (deterministic). |
| **Rollback** | On any `ConfigError`, all entries produced during the failing run are evicted (`rollback`), so a failed load leaves the cache exactly as it was before the run. |
| **Read-through** | `ConfigurationRegistry.get()` reads from the resolved effective view (already in memory/cache); it never re-opens source files at query time. |
| **Immutability** | Cached values are sealed references; consumers cannot mutate them, preserving config authority. |

**Determinism note:** because keys are content hashes and there is no time-based expiry, cache hits
never change resolution results — the same inputs always produce the same `EffectiveConfiguration`.

---

## 11. Implementation Readiness Assessment

| Dimension | What is implemented here | Ready? |
|-----------|--------------------------|--------|
| Load orchestration | `ConfigurationLoaderController` + fixed pipeline L0–L8, single result | **Yes** |
| Source consumption | Reads all 5 locked files in manifest-declared order, read-only | **Yes** |
| Validation | Ordered `ConfigValidationReport`, validate-before-resolve | **Yes** |
| Resolution | Precedence merge + provenance + mode/version selection → sealed `EffectiveConfiguration` | **Yes** |
| Registry | Sealed, queryable `ConfigRegistryObject` + per-module views; read-only surface | **Yes** |
| Context/Session split | Mutable `ConfigurationContext` vs sealed `ConfigurationSession` | **Yes** |
| Interfaces | Behavioral contracts for every component | **Yes** |
| Caching | Content-hash keyed, coherence-checked, rollback-safe, deterministic | **Yes** |
| Errors | Single structured `ConfigError` + rollback wiring | **Yes** |
| Continuity | Seed-hash match binds Phase 2 to Phase 1 (`CC-SEED-MATCH`) | **Yes** |

**Deferred to later phases (require executable bindings + resolvable locked YAML at runtime):**
1. Binding the interfaces per platform (Claude/OpenAI/Python/LangGraph/n8n) and asserting identical
   `config_hash` / `registry_hash` across all five.
2. Executing validation checks against the *actual* schemas of the five locked YAML files.
3. Fault-injecting each `error_class` to confirm deterministic `error_code`s and clean rollback.

**Verdict:** The Configuration Loader is **implementation-ready**. Every artifact is concrete,
consumes every component of the locked Configuration System without altering or duplicating it, and
produces the objects Phase 3 requires.

---

## 12. Internal Quality Review (self-verification)

| Check | Result |
|-------|--------|
| No Runtime Configuration duplicated | **PASS** — files read via `CFG.*`; registry indexes *references* (CC-NO-DUP), never copies content |
| No Runtime Architecture modified | **PASS** — no architecture defined or changed; only loader machinery |
| Loader consumes every configuration component | **PASS** — L1b/L2/L4 consume all 5 files; §8 maps each file to stages |
| Runtime Objects support later phases | **PASS** — `ConfigurationSession` + `ConfigurationRegistry` are the Phase 3 read surface (§4, §6) |
| Output is implementation-oriented | **PASS** — objects, interfaces, controller flow, cache/error wiring; no design narrative |
| No module responsibilities changed | **PASS** — per-module views are slices from `module_registry` (CC-MODULE-SLICE); modules not reshaped |
| Single entry, single result; fail-closed | **PASS** — §1.1 (CC-SINGLE-RESULT, CC-FAILCLOSED) |

**No section resembled a design document; no rewrite required. Approved for commit.**

---

*End of Runtime Configuration Loader Implementation — Phase 2, Project C-Cloning.*
