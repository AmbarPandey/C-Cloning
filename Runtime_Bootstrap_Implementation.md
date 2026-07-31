# Runtime Bootstrap Implementation

**Project:** C-Cloning — Master Runtime Implementation
**Phase:** Phase 1 — Runtime Bootstrap (the Runtime bootloader)
**Artifact Type:** Implementation (runtime objects, contracts, interfaces, pipeline)
**Branch:** `feature/master-runtime-implementation`
**Consumes (LOCKED, never modified):** Master Runtime Architecture v1.1, Runtime Engineering
Standard, Runtime Configuration System (`runtime_manifest.yaml`, `repository_map.yaml`,
`module_registry.yaml`, `execution_modes.yaml`, `runtime_versions.yaml`), Runtime Modules 1–8.

> This document is **not** a specification and **not** a design. It defines the concrete
> implementation artifacts that make the Runtime start: the entry point, the controller, the
> pipeline, the objects that flow through it, the contracts between them, and the object handed to
> Module 1. The Runtime Design already exists; here we describe only **how the implementation
> consumes it**.

---

## 0. Implementation Conventions

- **Object notation:** objects are shown as typed field lists (`name: Type`). Types are abstract
  (`String`, `Int`, `Bool`, `Enum`, `Map<K,V>`, `List<T>`, `Ref<T>`, `Hash`, `Timestamp`). No
  platform types are used — each platform binds them natively (Section 13).
- **Interface notation:** interfaces are shown as `operation(inputs) -> outputs throws Failure`.
  They are behavioral contracts, not code.
- **Config access notation:** `CFG.<file>.<path>` denotes a **read** of a value from a locked
  configuration file, e.g. `CFG.runtime_manifest.runtime.version`. The bootloader **reads only**;
  it never writes config.
- **Immutability:** any object marked `sealed` is frozen after construction; downstream readers get
  `Ref<T>` handles, never mutable copies.
- **Determinism:** all ordering (config merge, module init) is derived from the locked config, not
  from runtime enumeration order. Same repo + same config ⇒ same objects and same hashes.

---

## 1. Runtime Bootstrap Implementation (the bootloader)

### 1.1 Component inventory
The bootloader is implemented as five cooperating components plus the object set they exchange.

| Component | Role (implementation) |
|-----------|-----------------------|
| **RuntimeEntryPoint** | The single callable invoked by the platform to start a Runtime session. Normalizes the raw trigger into a `BootstrapRequest` and calls the controller. |
| **BootstrapController** | Owns the run. Executes the pipeline stage-by-stage, holds the working objects, enforces fail-closed behavior, and returns exactly one of `RuntimeHandoff` (success) or `BootstrapFailure` (failure). |
| **BootstrapPipeline** | The ordered list of `BootstrapStage` executors (Section 6). Pure orchestration; each stage is an interface implementation. |
| **ConfigLoader** | Reads the five locked config files, in the manifest-declared order, into a sealed `EffectiveConfig`. Does not interpret module logic. |
| **HandoffDispatcher** | Constructs the `RuntimeHandoff` and activates Module 1 through the `ModuleActivation` contract. |

### 1.2 Runtime Entry Point (implementation)
```
RuntimeEntryPoint.start(raw_trigger: RawTrigger) -> BootstrapResult
  1. request  := normalize(raw_trigger)            # -> BootstrapRequest
  2. controller := BootstrapController(request)
  3. return controller.run()                       # BootstrapResult = RuntimeHandoff | BootstrapFailure
```
- **Single entry, single exit.** `BootstrapResult` is a tagged union: `{ status: SUCCESS, handoff }`
  or `{ status: FAILED, failure }`. There is no third outcome.
- The entry point performs **no** business logic and **no** config loading itself — it only
  normalizes and delegates. This keeps the entry surface identical across all five platforms.

### 1.3 Bootstrap Controller (implementation)
```
BootstrapController.run() -> BootstrapResult
  ctx := new BootstrapContext(request)             # mutable working ctx during bootstrap only
  for stage in BootstrapPipeline.stages:           # fixed order, Section 6
      outcome := stage.execute(ctx)
      if outcome.is_failure:
          failure := BootstrapFailure.from(stage, outcome, ctx)
          Shutdown.run(ctx, failure)               # tear down partial objects (Section 12 of spec)
          return { status: FAILED, failure }
      ctx.apply(outcome.produced_objects)          # attach produced objects to ctx
  session := BootstrapSession.seal(ctx)            # sealed, immutable
  handoff := HandoffDispatcher.dispatch(session)   # activates Module 1
  return { status: SUCCESS, handoff }
```
- The controller is the **only** component that mutates `BootstrapContext`, and only by *appending*
  stage-produced objects. Once a stage produces an object, it is sealed and never rewritten.
- On the first failing stage the controller stops, builds a `BootstrapFailure`, runs shutdown, and
  returns. No later stage runs. (Fail-closed.)

---

## 2. Bootstrap Runtime Objects

All objects the bootloader produces and passes forward. These are the concrete data the later
phases will receive.

### 2.1 `BootstrapRequest` (input object, sealed at entry)
```
BootstrapRequest {
  session_id:        String        # deterministic id (correlation_id + monotonic seq)
  correlation_id:    String        # supplied by caller/orchestrator
  trigger_kind:      Enum{ MANUAL, SCHEDULED, EVENT, CHAINED }
  requested_repo:    String        # repo target to resolve
  requested_branch:  String        # expected: feature/master-runtime-implementation
  requested_mode:    String        # key into CFG.execution_modes.modes
  invocation_overrides: Map<String, Any>   # highest-precedence config overrides
  caller_identity:   String
  received_at:       Timestamp
}
```

### 2.2 `EffectiveConfig` (produced by ConfigLoader, sealed)
```
EffectiveConfig {
  manifest:      Map   # from runtime_manifest.yaml
  repo_map:      Map   # from repository_map.yaml
  module_registry: Map # from module_registry.yaml
  execution_mode:  Map # the single selected mode from execution_modes.yaml
  versions:      Map   # from runtime_versions.yaml
  merged_view:   Map   # flattened effective values after precedence merge
  source_manifest: List<ConfigSourceRecord>   # what was read, in order, with hashes
  config_hash:   Hash  # deterministic hash of merged_view
}
ConfigSourceRecord { source_id: String, class: Enum, path: String, hash: Hash, order_index: Int }
```
> `EffectiveConfig` **references** the locked files' values; it does not restate their meaning or
> alter them. It is a read projection.

### 2.3 `RepositoryBinding` (produced by Repository Discovery, sealed)
```
RepositoryBinding {
  repo_id:       String    # owner/name resolved via CFG.repository_map
  connection:    Ref<RepositoryConnection>
  pinned_branch: String
  pinned_commit: String    # exact commit the run operates against
  access_scope:  Enum{ READ, READ_WRITE }   # bootloader requires READ
  verified:      Bool
}
```

### 2.4 `ValidationReport` (produced by Runtime Validation, sealed)
```
ValidationReport {
  passed:        Bool
  checks:        List<ValidationCheck>   # ordered, deterministic
  first_failure: Optional<String>        # check_id of first failing check
}
ValidationCheck { id: String, category: Enum, passed: Bool, detail: String }
```

### 2.5 `ModuleInitTable` (produced by module preparation, sealed)
```
ModuleInitTable {
  order:         List<String>            # topological order from CFG.module_registry
  entries:       Map<String, ModuleInitEntry>
}
ModuleInitEntry {
  module_id:     String                  # e.g. "module_1"..."module_8"
  state:         Enum{ REGISTERED, INITIALIZED }   # bootloader never sets ACTIVE except M1 at handoff
  config_slice:  Ref<Map>                # this module's slice of EffectiveConfig
  interfaces:    List<String>            # declared inter-module interfaces from integration report
}
```

### 2.6 `RuntimeStateObject` (produced by Bootstrap Context Construction, sealed)
```
RuntimeStateObject {
  session_id:      String
  effective_config: Ref<EffectiveConfig>
  repository:      Ref<RepositoryBinding>
  module_table:    Ref<ModuleInitTable>
  validation:      Ref<ValidationReport>
  runtime_version: String                # CFG.runtime_versions active version
  status:          Enum{ READY }         # only READY is valid at seal time
  state_hash:      Hash
}
```

### 2.7 Object lineage (what produces what)
```
RawTrigger
   └─(normalize)→ BootstrapRequest
                     └─(ConfigLoader)→ EffectiveConfig
                                          └─(RepoDiscovery)→ RepositoryBinding
                                                                └─(Validation)→ ValidationReport
                                                                                   └─(ModulePrep)→ ModuleInitTable
                                                                                                     └─(ContextConstruct)→ RuntimeStateObject
                                                                                                                              └─(SessionCreate)→ BootstrapSession
                                                                                                                                                    └─(Handoff)→ RuntimeHandoff → Module 1
```

---

## 3. Bootstrap Contracts

Contracts are the guarantees each component upholds. They are enforced by the controller.

| Contract ID | Between | Guarantee |
|-------------|---------|-----------|
| **C-ENTRY** | Platform → EntryPoint | A single normalized `BootstrapRequest` is produced; malformed triggers are rejected before any stage runs. |
| **C-CFG-READONLY** | ConfigLoader → locked files | Config files are opened read-only; the loader never writes, moves, or reorders source files. |
| **C-CFG-ORDER** | ConfigLoader → EffectiveConfig | Sources are merged in the order declared by `CFG.runtime_manifest`; precedence is total and deterministic. |
| **C-REPO** | RepoDiscovery → RepositoryBinding | The branch is `requested_branch` and a commit is pinned; otherwise the stage fails. |
| **C-VALIDATE** | Validation → ValidationReport | Every check runs in fixed order; the first failure aborts; `passed` is true only if all checks passed. |
| **C-MODULE-IMMUTABLE** | ModulePrep → Modules | Module *responsibilities* are read from `CFG.module_registry` and never altered; only containers are initialized. |
| **C-STATE-SEAL** | ContextConstruct → RuntimeStateObject | State is sealed once; `status=READY` and `state_hash` are set atomically. |
| **C-SESSION** | SessionCreate → BootstrapSession | A session exists only if a sealed `RuntimeStateObject` exists. |
| **C-HANDOFF** | HandoffDispatcher → Module 1 | `RuntimeHandoff` is delivered only after all completion gates pass; Module 1 goes `INITIALIZED → ACTIVE` on ACK. |
| **C-FAILCLOSED** | Controller → all | Any contract breach yields a `BootstrapFailure` and shutdown; never a partial handoff. |
| **C-SINGLE-RESULT** | Controller → caller | Exactly one of `RuntimeHandoff` or `BootstrapFailure` is returned. |

---

## 4. Bootstrap Session Model

The **BootstrapSession** is the sealed, run-scoped object that represents "this Runtime start". It is
the boundary object between the bootloader and everything after it.

```
BootstrapSession {
  session_id:      String
  runtime_state:   Ref<RuntimeStateObject>   # sealed
  created_at:      Timestamp
  bootstrap_trace: List<StageTrace>          # ordered per-stage record (deterministic content)
  lifecycle:       Enum{ SEALED, HANDED_OFF, TORN_DOWN }
  session_hash:    Hash                       # over session_id + state_hash + config_hash
}
StageTrace { stage_id: String, inputs_hash: Hash, outputs_hash: Hash, ok: Bool }
```
**Rules**
- A `BootstrapSession` is created **only** by sealing a fully-populated `BootstrapContext` that
  contains a `RuntimeStateObject` with `status=READY`.
- `lifecycle` moves `SEALED → HANDED_OFF` at successful handoff, or `SEALED → TORN_DOWN` never occurs
  (a sealed session always hands off; failures happen *before* sealing). If handoff itself fails,
  the session moves `SEALED → TORN_DOWN` via shutdown.
- The session is the object later phases treat as "the running Runtime's identity".

---

## 5. Bootstrap Context Model

The **BootstrapContext** is the mutable-during-bootstrap working area owned by the controller. It is
**not** exposed to modules; it is the assembly buffer that becomes the session.

```
BootstrapContext {
  request:         BootstrapRequest          # sealed
  config:          Optional<EffectiveConfig> # set by ConfigLoader stage
  repo:            Optional<RepositoryBinding>
  validation:      Optional<ValidationReport>
  module_table:    Optional<ModuleInitTable>
  runtime_state:   Optional<RuntimeStateObject>
  stage_cursor:    Int                        # index of next stage to run
  trace:           List<StageTrace>
}
```
**Rules**
- Only the controller mutates the context, and only by **appending** a stage's produced objects.
- Each `Optional` field is written **once** (by its producing stage) then treated as read-only.
- When all stages complete, `BootstrapSession.seal(ctx)` freezes the context into a session and the
  context is discarded.
- If any stage fails, the context (with whatever partial objects exist) is passed to `Shutdown.run`
  and then discarded; nothing partial is ever promoted to a session.

---

## 6. Bootstrap Pipeline

The pipeline is the ordered list of stage executors. Each stage declares **Inputs**, **Consumed
Runtime Configuration**, **Produced Runtime Objects**, **Outputs**, and **Failure Behaviour**, per
the required implementation flow.

### Stage P0 — Bootstrap Entry (normalize trigger)
- **Inputs:** `RawTrigger`
- **Consumed config:** none
- **Produced objects:** `BootstrapRequest`
- **Outputs:** sealed request attached to context
- **Failure behaviour:** unauthenticated/malformed trigger → `BootstrapFailure{ stage: P0, class: TRIGGER_ERROR }`; no further stage runs.

### Stage P1 — Repository Discovery
- **Inputs:** `BootstrapRequest`
- **Consumed config:** `CFG.repository_map.repositories`, `CFG.runtime_manifest.repository`
- **Produced objects:** `RepositoryBinding` (connection + pinned branch/commit)
- **Outputs:** repo binding on context
- **Failure behaviour:** repo unreachable / access denied / branch mismatch → `REPO_ERROR` or `BRANCH_ERROR`; abort.

### Stage P2 — Runtime Configuration Loading
- **Inputs:** `BootstrapRequest`, `RepositoryBinding`
- **Consumed config:** all five locked files, read in `CFG.runtime_manifest.config_load_order`:
  `runtime_manifest.yaml` → `repository_map.yaml` → `module_registry.yaml` → `execution_modes.yaml`
  → `runtime_versions.yaml`, then `invocation_overrides` applied last (highest precedence).
- **Produced objects:** `EffectiveConfig` (with `merged_view`, `source_manifest`, `config_hash`)
- **Outputs:** effective config on context
- **Failure behaviour:** required source missing / parse error / unresolved precedence conflict → `CONFIG_LOAD_ERROR`; abort.

### Stage P3 — Runtime Validation
- **Inputs:** `EffectiveConfig`, `RepositoryBinding`
- **Consumed config:** `CFG.runtime_versions` (compatibility), `CFG.module_registry` (expected module set), `CFG.execution_modes` (selected mode constraints)
- **Produced objects:** `ValidationReport`
- **Outputs:** validation report on context
- **Failure behaviour:** any check fails → `VALIDATION_ERROR` carrying `first_failure`; abort.

### Stage P4 — Module Preparation
- **Inputs:** validated `EffectiveConfig`
- **Consumed config:** `CFG.module_registry.modules`, `CFG.module_registry.dependencies`
- **Produced objects:** `ModuleInitTable` (topological order, per-module config slices, `INITIALIZED` states)
- **Outputs:** module table on context
- **Failure behaviour:** a module container fails to initialize / dependency cycle → `MODULE_INIT_ERROR`; abort (reverse-order teardown in shutdown).

### Stage P5 — Bootstrap Context Construction
- **Inputs:** `EffectiveConfig`, `RepositoryBinding`, `ValidationReport`, `ModuleInitTable`
- **Consumed config:** `CFG.runtime_versions.active`
- **Produced objects:** `RuntimeStateObject` (sealed, `status=READY`, `state_hash`)
- **Outputs:** runtime state on context
- **Failure behaviour:** state cannot be constructed/sealed → `STATE_ERROR`; abort.

### Stage P6 — Bootstrap Session Creation
- **Inputs:** fully-populated `BootstrapContext`
- **Consumed config:** none (reads only already-loaded objects)
- **Produced objects:** `BootstrapSession` (sealed)
- **Outputs:** session ready for handoff
- **Failure behaviour:** context incomplete (any required object missing) → `STATE_ERROR`; abort.

### Stage P7 — Runtime Handoff
- **Inputs:** `BootstrapSession`
- **Consumed config:** `CFG.module_registry.modules.module_1` (activation contract)
- **Produced objects:** `RuntimeHandoff`; Module 1 transitions to `ACTIVE`
- **Outputs:** `BootstrapResult{ SUCCESS, handoff }`
- **Failure behaviour:** Module 1 rejects envelope / ACK timeout → `HANDOFF_ERROR`; abort + shutdown (no partial activation).

### Pipeline order (fixed)
```
P0 Bootstrap Entry → P1 Repository Discovery → P2 Configuration Loading →
P3 Runtime Validation → P4 Module Preparation → P5 Context Construction →
P6 Session Creation → P7 Runtime Handoff → Module 1
```

---

## 7. Bootstrap Runtime Interfaces

Behavioral contracts each component implements. Platform bindings in Section 13.

```
interface RuntimeEntryPoint {
  start(raw: RawTrigger) -> BootstrapResult
}

interface BootstrapStage {
  id() -> String
  execute(ctx: BootstrapContext) -> StageOutcome    # { produced_objects, ok, failure? }
}

interface ConfigLoader {
  load(request: BootstrapRequest, repo: RepositoryBinding) -> EffectiveConfig throws BootstrapFailure
}

interface RepositoryProvider {
  connect(repo_id: String) -> RepositoryConnection throws BootstrapFailure
  pinBranch(conn: RepositoryConnection, branch: String) -> (String /*branch*/, String /*commit*/) throws BootstrapFailure
}

interface RuntimeValidator {
  validate(config: EffectiveConfig, repo: RepositoryBinding) -> ValidationReport
}

interface ModulePreparer {
  prepare(config: EffectiveConfig) -> ModuleInitTable throws BootstrapFailure
}

interface HandoffDispatcher {
  dispatch(session: BootstrapSession) -> RuntimeHandoff throws BootstrapFailure
}

interface ModuleActivation {                          # implemented by Module 1's container
  accept(handoff: RuntimeHandoff) -> Ack throws BootstrapFailure
}
```
**Interface rules**
- Every interface that can fail throws a `BootstrapFailure` — never a platform-native exception that
  escapes the bootloader boundary.
- `BootstrapStage.execute` is pure w.r.t. the locked config (reads only) and returns produced
  objects rather than mutating shared state directly.

---

## 8. Bootstrap Runtime Inputs

The complete set of inputs the bootloader consumes.

| Input | Kind | Source | Consumed by |
|-------|------|--------|-------------|
| `RawTrigger` | External | Platform entrypoint | P0 |
| `requested_repo` / `requested_branch` | Field | `BootstrapRequest` | P1 |
| `requested_mode` | Field | `BootstrapRequest` | P2 (mode selection) |
| `invocation_overrides` | Field | `BootstrapRequest` | P2 (highest precedence) |
| `runtime_manifest.yaml` | Locked config | Repository | P2 (load order, runtime identity) |
| `repository_map.yaml` | Locked config | Repository | P1, P2 (repo resolution) |
| `module_registry.yaml` | Locked config | Repository | P3, P4 (module set, deps, M1 contract) |
| `execution_modes.yaml` | Locked config | Repository | P2, P3 (selected mode + constraints) |
| `runtime_versions.yaml` | Locked config | Repository | P2, P3, P5 (version + compatibility) |

**Input rules:** every locked config file is an **input only**. The bootloader treats them as
authoritative and read-only; it fails closed if any required input is absent or malformed.

---

## 9. Bootstrap Runtime Outputs

The complete set of objects the bootloader produces for downstream consumption.

| Output | Produced by | Sealed | Consumer |
|--------|-------------|--------|----------|
| `BootstrapRequest` | P0 | yes | pipeline |
| `EffectiveConfig` | P2 | yes | P3–P7, all later phases (read) |
| `RepositoryBinding` | P1 | yes | P2–P7, later phases |
| `ValidationReport` | P3 | yes | P5, audit/testing phase |
| `ModuleInitTable` | P4 | yes | P5–P7, Module 1..8 phases |
| `RuntimeStateObject` | P5 | yes | P6, P7, all modules (read) |
| `BootstrapSession` | P6 | yes | P7, later phases (runtime identity) |
| `RuntimeHandoff` | P7 | yes | Module 1 |
| `BootstrapResult` | Controller | yes | caller/orchestrator |
| `BootstrapFailure` | Controller (on error) | yes | caller, shutdown, testing phase |

**Primary success output:** `RuntimeHandoff`. **Primary failure output:** `BootstrapFailure`. Exactly
one is produced per run.

---

## 10. Runtime Handoff Object

The object the bootloader delivers to Module 1. This is the contract boundary between Phase 1 and
Phase 2.

```
RuntimeHandoff {
  handoff_id:       String
  session:          Ref<BootstrapSession>       # sealed, contains RuntimeStateObject
  runtime_state:    Ref<RuntimeStateObject>     # convenience direct ref (read-only)
  module_table:     Ref<ModuleInitTable>        # Modules 2..8 = INITIALIZED, for M1 to orchestrate
  effective_config: Ref<EffectiveConfig>        # read-only
  entry_module:     String                       # "module_1"
  handoff_token:    String                        # one-time token asserting a verified bootstrap
  issued_at:        Timestamp
  contract_version: String                        # matches CFG.runtime_versions.active
}
```
**Handoff behaviour (implementation)**
1. `HandoffDispatcher.dispatch(session)` builds the `RuntimeHandoff`.
2. It calls `ModuleActivation.accept(handoff)` on Module 1's container.
3. On `Ack`, Module 1's `ModuleInitEntry.state` → `ACTIVE`, session `lifecycle` → `HANDED_OFF`,
   controller returns `BootstrapResult{ SUCCESS }`.
4. On rejection/timeout, dispatcher throws `BootstrapFailure{ class: HANDOFF_ERROR }`; controller runs
   shutdown; no module remains `ACTIVE`.
- The handoff is **read-only** toward `RuntimeStateObject`: Module 1 receives references, cannot
  mutate sealed state, and cannot reach back into the discarded `BootstrapContext`.

---

## 11. Bootstrap Failure Object

The single, structured failure object returned on any unrecoverable error.

```
BootstrapFailure {
  failure_id:      String
  session_id:      String
  stage_id:        Enum{ P0, P1, P2, P3, P4, P5, P6, P7 }
  failure_class:   Enum{ TRIGGER_ERROR, REPO_ERROR, BRANCH_ERROR, CONFIG_LOAD_ERROR,
                          VALIDATION_ERROR, MODULE_INIT_ERROR, STATE_ERROR, HANDOFF_ERROR }
  error_code:      String        # stable, deterministic per (stage, cause)
  message:         String        # human-readable
  cause_detail:    String        # e.g. failing validation check id, missing config key
  consumed_before_failure: List<String>   # object ids successfully produced before abort
  shutdown_performed: Bool
  occurred_at:     Timestamp
  recoverable:     Bool          # always false within bootloader (retry is outer-orchestration only)
}
```
**Failure behaviour (implementation)**
- Built by the controller the instant a stage returns a failure outcome or an interface throws.
- Deterministic: identical faulty inputs ⇒ identical `stage_id` + `error_code` on every platform.
- Triggers `Shutdown.run(ctx, failure)`, which tears down any `INITIALIZED` modules in reverse order,
  releases the repository connection, discards partial objects, sets `shutdown_performed=true`, and
  returns the failure to the caller. No partial `RuntimeHandoff` is ever emitted.

---

## 12. Implementation Readiness Assessment

| Dimension | What is implemented here | Ready? |
|-----------|--------------------------|--------|
| Entry surface | `RuntimeEntryPoint.start` single entry/exit, tagged-union result | **Yes** |
| Orchestration | `BootstrapController` + fixed `BootstrapPipeline` (P0–P7) | **Yes** |
| Config consumption | `ConfigLoader` reads all 5 locked files in manifest-declared order; read-only | **Yes** |
| Object model | Full set of sealed runtime objects with lineage (Section 2) | **Yes** |
| Contracts | 11 enforced contracts incl. fail-closed and single-result | **Yes** |
| Session/Context split | Mutable `BootstrapContext` (assembly) vs sealed `BootstrapSession` (identity) | **Yes** |
| Interfaces | Behavioral contracts for all components, platform-agnostic | **Yes** |
| Handoff | `RuntimeHandoff` object + `ModuleActivation` protocol to Module 1 | **Yes** |
| Failure | Single structured `BootstrapFailure` + shutdown wiring | **Yes** |
| Determinism | Ordering + hashing derived from locked config, not enumeration | **Yes (spec-level; verify in test phase)** |

**Deferred to later phases (require executable bindings + resolvable locked files at runtime):**
1. Binding the abstract interfaces to each of Claude / OpenAI / Python / LangGraph / n8n and proving
   identical `state_hash` / `config_hash` across all five.
2. Executing `ValidationReport` checks against the *actual* schema of the five locked YAML files.
3. Fault-injecting each `failure_class` to confirm deterministic `error_code`s and clean shutdown.

**Verdict:** The bootloader is **implementation-ready**. Every artifact is concrete, consumes the
locked design without altering it, and produces the objects the next phases need.

---

## 13. Platform Binding Notes (implementation surface only)

| Artifact | Claude | OpenAI | Python | LangGraph | n8n |
|----------|--------|--------|--------|-----------|-----|
| RuntimeEntryPoint | tool/session entry | assistant run entry | module entry fn | graph entry node | trigger node |
| BootstrapController | orchestrated tool steps | orchestrated calls | controller class | graph runner | main workflow |
| BootstrapStage | one step each | one call each | class per stage | one node each | one node each |
| EffectiveConfig | in-context object | in-context object | dataclass/dict | graph state channel | workflow static data |
| RuntimeHandoff | payload to M1 step | payload to M1 call | object to M1 fn | edge payload to M1 node | payload to execute-workflow |
| BootstrapFailure | error result object | error result object | exception→result | error edge payload | error branch payload |

No platform-specific code is defined; each cell names only *where* the artifact lives so behavior is
identical everywhere.

---

## 14. Internal Quality Review (self-verification)

| Check | Result |
|-------|--------|
| No Runtime Architecture redesigned (only consumed) | **PASS** — artifacts reference A1 order; define no new architecture |
| No Runtime Configuration duplicated | **PASS** — the 5 YAML files are read via `CFG.*`, never restated or copied |
| No Module responsibilities changed | **PASS** — `ModulePreparer` only initializes containers from `module_registry`; C-MODULE-IMMUTABLE |
| All artifacts support Runtime execution | **PASS** — objects/contracts/interfaces/pipeline are execution machinery |
| Implementation-oriented, not specification-oriented | **PASS** — objects, interfaces, controller flow, failure/handoff wiring; no design narrative |
| Single entry, single result; fail-closed | **PASS** — Sections 1.2, 3 (C-SINGLE-RESULT, C-FAILCLOSED) |
| Handoff to Module 1 correct | **PASS** — Section 10 `RuntimeHandoff` + `ModuleActivation` |

**No section resembled a design document; no rewrite required. Approved for commit.**

---

*End of Runtime Bootstrap Implementation — Phase 1, Project C-Cloning.*
