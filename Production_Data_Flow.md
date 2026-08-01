# Production Data Flow

**Project:** C-Cloning
**Project 5:** Production Tool Stack & Automation Workflow
**Stage:** A — Architectural Foundation
**Module:** A4 — Production Data Flow
**Document Type:** Architecture (Canonical Data Flow Specification)
**Status:** Draft for review — architecture-only, implementation-independent
**Branch:** `feature/production-tool-stack`
**Depends on (locked):** A1 — Vision & Philosophy · A2 — System Architecture · A3 — Repository Structure

---

## 0. Preface — Nature and Boundaries of This Document

This document is an **architecture-phase artifact** that defines the **canonical Production Data
Flow** of the Production Tool Stack: what data enters, how it moves through the A2 layers, who
owns it at each point, how it is handed off across boundaries, and the constraints that bind it.
It describes **flow, ownership, and contracts** — never their realization.

Accordingly, this module deliberately does **not**:

- define implementation (no code, schemas, serialization formats, APIs, or storage engines);
- select, name, or endorse any AI provider, model, or renderer;
- define rendering logic or rendering behavior;
- define automation workflows, pipelines, triggers, or orchestration logic.

Where Projects 1–4 are referenced, they are treated as **fixed authorities** whose data
contracts this flow consumes but never rewrites.

### Inherited Foundations

| Source | What A4 inherits |
|--------|------------------|
| A1 (Vision & Philosophy) | Principles P1–P10 (Runtime supremacy, VPS ownership, provider/renderer-agnosticism, cloud-first, manual review, implementation-independence, boundary preservation, reversibility, roadmap fidelity). |
| A2 (System Architecture) | Layers L1–L5, cross-cutting concerns (esp. State & Provenance), integration boundaries (Runtime, VPS, Publishing), constraints C1–C10. |
| A3 (Repository Structure) | Where flow/contract specifications live (`contracts/`, `integration/`). |

### New Governing Concept — Single Source of Truth (SSoT)

Beyond the inherited principles, A4 introduces one governing data concept required by the brief:

> **SSoT — Single Source of Truth.** For every category of production data, exactly **one**
> authoritative owner holds the canonical value. All other holders carry **references or
> derived copies**, never competing authoritative originals. The Tool Stack never becomes the
> authoritative owner of data owned by the Runtime or the VPS.

---

## 1. Production Data Flow Specification (Overview)

Production data flows **downward through the A2 layers** from governed intent to a publish-ready
outcome, crossing external boundaries only through defined handoffs, while the **State &
Provenance** cross-cutting concern records lineage without ever taking ownership.

```
  PRODUCTION INTENT (inbound, governed)
        │
        ▼
  [L1] Intent & Governance ......... normalize → Canonical Production Intent (CPI)
        │                                   (Tool Stack authoritative, SSoT for CPI)
        ▼
  [L2] Orchestration ............... derive Production Plan; issue EXECUTION REQUESTS
        │        └── request ▶ [Runtime boundary] ── execute under Runtime authority ──┐
        │        ◀── execution results (Runtime-owned, referenced) ────────────────────┘
        ▼
  [L3] Capability Abstraction ...... route through abstract slots (provider-agnostic)
        │                                   (no provider named; no rendering logic)
        ▼
  [L4] Asset Coordination .......... reference VPS-owned assets by reference + provenance
        │        └── reference ▶ [VPS boundary] ── VPS remains asset owner ─────────────┐
        │        ◀── asset references + provenance (VPS-owned) ───────────────────────────┘
        ▼
  [L5] Assembly & Review-Handoff ... compose Publish-Ready Production Package (PRPP)
        │                                   → MANDATORY MANUAL REVIEW GATE (P6)
        ▼ (approved only)
  [Publishing boundary] ............ one-directional handoff of approved PRPP
        │
        ▼
  FUTURE PUBLISHING SYSTEM (not defined here)

  cross-cutting: STATE & PROVENANCE records lineage at every step (owns lineage, not payloads)
```

**Canonical data artifacts (names are architectural roles, not schemas):**
- **CPI — Canonical Production Intent:** normalized inbound intent; Tool-Stack-authoritative.
- **Production Plan:** L2-derived ordering of steps; Tool-Stack-authoritative; carries execution
  *requests*, not authority.
- **Execution Results:** produced by the Runtime; **Runtime-owned**, referenced by the Tool Stack.
- **Asset References:** pointers + provenance to **VPS-owned** assets; never copies of ownership.
- **PRPP — Publish-Ready Production Package:** L5 composition of references/results; presented at
  the review gate; Tool-Stack-authoritative as a *composition*, not as owner of its constituents.
- **Provenance Record:** lineage/state metadata; owned by the Tool Stack's State & Provenance
  concern.

---

## 2. Production Input Model

- **Source:** governed production intent arrives at **L1** from upstream (per A2 §1).
- **Admission:** L1 validates and normalizes it into the **Canonical Production Intent (CPI)**.
- **Authority:** the CPI is the Tool Stack's SSoT for "what production was requested." It does
  **not** duplicate or re-own any Runtime- or VPS-owned data; where it references such data, it
  holds references only.
- **Neutrality:** the input model is **provider-agnostic** and **implementation-independent** —
  it prescribes no format, transport, schema, or provider (P3, P7).
- **Forbidden:** L1 does not originate intent, execute, render, or own assets.

---

## 3. Production Output Model

- **Primary output:** the **Publish-Ready Production Package (PRPP)** composed at **L5**.
- **Composition, not ownership:** the PRPP is a *composition* of Runtime-owned execution results
  (by reference) and VPS-owned asset references (by reference), plus Tool-Stack-authoritative
  coordination metadata. The PRPP never re-owns its constituents (SSoT preserved).
- **Gated:** the PRPP becomes an **output** only after passing the **mandatory manual review gate**
  (P6). Nothing is emitted downstream without human approval.
- **Handoff:** on approval, the PRPP is handed off one-directionally across the Publishing
  boundary; the Tool Stack never defines what Publishing does with it.
- **Forbidden:** the output model defines no rendering logic and no publishing behavior.

---

## 4. Data Transformation Stages

Transformations are **role-level**, describing *what changes hands or form* — never *how*.

| Stage | Layer | Input → Output | Authority / Ownership | Guardrails |
|-------|-------|----------------|-----------------------|------------|
| T1 Normalization | L1 | Inbound intent → CPI | Tool Stack authoritative (CPI) | No execution/rendering; references only for external data |
| T2 Planning | L2 | CPI → Production Plan (+ execution requests) | Tool Stack authoritative (Plan) | Requests execution; holds no execution authority (P1) |
| T3 Execution-by-request | L2 ↔ Runtime | Execution requests → Execution Results | **Runtime-owned** results (referenced) | No Runtime redesign; results consumed by reference |
| T4 Capability Routing | L3 | Plan/results → routed via abstract slots | Tool Stack (routing metadata) | Provider/renderer-agnostic; no provider named; no rendering logic |
| T5 Asset Coordination | L4 ↔ VPS | Routed needs → Asset References + provenance | **VPS-owned** assets (referenced) | No re-ownership or mutation of assets (P2) |
| T6 Assembly | L5 | Results refs + asset refs + metadata → PRPP | Tool Stack (composition only) | Composes references; does not re-own constituents |
| T7 Review Handoff | L5 ↔ Publishing | Approved PRPP → downstream handoff | Handoff seam only | Mandatory manual gate (P6); one-directional |

Across **all** stages, the **State & Provenance** concern records lineage (which artifact derived
from which, and by which reference) — it owns the *lineage*, never the *payloads*.

---

## 5. Data Ownership Matrix

Ownership strictly enforces **SSoT**, P1 (Runtime authority), and P2 (VPS ownership).

| Data Artifact | Authoritative Owner (SSoT) | Held by Tool Stack as | Never |
|---------------|----------------------------|-----------------------|-------|
| Canonical Production Intent (CPI) | **Production Tool Stack** | Authoritative original | Owned by Runtime/VPS |
| Production Plan | **Production Tool Stack** | Authoritative original | An execution authority |
| Execution Results | **Master Runtime** (Projects 2 & 3) | Reference / derived view | Re-owned or redefined by Tool Stack |
| Visual / Asset data | **Visual Production System** (Project 4) | Reference + provenance | Copied as a competing original |
| Asset provenance (source-of) | **VPS** (originating) | Referenced provenance | Rewritten by Tool Stack |
| PRPP (composition) | **Production Tool Stack** | Authoritative *composition* | Owner of its constituents |
| Provenance / lineage record | **Production Tool Stack** (State & Provenance) | Authoritative lineage | A payload owner |
| Published output | **Future Publishing System** | Not held (post-gate) | Defined by Tool Stack |

**Ownership rules:**
- OW1 — Exactly one authoritative owner per data category (SSoT).
- OW2 — Runtime-owned and VPS-owned data are always **referenced**, never re-originated (P1, P2).
- OW3 — The Tool Stack owns only coordination artifacts (CPI, Plan, PRPP composition, lineage).
- OW4 — Ownership is stable across the flow; transformations change *form/reference*, not *owner*.

---

## 6. Handoff Contract Model

Handoffs are **abstract contracts** at boundaries between owners (P7, P8). Each specifies
direction, what is transferred (value vs reference), and the invariant preserved.

| Handoff | Between | Direction | Transfers | Invariant |
|---------|---------|-----------|-----------|-----------|
| H1 Intake | Upstream → L1 | inbound | governed intent (value) → normalized to CPI | Intent not originated by Tool Stack |
| H2 Execution Request | L2 → Runtime | request-out | execution request (reference to Plan) | Runtime retains execution authority (P1) |
| H3 Execution Result | Runtime → L2 | result-in | execution results **by reference** | Results remain Runtime-owned (SSoT) |
| H4 Asset Reference | L4 ↔ VPS | reference | asset references + provenance | Assets remain VPS-owned (P2, SSoT) |
| H5 Assembly | L3/L4 → L5 | internal | references + metadata → PRPP | Composition only; no re-ownership |
| H6 Review Gate | L5 → Reviewer | gate | PRPP presented for approval | Mandatory human approval (P6) |
| H7 Publishing Handoff | L5 → Publishing | outbound, one-way | approved PRPP | No publishing internals defined (P8) |

**Handoff rules:**
- HC1 — Every handoff is one-directional with respect to authority; authority never transfers to
  the Tool Stack.
- HC2 — Cross-boundary handoffs transfer **references**, preserving SSoT (H3, H4, H7).
- HC3 — No handoff bypasses the review gate before publishing (H6 precedes H7).
- HC4 — Handoff contracts are abstract (no schema/format/API); they define shape and invariant
  only (P7).

---

## 7. Data Lifecycle Model

The lifecycle describes the **states a production data set passes through** — architectural
states, not storage or retention implementation (P7).

```
  RECEIVED ─▶ NORMALIZED(CPI) ─▶ PLANNED ─▶ EXECUTED(ref) ─▶ COORDINATED(ref)
                                                                    │
                                                                    ▼
                                                            ASSEMBLED(PRPP)
                                                                    │
                                                        ┌───────────┴───────────┐
                                                        ▼                       ▼
                                                  UNDER REVIEW ──rejected──▶ RETURNED
                                                        │                   (re-plan/revise)
                                                     approved
                                                        ▼
                                                  APPROVED ─▶ HANDED-OFF ─▶ (Publishing owns)
```

- **Provenance-tracked throughout:** each state transition is recorded by State & Provenance
  (lineage owned by the Tool Stack; payloads owned by their SSoT owners).
- **Rejection path:** a rejected review returns the data set to planning/revision — the gate is
  never bypassed (P6).
- **Reversibility (P9):** because Runtime/VPS data is referenced, lifecycle states can be revisited
  without duplicating or corrupting authoritative originals.
- **Termination:** the Tool Stack's responsibility ends at HANDED-OFF; the Publishing System owns
  everything beyond (P8). No retention/deletion implementation is defined here.

---

## 8. Runtime Interaction Flow

- **Nature:** request/consume. L2 issues **execution requests** across the Runtime boundary; the
  Runtime **governs and performs** execution and returns results.
- **Ownership:** execution results are **Runtime-owned** (SSoT); the Tool Stack holds them by
  reference (OW2, H3).
- **Direction:** Tool Stack → Runtime (request); Runtime → Tool Stack (result reference). The
  Runtime never depends on the Tool Stack.
- **Invariants:** Runtime authority preserved (P1); no Runtime redesign; execution never enters
  the Tool Stack's ownership.

## 9. VPS Interaction Flow

- **Nature:** reference/consume. L4 references **VPS-owned** assets with their provenance across
  the VPS boundary.
- **Ownership:** visual/asset data is **VPS-owned** (SSoT); the Tool Stack holds references +
  provenance only (OW2, H4).
- **Direction:** Tool Stack → VPS (reference request); VPS → Tool Stack (asset references +
  provenance). The VPS never depends on the Tool Stack.
- **Invariants:** VPS ownership preserved (P2); no VPS redesign; **no rendering logic** defined
  here; assets are never copied as competing originals.

## 10. External Tool Interaction Flow

- **Nature:** slot-mediated. External capability/renderer tools are reached **only** through the
  L3 abstract slots (A2 §2), never directly and never by name.
- **Provider-agnostic (P3) / renderer-agnostic (P4):** the flow treats each tool as a swappable
  occupant of a slot; the data flow is identical regardless of which tool occupies a slot.
- **Ownership:** tools produce **derived** data routed through the flow; authoritative ownership
  remains with the appropriate SSoT owner (Runtime for execution, VPS for assets, Tool Stack for
  coordination artifacts).
- **Invariants:** no provider selected, no rendering logic defined, no automation workflow; slots
  remain abstract (C2, C3, P7).

---

## 11. Data Flow Constraints

These constraints bind all subsequent Stage B modules:

- **DF1 — SSoT integrity:** exactly one authoritative owner per data category; all else is
  reference/derived.
- **DF2 — Runtime authority external:** execution results are Runtime-owned and referenced (P1).
- **DF3 — VPS ownership external:** asset data is VPS-owned and referenced (P2).
- **DF4 — Reference across boundaries:** cross-boundary handoffs transfer references, not
  re-owned originals (HC2).
- **DF5 — Mandatory review before output:** no data is emitted downstream without passing the
  manual gate (P6).
- **DF6 — Directional flow:** data flows downward through layers and outward to boundaries; no
  upward or cyclic authority transfer.
- **DF7 — Provider/renderer neutrality:** the flow is identical regardless of slot occupants
  (P3, P4); no provider named, no rendering logic.
- **DF8 — Implementation independence:** no schema, format, transport, storage, or retention
  implementation (P7).
- **DF9 — Provenance always recorded:** every transformation and handoff is lineage-tracked
  (State & Provenance owns lineage, not payloads).
- **DF10 — Roadmap fidelity & alignment:** consistent with A1–A3 and locked Projects 1–4 (P10).

---

## 12. Production Readiness Assessment

| Readiness Criterion | Status | Notes |
|---------------------|--------|-------|
| Data flow specification defined | ✅ Ready | §1; downward through L1–L5, gated output. |
| Data flow diagram provided | ✅ Ready | §1 and §7 lifecycle diagram. |
| Production input model defined | ✅ Ready | §2; CPI, provider-agnostic. |
| Production output model defined | ✅ Ready | §3; gated PRPP composition. |
| Transformation stages defined | ✅ Ready | §4; T1–T7, role-level only. |
| Handoff contract model defined | ✅ Ready | §6; H1–H7, HC1–HC4. |
| Data ownership matrix defined | ✅ Ready | §5; OW1–OW4, SSoT enforced. |
| Data lifecycle model defined | ✅ Ready | §7; states + rejection path. |
| Runtime interaction flow defined | ✅ Ready | §8; request/consume, results referenced. |
| VPS interaction flow defined | ✅ Ready | §9; reference/consume, assets referenced. |
| External tool interaction flow defined | ✅ Ready | §10; slot-mediated, provider-neutral. |
| Data flow constraints defined | ✅ Ready | §11; DF1–DF10. |
| Runtime authority preserved | ✅ Ready | P1; DF2. |
| VPS ownership preserved | ✅ Ready | P2; DF3. |
| Single Source of Truth preserved | ✅ Ready | DF1; ownership matrix. |
| Provider-agnostic | ✅ Ready | P3; DF7. |
| Implementation-independent | ✅ Ready | P7; DF8. |
| No implementation | ✅ Ready | Flow/ownership/contracts only. |
| No AI provider selected | ✅ Ready | Slot-mediated; none named. |
| No rendering logic defined | ✅ Ready | §9, §10; explicitly excluded. |
| No automation workflow defined | ✅ Ready | §10; DF7. |
| Supports future Stage B modules | ✅ Ready | Abstract, slot-based, boundary-preserving. |
| Aligns with A1–A3 and Projects 1–4 | ✅ Ready | Direct projection of A2; principles preserved. |

**Overall verdict:** ✅ **Production-ready (data-flow).** Module A4 defines a stable, SSoT-preserving,
provider-agnostic canonical data flow consistent with A1–A3, ready for the remainder of Stage A
and all future Stage B modules.

---

## 13. Internal Consistency Review (Self-Check)

Verified before finalizing:

- ✅ Contains **no** implementation (no code, schemas, formats, transports, storage, retention).
- ✅ Selects **no** AI provider, model, or renderer (external tools reached via abstract slots).
- ✅ Defines **no** rendering logic.
- ✅ Defines **no** automation workflow, trigger, or pipeline.
- ✅ Does **not** redesign the Master Runtime; execution results remain Runtime-owned by reference.
- ✅ Does **not** redesign the VPS; asset data remains VPS-owned by reference.
- ✅ Preserves **Single Source of Truth** (one authoritative owner per data category).
- ✅ Preserves provider-agnosticism and implementation-independence.
- ✅ Enforces the mandatory manual review gate before any downstream output (P6).
- ✅ Consistent with A1 (P1–P10), A2 (layers/C1–C10), A3 (repository), and locked Projects 1–4.
- ✅ Abstract and boundary-preserving enough to support all future Stage B modules.

Inconsistencies found: none. Document ready for commit on `feature/production-tool-stack`.
