# Visual Production System (VPS)

## Stage A — Module A7: Engineering Standards

> **Document type:** Architecture governance (standards only)
> **Project:** Visual Production System (VPS)
> **Roadmap position:** Stage A · Module A7 — follows locked *A1–A6*; the governance layer every Stage B module must obey
> **Depends on / inherits:** `VPS_Vision_and_Philosophy.md` (A1), `VPS_System_Architecture.md` (A2), `VPS_Repository_Structure.md` (A3), `VPS_Data_Flow_Architecture.md` (A4), `VPS_Runtime_Integration_Architecture.md` (A5), `VPS_Module_Overview.md` (A6)
> **Status:** Proposed — the binding engineering standards for Stage B
> **Scope discipline:** This document defines **the rules every Stage B module must follow** — naming, identifiers, metadata principles, contracts, compatibility, versioning, validation, governance, change management, error classification, and deprecation. It **defines no assets** and **implements no module behavior.** It introduces **no implementation details** (no engines, models, formats, file syntaxes, schemas-as-code, or tools). Standards are stated as *principles and rules*, applicable uniformly regardless of how any module is later implemented.

---

## 0. Purpose of This Document

A1–A6 defined the constitution, the four layers, the repository layout, the data flow, the Runtime seam, and the Stage B module map. A7 defines the **engineering standards** that make those modules *consistent with one another* — so ten modules built by different hands at different times behave as one coherent system.

A7 is **governance, not construction.** It is the rulebook a Stage B module is measured against before it can be considered complete. If a Stage B design cannot satisfy these standards, either the design is wrong or A7 must be formally amended first (§13).

Every standard applies the locked disciplines: **single source of truth**, **determinism**, **four-layer fidelity**, **Runtime-driven / contract-based**, **implementation-independence**, and **minimize future redesign**.

---

## 1. Naming Conventions

Naming exists to make **ownership, layer, and intent** unambiguous at a glance and stable over time.

- **N-1 · Layer-evident names.** A module's name and location must reveal its home layer (A2/A3). No name may imply a responsibility that belongs to another layer.
- **N-2 · Responsibility-true names.** A name reflects the module's single responsibility (A6). Names must not overstate or borrow another module's concern.
- **N-3 · One casing rule per artifact class.** Directories use lower-case `kebab-case`; conceptual entities use a single, consistent casing per class, applied uniformly across all modules (no per-module dialects).
- **N-4 · Singular vs. plural.** Singular for a concept-owner; plural for a collection of like items (consistent with A3 §5).
- **N-5 · No abbreviations that hide ownership**, and **no name reused across two owners** (prevents accidental dual ownership; A3).
- **N-6 · Renderer/model neutrality.** Names must never encode a specific renderer, engine, model, or vendor (A1/A2 agnosticism).
- **N-7 · Stability over cleverness.** Names are chosen to remain valid as the system grows; renaming is a governed change (§10).

---

## 2. Asset Identifier Standard

Identifiers are the backbone of single source of truth and determinism — everything references by **identity**, not by location or content.

- **ID-1 · Stable and immutable.** An asset identity, once assigned, never changes and is never reused for a different asset. Reorganizing storage must not change identities (A3 §5).
- **ID-2 · Globally unique within the VPS.** Every asset identity is unique across all kinds and modules; no two modules may mint colliding identities.
- **ID-3 · Kind-attributable.** An identity makes its owning asset-kind/module unambiguous, so ownership is resolvable from the identity alone (supports A6 disjoint ownership).
- **ID-4 · Opaque to consumers.** Consumers treat identities as opaque references; they must not parse identities to infer content, embed business meaning, or bypass the owning module.
- **ID-5 · Identity ≠ version.** Identity denotes *which asset*; version denotes *which revision* (§6). The two are distinct fields and never conflated (A4 §10, A5 §10).
- **ID-6 · Reference-only across boundaries.** Data crossing any layer or the Runtime seam carries identities (references), never copies of definitions (A4 §12, A5 §5).
- **ID-7 · Deterministic resolution.** An identity resolves to the same canonical definition given the same repository/version state (A4 determinism).

---

## 3. Metadata Schema Principles

Metadata describes assets; it is **owned solely by the Knowledge Layer** (A2/A6 B8) and always references assets by identity.

- **MD-1 · Single owner.** Metadata, relationships, and compatibility are owned by the Knowledge Layer only; asset-kind modules never store metadata about themselves elsewhere (SSOT).
- **MD-2 · Reference, never duplicate.** Metadata records point to asset identities; they never embed a copy of an asset definition.
- **MD-3 · Separation of concerns.** Descriptive metadata (what/relations/compatibility) is kept distinct from the asset definition (the thing itself) and from selection/assembly decisions (Composition).
- **MD-4 · Additive, versioned dimensions.** New metadata dimensions are added additively behind versioned contracts (A6 §8); existing consumers are never broken.
- **MD-5 · Deterministic and explainable.** Metadata queries return the same facts for the same state; every fact is attributable to a governed record (A1 §13).
- **MD-6 · Implementation-independent shape.** Metadata is specified as *principles* here (ownership, reference, separation); concrete shapes are Stage B and must conform, not contradict.

---

## 4. Documentation Standards

Documentation is part of the deliverable, not an afterthought; it makes the system self-describing (A1 maintainability).

- **DOC-1 · Every module is self-documented.** Each Stage B module documents its purpose, scope, single responsibility, inputs, outputs, ownership, dependencies, integration points, constraints, and expansion strategy — the A6 ten-field envelope.
- **DOC-2 · In-place ownership statement.** Each hierarchy carries an ownership/README note stating its owner (layer or governance) and its rules (A3 §9).
- **DOC-3 · Traceability to architecture.** Module docs cite the A1–A6 principles they satisfy; a decision with no architectural basis is a defect.
- **DOC-4 · Locked-decision discipline.** Only final, governed decisions are documented as authoritative; superseded options are recorded as history, not as current truth (mirrors the platform decision-log discipline).
- **DOC-5 · Consistent structure.** All module docs follow the same section structure so any module is navigable by anyone.
- **DOC-6 · No implementation leakage in architecture docs.** Architecture/governance docs describe rules and envelopes; implementation notes live with the implementation.

---

## 5. Contract Standards

All cross-boundary communication is contract-based (A2, A5); contracts are the only integration surface.

- **CT-1 · Contract-first.** A module's interface (contract) is defined and versioned before its internals. Consumers depend on contracts, never internals.
- **CT-2 · Versioned and explicit.** Every contract declares an explicit version and lives in `vps/contracts/` (A3). No implicit or undocumented interface is permitted.
- **CT-3 · Directional and acyclic.** Contracts respect the A2 downward direction and the A6 dependency DAG; a contract must not create a cycle.
- **CT-4 · Reference-bearing.** Contracts carry identities, references, and immutable payloads — never mutable shared state and never copies that create a second owner (SSOT).
- **CT-5 · Renderer/model-agnostic.** No contract encodes renderer or model specifics; those are configuration references (A5 §4).
- **CT-6 · Backward-compatible evolution.** Contracts evolve additively; breaking changes require a new version and a governed deprecation (§12).
- **CT-7 · Repository-driven & deterministic.** Because contracts are repository-resident, the Runtime can drive modules deterministically from the repository (A5).

---

## 6. Compatibility Standard

Compatibility is a **Knowledge-Layer-owned** concept (A6 B8) that governs which assets may be combined and which contract/versions interoperate.

- **CP-1 · Compatibility is declared, not inferred.** Whether two asset identities may be combined is a governed relationship owned by the Relationship Graph; no module invents compatibility to satisfy a request (A4 FB-2).
- **CP-2 · Checked at defined gates.** Compatibility is enforced at the A4 checkpoints (V3) by Asset Validation (B10); violations block advancement (fail loud).
- **CP-3 · Contract compatibility is explicit.** Interacting parties agree on contract versions (§5, A5 §10); mismatches are detected, not silently coerced.
- **CP-4 · No cross-kind ownership leakage.** An asset-kind module never encodes compatibility with another kind inside its own definitions; that link is a Knowledge relationship (A6 overlap guard).
- **CP-5 · Deterministic outcome.** The same selection against the same compatibility state yields the same compatibility verdict.

---

## 7. Versioning Standard

Two distinct version concerns must never be conflated (A5 §10).

- **VER-1 · Content versioning.** Asset/definition versions denote revisions of a thing; **authority lives solely in the Knowledge Layer version registry** (`knowledge/versions/`, A3 §6). No downstream layer re-derives it.
- **VER-2 · Contract versioning.** Contracts are semantically versioned; integration parties negotiate on version (§5, A5 §10).
- **VER-3 · Immutability per version.** A change produces a new version; existing versions are never mutated — enabling deterministic reproduction (A4 §10).
- **VER-4 · Self-describing packages.** The immutable production package embeds the exact resolved version set it was built from (A4 §10, A6 B9).
- **VER-5 · Additive & backward-compatible by default.** Both content and contract evolution favor additive change; breaking change is a governed, versioned, deprecated transition (§12).
- **VER-6 · Append-only history.** Structural/version history is recorded append-only for audit (`versioning/changelog/`, A3 §6).

---

## 8. Validation Requirements

Validation makes the standards **enforceable**, not merely aspirational; it is owned by Asset Validation (A6 B10) as flow gates (A4 V1–V6).

- **VAL-1 · Every invariant has a gate.** Structural correctness, single-source-of-truth/ownership, and compatibility each map to a checkpoint that blocks on violation.
- **VAL-2 · Fail loud, fail attributable.** A failed check stops the flow and reports layer + checkpoint + request identity (A4 §9); it never degrades into a silent, non-deterministic success.
- **VAL-3 · No-duplicate-ownership check is continuous.** The SSOT/ownership gate (A4 V6) runs across all transitions; a datum with two owners fails the build.
- **VAL-4 · Deterministic checks.** The same inputs yield the same verdict; validation adds no non-determinism.
- **VAL-5 · Automatable.** All checks are automatable and repository-checkable, supporting future unattended execution (A1/A3/A5).
- **VAL-6 · Gate, not owner.** Validation reads by reference and issues verdicts; it never mutates or owns the data it checks, so it introduces no dependency cycle (A6 B10).

---

## 9. Repository Governance

Governance keeps the repository the trustworthy system of record (A3 §9).

- **GOV-1 · One home, one owner.** Every concept has exactly one home hierarchy and one owner (layer or governance); the layout physically prevents duplication (A3).
- **GOV-2 · Layer-to-hierarchy fidelity.** Each layer owns exactly one hierarchy; cross-cutting concerns (contracts, config, validation, versioning, docs) are governance-owned, never layer-owned.
- **GOV-3 · Additive by default.** New directories/modules follow the A6/A3 additive rules; removing or relocating a top-level hierarchy or changing top-level ownership requires a governed amendment (§10).
- **GOV-4 · Repository-driven execution.** Everything required to run is describable from the repository (A5), enabling deterministic, Runtime-driven execution.
- **GOV-5 · Alignment gate.** Any change must remain consistent with A1–A7; inconsistency blocks the change.
- **GOV-6 · Enforced, not trusted.** Governance rules that can be automated (naming, ownership, contract conformance, versioning) are enforced via `vps/validation/`.

---

## 10. Change Management

Changes are **deliberate, traceable, and reversible in intent** — never silent drift.

- **CM-1 · Additive-first.** Prefer additive change (new module/subtree/contract version) over modifying shared surfaces (A6 §8).
- **CM-2 · Contract-versioned change.** Any change to a cross-boundary surface goes through a contract version bump (§5/§7); consumers migrate on their own timeline.
- **CM-3 · Amend-the-constitution discipline.** Changing a locked principle (A1–A7) is a conscious, recorded amendment, not an incidental edit.
- **CM-4 · Single-file, single-concern commits.** Each governed document/module change is committed on its own, with a message tracing it to the architecture it serves (matches the Stage A commit discipline).
- **CM-5 · Append-only audit.** Structural/version changes are recorded append-only (`versioning/changelog/`, A3).
- **CM-6 · No unreviewed breaking change.** Breaking changes require an explicit deprecation path (§12) and governed review before adoption.

---

## 11. Error Classification

A uniform error taxonomy makes failures explainable and lets the Runtime respond consistently (A4 §9, A5 §9).

| Class | Meaning | Origin (typical) | Reporting |
|-------|---------|------------------|-----------|
| **E1 · Input/Contract error** | Malformed or contract-incompatible request | A4 V1 / A5 invocation | Attributable failure to Runtime |
| **E2 · Resolution error** | An asset identity cannot be resolved | A4 V2 / Asset Layer | Attributable failure to Runtime |
| **E3 · Compatibility/Version error** | Unsatisfiable selection, incompatible pair, or version conflict | A4 V3 / Knowledge | Attributable failure to Runtime |
| **E4 · Composition/Seal error** | A complete, deterministic package cannot be assembled/sealed | A4 V4 / Composition | Attributable failure to Runtime |
| **E5 · Renderer/Adapter error** | A specific renderer/adapter fails | A4 V5 / Production | **Renderer-scoped**, isolated; reported per-renderer |
| **E6 · Governance/Ownership error** | SSOT/ownership or governance invariant violated | A4 V6 / cross-cutting | Build/flow blocked; attributable |

- **EC-1 · Every error carries** layer, checkpoint, request identity, and cause (never remediation — the Runtime decides response).
- **EC-2 · No reclassification to succeed.** A module must not downgrade an error into a silent success (fail loud).
- **EC-3 · Isolation preserved.** E5 stays renderer-scoped and never corrupts the immutable package or other adapters (A2 FB-4).

---

## 12. Deprecation Policy

Deprecation is how the system evolves without breaking consumers (A1 long-term evolution).

- **DEP-1 · Deprecate, don't delete abruptly.** A superseded contract/version/module is marked deprecated with a defined successor before removal.
- **DEP-2 · Overlap window.** Deprecated and successor versions coexist for a governed window so consumers migrate on their own timeline (A5 §10 independence).
- **DEP-3 · Additive successor.** The successor is introduced additively; the deprecation does not force a lockstep, system-wide change.
- **DEP-4 · Recorded.** Deprecations and removals are recorded append-only (`versioning/changelog/`), preserving reproducibility of past productions (immutable versions, VER-3).
- **DEP-5 · Governed removal.** Final removal occurs only after the window closes and dependents have migrated, via a governed change (§10).
- **DEP-6 · No orphaned references.** Removal is blocked while any governed reference to the deprecated item remains (enforced by validation).

---

## 13. Governance Rules (How A7 Itself Is Applied)

- **APP-1 · Uniform application.** These standards apply **identically to all ten Stage B modules** (B1–B10) and to any future module; no module is exempt.
- **APP-2 · Completion gate.** A Stage B module is "done" only when it satisfies every applicable standard here; conformance is part of its definition of done.
- **APP-3 · Enforced via validation.** Automatable standards are enforced by `vps/validation/`; non-automatable ones are enforced by governed review (§9 GOV-6).
- **APP-4 · A7 is amendable, not bypassable.** A standard may be changed only by amending A7 (CM-3); it may never be silently ignored by a module.
- **APP-5 · Precedence.** Where a module design conflicts with A7, A7 prevails until formally amended.

---

## 14. Engineering Readiness Assessment

| Dimension | Question | Assessment |
|-----------|----------|------------|
| **Uniformity** | Do standards apply uniformly to every Stage B module? | **Yes** — §13 binds B1–B10 and all future modules identically. |
| **Implementation neutrality** | Any implementation details introduced? | **No** — principles/rules only; no engines, models, formats, schemas-as-code, or tools; no assets or behavior. |
| **A1 alignment** | Asset-first, deterministic, evolve-by-extension? | **Yes** — identity/reference rules, deterministic checks, additive/deprecation policies. |
| **A2 alignment** | Four-layer fidelity + acyclic + single owner? | **Yes** — naming/governance enforce layer homes; contract rules keep dependencies acyclic. |
| **A3 alignment** | Uses layout homes for contracts/config/validation/versioning? | **Yes** — standards cite the exact A3 hierarchies. |
| **A4 alignment** | Honors flow, checkpoints, version flow, error flow? | **Yes** — validation and error classes map to V1–V6; version authority in Knowledge. |
| **A5 alignment** | Preserves the single contract seam + Runtime authority? | **Yes** — contract-first, versioned, reference-bearing, Runtime decides response. |
| **A6 alignment** | Preserves module map ownership/overlap rules? | **Yes** — SSOT, disjoint ownership, and gate-not-owner validation are enforced. |
| **Redesign risk** | Is future redesign minimized? | **Yes** — additive-first, versioned contracts, governed deprecation, amend-not-bypass. |

**Readiness verdict:** **READY.** The engineering standards are complete, uniform, implementation-independent, and aligned with A1–A6. Stage B modules may be designed and built against these standards without governance gaps.

---

## 15. Internal Quality Review (self-check performed before finalization)

- ✅ **Standards apply uniformly to every Stage B module.** Verified — §13 explicitly binds all of B1–B10 and any future module identically, with conformance as the definition of done.
- ✅ **No implementation details introduced.** Verified — every standard is stated as a principle/rule; no engine, model, file syntax, schema-as-code, or tool appears, and no assets or behavior are defined.
- ✅ **Aligns with A1–A6.** Verified — the readiness matrix (§14) traces each standard family to the constitution, layers, repository layout, data flow, Runtime seam, and module map.
- ✅ **Future expansion remains governed by these standards.** Verified — change management (§10), deprecation (§12), and governance (§9, §13) require every future change to be additive-first, contract-versioned, recorded, and A7-conformant or an explicit amendment.
- ✅ **Scope discipline held.** Verified — governance-only; a single document is committed.

No inconsistencies remained at finalization.

---

## 16. Relationship to Remaining Modules

A7 is the governance rulebook Stage B is measured against; it builds nothing.

- **Stage A status after A7:** A1 (Vision & Philosophy), A2 (System Architecture), A3 (Repository Structure), A4 (Data Flow Architecture), A5 (Runtime Integration Architecture), A6 (Module Overview), and A7 (Engineering Standards) are complete. This governance module identifies **no further required Stage A module**; any additional Stage A work is at the discretion of the locked VPS roadmap, which A7 does not itself declare.
- **Stage B (next):** design and build **B1–B10** inside their assigned layers (A6), obeying the flow (A4) and Runtime seam (A5), and satisfying **every standard in A7** as their definition of done.

A7 guarantees that every Stage B module — and every future module — is engineered to one consistent, enforceable, implementation-independent standard.

---

*End of Stage A · Module A7 — Engineering Standards. This document governs the engineering of all Stage B modules and inherits the locked A1–A6. It defines no assets and implements no behavior.*
