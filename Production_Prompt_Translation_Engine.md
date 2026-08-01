# Prompt Translation Engine

**Project:** C-Cloning
**Project 5:** Production Tool Stack & Automation Workflow
**Stage:** B — Design Deepening
**Module:** B3 — Prompt Translation Engine
**Document Type:** Specification (Design — implementation-independent)
**Status:** Draft for review — specification-only, provider-agnostic
**Branch:** `feature/production-tool-stack`
**Depends on (locked):** Stage A — A1 · A2 · A3 · A4 · A5 · A6 · A7 · A8 · A9 · A10 · Stage B — B1 · B2

---

## 0. Preface — Nature and Boundaries of This Document

This document is the third **Stage B specification** module. It defines the **canonical Prompt
Translation Engine (PTE)**: the abstract mechanism that translates a *provider-neutral production
intent expression* into the *shape a capability slot expects*, while preserving meaning — so that
the same intent can drive any occupant of a B1 slot (via a B2 adapter) without provider-specific
prompt formats leaking into the architecture.

This module is a **specification/design deepening** of the locked Stage A architecture, B1, and
B2. It adds detail *within* the existing architecture; it introduces no new architecture and
**does not redesign** the B1 abstraction layer or the B2 adapter framework (it consumes them).

Accordingly, this module deliberately does **not**:

- define provider-specific prompt formats, templates, syntaxes, or model-specific phrasings;
- define APIs (no endpoints, signatures, payload formats, or protocols);
- define authentication, credentials, secrets, or authorization mechanisms;
- define implementation logic (no code, schemas, parsers, storage, or execution logic).

The Runtime and VPS remain **fixed authorities** (Stage A); B1's slots/contracts and B2's
adapters/bindings remain **fixed** (this module conforms to them, never alters them).

### Placement Within the Locked Architecture

The PTE operates within **A2 L2 (Orchestration & Coordination)** as it prepares intent for
capability use, feeding the **B1 capability slots** (and, for rendering, **B2 adapters**). It
consumes the **Canonical Production Intent (CPI)** defined in **A4** and produces a
**slot-shaped translation** carried by reference through B1's contracts.

```
  CPI (A4, SSoT) ──▶ [ PROMPT TRANSLATION ENGINE (B3) ] ──▶ slot-shaped translation (by reference)
                         normalize · preserve meaning ·            │
                         validate · provenance-mark                 ▼
                                                            B1 capability slot  ──(render)──▶ B2 adapter
```

### Inherited Foundations

| Source | What B3 inherits |
|--------|------------------|
| A1 | Principles P1–P10 (esp. P3 provider-agnostic, P7 impl-independence, P9 reversibility). |
| A2 | L2 orchestration/coordination; L3 slots; C1–C10. |
| A4 | Canonical Production Intent (CPI); SSoT; references-not-ownership; derived-output semantics. |
| A5 | Slot-mediated external interaction; boundary/failure models. |
| A7 | Standards; acceptance criteria MA1–MA10; compliance AC1–AC8; traceability TR. |
| A8 | Slot-bounded resource use; policy envelopes. |
| B1 | Abstract capability slots; shape-only contracts (TC1–TC4); anonymous occupants. |
| B2 | Renderer adapters; conformance shapes; bindings. |

---

## 1. Prompt Translation Specification (Overview)

Central premise, consistent with the roadmap:

> **Intent is expressed once, provider-neutrally, and translated to slot shape — never authored
> per provider.** The PTE converts the provider-neutral CPI (or a portion of it) into the abstract
> *shape* a capability slot expects, **preserving semantic meaning** and recording provenance. It
> never emits a provider-specific prompt; it emits a slot-shaped, still-abstract translation that
> a B1 occupant (via a B2 adapter) can consume.

The engine is specified as: a **translation responsibility model** (§2), a **semantic preservation
model** (§3), a **prompt normalization model** (§4), a **translation contract model** as
shape+invariant only (§5), a **translation lifecycle** (§6), a **validation model** (§7), a
**failure boundary model** (§8), and an **extension strategy** (§9).

**Meta-rules:**
- **PT1 — Neutral-in, shape-out:** input is provider-neutral intent; output is slot *shape*, never
  a provider-specific prompt (PT is abstract).
- **PT2 — Meaning is invariant:** translation must preserve semantic meaning; it may reshape, never
  redefine, intent (§3).
- **PT3 — Consumes B1/B2, never redesigns them:** the PTE targets B1 slot shapes and B2 adapter
  conformance as-is (no abstraction/adapter redesign).
- **PT4 — Authority-respecting:** the PTE prepares intent; it never executes, renders, or owns
  Runtime/VPS data (P1, P2).
- **PT5 — Implementation-independent:** the engine constrains *shape and invariant*, not
  realization (P7).

---

## 2. Translation Responsibility Model

An engine's responsibilities are defined by what it **must uphold** and what it **must never do**.

| Responsibility | Description | Must NOT |
|----------------|-------------|----------|
| TR-1 Neutral intake | Accept provider-neutral intent by reference (from the CPI, A4) | Accept or require provider-specific prompt formats |
| TR-2 Normalization | Normalize intent into a canonical, provider-neutral internal form (§4) | Bind normalization to any provider/model |
| TR-3 Semantic preservation | Preserve the meaning of intent through translation (§3) | Add, drop, or alter intent semantics |
| TR-4 Slot-shape mapping | Map normalized intent to the abstract *shape* a target B1 slot expects | Emit a provider-specific prompt or API payload |
| TR-5 Validation | Validate translations against semantic and shape rules (§7) | Assume validity; skip validation |
| TR-6 Provenance marking | Mark translations with lineage (source intent → translation) | Emit unattributed translations (A7 TR) |
| TR-7 Failure signalling | Raise a non-result signal when meaning cannot be preserved/mapped | Emit a lossy or fabricated translation (SSoT) |

**Responsibility rules:**
- TRr1 — The PTE is a **preparation** step in L2 coordination; it performs no execution/rendering
  (PT4).
- TRr2 — Translation is **reference-carried**; the authoritative CPI is never mutated (SSoT, A4).
- TRr3 — Responsibilities preserve Runtime authority (P1) and VPS ownership (P2) throughout.

---

## 3. Semantic Preservation Model

Semantic preservation is the PTE's central invariant.

- **SP1 — Meaning-equivalence:** a translation must be **semantically equivalent** to the source
  intent — same intent, reshaped for a slot, never redefined (PT2).
- **SP2 — No semantic addition:** the PTE never introduces intent not present in the source
  (no embellishment, no assumptions).
- **SP3 — No semantic loss:** the PTE never silently drops intent; if a target slot cannot
  represent some intent, that is a validation failure (§7), not a silent omission.
- **SP4 — Provider-neutral semantics:** meaning is expressed in provider-neutral terms; no
  meaning is defined by reference to a provider's prompt conventions (P3).
- **SP5 — Reversible mapping:** the source→translation mapping is traceable and reversible enough
  to audit that meaning was preserved (P9, provenance).
- **SP6 — Ambiguity is surfaced, not resolved arbitrarily:** genuine ambiguity in intent is
  flagged for governed handling, never resolved by an implicit provider-specific default.

---

## 4. Prompt Normalization Model

Normalization produces a **canonical, provider-neutral internal form** of intent prior to
slot-shape mapping (abstract; no formats — PT1, PT5).

- **NM1 — Canonical neutral form:** intent is normalized into a single canonical, provider-neutral
  representation *shape* (described abstractly; no schema/syntax).
- **NM2 — Idempotent:** normalizing already-normalized intent yields the same canonical form.
- **NM3 — Separation of concerns:** normalization organizes intent by *what is meant*, independent
  of *which slot* will consume it or *which occupant* fills the slot.
- **NM4 — Neutral vocabulary:** normalization uses provider-neutral terms only; no provider/model
  tokens (P3, A7 NC).
- **NM5 — Normalization precedes mapping:** slot-shape mapping (TR-4) always operates on the
  normalized form, never on raw provider-specific input (which is out of scope anyway).
- **NM6 — Provenance-preserving:** normalization records lineage from source intent to canonical
  form (A7 TR).

---

## 5. Translation Contract Model

Contracts are expressed as **shape + invariant only** — explicitly **not APIs** and **not
provider-specific prompt formats** (PT1, PT5).

| Contract | Direction | Carries (shape) | Invariant preserved |
|----------|-----------|-----------------|---------------------|
| PC-1 Intent Intake | Coordinator (L2) → PTE | reference to provider-neutral intent (CPI portion) | CPI not mutated; SSoT (A4) |
| PC-2 Normalized Form | PTE (internal) | canonical neutral intent *shape* + provenance | Meaning-equivalent; provider-neutral (SP1, NM4) |
| PC-3 Slot-Shaped Translation | PTE → B1 slot (by reference) | translation matching the target slot's abstract shape | No provider prompt/API; meaning preserved (PT4, SP1) |
| PC-4 Validation Result | Validator → Coordinator | pass / needs-revision / cannot-preserve signal | No lossy/fabricated translation admitted (§7, SSoT) |
| PC-5 Non-Result Signal | PTE → Coordinator | signal that translation cannot preserve meaning/shape | Failure surfaced, not masked (§8) |

**Contract rules:**
- PCr1 — Contracts define *what shape crosses* and *what invariant holds*, never *how* (no API,
  auth, or provider prompt format).
- PCr2 — No contract names or implies a provider, model, or provider-specific prompt convention
  (P3, PT1).
- PCr3 — Intent and translations cross **by reference**; the authoritative CPI is never re-owned
  or mutated (SSoT, A4).
- PCr4 — PC-3 targets **B1 slot shapes** (and, for rendering, remains consumable via B2 adapters)
  as-is; it never redefines B1/B2 contracts (PT3).
- PCr5 — Every contract interaction is provenance-marked (TR-6, A7 TR).

---

## 6. Translation Lifecycle Model

The lifecycle describes the **states of a translation** — architectural states, not parsing,
templating, or execution implementation (PT5):

```
  INTENT-RECEIVED ─▶ NORMALIZED ─▶ MAPPED(to slot shape) ─▶ VALIDATED ─▶ EMITTED(by reference)
        │                │               │                     │              │
        │                │               │              (needs-revision)      │ (consumed by B1 slot)
        │                │               ▼                     ▼              ▼
        │                │        UNMAPPABLE            RETURNED (to L2    RELEASED
        │                │        (cannot shape)        coordination)     (provenance recorded)
        ▼                ▼
   REJECTED         (meaning cannot be preserved → non-result signal, §8)
```

- **Intent-received / Normalized:** provider-neutral intent is taken by reference and normalized
  (§4).
- **Mapped / Validated:** normalized intent is mapped to the target slot's abstract shape (TR-4)
  and validated for semantic preservation and shape conformance (§7).
- **Emitted / Released:** a valid slot-shaped translation is emitted **by reference** for a B1 slot
  to consume; provenance is recorded.
- **Unmappable / Returned / Rejected:** if meaning cannot be preserved or the shape cannot be
  produced, a non-result signal is raised (§8) and the item returns to L2 coordination — never a
  lossy emission. Reversibility (P9) allows safe retry/revision.

---

## 7. Validation Model

Validation guards the semantic-preservation invariant before any translation is emitted.

- **VM1 — Semantic-preservation check:** verify the translation is meaning-equivalent to the
  source intent (SP1–SP3).
- **VM2 — Shape-conformance check:** verify the translation matches the target B1 slot's abstract
  shape (PCr4) — a shape check, never an API/format check.
- **VM3 — Neutrality check:** verify no provider-specific prompt/format/token has entered the
  translation (PT1, NM4).
- **VM4 — Completeness check:** verify no source intent was silently dropped (SP3).
- **VM5 — Ambiguity check:** verify genuine ambiguities are surfaced for governed handling, not
  auto-resolved (SP6).
- **VM6 — Outcome:** validation yields **pass**, **needs-revision**, or **cannot-preserve**
  (PC-4); only **pass** may be emitted.
- **VM7 — Provenance of validation:** validation outcomes are recorded as lineage (A7 TR, A8 CR5).

## 8. Failure Boundary Model

Failures are **contained at the PTE boundary** — a translation failure never emits lossy output,
propagates authority, or corrupts SSoT (mirrors A5 §9 / B1 §7 / B2 §7):

| Failure | Contained at | Effect | Guardrail |
|---------|--------------|--------|-----------|
| Meaning cannot be preserved | PTE boundary | cannot-preserve → non-result signal (PC-5) | No lossy/fabricated translation (SP3, TR-7) |
| Target shape cannot be produced | mapping step | UNMAPPABLE; returned to L2 | No provider prompt improvised (PT1) |
| Provider token leaks into translation | neutrality check (VM3) | rejected as non-neutral | Provider-agnostic preserved (P3) |
| Genuine ambiguity in intent | ambiguity check (VM5) | surfaced for governed decision | No arbitrary default (SP6) |
| Out of policy envelope | policy check (A8) | escalated for governed decision | No silent over-use (A8 UP7) |
| Downstream slot/adapter fault | respective boundary (B1/B2) | surfaced by reference, not absorbed | B1/B2 remain authoritative |

**Failure rules:**
- FBt1 — A translation fault is contained at the PTE; authority/ownership never transfers as a
  workaround.
- FBt2 — The PTE never emits a lossy, embellished, or fabricated translation to mask failure
  (SSoT, semantic preservation).
- FBt3 — Failures are provenance-recorded (TR-6) and reversible (P9).
- FBt4 — No failure path bypasses the downstream manual review gate for publishing (P6).

---

## 9. Extension Strategy

The engine grows **by addition within the abstract model**, never by redesign (mirrors A2 §9 /
B1 §8 / B2 §8):

- **EXt1 — New target slot shape = new mapping:** support for a new B1 slot shape is added as a new
  slot-shape mapping (TR-4); normalization and semantics are unaffected (NM3).
- **EXt2 — New intent category = extend normalization:** genuinely new intent categories extend the
  canonical neutral form additively (NM1), never overloading existing meaning.
- **EXt3 — No provider specialization:** extension never adds a provider-specific prompt path;
  provider differences are absorbed behind B1 slots / B2 adapters, not in the PTE (PT1).
- **EXt4 — Reversible:** any mapping or normalization extension can be retired without cascading
  redesign (P9).
- **EXt5 — Meaning-preserving growth:** every extension upholds semantic preservation (§3).
- **EXt6 — Governed:** mapping/normalization changes are governed, traceable (A7 VC4/CM, A8).

---

## 10. Architectural Constraints

Binding on this engine and its consumers:

- **ACt1 — No provider-specific prompt formats:** no templates, syntaxes, or model phrasings
  (PT1, VM3).
- **ACt2 — No APIs / no auth:** contracts are shape+invariant only (§5, PCr1).
- **ACt3 — No implementation logic:** the PTE specifies shape/invariant; no parsers, code, or
  execution logic (P7).
- **ACt4 — No abstraction/adapter redesign:** B1 and B2 are consumed unchanged (PT3, PCr4).
- **ACt5 — Runtime authority preserved:** the PTE prepares intent; execution stays with the
  Runtime (P1).
- **ACt6 — VPS ownership preserved:** no asset is created/owned by the PTE (P2).
- **ACt7 — SSoT preserved:** CPI is authoritative and never mutated; translations carried by
  reference.
- **ACt8 — Provider-agnostic:** neutral-in, shape-out by construction (P3).
- **ACt9 — Implementation-independent:** shape/invariant only (P7).
- **ACt10 — Boundary & policy fidelity:** targets B1/B2 via their boundaries; stays within A8
  envelopes and the locked roadmap (P8, P10).

---

## 11. Stage B Readiness Assessment (Readiness for B4)

| Readiness Criterion | Status | Notes |
|---------------------|--------|-------|
| Prompt translation specification defined | ✅ Ready | §1; neutral-in/shape-out + PT1–PT5. |
| Purpose defined | ✅ Ready | §0–§1. |
| Translation responsibility model defined | ✅ Ready | §2; TR-1..TR-7. |
| Semantic preservation model defined | ✅ Ready | §3; SP1–SP6. |
| Prompt normalization model defined | ✅ Ready | §4; NM1–NM6. |
| Translation contract model defined | ✅ Ready | §5; PC-1..PC-5 (no APIs, no provider formats). |
| Lifecycle model defined | ✅ Ready | §6; states + provenance + reversibility. |
| Validation model defined | ✅ Ready | §7; VM1–VM7. |
| Failure boundary model defined | ✅ Ready | §8; FBt1–FBt4. |
| Extension strategy defined | ✅ Ready | §9; EXt1–EXt6, additive. |
| Architectural constraints defined | ✅ Ready | §10; ACt1–ACt10. |
| No provider-specific prompt formats | ✅ Ready | PT1, VM3, ACt1. |
| No implementation | ✅ Ready | Specification only. |
| No APIs / auth | ✅ Ready | §5, ACt2. |
| No abstraction (B1) / adapter (B2) redesign | ✅ Ready | PT3, PCr4, ACt4. |
| Runtime authority preserved | ✅ Ready | ACt5. |
| VPS ownership preserved | ✅ Ready | ACt6. |
| Single Source of Truth preserved | ✅ Ready | TRr2, ACt7. |
| Provider-agnostic | ✅ Ready | PT1, ACt8. |
| Implementation-independent | ✅ Ready | PT5, ACt3. |
| No Runtime/VPS redesign | ✅ Ready | Treated as fixed authorities. |
| Ready for B4 | ✅ Ready | Validated, slot-shaped, meaning-preserving translations provide a stable surface for B4. |
| Aligns with Stage A (A1–A10), B1, B2 | ✅ Ready | Operates in L2; consumes CPI (A4), B1 slots, B2 adapters. |

**Overall verdict:** ✅ **Translation-engine-ready.** Module B3 specifies a complete,
provider-agnostic, implementation-independent Prompt Translation Engine — neutral-in/shape-out,
meaning-preserving, validated, with shape-only contracts and no provider prompt formats/APIs —
consistent with Stage A, B1, and B2, ready for B4.

---

## 12. Internal Consistency Review (Self-Check)

Verified before finalizing:

- ✅ Defines **no** provider-specific prompt formats, templates, syntaxes, or model phrasings.
- ✅ Defines **no** APIs, authentication, or credentials.
- ✅ Contains **no** implementation logic (shape/invariant only; no parsers/code/execution).
- ✅ Does **not** redesign the Master Runtime, the VPS, the B1 abstraction layer, or the B2 adapter
  framework (all consumed as fixed).
- ✅ Preserves **Single Source of Truth** (CPI authoritative, never mutated; translations by
  reference), Runtime authority (P1), and VPS ownership (P2).
- ✅ Preserves **semantic meaning** as the central invariant (no addition, no loss, no arbitrary
  resolution of ambiguity).
- ✅ Provider-agnostic (neutral-in/shape-out) and implementation-independent throughout.
- ✅ Introduces **no new architecture** — operates in A2 L2 and consumes CPI (A4), B1 slots, and
  B2 adapters.
- ✅ Consistent with A1–A10, B1, B2, and locked Projects 1–4; provides a stable surface **ready
  for B4**.

Inconsistencies found: none requiring modification of a locked module. Document ready for commit
on `feature/production-tool-stack`.
