# Runtime Output Engine Implementation

**Project:** C-Cloning — Master Runtime Implementation
**Phase:** Phase 7 — Output Engine
**Artifact Type:** Implementation (runtime objects, contracts, interfaces, pipeline)
**Branch:** `feature/master-runtime-implementation`
**Consumes (LOCKED / prior implementation phases, never modified):** Master Runtime Architecture
v1.1; Runtime Engineering Standard; Runtime Configuration System; Runtime Bootstrap Implementation
(Phase 1); Runtime Configuration Loader Implementation (Phase 2); Runtime Module Engine
Implementation (Phase 3); Runtime Context Engine Implementation (Phase 4); Runtime Execution Engine
Implementation (Phase 5 → `ExecutionHandle`); Runtime Validation Engine Implementation (Phase 6 →
`ValidationHandle` / `ValidationResult` / `ValidationReport`).

> This is an **implementation** artifact, not a design or specification. It defines the concrete
> engine that **constructs the standardized Runtime Output Package** from validated Runtime
> artifacts. It does **not** redesign Runtime outputs and **never modifies validated artifacts**. It
> reads validation and execution outputs only through the Phase-5/Phase-6 handles — it never bypasses
> an implementation layer and never edits upstream artifacts.

---

## 0. Implementation Conventions (inherited from Phases 1–6)

- **Object notation:** typed field lists (`name: Type`) with abstract types (`String`, `Int`, `Bool`,
  `Enum`, `Map<K,V>`, `List<T>`, `Ref<T>`, `Hash`, `Timestamp`, `Bytes`). No platform types.
- **Interface notation:** `operation(inputs) -> outputs throws OutputError`.
- **Layering rule:** the Output Engine consumes **only** upstream runtime handles —
  `ValidationHandle`, `ValidationResult`, `ValidationReport`, `ExecutionHandle`. No direct YAML/config
  access; no reaching past a layer's exposed surface.
- **Read-only over upstream:** the engine **references** validated/executed artifacts and produces a
  **new package**; it never writes back, mutates, or re-derives upstream artifacts.
- **Immutability:** objects marked `sealed` are frozen after construction; consumers receive `Ref<T>`.
- **Determinism:** assembly order, metadata field order, and serialization are fixed and
  content-derived (sections sorted by section rank; keys canonicalized). Same validated artifacts +
  same output request ⇒ same `RuntimeOutputPackage` bytes and same hashes. No wall-clock, randomness,
  or enumeration-order dependence. (Any timestamp that must appear is sourced from upstream sealed
  objects, not generated at packaging time, to preserve byte-determinism.)

### 0.1 Relationship to prior phases
- **Phase 6** → `ValidationHandle` exposing a sealed `ValidationResult` (`verdict`, `counts`,
  `first_failure`, `result_hash`) and a `ValidationReport` (ordered `RuleOutcome`s).
- **Phase 5** → `ExecutionHandle` exposing the sealed `ExecutionResult` (`outputs_index`,
  `overall_state`, `result_hash`) referenced by the package (never copied wholesale).
- **Phase 7 (this)** consumes those and produces the sealed **`RuntimeOutputPackage`** plus an
  **`OutputHandle`** exposed to Phase 8. It standardizes and packages the results; it does not decide
  their content or re-judge them.

---

## 1. Output Engine Implementation (component inventory)

| Component | Role (implementation) |
|-----------|-----------------------|
| **OutputEngine** | Top-level façade owning the output runtime. Accepts an `OutputRequest`, drives the pipeline, and exposes the `OutputHandle`/`RuntimeOutputPackage` to Phase 8. Holds the controller, coordinator, package builder, formatter, and metadata builder. |
| **OutputController** | Orchestrates the output pipeline (O0–O8); enforces fail-closed behavior; returns exactly one of `OutputHandle` (success) or `OutputError` (failure). Sole owner of the mutable `OutputScope`. |
| **OutputCoordinator** | Determines which upstream artifacts populate which package sections, per the declared package model; coordinates assembly order. Contains no domain logic. |
| **OutputPackageBuilder** | Assembles the section set into a sealed `RuntimeOutputPackage`; wires references to upstream artifacts (no copies of large payloads). |
| **OutputFormatter** | Produces the canonical serialized form (`OutputRendering`) of the package deterministically (stable key order, canonical encoding). |
| **OutputMetadataBuilder** | Builds the `OutputMetadata` (provenance, upstream hashes, verdict summary, package hash inputs) from upstream sealed objects only. |
| **OutputSession** | The sealed, run-scoped object representing "this output over this validation"; boundary object to Phase 8. |

### 1.1 Output Controller (implementation)
```
OutputController.run(request: OutputRequest, validation: ValidationHandle,
                     execution: ExecutionHandle) -> OutputResult    # OutputHandle | OutputError
  scope := new OutputScope(request, validation, execution)
  for stage in OutputPipeline.stages:            # O0..O8, fixed order
      outcome := stage.execute(scope)
      if outcome.is_failure:
          err := OutputError.from(stage, outcome, scope)
          return { status: FAILED, error: err }  # no partial package exposed
      scope.apply(outcome.produced_objects)        # append-only
  session := OutputEngine.seal(scope)              # sealed OutputSession + RuntimeOutputPackage
  return { status: SUCCESS, handle: session.handle() }
```
- Single entry, single result (`OutputResult` tagged union). Fail-closed: first failing stage aborts
  and returns a structured `OutputError`; no partial package escapes.
- Only the controller mutates the scope (append-only). Upstream validated/executed artifacts are never
  written.

> **Verdict-agnostic packaging.** The engine packages the result **regardless of the validation
> verdict** (PASSED / FAILED / PASSED_WITH_WARNINGS). A FAIL verdict still yields a valid, complete
> output package that records the verdict — it is not an engine error.

---

## 2. Output Runtime Objects

### 2.1 `OutputRequest` (input object, sealed at intake)
```
OutputRequest {
  request_id:     String
  session_id:     String                    # inherited from ValidationResult/upstream sessions
  target_validation: Ref<ValidationResult>  # the validated result to package (read-only)
  format_profile: String                     # declared serialization profile id (no logic)
  section_selection: List<String>            # declared package sections to include
  received_at:    Timestamp                  # sourced from upstream request context
}
```

### 2.2 `OutputAssemblyPlan` (produced by O1, sealed)
```
OutputAssemblyPlan {
  plan_id:        String
  sections:       List<PlannedSection>       # ordered, deterministic
  plan_hash:      Hash
}
PlannedSection {
  section_id:     String
  section_rank:   Int                        # deterministic ordering key
  source_ref:     Ref<Any>                   # which upstream artifact populates this section (read-only)
  required:       Bool
}
```

### 2.3 `OutputSection` (produced by O2, sealed per section)
```
OutputSection {
  section_id:     String
  content_ref:    Ref<Any>                   # reference to upstream artifact (no wholesale copy)
  projection:     Map<String, Ref<Any>>      # selected fields exposed in the package (references)
  section_hash:   Hash
}
```

### 2.4 `OutputMetadata` (produced by O3, sealed)
```
OutputMetadata {
  session_id:     String
  runtime_version:String                     # from upstream sealed objects (not re-read from config)
  verdict:        Enum{ PASSED, FAILED, PASSED_WITH_WARNINGS }
  upstream_hashes: Map<String, Hash>         # execution.result_hash, validation.result_hash, report_hash, ...
  produced_by:    String                     # "phase-7 output-engine"
  provenance:     List<ProvenanceLink>       # ordered links to source phases/objects
  metadata_hash:  Hash
}
ProvenanceLink { phase: String, object: String, hash: Hash }
```

### 2.5 `RuntimeOutputPackage` (produced by O4, sealed) — see Section 5.

### 2.6 `OutputRendering` (produced by O6, sealed)
```
OutputRendering {
  format_profile: String
  bytes_ref:      Ref<Bytes>                 # canonical serialized package (deterministic)
  encoding:       String
  rendering_hash: Hash                       # hash of bytes; equals package_hash-derived digest
}
```

### 2.7 Object lineage (what produces what)
```
ValidationHandle (ValidationResult + ValidationReport) + ExecutionHandle (ExecutionResult)
   └─(O0 Intake)→ OutputScope
   └─(O1 Request/Assembly)→ OutputRequest + OutputAssemblyPlan
                              └─(O2 Assembly)→ OutputSection[*]
                              └─(O3 Metadata)→ OutputMetadata
                                                 └─(O4 Package)→ RuntimeOutputPackage
                                                                   └─(O5 Output Validation)→ PackageCheckReport (self-check)
                                                                                                └─(O6 Finalization)→ OutputRendering (canonical bytes)
                                                                                                                       └─(O7 Package seal)→ OutputSession
                                                                                                                                              └─(O8 Expose)→ OutputHandle → Phase 8
```

---

## 3. Output Runtime Contracts

| Contract ID | Between | Guarantee |
|-------------|---------|-----------|
| **OP-UPSTREAM-ONLY** | Engine → sources | Consumes only `ValidationHandle`/`ValidationResult`/`ValidationReport` and `ExecutionHandle`; never reads config files directly. |
| **OP-READ-ONLY** | Engine → validated artifacts | Validated/executed artifacts are read-only inputs; the engine never mutates or re-derives them. |
| **OP-NO-BYPASS** | Engine → layers | Upstream data is read via exposed handles only; no layer bypass. |
| **OP-NO-REDESIGN** | Engine → output model | Packaging follows the existing output model; no new output semantics are defined. |
| **OP-REFERENCE-NOT-COPY** | PackageBuilder → sections | Sections hold references/projections to upstream artifacts, not wholesale copies of payloads or config. |
| **OP-VERDICT-AGNOSTIC** | Controller → package | A FAIL verdict still produces a complete, valid package recording the verdict; it is not an engine error. |
| **OP-ORDER** | Coordinator → assembly | Sections assemble in a deterministic order (`section_rank` then `section_id`); metadata keys canonicalized. |
| **OP-DETERMINISTIC** | Formatter → bytes | Same validated artifacts + same request ⇒ byte-identical `OutputRendering` and identical `package_hash`. |
| **OP-SELF-VALIDATED** | Output validation → package | The package passes structural self-checks (required sections present, hashes consistent) before exposure. |
| **OP-FAILCLOSED** | Controller → all | Any engine fault → structured `OutputError`; no partial package exposed. |
| **OP-SINGLE-RESULT** | Controller → caller | Exactly one of `OutputHandle` or `OutputError` is returned. |

---

## 4. Output Session Model

The **OutputSession** is the sealed, run-scoped boundary object handed to Phase 8.

```
OutputSession {
  session_id:      String                    # inherited from upstream sessions
  request_ref:     Ref<OutputRequest>         # sealed
  plan_ref:        Ref<OutputAssemblyPlan>    # sealed
  package_ref:     Ref<RuntimeOutputPackage>  # sealed
  rendering_ref:   Ref<OutputRendering>       # sealed canonical bytes
  validation_ref:  Ref<ValidationResult>      # read-only (Phase 6, unmodified)
  execution_ref:   Ref<ExecutionResult>       # read-only (Phase 5, unmodified)
  created_at:      Timestamp
  lifecycle:       Enum{ SEALED, EXPOSED, CLOSED }
  session_hash:    Hash                        # over session_id + package_hash + plan_hash
}
```
**Rules**
- An `OutputSession` is created only from a fully-populated scope containing a sealed
  `RuntimeOutputPackage` and `OutputRendering`.
- On any engine fault before sealing, no session is produced; the controller returns `OutputError`.
- `lifecycle` moves `SEALED → EXPOSED` when Stage O8 publishes the handle to Phase 8.
- `validation_ref`/`execution_ref` are the untouched upstream results (`OP-READ-ONLY`).

---

## 5. Output Package Model

The **RuntimeOutputPackage** is the standardized deliverable Phase 8 consumes.

```
RuntimeOutputPackage {
  package_id:      String
  session_id:      String
  schema_id:       String                     # declared package schema/version (from upstream, not config-read)
  metadata:        Ref<OutputMetadata>        # sealed
  sections:        Map<String, Ref<OutputSection>>   # by section_id
  section_order:   List<String>               # deterministic order (section_rank then section_id)
  verdict:         Enum{ PASSED, FAILED, PASSED_WITH_WARNINGS }
  package_hash:    Hash                        # deterministic over metadata_hash + ordered section_hashes
}
```
**Standard section set (assembled from upstream references):**
| section_id | Source (read-only) | Content projection |
|------------|--------------------|--------------------|
| `metadata` | `OutputMetadata` | session id, runtime version, verdict, upstream hashes, provenance |
| `validation_summary` | `ValidationResult` | verdict, counts, first_failure, result_hash |
| `validation_report` | `ValidationReport` | ordered rule outcomes (references), category summaries |
| `execution_summary` | `ExecutionResult` | overall_state, result_hash, step count |
| `execution_outputs` | `ExecutionResult.outputs_index` | references to step outputs (never copied wholesale) |

**Rules**
- The package is **read-only** after seal; it references upstream artifacts and never edits them.
- `package_hash` is content-derived and stable, enabling deterministic parity/idempotency checks.

---

## 6. Output Interfaces

Behavioral contracts implemented by engine components. Platform bindings deferred to the conformance phase.

```
interface OutputCoordinator {
  plan(request: OutputRequest, validation: ValidationHandle, execution: ExecutionHandle)
      -> OutputAssemblyPlan throws OutputError
}

interface OutputPackageBuilder {
  assemble(plan: OutputAssemblyPlan) -> List<OutputSection> throws OutputError
  build(sections: List<OutputSection>, metadata: OutputMetadata) -> RuntimeOutputPackage throws OutputError
}

interface OutputMetadataBuilder {
  build(request: OutputRequest, validation: ValidationResult, execution: ExecutionResult)
      -> OutputMetadata throws OutputError
}

interface OutputFormatter {
  render(package: RuntimeOutputPackage, format_profile: String) -> OutputRendering throws OutputError   # deterministic
}

interface OutputValidator {                      # engine's own package self-check (not Phase 6 revalidation)
  check(package: RuntimeOutputPackage) -> PackageCheckReport throws OutputError
}

interface OutputEngine {                          # exposed façade
  handle() -> OutputHandle
  package() -> Ref<RuntimeOutputPackage>
  rendering() -> Ref<OutputRendering>
}
```
**Interface rules**
- Every failable operation throws an `OutputError` (never a platform-native exception escaping the
  engine boundary).
- `OutputValidator.check` performs **structural** self-validation of the package only; it does **not**
  re-run Phase-6 validation or alter the verdict.
- `OutputFormatter.render` must be deterministic: identical package ⇒ identical bytes.

---

## 7. Output Pipeline

Ordered stages. Each declares **Inputs**, **Consumed Runtime Objects**, **Produced Runtime Objects**,
**Outputs**, and **Failure Behaviour**, matching the required implementation flow
(Validation Result → Output Request → Output Assembly → Metadata Construction → Package Construction →
Output Validation → Output Finalization → Runtime Output Package → Expose → Phase 8).

### Stage O0 — Validation Result Intake
- **Inputs:** `ValidationHandle` (exposing `ValidationResult` + `ValidationReport`), `ExecutionHandle`
- **Consumed objects:** the upstream handles (read-only)
- **Produced objects:** initialized `OutputScope`
- **Failure behaviour:** missing/unexposed validation or execution handle → `OutputError{ INTAKE_ERROR }`; abort.

### Stage O1 — Output Request & Assembly Plan
- **Inputs:** raw request + `ValidationResult`
- **Consumed objects:** `ValidationResult`, `ValidationReport`, `ExecutionResult`
- **Produced objects:** `OutputRequest` (sealed), `OutputAssemblyPlan` (ordered sections)
- **Failure behaviour:** malformed request / unknown section id / unknown format profile → `OutputError{ REQUEST_ERROR }`; abort.

### Stage O2 — Output Assembly
- **Inputs:** `OutputAssemblyPlan`
- **Consumed objects:** upstream artifacts referenced by planned sections
- **Produced objects:** `OutputSection[*]` (references/projections, no wholesale copies)
- **Failure behaviour:** required section source missing / unresolved reference → `OutputError{ ASSEMBLY_ERROR }`; abort.

### Stage O3 — Metadata Construction
- **Inputs:** `OutputRequest`, `ValidationResult`, `ExecutionResult`
- **Consumed objects:** upstream sealed objects (hashes, verdict, runtime version)
- **Produced objects:** `OutputMetadata` (provenance, upstream hashes, verdict)
- **Failure behaviour:** missing provenance/hash inputs → `OutputError{ METADATA_ERROR }`; abort.

### Stage O4 — Package Construction
- **Inputs:** `OutputSection[*]`, `OutputMetadata`
- **Consumed objects:** sections + metadata
- **Produced objects:** `RuntimeOutputPackage` (sealed; ordered sections; `package_hash`)
- **Failure behaviour:** section/metadata inconsistency → `OutputError{ PACKAGE_ERROR }`; abort.

### Stage O5 — Output Validation (structural self-check)
- **Inputs:** `RuntimeOutputPackage`
- **Consumed objects:** package sections + metadata
- **Produced objects:** `PackageCheckReport` (required sections present, hashes consistent, order canonical)
- **Failure behaviour:** structural check fails → `OutputError{ SELF_CHECK_ERROR }`; abort. (This is a structural check only; it never re-judges Phase-6 validation.)

### Stage O6 — Output Finalization (render)
- **Inputs:** self-checked `RuntimeOutputPackage`, `format_profile`
- **Consumed objects:** package
- **Produced objects:** `OutputRendering` (canonical, deterministic bytes)
- **Failure behaviour:** serialization/non-determinism detected → `OutputError{ RENDER_ERROR }`; abort.

### Stage O7 — Runtime Output Package (session seal)
- **Inputs:** package + rendering
- **Consumed objects:** upstream session ids
- **Produced objects:** `OutputSession` (sealed)
- **Failure behaviour:** seal failure / incomplete scope → `OutputError{ SESSION_ERROR }`; abort.

### Stage O8 — Expose Output Handle & Pass to Phase 8
- **Inputs:** sealed `OutputSession`
- **Consumed objects:** `RuntimeOutputPackage`, `OutputRendering`
- **Produced objects:** `OutputHandle`; session `lifecycle → EXPOSED`
- **Failure behaviour:** exposure/publish failure → `OutputError{ EXPOSE_ERROR }`; abort.

### Pipeline order (fixed)
```
O0 Intake → O1 Request/Assembly Plan → O2 Assembly → O3 Metadata → O4 Package →
O5 Output Validation → O6 Finalization → O7 Session → O8 Expose → Phase 8
```

---

## 8. Output Error Objects

The single structured error returned on any unrecoverable engine failure.

```
OutputError {
  error_id:        String
  session_id:      String
  stage_id:        Enum{ O0, O1, O2, O3, O4, O5, O6, O7, O8 }
  section_id:      Optional<String>       # the offending section, if applicable
  error_class:     Enum{ INTAKE_ERROR, REQUEST_ERROR, ASSEMBLY_ERROR, METADATA_ERROR,
                          PACKAGE_ERROR, SELF_CHECK_ERROR, RENDER_ERROR, SESSION_ERROR, EXPOSE_ERROR }
  error_code:      String                 # stable, deterministic per (stage, cause)
  message:         String
  cause_detail:    String                 # e.g. missing section source, hash mismatch, non-deterministic render
  produced_before_failure: List<String>   # object ids produced before abort
  occurred_at:     Timestamp
  recoverable:     Bool                    # always false within the engine (retry is outer-orchestration only)
}
```
**Failure behaviour (implementation)**
- Built by the controller the instant a stage returns failure or an interface throws.
- Deterministic: identical faulty inputs ⇒ identical `stage_id` + `error_code` across all platforms.
- Returns the error; no `OutputHandle` is exposed on failure. Upstream validated/executed artifacts
  remain untouched (`OP-READ-ONLY`). A FAIL validation verdict is **not** an `OutputError`
  (`OP-VERDICT-AGNOSTIC`).

---

## 9. Output Packaging Strategy

The packaging strategy guarantees a standardized, deterministic, self-consistent deliverable without
altering upstream artifacts.

| Aspect | Strategy (implementation) |
|--------|---------------------------|
| **Standardization** | Every package has the same section skeleton (Section 5) and metadata shape, so Phase 8 consumers see a uniform structure regardless of verdict. |
| **Reference model (OP-REFERENCE-NOT-COPY)** | Sections carry references/projections into upstream artifacts; large payloads (e.g., step outputs) are referenced via `outputs_index`, never duplicated. |
| **Deterministic ordering** | Sections ordered by `section_rank` then `section_id`; metadata keys canonicalized; provenance links in fixed phase order. |
| **Deterministic serialization** | The formatter uses a canonical encoding (stable key order, fixed number/string normalization, no wall-clock). `rendering_hash` is a pure function of package content. |
| **Integrity** | `package_hash` folds `metadata_hash` + ordered `section_hash`es; `OutputMetadata.upstream_hashes` pins the exact validation/execution artifacts packaged, enabling downstream integrity checks. |
| **Verdict-agnostic** | PASSED / FAILED / PASSED_WITH_WARNINGS all produce complete packages; the verdict is a recorded field, not a gate on packaging. |
| **Self-check (OP-SELF-VALIDATED)** | O5 verifies required sections present and hashes consistent before exposure — structural only, never re-judging Phase-6. |
| **Idempotency** | Re-running with identical inputs yields byte-identical renderings and identical `package_hash` (safe to cache/compare). |
| **Conformance** | Package/metadata field naming and severity levels follow the Runtime Engineering Standard. |

---

## 10. Implementation Readiness Assessment

| Dimension | What is implemented here | Ready? |
|-----------|--------------------------|--------|
| Output orchestration | `OutputController` + fixed pipeline O0–O8, single result | **Yes** |
| Upstream consumption | Consumes only Phase-5/Phase-6 handles; no direct config reads; no layer bypass | **Yes** |
| Read-only over validated artifacts | Upstream artifacts are inputs only; package is a separate object (`OP-READ-ONLY`) | **Yes** |
| Assembly/metadata | Deterministic `OutputAssemblyPlan` + `OutputSection`s + `OutputMetadata` | **Yes** |
| Package model | Standardized, sealed `RuntimeOutputPackage` with fixed section skeleton | **Yes** |
| Determinism | Canonical ordering + serialization; content-derived hashes | **Yes (spec-level; verify in test phase)** |
| Verdict-agnostic | FAIL verdict still produces a complete package (`OP-VERDICT-AGNOSTIC`) | **Yes** |
| Self-validation | Structural self-check before exposure (`OP-SELF-VALIDATED`) | **Yes** |
| Errors | Single structured `OutputError` + fail-closed wiring | **Yes** |

**Deferred to later phases (require executable bindings + resolvable upstream objects at runtime):**
1. Binding the interfaces per platform (Claude/OpenAI/Python/LangGraph/n8n) and asserting byte-identical
   `OutputRendering` and identical `package_hash` across all five.
2. Rendering packages from *actual* `ValidationResult`/`ValidationReport`/`ExecutionResult` outputs.
3. Fault-injecting each `error_class` to confirm deterministic codes and clean abort; verifying FAIL
   verdicts package cleanly.

**Verdict:** The Output Engine is **implementation-ready**. Every artifact is concrete, consumes only
prior implementation-layer runtime objects (never configuration directly, never bypassing a layer),
never modifies validated artifacts, packages deterministically, and produces the
`RuntimeOutputPackage`/`OutputHandle` Phase 8 requires.

---

## 11. Internal Quality Review (self-verification)

| Check | Result |
|-------|--------|
| No Runtime Architecture modified | **PASS** — no architecture defined/changed; only output-packaging machinery |
| No Runtime validation modified | **PASS** — `OP-READ-ONLY`; validation artifacts are read-only inputs; O5 is structural self-check, not revalidation |
| Output Engine consumes only Runtime implementation artifacts | **PASS** — `OP-UPSTREAM-ONLY` / `OP-NO-BYPASS`; O0 takes only Phase-5/6 handles; no direct config reads |
| Runtime Output Package is deterministic | **PASS** — canonical ordering + serialization; content-derived hashes; §0, §9 |
| Output is implementation-oriented | **PASS** — components, objects, interfaces, pipeline, packaging/error wiring; no design narrative |
| References not copies; no duplication | **PASS** — `OP-REFERENCE-NOT-COPY`; sections reference upstream artifacts |
| Single entry, single result; fail-closed | **PASS** — §1.1 (`OP-SINGLE-RESULT`, `OP-FAILCLOSED`) |

**No section resembled a design document; no rewrite required. Approved for commit.**

---

*End of Runtime Output Engine Implementation — Phase 7, Project C-Cloning.*
