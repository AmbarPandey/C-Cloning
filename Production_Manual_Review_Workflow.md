# Manual Review Workflow

**Project:** C-Cloning
**Project 5:** Production Tool Stack & Automation Workflow
**Stage:** B — Design Deepening
**Module:** B7 — Manual Review Workflow
**Document Type:** Specification (Design — implementation-independent)
**Status:** Draft for review — specification-only, architecture-level
**Branch:** `feature/production-tool-stack`
**Depends on (locked):** Stage A — A1 · A2 · A3 · A4 · A5 · A6 · A7 · A8 · A9 · A10 · Stage B — B1 · B2 · B3 · B4 · B5 · B6

---

## 0. Preface — Nature and Boundaries of This Document

This document is the seventh **Stage B specification** module. It defines the **canonical Manual
Review Workflow (MRW)**: the architecture of the **mandatory human approval gate (P6)** that sits
at **A2 L5 (Assembly & Review-Handoff)** between a publish-ready production package and the future
Publishing System. It formalizes how a human reviewer approves, rejects, or requests revision of
composed, VPS-owned outputs before anything is handed off for publishing.

This module is a **specification/design deepening** of the locked Stage A architecture and B1–B6.
It adds detail *within* the existing architecture; it introduces no new architecture and **does
not redesign** B1–B6 — it consumes them. It **formalizes** the review gate that A1 (P6), A4 (PRPP
+ gate), A5 (review-gated handoff), and B4/B5/B6 (gate-guarded handoff to L5) have consistently
referenced.

Accordingly, this module deliberately does **not**:

- define UI implementation (no screens, layouts, components, or interaction design);
- define workflow software, tools, or products;
- define automation implementation (no schedulers, bots, or auto-approval logic);
- define implementation generally (no code, storage, transport, or execution logic).

The Runtime and VPS remain **fixed authorities** (Stage A); B1–B6 remain **fixed** (consumed
as-is). The human review decision is an **authority automation cannot assume** (A5 AU4, A7 RV8,
A8, A9 RGov4).

### Placement Within the Locked Architecture

The MRW is the design of the **L5 review gate**. It receives a **Publish-Ready Production Package
(PRPP)** — composed of VPS-owned asset references (B4 visual, B5 audio, B6 composed scene) and
coordination metadata (A4 §3) — presents it for human decision, and either releases it toward the
**future Publishing boundary** (A5 §7.3) on approval, or returns it for revision.

```
  PRPP (VPS-owned refs + metadata, A4) ─▶ [ MANUAL REVIEW WORKFLOW (B7 @ L5) ] ─▶ (APPROVED) ─▶ Publishing handoff seam (future)
                                              present · human decides ·                │
                                              feedback · audit · provenance             └─(REJECTED/REVISE)─▶ return to pipelines (B4/B5/B6)
```

### Inherited Foundations

| Source | What B7 inherits |
|--------|------------------|
| A1 | Principles P1–P10 (esp. **P6 mandatory manual review**, P7 impl-independence, P9 reversibility). |
| A2 | L5 Assembly & Review-Handoff; the review gate; C1–C10. |
| A4 | PRPP composition; SSoT; references-not-ownership; the mandatory review gate before output. |
| A5 | Review-gated, one-directional Publishing handoff; human approval is an authority not assumed by automation. |
| A7 | Standards; acceptance criteria; review process (RV1–RV8); traceability (TR1–TR6); governance (EG). |
| A8 | Gate-before-spend for publishing; cost-risk governance; provenance of decisions. |
| A9 | Readiness-gate/human-authority model (RGov4); milestone governance. |
| B4/B5/B6 | Gate-guarded handoff of VPS-owned (composed) asset references to L5. |

---

## 1. Manual Review Workflow Specification (Overview)

Central premise, consistent with the whole roadmap:

> **No production output is published without a deliberate human approval.** The MRW is the
> architectural embodiment of P6: it presents a publish-ready package for human judgment and
> **only a human Approve decision** may release it toward publishing. The workflow coordinates the
> decision, its feedback, and its audit trail; it never makes, automates, or bypasses the
> decision, and it never owns the assets under review.

The workflow is specified as: a **review lifecycle** (§2), an **approval gate model** (§3), a
**rejection & revision model** (§4), a **feedback integration model** (§5), an **ownership model**
(§6), an **audit & traceability model** (§7), an **extension strategy** (§8), and **architectural
constraints** (§9).

**Meta-rules:**
- **MR1 — Human-decided:** the Approve/Reject/Revise decision is always a human authority; never
  automated, defaulted, or inferred (P6).
- **MR2 — Mandatory & non-bypassable:** every publish-bound package passes the gate; there is no
  path around it (P6, A4).
- **MR3 — Review, don't own:** the MRW references VPS-owned assets under review; it never re-owns,
  mutates, or renders them (P2).
- **MR4 — Consumes B1–B6, never redesigns them:** it reviews their outputs (PRPP) as-is.
- **MR5 — Coordinate, don't automate:** the MRW coordinates presentation, decision capture,
  feedback, and audit — it defines **no** UI, workflow software, or automation.
- **MR6 — Implementation-independent:** the workflow constrains *states, roles, and invariants*,
  not realization (P7).

---

## 2. Review Lifecycle Model

The lifecycle describes the **states of a review** — architectural states, not UI screens or
workflow-tool steps (MR6). Every transition is provenance-recorded (§7).

```
  SUBMITTED(PRPP by ref) ─▶ UNDER-REVIEW ─▶ DECISION
        │                        │             ├─ APPROVED ─▶ RELEASED-TO-HANDOFF (Publishing seam)
        │                        │             ├─ REVISION-REQUESTED ─▶ RETURNED (to B4/B5/B6) ─▶ (re-submitted)
        │                        │             └─ REJECTED ─▶ CLOSED (not published)
        │                   (withdrawn / superseded)
        ▼                        ▼
   INADMISSIBLE            WITHDRAWN
   (malformed PRPP)        (superseded submission)
```

| State | Role | Authority/Ownership |
|-------|------|---------------------|
| **Submitted** | A publish-ready PRPP (VPS-owned refs + metadata) is submitted for review | VPS owns assets; Tool Stack references |
| **Under-Review** | A human reviewer examines the referenced package | Reviewer holds decision authority |
| **Decision** | The reviewer records **Approve / Revision-Requested / Reject** | Human authority only (MR1) |
| **Approved → Released-to-Handoff** | Approved package released toward the Publishing boundary | Handoff seam (A5); Publishing owns beyond gate |
| **Revision-Requested → Returned** | Feedback attached; package returned to originating pipeline(s) | Tool Stack coordinates; pipelines revise |
| **Rejected → Closed** | Package rejected; not published; recorded | Nothing released (P6) |
| **Inadmissible / Withdrawn** | Malformed PRPP rejected at intake / submission superseded | No review of ill-formed input |

**Lifecycle rules:**
- RL1 — A package reaches **Released-to-Handoff** *only* via an explicit human **Approve** (MR1,
  MR2).
- RL2 — No state auto-advances to approval; timeouts/inaction never approve (they may escalate,
  never approve).
- RL3 — All package data is referenced (VPS-owned); the review never mutates it (MR3, SSoT).

---

## 3. Approval Gate Model

The approval gate is the **single, mandatory, human-authoritative checkpoint** before publishing.

- **AG1 — One mandatory gate:** exactly one approval gate governs the transition from review to
  publishing handoff; it cannot be duplicated-away or bypassed (P6, MR2).
- **AG2 — Human authority only:** only a human Approve decision opens the gate; automation may
  present and record, never decide (MR1, A5 AU4, A9 RGov4).
- **AG3 — Explicit, positive approval:** the gate opens only on an explicit affirmative decision —
  never on default, silence, timeout, or inferred consent (RL2).
- **AG4 — Scoped approval:** an approval applies to the specific submitted package version
  (identified by reference/provenance); it does not blanket-approve future or altered packages.
- **AG5 — Gate-before-spend:** any cost-bearing publishing action occurs only after approval (A8
  gate-before-spend; CR2).
- **AG6 — Invariant confirmation at the gate:** approval implies a confirmation that P1/P2/SSoT are
  intact in the package (references valid, ownership correct) — the gate never launders a breach.
- **AG7 — One-directional release:** on approval, the package is released one-directionally to the
  Publishing handoff seam (A5 §7.3); the MRW defines no publishing internals.

## 4. Rejection & Revision Model

- **RV1 — Two negative outcomes:** a review may end in **Reject** (do not publish; close) or
  **Revision-Requested** (return for changes). Both are first-class, recorded outcomes.
- **RV2 — Revision returns to origin:** a revision request returns the package to its originating
  pipeline(s) — B4 (visual), B5 (audio), and/or B6 (composition) — by reference, with feedback
  attached (§5).
- **RV3 — No in-gate editing:** the MRW never edits assets to "fix" them; revision is performed by
  the owning pipelines under their own rules (MR3, no redesign of B1–B6).
- **RV4 — Re-submission is a new review:** a revised package is re-submitted as a new review
  (new version/provenance); approval never carries over from a prior version (AG4).
- **RV5 — Rejection is terminal for that package:** a rejected package is closed and never
  published; a new attempt is a new submission.
- **RV6 — Reversibility:** because packages are referenced (not re-owned), revision/rejection
  unwind cleanly without corrupting authoritative originals (P9).
- **RV7 — Escalation, not auto-resolution:** ambiguous or contested reviews escalate for a governed
  human decision; they are never auto-resolved (A8 UP7).

## 5. Feedback Integration Model

- **FI1 — Feedback is coordination metadata:** reviewer feedback is Tool-Stack-owned coordination
  metadata attached **by reference** to the reviewed package version — never an edit to the assets
  (MR3, SSoT).
- **FI2 — Feedback targets pipelines, not tools:** feedback is routed to the originating pipeline
  (B4/B5/B6), which decides how to revise via its slots/adapters — the MRW names no provider/tool
  and prescribes no change (B1 PA2).
- **FI3 — Feedback is provenance-linked:** each feedback item links source (reviewer, package
  version) to target (pipeline/asset reference) for traceability (§7, A7 TR).
- **FI4 — Feedback is advisory to revision, authoritative to the gate:** feedback guides pipeline
  revision (advisory) but the *decision* (approve/reject/revise) is authoritative and human (MR1).
- **FI5 — No feedback-driven automation:** feedback triggers no automated change; a human/pipeline
  acts on it under governance (MR5).
- **FI6 — Feedback neutrality:** feedback references assets and intent abstractly; it defines no UI,
  format, or provider specifics (MR6).

---

## 6. Ownership Model

Ownership strictly mirrors Stage A SSoT and B1–B6 (A4, A5):

| Element | Owner (SSoT) | MRW relation | Never |
|---------|--------------|--------------|-------|
| Assets under review (visual/audio/composed) | **VPS** | references + provenance | re-owns/mutates/renders (P2) |
| Composition/execution results | **Master Runtime** | references | re-owns/executes (P1) |
| PRPP composition | **Production Tool Stack** (A4) | references the composed package | re-owns constituents |
| Review record (states, decisions) | **Production Tool Stack (MRW)** | **owns** | owns the assets under review |
| Feedback metadata | **Production Tool Stack (MRW)** | **owns** (by reference) | edits assets |
| The decision authority | **Human reviewer** | records the human decision | assumed by automation (MR1) |
| Published output | **Future Publishing System** | not held (post-gate) | defined by the MRW |
| Provenance/lineage of the review | **Production Tool Stack (MRW)** | **owns lineage** | owns underlying assets |

**Ownership rules:**
- OW1 — The MRW owns only the **review record, feedback metadata, and review lineage** — never the
  assets, results, or the published output (SSoT).
- OW2 — One authoritative owner per element; the workflow never transfers ownership.
- OW3 — The **decision** is owned by the human reviewer; the workflow records but never makes it
  (MR1, P6).

---

## 7. Audit & Traceability Model

- **AT1 — Every decision is recorded:** each Approve/Reject/Revision-Requested outcome is recorded
  with reviewer identity (role), package version (by reference), and rationale (A7 RV6, TR4).
- **AT2 — Immutable decision record:** review records are append-only/immutable once made; changes
  are new records, never silent edits (A7 VC2, EG6).
- **AT3 — Bidirectional traceability:** a published (approved) package traces back to its review
  decision, feedback, and source pipelines; a review traces forward to its outcome and any
  resulting revision (A7 TR6).
- **AT4 — Provenance continuity:** the review lineage extends the production provenance chain (A4
  State & Provenance, A8 CR5) — the same lineage discipline used throughout the stack.
- **AT5 — Gate-decision auditability:** the mandatory gate's every opening is auditable, with the
  human authority attributable (AG2, A7 §10).
- **AT6 — No anonymous approval:** an approval is always attributable to a human authority; the
  system never records an approval without an accountable decider (MR1).

---

## 8. Extension Strategy

The workflow grows **by addition within the abstract model**, never by redesign (mirrors A2 §9 /
B-module extension strategies):

- **EX1 — New decision outcome = additive:** any additional review outcome is added additively,
  provided **Approve remains the sole path to release** (MR1, AG1) — no extension may create a
  non-human or bypass path.
- **EX2 — New reviewer role = additive:** additional human reviewer roles/authorities are added by
  governance (A7 EG), never automating the decision.
- **EX3 — New feedback category = additive:** feedback categories extend additively as coordination
  metadata (§5), never as asset edits.
- **EX4 — Multi-stage review = composition of gates:** if multiple human review stages are needed,
  they compose as additional mandatory human gates — none may be automated or skipped (AG1, MR2).
- **EX5 — No UI/workflow-software/automation specialization:** extension never introduces UI,
  workflow products, or automation (MR5).
- **EX6 — Reversible & governed:** any extension is reversible (P9) and a governed, traceable
  change (A7 VC4/CM).

---

## 9. Architectural Constraints

Binding on this workflow and its consumers:

- **AC1 — No UI implementation:** no screens, layouts, components, or interaction design (MR6).
- **AC2 — No workflow software:** no products, engines, or tools named or defined (MR5).
- **AC3 — No automation implementation:** no schedulers, bots, or auto-approval; the decision is
  human (MR1, MR5).
- **AC4 — No implementation:** states/roles/invariants only; no code/storage/transport (P7).
- **AC5 — No redesign of B1–B6:** their outputs (PRPP) are reviewed as-is (MR4).
- **AC6 — Runtime authority preserved:** the MRW performs no execution (P1).
- **AC7 — VPS ownership preserved:** assets under review are VPS-owned by reference; never
  re-owned/edited (P2, MR3).
- **AC8 — SSoT preserved:** one owner per element; review record/feedback are metadata by
  reference.
- **AC9 — Mandatory human gate:** the approval gate is non-bypassable and human-decided; no
  default/timeout/auto approval (P6, MR1, MR2, AG1–AG3).
- **AC10 — One-directional, governed handoff:** approval releases one-directionally to the
  Publishing seam; audit is immutable; within A8 envelopes and the locked roadmap (A5, P8, P10).

---

## 10. Stage B Readiness Assessment (Readiness for B8)

| Readiness Criterion | Status | Notes |
|---------------------|--------|-------|
| Manual review workflow specification defined | ✅ Ready | §1; human-decided, mandatory gate + MR1–MR6. |
| Purpose defined | ✅ Ready | §0–§1. |
| Review lifecycle model defined | ✅ Ready | §2; states + RL1–RL3, provenance-tracked. |
| Approval gate model defined | ✅ Ready | §3; AG1–AG7, human-only, non-bypassable. |
| Rejection & revision model defined | ✅ Ready | §4; RV1–RV7. |
| Feedback integration model defined | ✅ Ready | §5; FI1–FI6, feedback as metadata. |
| Ownership model defined | ✅ Ready | §6; OW1–OW3, decision human-owned. |
| Audit & traceability model defined | ✅ Ready | §7; AT1–AT6, immutable records. |
| Extension strategy defined | ✅ Ready | §8; EX1–EX6, Approve remains sole release path. |
| Architectural constraints defined | ✅ Ready | §9; AC1–AC10. |
| No UI implementation | ✅ Ready | AC1. |
| No workflow software | ✅ Ready | AC2. |
| No automation implementation | ✅ Ready | AC3, MR1. |
| No implementation | ✅ Ready | Specification only (AC4). |
| No redesign of B1–B6 | ✅ Ready | AC5; PRPP reviewed as-is. |
| Runtime authority preserved | ✅ Ready | AC6. |
| VPS ownership preserved | ✅ Ready | AC7, OW1. |
| Single Source of Truth preserved | ✅ Ready | AC8, OW2. |
| Mandatory human gate (P6) | ✅ Ready | AC9; AG1–AG3, RL1–RL2. |
| Implementation-independent | ✅ Ready | MR6, AC4. |
| No Runtime/VPS redesign | ✅ Ready | Treated as fixed authorities. |
| Ready for B8 | ✅ Ready | Approved, audited, VPS-owned package references released toward the Publishing seam provide a stable surface for B8. |
| Aligns with Stage A (A1–A10), B1–B6 | ✅ Ready | Formalizes the L5/P6 gate; consumes PRPP from B4/B5/B6. |

**Overall verdict:** ✅ **Review-workflow-ready.** Module B7 specifies a complete,
implementation-independent Manual Review Workflow — a mandatory, human-decided, non-bypassable
approval gate with feedback, revision, and immutable audit — consistent with Stage A and B1–B6,
ready for B8.

---

## 11. Internal Consistency Review (Self-Check)

Verified before finalizing:

- ✅ Defines **no** UI implementation (no screens, layouts, or components).
- ✅ Defines **no** workflow software, products, or engines.
- ✅ Defines **no** automation implementation; the Approve/Reject/Revise **decision is human**
  and never automated, defaulted, or inferred (P6).
- ✅ Contains **no** implementation (states/roles/invariants only).
- ✅ Does **not** redesign the Master Runtime, the VPS, or B1–B6 (all consumed as fixed).
- ✅ Preserves **Single Source of Truth**, Runtime authority (P1), and **VPS ownership (P2)**:
  assets under review are VPS-owned by reference, never re-owned or edited in the gate.
- ✅ The approval gate is **mandatory and non-bypassable**; only an explicit human Approve releases
  toward the one-directional Publishing handoff seam.
- ✅ Feedback is coordination metadata by reference; revision is performed by the owning pipelines,
  not by the MRW.
- ✅ Audit records are immutable and fully attributable; provenance extends the production lineage.
- ✅ Introduces **no new architecture** — formalizes the A2 L5 / P6 review gate and consumes B1–B6.
- ✅ Consistent with A1–A10, B1–B6, and locked Projects 1–4; provides a stable surface **ready for
  B8**.

Inconsistencies found: none requiring modification of a locked module. Document ready for commit
on `feature/production-tool-stack`.
