# Production Queue & Retry System

**Project:** C-Cloning
**Project 5:** Production Tool Stack & Automation Workflow
**Stage:** B — Design Deepening
**Module:** B8 — Production Queue & Retry System
**Document Type:** Specification (Design — implementation-independent)
**Status:** Draft for review — specification-only, architecture-level
**Branch:** `feature/production-tool-stack`
**Depends on (locked):** Stage A — A1 · A2 · A3 · A4 · A5 · A6 · A7 · A8 · A9 · A10 · Stage B — B1 · B2 · B3 · B4 · B5 · B6 · B7

---

## 0. Preface — Nature and Boundaries of This Document

This document is the eighth **Stage B specification** module. It defines the **canonical
Production Queue & Retry System (PQRS)**: the architecture that governs how production work items
are **admitted, ordered, tracked, retried, and recovered** as they move through the pipelines
(B4/B5/B6), the translation engine (B3), and toward the manual review gate (B7) — all under
Runtime authority and without owning any asset or execution.

This module is a **specification/design deepening** of the locked Stage A architecture and B1–B7.
It adds detail *within* the existing architecture; it introduces no new architecture and **does
not redesign** B1–B7 — it consumes and coordinates them. It **consolidates** the per-pipeline
retry/recovery boundaries already defined in B4 (§7), B5 (§8), and B6 (§7) into one coherent,
system-level queue-and-retry discipline, without altering them.

Accordingly, this module deliberately does **not**:

- define queue technologies (no brokers, topics, streams, or products);
- define infrastructure (no servers, clusters, storage, or deployment topology);
- define scheduling algorithms (no priority math, fair-share, backoff formulas, or heuristics);
- define implementation generally (no code, schemas, transport, or execution logic).

The Runtime and VPS remain **fixed authorities** (Stage A); B1–B7 remain **fixed** (consumed
as-is). Execution is always **requested under Runtime authority** (P1); the queue coordinates *the
work of asking*, never the execution itself.

### Placement Within the Locked Architecture

The PQRS is a **cross-cutting coordination concern** operating primarily in **A2 L2
(Orchestration & Coordination)** with the cross-cutting **State & Provenance** concern (A2). It
holds **work items by reference** (each referencing a Production Plan step, A4), sequences their
progress through B3→B4/B5/B6→B7, and applies **bounded** retry/recovery — governed by **A8 policy
envelopes** (cost-risk, gate-before-spend). It never bypasses the **B7 manual review gate** (P6).

```
  Production Plan steps (A4, by ref) ─▶ [ PRODUCTION QUEUE & RETRY SYSTEM (B8 @ L2) ]
                                            admit · order · track · retry(bounded) · recover · contain
                                                 │  drives (by request/ref)
                                                 ├─▶ B3 translation ─▶ B4/B5/B6 pipelines ─▶ B7 review gate
                                                 └─▶ (execution requested under Runtime authority, A5)
```

### Inherited Foundations

| Source | What B8 inherits |
|--------|------------------|
| A1 | Principles P1–P10 (esp. P1 Runtime authority, P2 VPS ownership, P6 review gate, P9 reversibility). |
| A2 | L2 orchestration; State & Provenance cross-cutting; C1–C10. |
| A4 | Canonical flow; Production Plan; SSoT; references-not-ownership. |
| A5 | Execution requested under Runtime authority; failure boundaries. |
| A7 | Standards; acceptance criteria; traceability TR; governance EG. |
| A8 | Policy envelopes; slot-bounded resource use; cost-risk governance; escalation over silent breach (UP7). |
| B3 | Validated slot-shaped translations (work inputs). |
| B4/B5/B6 | Gate-guarded pipelines with per-pipeline bounded retry/recovery (consolidated here). |
| B7 | Mandatory manual review gate (never bypassed). |

---

## 1. Production Queue & Retry Specification (Overview)

Central premise, consistent with the whole roadmap:

> **The queue coordinates the ordering and resilience of production work; it never executes,
> owns, or optimizes.** Each queued item is a **reference** to production work (a Plan step and
> its state), not an asset and not an execution. Retry/recovery is **bounded and governed by
> policy** (A8), never an algorithm and never unbounded. The queue never fabricates results and
> never bypasses the review gate (P6).

The system is specified as: a **queue lifecycle** (§2), an **admission model** (§3), a
**prioritization model** (§4), a **retry & recovery architecture** (§5), a **failure containment
model** (§6), an **ownership model** (§7), an **extension strategy** (§8), and **architectural
constraints** (§9).

**Meta-rules:**
- **QR1 — Coordinate, don't execute/own:** the PQRS orders and tracks work references; it never
  executes, renders, or owns assets/results (P1, P2).
- **QR2 — Reference-only items:** queued items reference Plan steps and their state; no asset,
  result, or execution is stored in the queue (SSoT).
- **QR3 — Bounded, policy-governed retry:** retries are bounded by A8 policy envelopes; no
  unbounded/auto retry and no backoff/priority *algorithm* is defined (implementation-independent).
- **QR4 — Consolidates B4/B5/B6 retry, never redesigns it:** per-pipeline retry boundaries are
  honored as-is and coordinated at the system level.
- **QR5 — Gate-respecting:** the queue never bypasses the B7 review gate (P6).
- **QR6 — Implementation-independent:** the system constrains *states, roles, and invariants*, not
  realization — no queue tech, infra, or scheduling math (P7).

---

## 2. Queue Lifecycle Model

The lifecycle describes the **states of a queued work item** — architectural states, not queue
data structures, messages, or scheduler steps (QR6). Every transition is provenance-recorded (A2
State & Provenance, A7 TR).

```
  SUBMITTED ─▶ ADMITTED ─▶ READY ─▶ IN-PROGRESS ─▶ AWAITING-REVIEW(B7) ─▶ COMPLETED
      │           │          │           │                │                   
      │        (rejected) (deferred)  (fault)         (revision)              
      ▼           ▼          ▼           ▼                ▼                   
  INADMISSIBLE  DENIED   HELD        RETRY? ──bounded──▶ (READY) / ESCALATED / FAILED-CONTAINED
                                        │
                                        └─(exhausted, §5)─▶ FAILED-CONTAINED (no fabrication)
```

| State | Meaning | Authority/Ownership |
|-------|---------|---------------------|
| **Submitted** | A work reference (Plan step) is offered to the queue | Tool Stack (coordination) |
| **Admitted / Denied** | Admission decision applied (§3) | Tool Stack; policy-gated (A8) |
| **Ready** | Eligible to proceed; ordered by prioritization (§4) | Tool Stack |
| **In-Progress** | Work is being carried out downstream (B3→B4/B5/B6); execution requested under Runtime authority | **Runtime** governs execution (P1) |
| **Awaiting-Review** | Output handed to the B7 manual review gate | Human reviewer decides (P6) |
| **Completed** | Approved and released (B7) toward Publishing seam | Publishing owns beyond gate |
| **Retry? / Escalated / Failed-Contained** | Bounded retry, governed escalation, or contained failure (§5, §6) | Tool Stack; no fabrication (SSoT) |
| **Held / Deferred** | Temporarily not ready (policy/dependency) | Tool Stack |
| **Inadmissible** | Malformed/unauthorized submission rejected at intake | — |

**Lifecycle rules:**
- QL1 — States progress only forward or into explicit retry/hold/escalation/failure states; no
  silent skips.
- QL2 — Reaching **Completed** requires passing the **B7 review gate** (P6); the queue cannot
  complete a publish-bound item on its own (QR5).
- QL3 — Every item and transition is a **reference + provenance**; the queue holds no assets/results
  (QR2, SSoT).

---

## 3. Admission Model

Admission decides whether a submitted work reference enters the queue — a policy decision, not a
scheduling computation (QR3, QR6).

- **AD1 — Reference & authorization check:** admit only well-formed work references to valid Plan
  steps (A4) from authorized coordination; reject malformed/unauthorized (→ Inadmissible).
- **AD2 — Policy-envelope admission:** admission is bounded by A8 policy envelopes (e.g., a work
  class must be within its governance envelope); over-envelope submissions **escalate**, never
  silently admit (A8 UP7).
- **AD3 — Idempotent admission:** re-submitting an already-admitted reference does not create a
  duplicate; the queue references one canonical work item (SSoT).
- **AD4 — Admission confers no authority:** admitting an item grants no execution authority (P1)
  and no asset ownership (P2); it only enqueues a reference.
- **AD5 — Admission is provenance-recorded:** every admit/deny decision is recorded (A7 TR).
- **AD6 — No infrastructure assumptions:** admission references no broker, capacity, or
  deployment; it is a policy/boundary decision only (QR6).

## 4. Prioritization Model

Prioritization defines **ordering intent as policy**, never an algorithm, formula, or scheduler
(QR3, QR6).

- **PR1 — Ordering is declarative policy:** relative ordering of ready items is expressed as
  governance policy (ordering *intent*), not a computed priority score or scheduling algorithm.
- **PR2 — Governed classes, not magic numbers:** items may belong to declared ordering classes;
  class definitions are governed, provider-neutral, and carry no numeric weights here (A7/A8).
- **PR3 — Fairness is a policy property:** avoidance of starvation is stated as a policy intent
  (no item is indefinitely deferred without escalation), not a fair-share algorithm (QR6).
- **PR4 — Priority confers no authority:** ordering never grants execution authority or ownership;
  it only affects *when* a Ready item is offered downstream (P1, P2).
- **PR5 — Review gate is order-independent:** prioritization affects queue ordering only; it never
  reorders around or bypasses the B7 review gate (P6, QR5).
- **PR6 — Escalation over silent starvation:** items at risk of indefinite deferral escalate for a
  governed decision (A8 UP7), never silently dropped.

---

## 5. Retry & Recovery Architecture

Retry/recovery is **bounded, governed, and consolidating** — it unifies the per-pipeline
retry/recovery of B4 (§7), B5 (§8), and B6 (§7) at the system level, without redesigning them
(QR4).

- **RR1 — Bounded by policy, not algorithm:** the *number/extent* of retries is bounded by A8
  policy envelopes; **no backoff/scheduling formula** is defined here (QR3, QR6).
- **RR2 — Retry re-requests, never fabricates:** a retry re-issues the *request* (translation,
  generation, composition) under the same invariants; it never fabricates or synthesizes a result
  to appear successful (SSoT).
- **RR3 — Recovery favors substitution & rollback:** recovery prefers substituting a conforming
  slot occupant (B1) / adapter (B2) or safe rollback over irreversible commitment (P9), delegating
  to the owning pipeline's recovery rules (B4/B5/B6) unchanged.
- **RR4 — Runtime-governed re-execution:** any retried execution is again **requested under
  Runtime authority** (P1); the queue never self-executes a retry.
- **RR5 — Exhaustion is contained, not forced:** when bounded retries are exhausted, the item moves
  to **Failed-Contained** or **Escalated** — never force-completed or auto-approved (§6, P6).
- **RR6 — Idempotent, reference-safe retry:** because items are references (not owned results),
  retries are safe and do not corrupt authoritative originals (SSoT, P9).
- **RR7 — Retry is provenance-recorded:** every retry/recovery action and its outcome is recorded
  as lineage (A7 TR, A8 CR5).
- **RR8 — Gate-before-spend on retry:** cost-bearing retries respect A8 gate-before-spend; nothing
  publishing-bound spends before the B7 approval (A8, P6).

## 6. Failure Containment Model

Failures are **contained at the responsible boundary** and never propagate authority, corrupt
SSoT, or bypass the review gate (mirrors A5 §9, B4/B5/B6 failure boundaries):

| Failure | Contained at | Effect | Guardrail |
|---------|--------------|--------|-----------|
| Malformed/unauthorized submission | admission (AD1) | Inadmissible | Only valid references admitted |
| Over-envelope admission/retry | policy check (A8) | Escalated for governed decision | No silent over-use (A8 UP7) |
| Downstream pipeline fault (B4/B5/B6) | that pipeline's boundary | surfaced to queue; bounded retry/recover | Pipeline rules unchanged (QR4) |
| Execution fault (Runtime) | Runtime boundary | bounded re-request | Runtime governs; no self-execution (P1) |
| Retry exhaustion | queue | Failed-Contained / Escalated | No forced completion/approval (RR5, P6) |
| Starvation risk (ordering) | prioritization | Escalated | No indefinite silent deferral (PR6) |
| Attempt to bypass review gate | queue→B7 boundary | blocked | B7 gate mandatory (QR5, P6) |

**Containment rules:**
- FC1 — A failure is contained at its owning boundary; authority/ownership never transfers as a
  workaround.
- FC2 — The queue never fabricates, synthesizes, or force-completes work to mask a failure (SSoT).
- FC3 — Failures/escalations are provenance-recorded (RR7); recovery favors reversibility (P9).
- FC4 — No containment or recovery path bypasses the B7 manual review gate for publishing (P6).

---

## 7. Ownership Model

Ownership strictly mirrors Stage A SSoT and B1–B7 (A4, A5):

| Element | Owner (SSoT) | PQRS relation | Never |
|---------|--------------|---------------|-------|
| Execution results | **Master Runtime** | references | re-owns/executes (P1) |
| Generated/visual/audio/composed assets | **VPS** | references | re-owns/mutates (P2) |
| Production Plan / intent | **Production Tool Stack** (A4) | references Plan steps | mutates the Plan authoritatively |
| Queue state (work items, transitions) | **Production Tool Stack (PQRS)** | **owns** the queue record | owns assets/results |
| Retry/recovery lineage | **Production Tool Stack (PQRS)** | **owns lineage** | owns underlying result/asset |
| Ordering policy | **Production Tool Stack (governance)** | **owns** (declarative) | encodes an algorithm (QR3) |
| Review decision | **Human reviewer (B7)** | hands off to gate | auto-approves (P6) |

**Ownership rules:**
- OW1 — The PQRS owns only the **queue record, retry/recovery lineage, and (declarative) ordering
  policy** — never the assets, results, or the execution (SSoT).
- OW2 — One authoritative owner per element; the queue never transfers ownership.
- OW3 — Queued items are **references**; the queue never becomes a store of assets or results
  (QR2).

---

## 8. Extension Strategy

The system grows **by addition within the abstract model**, never by redesign (mirrors A2 §9 and
B-module extension strategies):

- **EX1 — New work class = new ordering-policy class:** additional work classes are added as
  declarative ordering classes (PR2), not new scheduling logic.
- **EX2 — New recovery strategy = additive & bounded:** additional bounded recovery strategies are
  added under RR1, delegating to owning pipelines unchanged (QR4).
- **EX3 — New lifecycle sub-state = additive:** additional hold/defer/escalation sub-states are
  added without removing existing invariants (QL1–QL3).
- **EX4 — No technology/infra specialization:** extension never introduces a queue product,
  infrastructure, or scheduling algorithm (QR6).
- **EX5 — Gate-preserving:** no extension may create a path that bypasses the B7 review gate or
  auto-approves (QR5, P6).
- **EX6 — Reversible & governed:** any extension is reversible (P9) and a governed, traceable
  change (A7 VC4/CM, A8 envelopes).

---

## 9. Architectural Constraints

Binding on this system and its consumers:

- **AC1 — No queue technologies:** no brokers, streams, topics, or products (QR6).
- **AC2 — No infrastructure:** no servers, clusters, storage, or deployment topology (QR6).
- **AC3 — No scheduling algorithms:** no priority math, backoff formulas, or fair-share
  algorithms; ordering is declarative policy (QR3, PR1).
- **AC4 — No implementation:** states/roles/invariants only; no code/transport/execution (P7).
- **AC5 — No redesign of B1–B7:** pipelines, gate, and their retry boundaries are consumed as-is
  (QR4).
- **AC6 — Runtime authority preserved:** execution/retry is requested; the Runtime governs it
  (P1, RR4).
- **AC7 — VPS ownership preserved:** the queue references VPS-owned assets; never re-owns (P2).
- **AC8 — SSoT preserved:** items are references; the queue owns only queue/lineage/ordering-policy
  metadata (QR2, OW1).
- **AC9 — Review gate mandatory:** the B7 manual review gate is never bypassed; no auto-approval
  or force-completion (P6, QR5, FC4).
- **AC10 — Bounded, governed, roadmap-faithful:** retries are bounded by A8 envelopes; escalation
  over silent breach; within the locked roadmap (A8, P8, P10).

---

## 10. Stage B Readiness Assessment (Readiness for B9)

| Readiness Criterion | Status | Notes |
|---------------------|--------|-------|
| Queue & retry specification defined | ✅ Ready | §1; coordinate-not-execute + QR1–QR6. |
| Purpose defined | ✅ Ready | §0–§1. |
| Queue lifecycle model defined | ✅ Ready | §2; states + QL1–QL3, provenance-tracked. |
| Admission model defined | ✅ Ready | §3; AD1–AD6, policy-gated. |
| Prioritization model defined | ✅ Ready | §4; PR1–PR6, declarative (no algorithm). |
| Retry & recovery architecture defined | ✅ Ready | §5; RR1–RR8, bounded & consolidating. |
| Failure containment model defined | ✅ Ready | §6; FC1–FC4. |
| Ownership model defined | ✅ Ready | §7; OW1–OW3, reference-only items. |
| Extension strategy defined | ✅ Ready | §8; EX1–EX6, additive. |
| Architectural constraints defined | ✅ Ready | §9; AC1–AC10. |
| No queue implementation | ✅ Ready | AC1. |
| No infrastructure implementation | ✅ Ready | AC2. |
| No scheduling algorithms | ✅ Ready | AC3, PR1. |
| No implementation | ✅ Ready | Specification only (AC4). |
| No redesign of B1–B7 | ✅ Ready | AC5; consolidates B4/B5/B6 retry as-is. |
| Runtime authority preserved | ✅ Ready | AC6, RR4. |
| VPS ownership preserved | ✅ Ready | AC7. |
| Single Source of Truth preserved | ✅ Ready | AC8, OW1–OW3. |
| Review gate mandatory | ✅ Ready | AC9; QL2, QR5, FC4. |
| Implementation-independent | ✅ Ready | QR6, AC4. |
| No Runtime/VPS redesign | ✅ Ready | Treated as fixed authorities. |
| Ready for B9 | ✅ Ready | Ordered, resilient, reference-only work coordination provides a stable surface for B9. |
| Aligns with Stage A (A1–A10), B1–B7 | ✅ Ready | Operates in L2; consolidates B4/B5/B6 retry; respects B7 gate. |

**Overall verdict:** ✅ **Queue-and-retry-ready.** Module B8 specifies a complete,
implementation-independent Production Queue & Retry System — reference-only items, policy-based
admission/ordering, bounded governed retry/recovery, contained failures, mandatory review gate —
consistent with Stage A and B1–B7, ready for B9.

---

## 11. Internal Consistency Review (Self-Check)

Verified before finalizing:

- ✅ Defines **no** queue technologies (no brokers, streams, or products).
- ✅ Defines **no** infrastructure (no servers, clusters, storage, or topology).
- ✅ Defines **no** scheduling algorithms (ordering is declarative policy; retries are bounded by
  policy, not formula).
- ✅ Contains **no** implementation (states/roles/invariants only).
- ✅ Does **not** redesign the Master Runtime, the VPS, or B1–B7 (all consumed as fixed;
  consolidates B4/B5/B6 retry without altering it).
- ✅ Preserves **Single Source of Truth**, Runtime authority (P1) — execution/retry requested,
  results Runtime-owned — and **VPS ownership (P2)** — assets referenced, never re-owned.
- ✅ Queued items are **references** only; the queue owns queue/lineage/ordering-policy metadata,
  never assets or results.
- ✅ The **B7 manual review gate is never bypassed**; no auto-approval or force-completion (P6).
- ✅ Retry/recovery is **bounded and governed by A8 policy**; escalation over silent breach; never
  fabricates results.
- ✅ Introduces **no new architecture** — operates in A2 L2 and consolidates B4/B5/B6 retry.
- ✅ Consistent with A1–A10, B1–B7, and locked Projects 1–4; provides a stable surface **ready for
  B9**.

Inconsistencies found: none requiring modification of a locked module. Document ready for commit
on `feature/production-tool-stack`.
