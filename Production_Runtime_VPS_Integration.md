# Runtime & VPS Integration

**Project:** C-Cloning
**Project 5:** Production Tool Stack & Automation Workflow
**Stage:** A — Architectural Foundation
**Module:** A5 — Runtime & VPS Integration
**Document Type:** Architecture (Canonical Integration Architecture)
**Status:** Draft for review — architecture-only, implementation-independent
**Branch:** `feature/production-tool-stack`
**Depends on (locked):** A1 — Vision · A2 — Architecture · A3 — Repository · A4 — Data Flow

---

## 0. Preface — Nature and Boundaries of This Document

This document is an **architecture-phase artifact** that defines the **canonical integration
architecture** connecting three parties: the **Master Runtime** (Projects 2 & 3, locked), the
**Visual Production System / VPS** (Project 4, locked), and the **Production Tool Stack**
(Project 5, this work). It defines *boundaries, authority, contracts-as-shape, lifecycle, and
failure containment* — never their realization.

Accordingly, this module deliberately does **not**:

- define implementation (no code, schemas, storage, transports, or serialization);
- define APIs (no endpoints, signatures, payload formats, or protocols);
- select, name, or endorse any AI provider, model, or renderer;
- define execution logic (execution belongs to the Runtime; this module never specifies *how*
  execution is performed);
- redesign, extend, or reinterpret the Master Runtime or the VPS.

The Runtime and the VPS are treated as **fixed authorities**. This module specifies how the Tool
Stack *relates to* them; it never rewrites their internal contracts.

### Inherited Foundations

| Source | What A5 inherits |
|--------|------------------|
| A1 (Vision) | Principles P1–P10 (Runtime supremacy, VPS ownership, provider/renderer-agnosticism, cloud-first, manual review, implementation-independence, boundary preservation, reversibility, roadmap fidelity). |
| A2 (Architecture) | Layers L1–L5, boundary roles (Runtime Gateway at L2, VPS Gateway at L4), integration boundaries. |
| A3 (Repository) | Boundary/integration doc locations (`contracts/boundaries/`, `integration/`). |
| A4 (Data Flow) | Single Source of Truth (SSoT), ownership matrix (OW1–OW4), handoff contracts (H1–H7), reference-not-ownership rule. |

---

## 1. Integration Objectives

The integration architecture exists to let the three parties cooperate **without any party
absorbing another's authority or ownership**. Its objectives (architecture-level; no
implementation):

1. **Preserve authority separation** — the Runtime remains the single execution authority; the
   VPS remains the single visual-asset owner; the Tool Stack remains a coordinator only.
2. **Define clean boundaries** — each party meets the others only through a defined boundary role,
   never through internal coupling.
3. **Enforce SSoT across integration** — cross-party data is exchanged by reference; no party
   re-originates another's authoritative data.
4. **Keep integration provider- and implementation-independent** — the integration shape holds
   regardless of tools, providers, or realization (P3, P7).
5. **Contain failures at boundaries** — a fault in one party must not silently corrupt the others
   or bypass the review gate.
6. **Remain extensible** — new capabilities or future parties (e.g., Publishing) attach by
   addition, without redesigning existing boundaries.

---

## 2. System Boundary Diagram

```
                          ┌───────────────────────────────────────────────┐
                          │        PRODUCTION TOOL STACK (Project 5)         │
                          │        coordinator — no execution authority,      │
                          │        no visual ownership                        │
                          │                                                   │
   request execution      │   ┌────────────────┐        ┌────────────────┐   │  reference assets
  (by reference, A4:H2)   │   │ Runtime Gateway │        │  VPS Gateway   │   │  (A4:H4)
        ┌─────────────────┼──▶│  role @ L2      │        │  role @ L4     │◀──┼──────────────┐
        │                 │   └────────┬────────┘        └────────┬───────┘   │              │
        │                 │            │ (internal, acyclic — A2 §6)          │              │
        │                 │            ▼                          ▼           │              │
        │                 │   L1▶L2▶L3▶L4▶L5 canonical data flow (A4)          │              │
        │                 │            │  PRPP → MANDATORY REVIEW GATE (P6)     │              │
        │                 └────────────┼──────────────────────────────────────┘              │
        │                              │ approved → Publishing boundary (future)               │
        ▼                              ▼                                                        ▼
┌───────────────────┐        ┌───────────────────┐                                 ┌───────────────────┐
│  MASTER RUNTIME    │        │ FUTURE PUBLISHING  │                                 │ VISUAL PRODUCTION  │
│  (Projects 2 & 3)  │        │  SYSTEM (undefined) │                                 │  SYSTEM (Project 4)│
│  EXECUTION         │        │  boundary preserved │                                 │  VISUAL OWNERSHIP  │
│  AUTHORITY (SSoT   │        └───────────────────┘                                 │  (SSoT for assets) │
│  for exec results) │                                                              └───────────────────┘
└───────────────────┘

  Directionality (all one-way w.r.t. authority):
   • Tool Stack ─request▶ Runtime ; Runtime ─result(ref)▶ Tool Stack
   • Tool Stack ─reference▶ VPS   ; VPS ─asset ref+provenance▶ Tool Stack
   • Neither Runtime nor VPS depends on the Tool Stack.
```

---

## 3. Runtime Integration Boundary

- **Boundary role:** the **Runtime Gateway** at L2 (per A2) is the *only* place the Tool Stack
  meets the Runtime.
- **Nature:** request/consume. The Tool Stack submits **execution requests** (references to its
  Production Plan, A4:H2); the Runtime governs and performs execution and returns **execution
  results by reference** (A4:H3).
- **Authority:** the Runtime holds **execution authority (P1)** and is the **SSoT for execution
  results**. The Tool Stack never executes and never re-owns results.
- **Invariants:** no Runtime redesign; no execution logic defined here; the boundary is
  one-directional with respect to authority (Runtime never depends on the Tool Stack).

## 4. VPS Integration Boundary

- **Boundary role:** the **VPS Gateway** at L4 is the *only* place the Tool Stack meets the VPS.
- **Nature:** reference/consume. The Tool Stack requests **asset references** and receives
  **references + provenance** (A4:H4).
- **Authority:** the VPS holds **visual-asset ownership (P2)** and is the **SSoT for asset data**.
  The Tool Stack never re-owns, mutates, copies as a competing original, or re-renders assets
  (no rendering logic — inherited from A4).
- **Invariants:** no VPS redesign; the boundary is one-directional with respect to ownership.

## 5. Production Tool Stack Boundary

- **Role:** coordinator. The Tool Stack owns only **coordination artifacts** (Canonical Production
  Intent, Production Plan, PRPP composition, provenance/lineage — A4 ownership matrix).
- **Outward faces:** it presents the Runtime Gateway (toward Runtime), the VPS Gateway (toward
  VPS), and — after the mandatory review gate — the Publishing handoff seam (toward the future
  Publishing System).
- **Invariants:** it holds **no execution authority** and **no visual ownership**; it never
  reaches past a boundary into another party's internals (P8).

---

## 6. Authority Matrix

Authority is fixed and never transfers through integration (enforces P1, P2, SSoT).

| Concern | Authoritative Party | Tool Stack's relation | Runtime's relation | VPS's relation |
|---------|---------------------|-----------------------|--------------------|----------------|
| Execution (performing work) | **Master Runtime** | requests only | **authority** | none |
| Execution results (data) | **Master Runtime** (SSoT) | reference | **owner** | none |
| Visual assets (data) | **VPS** (SSoT) | reference + provenance | none | **owner** |
| Asset ownership/provenance origin | **VPS** | consumes | none | **owner** |
| Canonical Production Intent | **Tool Stack** (SSoT) | **owner** | none | none |
| Production Plan | **Tool Stack** (SSoT) | **owner** | receives requests | none |
| PRPP (composition) | **Tool Stack** | **owner of composition** | contributes results (ref) | contributes assets (ref) |
| Provenance / lineage | **Tool Stack** (SSoT) | **owner** | none | none |
| Review approval decision | **Human reviewer** (gate) | presents to reviewer | none | none |
| Published output | **Future Publishing System** | not held (post-gate) | none | none |

**Authority rules:**
- AU1 — Authority is single-owner and non-transferable through any boundary.
- AU2 — The Tool Stack coordinates; it never becomes an execution authority (P1) or asset owner
  (P2).
- AU3 — Cross-party data crosses boundaries **by reference**, preserving SSoT (A4:HC2).
- AU4 — The human review approval is an authority the automation cannot assume (P6).

---

## 7. Request/Response Contract Model

Contracts are described as **shape and invariant only** — explicitly **not APIs** (no endpoints,
signatures, formats, or protocols; P7).

| Contract | Direction | Request carries (shape) | Response carries (shape) | Invariant preserved |
|----------|-----------|--------------------------|--------------------------|---------------------|
| RC1 Execution | Tool Stack → Runtime → Tool Stack | reference to Production Plan step | reference to execution result | Runtime authority; results Runtime-owned (P1, SSoT) |
| RC2 Asset Reference | Tool Stack → VPS → Tool Stack | reference to asset need | asset reference(s) + provenance | VPS ownership; assets VPS-owned (P2, SSoT) |
| RC3 Review Presentation | Tool Stack → Reviewer → Tool Stack | PRPP presented for decision | approval / rejection decision | Mandatory human gate (P6) |
| RC4 Publishing Handoff | Tool Stack → Publishing | approved PRPP (reference) | (none defined here) | One-directional; no publishing internals (P8) |

**Contract rules:**
- CN1 — Contracts define *what shape crosses* and *what invariant holds*, never *how* (no API).
- CN2 — Every request is directional; no response transfers authority to the Tool Stack.
- CN3 — Responses carrying cross-party data carry **references**, not re-owned originals.
- CN4 — No contract names a provider, model, or renderer (P3, P4).

---

## 8. Integration Lifecycle

The lifecycle describes the **states of an integration interaction** (architectural, not
implementation):

```
  ESTABLISHED ─▶ REQUEST-ISSUED ─▶ ACCEPTED-BY-AUTHORITY ─▶ RESULT-REFERENCED
                                          │                        │
                                     (declined/fault)              ▼
                                          │                 COORDINATED (A4 flow continues)
                                          ▼                        │
                                    FAULT-CONTAINED ◀──────────────┘ (on downstream fault)
                                          │
                                          ▼
                                    RESOLVED / RETURNED  (never bypasses review gate, P6)
```

- **Establishment:** a boundary relationship is established via its gateway role (Runtime Gateway
  or VPS Gateway).
- **Steady state:** requests are issued, accepted by the authoritative party, and results/assets
  are **referenced** back (SSoT).
- **Provenance:** every interaction is lineage-tracked (A4 State & Provenance).
- **Termination:** interactions resolve normally into the A4 flow, or are contained as faults
  (§9); neither path bypasses the mandatory review gate.
- **Reversibility (P9):** because cross-party data is referenced, an interaction can be retried or
  abandoned without corrupting authoritative originals.

---

## 9. Failure Boundary Model

Failures are **contained at the boundary of the party that owns the failing concern** — they do
not propagate authority or silently corrupt other parties.

| Failure Origin | Contained at | Effect on Tool Stack | Guardrail |
|----------------|--------------|----------------------|-----------|
| Runtime execution fault | Runtime boundary (Runtime Gateway) | receives a non-result signal; no partial re-ownership | Tool Stack never fabricates results; SSoT intact (P1) |
| VPS asset-unavailable | VPS boundary (VPS Gateway) | receives a non-reference signal; no synthesized assets | Tool Stack never re-renders or re-owns (P2) |
| Tool Stack coordination fault | within Tool Stack layers | halts/returns the affected data set | Never emits unreviewed output (P6) |
| Review rejection | Review gate | returns data set to planning/revision (A4 lifecycle) | Gate never bypassed (P6) |
| Publishing-side fault (future) | Publishing boundary | out of Tool Stack scope | Boundary preserved; no internals assumed (P8) |

**Failure rules:**
- FB1 — A failing party's fault is contained at its own boundary; authority/ownership never
  transfers as a "workaround."
- FB2 — The Tool Stack never fabricates, synthesizes, or re-owns another party's authoritative
  data to mask a failure (SSoT integrity).
- FB3 — No failure path emits output downstream without the mandatory review gate (P6).
- FB4 — Faults are recorded in provenance/lineage; reversibility (P9) allows safe retry/return.

---

## 10. Future Extensibility Strategy

Extensibility is achieved by **addition at boundaries**, never by redesigning existing ones
(mirrors A2 §9 / A3 §9):

1. **New capability via slots (P3/P4):** additional capability/renderer types attach through the
   A2 L3 abstract slots; the Runtime and VPS boundaries are unaffected.
2. **New external party (e.g., Publishing):** attaches as a new one-directional boundary + handoff
   seam, exactly as the Publishing boundary is reserved today (P8).
3. **Boundary stability:** the Runtime and VPS boundaries are stable contracts-of-shape; growth
   never alters their authority/ownership semantics (AU1, AU2).
4. **Reference-based coupling (SSoT):** because parties exchange references, new parties can be
   added without duplicating authoritative data.
5. **Reversibility (P9):** any added boundary or slot can be retired without cascading redesign.
6. **Roadmap fidelity (P10):** all extension remains within the locked C-Cloning roadmap.

---

## 11. Integration Readiness Assessment

| Readiness Criterion | Status | Notes |
|---------------------|--------|-------|
| Integration architecture specified | ✅ Ready | §1–§10; three-party coordination. |
| System boundary diagram provided | ✅ Ready | §2. |
| Integration objectives defined | ✅ Ready | §1. |
| Runtime integration boundary defined | ✅ Ready | §3; Runtime Gateway @ L2, request/consume. |
| VPS integration boundary defined | ✅ Ready | §4; VPS Gateway @ L4, reference/consume. |
| Production Tool Stack boundary defined | ✅ Ready | §5; coordinator, no authority/ownership. |
| Authority model / matrix defined | ✅ Ready | §6; AU1–AU4. |
| Request/response contract model defined | ✅ Ready | §7; RC1–RC4, CN1–CN4 (no APIs). |
| Integration lifecycle defined | ✅ Ready | §8; states + provenance. |
| Failure boundary model defined | ✅ Ready | §9; FB1–FB4. |
| Future extensibility strategy defined | ✅ Ready | §10; addition at boundaries. |
| Runtime authority preserved | ✅ Ready | P1; AU2, RC1. |
| VPS ownership preserved | ✅ Ready | P2; AU2, RC2. |
| Single Source of Truth preserved | ✅ Ready | AU3, references across boundaries. |
| Provider-agnostic | ✅ Ready | P3; CN4, slot-mediated. |
| Implementation-independent | ✅ Ready | P7; shape-only, no realization. |
| No implementation | ✅ Ready | Boundaries/authority/contracts only. |
| No API definitions | ✅ Ready | Contracts are shape+invariant, not APIs. |
| No AI provider selected | ✅ Ready | CN4; none named. |
| No execution logic defined | ✅ Ready | Execution belongs to Runtime (P1). |
| No Runtime/VPS redesign | ✅ Ready | Treated as fixed authorities. |
| Supports future Stage B modules | ✅ Ready | Stable boundaries + extension strategy. |
| Aligns with A1–A4 and Projects 1–4 | ✅ Ready | Direct projection of A2/A4; principles preserved. |

**Overall verdict:** ✅ **Integration-ready.** Module A5 defines a stable, SSoT-preserving,
provider-agnostic, API-free integration architecture consistent with A1–A4, ready for the
remainder of Stage A and all future Stage B modules.

---

## 12. Internal Consistency Review (Self-Check)

Verified before finalizing:

- ✅ Contains **no** implementation (no code, schemas, storage, transports, serialization).
- ✅ Defines **no** APIs (no endpoints, signatures, formats, or protocols — contracts are
  shape+invariant only).
- ✅ Selects **no** AI provider, model, or renderer.
- ✅ Defines **no** execution logic (execution authority remains with the Runtime).
- ✅ Does **not** redesign the Master Runtime; execution and its results remain Runtime-owned.
- ✅ Does **not** redesign the VPS; visual assets remain VPS-owned and referenced.
- ✅ Preserves **Single Source of Truth** (authority/ownership non-transferable; references across
  boundaries).
- ✅ Preserves provider-agnosticism and implementation-independence.
- ✅ Contains faults at boundaries and never bypasses the mandatory review gate (P6).
- ✅ Consistent with A1 (P1–P10), A2 (layers/boundaries), A3 (repository), A4 (data flow/SSoT), and
  locked Projects 1–4.
- ✅ Extensible by addition, supporting all future Stage B modules.

Inconsistencies found: none. Document ready for commit on `feature/production-tool-stack`.
