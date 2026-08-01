# Asset Generation Pipeline

**Project:** C-Cloning
**Project 5:** Production Tool Stack & Automation Workflow
**Stage:** B — Design Deepening
**Module:** B4 — Asset Generation Pipeline
**Document Type:** Specification (Design — implementation-independent)
**Status:** Draft for review — specification-only, provider-agnostic
**Branch:** `feature/production-tool-stack`
**Depends on (locked):** Stage A — A1 · A2 · A3 · A4 · A5 · A6 · A7 · A8 · A9 · A10 · Stage B — B1 · B2 · B3

---

## 0. Preface — Nature and Boundaries of This Document

This document is the fourth **Stage B specification** module. It defines the **canonical Asset
Generation Pipeline (AGP)**: the abstract, staged coordination flow by which a validated,
slot-shaped translation (from B3) is turned — through capability slots (B1) and renderer adapters
(B2), under Runtime authority — into a **VPS-owned generated asset (by reference)** ready for
downstream assembly and the mandatory review gate.

This module is a **specification/design deepening** of the locked Stage A architecture and B1–B3.
It adds detail *within* the existing architecture; it introduces no new architecture and **does
not redesign** B1 (abstraction), B2 (adapters), or B3 (translation) — it consumes them.

Accordingly, this module deliberately does **not**:

- select, name, rank, or endorse any AI provider, model, renderer, or vendor;
- define APIs (no endpoints, signatures, payload formats, or protocols);
- define authentication, credentials, secrets, or authorization mechanisms;
- define implementation logic (no code, schemas, queues, storage, or execution/generation logic).

The Runtime and VPS remain **fixed authorities** (Stage A); B1 slots/contracts, B2 adapters/
bindings, and B3 translations remain **fixed** (this module consumes them, never alters them).

### Placement Within the Locked Architecture

The AGP is the staged coordination that lives across **A2 L2 (Orchestration)** →
**L3 (Capability slots, via B1/B2)** → **L4 (Asset Coordination)**, terminating by handing a
VPS-owned asset reference toward **L5 (Assembly & Review-Handoff)**. It consumes the **B3
slot-shaped translation**, drives **B1 capability slots** (rendering via **B2 adapters**),
requests execution under **Runtime authority (A5)**, and coordinates **VPS-owned assets by
reference (A4)**.

```
  B3 translation (by ref) ─▶ [ ASSET GENERATION PIPELINE (B4) ] ─▶ VPS-owned asset ref ─▶ L5 (assembly + review gate)
                                stage flow · validation gates ·          │
                                retry/recovery · provenance               ▼
                             (drives B1 slots / B2 adapters; execution requested under Runtime authority)
```

### Inherited Foundations

| Source | What B4 inherits |
|--------|------------------|
| A1 | Principles P1–P10 (esp. P1 Runtime authority, P2 VPS ownership, P6 review gate, P9 reversibility). |
| A2 | L2/L3/L4/L5 layers; cross-cutting State & Provenance; C1–C10. |
| A4 | Canonical flow (T1–T7); SSoT; PRPP composition; references-not-ownership; execution results Runtime-owned; assets VPS-owned. |
| A5 | Execution requested under Runtime authority; asset reference via VPS boundary; failure boundaries. |
| A7 | Standards; acceptance criteria MA1–MA10; compliance AC1–AC8; traceability TR. |
| A8 | Policy envelopes; slot-bounded resource use; cost-risk governance (gate-before-spend). |
| B1 | Abstract capability slots; shape-only contracts (TC1–TC4); anonymous occupants. |
| B2 | Renderer adapters; conformance shapes; bindings. |
| B3 | Provider-neutral, meaning-preserving, validated slot-shaped translations. |

---

## 1. Asset Generation Pipeline Specification (Overview)

Central premise, consistent with the roadmap:

> **The pipeline coordinates generation; it never performs or owns it.** Each stage prepares,
> requests, references, or validates — capability occupants generate (behind B1/B2), the Runtime
> governs execution, and the VPS owns every resulting asset. The AGP owns only the *coordination*
> and the *provenance* of the flow; it produces a **VPS-owned asset reference**, never an owned
> asset.

The pipeline is specified as: a **stage model** (§2), a **generation responsibility model** (§3),
an **asset lifecycle** (§4), a **validation gate model** (§5), an **ownership model** (§6), a
**retry & recovery boundary model** (§7), an **extension strategy** (§8), and **architectural
constraints** (§9).

**Meta-rules:**
- **AG1 — Coordinate, don't generate:** the AGP sequences stages and requests capability use; it
  never generates, renders, or executes itself (P1).
- **AG2 — VPS-owned output:** every generated asset is VPS-owned and surfaced **by reference**
  (P2); the pipeline never re-owns or stores assets as originals.
- **AG3 — Consumes B1/B2/B3, never redesigns them:** the pipeline drives slots/adapters and
  consumes translations as-is (no redesign).
- **AG4 — Gate-guarded:** validation gates guard stage transitions; nothing reaches assembly
  unvalidated, and nothing publishes without the downstream manual review gate (P6).
- **AG5 — Implementation-independent:** the pipeline constrains *stage shape and invariant*, not
  realization (P7).

---

## 2. Pipeline Stage Model

Stages are **abstract coordination phases**, described by role — not implementation, queues, or
schedulers (AG5). Each stage has a validation gate (§5) at its exit.

```
  S1 INTAKE ─▶ S2 PREPARE ─▶ S3 GENERATE-REQUEST ─▶ S4 CAPTURE ─▶ S5 ASSET-COORDINATE ─▶ S6 HANDOFF
     │            │               │                    │               │                    │
   [G1]         [G2]            [G3]                 [G4]            [G5]                 [G6]
```

| Stage | Role | Consumes | Produces | Authority/Ownership |
|-------|------|----------|----------|---------------------|
| **S1 Intake** | Admit a validated B3 translation (by reference) into the pipeline | B3 slot-shaped translation | admitted generation task (ref) | Tool Stack (coordination) |
| **S2 Prepare** | Resolve the target capability slot (B1) / renderer adapter (B2) and bind policy envelope (A8) | admitted task; B1 slot; B2 adapter | prepared generation request (ref) | Tool Stack; slot/adapter anonymous |
| **S3 Generate-Request** | Issue the generation *request* under Runtime authority via the slot/adapter | prepared request | in-flight generation (ref) | **Runtime** governs execution (P1) |
| **S4 Capture** | Receive the derived generation output **by reference** with provenance | generation result reference | captured output ref + provenance | **Runtime-owned** result (ref, A4) |
| **S5 Asset-Coordinate** | Coordinate the output as a **VPS-owned asset** by reference (via VPS boundary) | captured output ref | VPS-owned asset reference | **VPS owns** the asset (P2) |
| **S6 Handoff** | Hand the VPS-owned asset reference toward L5 assembly + review gate | VPS-owned asset ref | handoff to L5 (ref) | Tool Stack coordinates; gate at L5 (P6) |

**Stage rules:**
- ST1 — Stages are strictly ordered S1→S6; no stage is skipped and none runs before its
  predecessor's gate passes (§5).
- ST2 — No stage performs generation/execution/rendering; S3 *requests* it, the Runtime governs
  it, occupants (behind B1/B2) perform it.
- ST3 — All inter-stage data is carried **by reference** with provenance (SSoT, A4).

---

## 3. Generation Responsibility Model (Responsibility Matrix)

| Concern | Responsible party | AGP relation | Never |
|---------|-------------------|--------------|-------|
| Sequencing the stages | **Production Tool Stack (AGP)** | owns the coordination | performs generation |
| Performing generation | capability occupant (behind B1/B2) | requests via slot/adapter | is named/selected here (B1 PA2) |
| Governing execution | **Master Runtime** | requests execution (S3) | re-owns execution (P1) |
| Owning generation results (data) | **Master Runtime** | references (S4) | re-originates results |
| Owning generated assets | **VPS** | references (S5) | re-owns/mutates/stores (P2) |
| Translation of intent | **B3 PTE** | consumes validated translations | re-translates or edits meaning |
| Slot/adapter conformance | **B1 / B2** | drives as-is | redesigns slots/adapters |
| Policy envelopes / cost-risk | **A8 governance** | operates within | bypasses/optimizes (A8 UP7) |
| Provenance/lineage of the flow | **Production Tool Stack (AGP)** | owns lineage | owns underlying result/asset |
| Review approval before publish | **Human reviewer (L5 gate)** | hands off to gate | auto-approves (P6) |

**Responsibility rules:**
- GR1 — The AGP owns only **coordination artifacts** and **flow provenance** — never the tools,
  results, or assets (SSoT).
- GR2 — Exactly one responsible party per concern (single-ownership, A6 MG2 / A7 EG3).
- GR3 — Responsibilities preserve Runtime authority (P1) and VPS ownership (P2) at every stage.

---

## 4. Asset Lifecycle Model

The lifecycle describes the **states of a generated asset within the pipeline** — architectural
states, not storage/retention implementation (AG5):

```
  REQUESTED ─▶ GENERATING(under Runtime authority) ─▶ CAPTURED(result ref) ─▶ ASSET-REGISTERED(VPS-owned ref)
      │               │                                     │                        │
      │        (fault / timeout)                       (validation)                  │ (validated)
      │               ▼                                     ▼                         ▼
      │        RECOVERABLE? ──▶ retry/recover (§7)     REJECTED (gate fail)     HANDED-OFF (to L5)
      ▼                                                     │                        │
   DENIED (policy/envelope, A8)                         RETURNED (revise)      → review gate (P6)
```

- **Requested / Generating:** a generation request is issued (S3) and performed under **Runtime
  authority**; the AGP holds only a reference.
- **Captured / Asset-registered:** the derived result is captured by reference (S4) and coordinated
  as a **VPS-owned asset reference** (S5) — the VPS owns it; the AGP references it.
- **Handed-off:** a validated VPS-owned asset reference is handed to L5 assembly, where the
  mandatory manual review gate applies before any publishing.
- **Recoverable / Denied / Rejected / Returned:** faults route to retry/recovery (§7) or denial;
  gate failures return the item for revision — never a fabricated or force-published asset.
- **Reversibility (P9):** because results/assets are referenced (not re-owned), lifecycle states
  can be safely retried or unwound without corrupting authoritative originals.

---

## 5. Validation Gate Model

Each stage exit is guarded by a **validation gate** (G1–G6). Gates validate conformance and
invariants — they are not tests of an implementation (AG5).

| Gate | Guards transition | Validates | Fail action |
|------|-------------------|-----------|-------------|
| **G1** | S1→S2 | translation is a valid B3 output (meaning-preserved, slot-shaped) | reject → return to L2/B3 |
| **G2** | S2→S3 | slot/adapter resolved (B1/B2 conformance); policy envelope bound (A8) | reject → revise/escalate |
| **G3** | S3→S4 | generation requested under Runtime authority (no self-execution) | reject → contain (P1) |
| **G4** | S4→S5 | result captured **by reference** with provenance (no re-owned data) | reject → recover/return (SSoT) |
| **G5** | S5→S6 | output registered as **VPS-owned asset by reference** (no re-own/mutate) | reject → contain (P2) |
| **G6** | S6→L5 | asset reference complete + provenance intact; ready for review gate | reject → return to assembly |

**Gate rules:**
- VG1 — No stage transition occurs without its gate passing (ST1).
- VG2 — Gates enforce the invariants (P1/P2/SSoT) at the point of transition (A7 D6/AC).
- VG3 — A failed gate yields **reject/return/escalate** — never a silent pass or fabricated
  artifact.
- VG4 — G6 readiness never substitutes for the L5 **manual review gate** (P6); it only ensures the
  asset reference is well-formed for it.
- VG5 — Every gate outcome is provenance-recorded (A7 TR, A8 CR5).

---

## 6. Ownership Model

Ownership strictly mirrors Stage A SSoT and B1–B3 (A4, A5, B1 §5):

| Element | Owner (SSoT) | AGP relation | Never |
|---------|--------------|--------------|-------|
| Generation results (data) | **Master Runtime** | references (S4) | re-owns/executes (P1) |
| Generated visual/asset outputs | **VPS** | references + provenance (S5) | re-owns/mutates/re-renders (P2) |
| Generation task / stage artifacts | **Production Tool Stack (AGP)** | **owns** coordination artifacts | extends into Runtime/VPS domains |
| Slot/adapter occupant | external, out of scope | drives anonymously (B1/B2) | binds as load-bearing |
| Translation | **B3 PTE** | references validated translation | edits meaning |
| Provenance/lineage of the pipeline | **Production Tool Stack (AGP)** | **owns lineage** | owns underlying result/asset |

**Ownership rules:**
- OWg1 — The AGP owns only coordination artifacts and flow lineage; results are Runtime-owned,
  assets are VPS-owned (SSoT).
- OWg2 — One authoritative owner per element; the pipeline never transfers ownership.
- OWg3 — Every generated asset is **always** VPS-owned and surfaced by reference (P2, AG2).

---

## 7. Retry & Recovery Boundary Model

Retry/recovery is bounded coordination — never fabrication, and never authority transfer (mirrors
A5 §9 / B1 §7 / B2 §7):

| Fault | Bounded at | Recovery action | Guardrail |
|-------|------------|-----------------|-----------|
| Generation request fault (S3) | Runtime boundary | bounded retry of the *request* | Runtime governs; no self-execution (P1) |
| Occupant/adapter failure | slot/adapter boundary (B1/B2) | substitute conforming occupant/adapter; retry | No fabricated output (SSoT); B1/B2 unchanged |
| Capture fault (S4) | capture stage | re-reference; recover result by reference | No invented result data (SSoT) |
| Asset-registration fault (S5) | VPS boundary | retry registration by reference | VPS remains owner (P2) |
| Out of policy envelope | policy check (A8) | escalate for governed decision | No silent over-use / infinite retry (A8 UP7) |
| Gate failure (§5) | the failing gate | reject/return/revise | No forced pass (VG3) |

**Retry & recovery rules:**
- RR1 — Retries are **bounded** and governed by policy envelopes (A8); unbounded/auto-retry is
  prohibited (cost-risk, A8 CR).
- RR2 — Recovery favors **substitution** (another conforming occupant/adapter, B1/B2) and safe
  **rollback** over irreversible commitment (P9).
- RR3 — The pipeline never fabricates, synthesizes, or force-completes an asset to mask a fault
  (SSoT).
- RR4 — Faults and recovery actions are provenance-recorded (A7 TR); no recovery path bypasses the
  L5 review gate (P6).

---

## 8. Extension Strategy

The pipeline grows **by addition within the abstract model**, never by redesign (mirrors A2 §9 /
B1 §8 / B2 §8 / B3 §9):

- **EXg1 — New generation kind = new capability slot usage:** supporting a new kind of asset uses
  a new/existing B1 capability slot (and B2 adapter for rendering) — the stage model is unchanged.
- **EXg2 — New validation = new gate rule:** additional validation is added as gate rules (§5),
  not by reworking stages.
- **EXg3 — New recovery strategy = additive:** new bounded recovery strategies are added under RR1
  without changing stage ownership.
- **EXg4 — No provider specialization:** extension never adds a provider-specific stage or path;
  provider differences stay behind B1/B2 (B1 PA2).
- **EXg5 — Reversible:** any stage rule, gate, or recovery extension can be retired without
  cascading redesign (P9).
- **EXg6 — Governed:** pipeline changes are governed, traceable (A7 VC4/CM, A8 envelopes).

---

## 9. Architectural Constraints

Binding on this pipeline and its consumers:

- **ACg1 — No provider selection:** no provider/model/renderer named, ranked, or chosen (B1 PA2).
- **ACg2 — No APIs / no auth:** stage/gate contracts are shape+invariant only (§2, §5).
- **ACg3 — No implementation / no generation logic:** the AGP coordinates and requests; it never
  generates, renders, or executes (P1, P7).
- **ACg4 — No redesign of B1–B3:** slots, adapters, and translations are consumed unchanged (AG3).
- **ACg5 — Runtime authority preserved:** generation is requested; the Runtime governs execution
  (P1).
- **ACg6 — VPS ownership preserved:** every generated asset is VPS-owned by reference; no re-own/
  re-render/store (P2, AG2).
- **ACg7 — SSoT preserved:** one owner per element; results/assets referenced, not re-owned.
- **ACg8 — Provider-agnostic:** the pipeline is identical regardless of slot/adapter occupants
  (P3).
- **ACg9 — Implementation-independent:** stage shape + invariant only (P7).
- **ACg10 — Gate & policy fidelity:** validation gates guard transitions; the L5 manual review
  gate is never bypassed; stays within A8 envelopes and the locked roadmap (P6, P8, P10).

---

## 10. Stage B Readiness Assessment (Readiness for B5)

| Readiness Criterion | Status | Notes |
|---------------------|--------|-------|
| Pipeline specification defined | ✅ Ready | §1; coordinate-not-generate + AG1–AG5. |
| Purpose defined | ✅ Ready | §0–§1. |
| Pipeline stage model defined | ✅ Ready | §2; S1–S6 + ST1–ST3. |
| Generation responsibility model defined | ✅ Ready | §3; responsibility matrix + GR1–GR3. |
| Asset lifecycle model defined | ✅ Ready | §4; states + provenance + reversibility. |
| Validation gate model defined | ✅ Ready | §5; G1–G6 + VG1–VG5. |
| Ownership model defined | ✅ Ready | §6; OWg1–OWg3, VPS-owned assets. |
| Retry & recovery boundary model defined | ✅ Ready | §7; RR1–RR4, bounded. |
| Extension strategy defined | ✅ Ready | §8; EXg1–EXg6, additive. |
| Architectural constraints defined | ✅ Ready | §9; ACg1–ACg10. |
| No provider selection | ✅ Ready | ACg1. |
| No implementation | ✅ Ready | Specification only. |
| No APIs / auth | ✅ Ready | §2/§5, ACg2. |
| No redesign of B1–B3 | ✅ Ready | AG3, ACg4; consumed as-is. |
| Runtime authority preserved | ✅ Ready | S3, ACg5. |
| VPS ownership preserved | ✅ Ready | S5, OWg3, ACg6. |
| Single Source of Truth preserved | ✅ Ready | OWg2, ACg7. |
| Provider-agnostic | ✅ Ready | ACg8. |
| Implementation-independent | ✅ Ready | AG5, ACg9. |
| No Runtime/VPS redesign | ✅ Ready | Treated as fixed authorities. |
| Ready for B5 | ✅ Ready | Validated VPS-owned asset references handed to L5 provide a stable surface for B5. |
| Aligns with Stage A (A1–A10), B1–B3 | ✅ Ready | Spans L2→L4 to L5; consumes B3 translations, B1 slots, B2 adapters. |

**Overall verdict:** ✅ **Pipeline-ready.** Module B4 specifies a complete, provider-agnostic,
implementation-independent Asset Generation Pipeline — staged, gate-guarded, coordinate-not-generate,
producing VPS-owned asset references — consistent with Stage A and B1–B3, ready for B5.

---

## 11. Internal Consistency Review (Self-Check)

Verified before finalizing:

- ✅ Selects **no** AI provider, model, renderer, or vendor (occupants stay anonymous behind
  B1/B2).
- ✅ Defines **no** APIs, authentication, or credentials.
- ✅ Contains **no** implementation or generation/execution logic (the pipeline coordinates and
  requests only).
- ✅ Does **not** redesign the Master Runtime, the VPS, or B1/B2/B3 (all consumed as fixed).
- ✅ Preserves **Single Source of Truth**, Runtime authority (P1) — generation requested, results
  Runtime-owned — and **VPS ownership (P2)** — assets VPS-owned by reference, never re-owned.
- ✅ Gate-guarded stages; the downstream **manual review gate (P6)** is never bypassed.
- ✅ Provider-agnostic and implementation-independent throughout (stage shape + invariant only).
- ✅ Introduces **no new architecture** — spans A2 L2→L4 into L5 and consumes B1/B2/B3.
- ✅ Consistent with A1–A10, B1–B3, and locked Projects 1–4; provides a stable surface **ready for
  B5**.

Inconsistencies found: none requiring modification of a locked module. Document ready for commit
on `feature/production-tool-stack`.
