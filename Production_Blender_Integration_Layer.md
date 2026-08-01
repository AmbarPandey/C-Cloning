# Blender Integration Layer

**Project:** C-Cloning
**Project 5:** Production Tool Stack & Automation Workflow
**Stage:** B — Design Deepening
**Module:** B6 — Blender Integration Layer
**Document Type:** Specification (Design — implementation-independent)
**Status:** Draft for review — specification-only, architecture-level
**Branch:** `feature/production-tool-stack`
**Depends on (locked):** Stage A — A1 · A2 · A3 · A4 · A5 · A6 · A7 · A8 · A9 · A10 · Stage B — B1 · B2 · B3 · B4 · B5

---

## 0. Preface — Nature and Boundaries of This Document

This document is the sixth **Stage B specification** module. It defines the **canonical Blender
Integration Layer (BIL)**: the architecture by which a scene-assembly / composition / timeline
tool — named in the locked roadmap as **Blender** — is integrated into the Production Tool Stack
to **assemble VPS-owned assets (visual from B4, audio from B5) into a composed scene**, entirely
by reference, under Runtime authority, without the tool ever owning the assets it composes.

This module is a **specification/design deepening** of the locked Stage A architecture and B1–B5.
It adds detail *within* the existing architecture; it introduces no new architecture and **does
not redesign** B1–B5 — it consumes them.

Accordingly, this module deliberately does **not**:

- define Blender APIs, operators, data-block schemas, or any interface;
- define Python scripts, expressions, or scripting of any kind;
- define add-ons, plug-ins, or extensions;
- define rendering implementation (no engines, passes, samples, codecs, or render logic);
- define implementation generally (no code, storage, transport, or execution logic).

The Runtime and VPS remain **fixed authorities** (Stage A); B1 slots/contracts, B2 adapters, B3
translations, B4 (visual) and B5 (audio) pipelines remain **fixed** (consumed as-is).

### Placement Within the Locked Architecture

Blender is integrated **as a named compositor/scene-assembly occupant of a B2 renderer/compositor
slot** — it is reached only through the **B2 adapter conformance discipline** behind a **B1
capability slot**, per **A5 §10** (external tools reached only through slots). This keeps the
architecture **renderer-agnostic at the structural level** (Blender is one interchangeable
occupant; the BIL is *how* that occupant is integrated) even though the roadmap names Blender as
the concrete target for this module.

```
  VPS-owned visual assets (B4, by ref) ─┐
  VPS-owned audio assets  (B5, by ref) ─┤
  sync metadata (B5, by ref) ───────────┼─▶ [ BLENDER INTEGRATION LAYER (B6) ] ─▶ VPS-owned composed scene ref ─▶ L5 (review gate)
  timeline anchors (by ref) ────────────┘        ingest · assemble · compose ·          │
                                                  coordinate timeline · isolate           ▼
                            (Blender occupies a B2 renderer/compositor slot; execution requested under Runtime authority)
```

> **Governance/consistency note.** B6's architectural rules (as issued) list Runtime authority,
> VPS ownership, SSoT, and implementation-independence, and name Blender specifically. To keep the
> locked architecture coherent, this module integrates Blender **through** the B1/B2 slot/adapter
> discipline, so renderer-agnosticism is preserved structurally (Blender is a substitutable
> occupant). No provider is *selected* by the Tool Stack here; the roadmap has *named* the
> integration target for this module. No locked module is modified.

### Inherited Foundations

| Source | What B6 inherits |
|--------|------------------|
| A1 | Principles P1–P10 (esp. P1 Runtime authority, P2 VPS ownership, P6 review gate, P7 impl-independence, P9 reversibility). |
| A2 | L3 (capability/renderer slot), L4 (asset coordination), L5 (assembly & review-handoff); C1–C10. |
| A4 | SSoT; PRPP composition; references-not-ownership; assets VPS-owned. |
| A5 | External tools reached only via slots; execution under Runtime authority; failure boundaries. |
| A7 | Standards; acceptance criteria MA1–MA10; compliance AC1–AC8; traceability TR. |
| A8 | Policy envelopes; slot-bounded resource use; cost-risk governance. |
| B1 | Abstract capability slots; anonymous occupants; shape-only contracts. |
| B2 | Renderer/compositor adapter conformance shapes; bindings (Blender integrates via an adapter). |
| B4 | VPS-owned visual asset references + provenance. |
| B5 | VPS-owned audio asset references + sync metadata (sync-by-reference). |

---

## 1. Blender Integration Layer Specification (Overview)

Central premise, consistent with the roadmap and with B1–B5:

> **The Blender Integration Layer coordinates scene assembly; it never owns the assets it composes
> or performs rendering here.** It ingests VPS-owned visual/audio assets **by reference**,
> declares how they are arranged into a scene and along a timeline, and requests any execution
> (e.g., compositing/rendering) under **Runtime authority** — with the composed output itself
> becoming a **VPS-owned asset by reference**. Blender is reached only as an occupant of a B2
> compositor slot; nothing about Blender's APIs, scripting, add-ons, or render engine is specified
> here.

The layer is specified as: an **asset ingestion model** (§2), a **scene assembly lifecycle** (§3),
a **composition responsibility model** (§4), a **timeline coordination model** (§5), an **ownership
model** (§6), a **failure isolation model** (§7), an **extension strategy** (§8), and
**architectural constraints** (§9).

**Meta-rules:**
- **BL1 — Coordinate, don't own or render:** the BIL arranges references and requests execution; it
  never owns assets or defines rendering (P1, P2).
- **BL2 — Reference-only ingestion:** all ingested assets are VPS-owned references; none are
  copied, embedded, or re-owned (SSoT, P2).
- **BL3 — Slot/adapter integration:** Blender is integrated only as a B2 compositor-slot occupant;
  no direct coupling, API, or script (AU/RA discipline).
- **BL4 — VPS-owned composed output:** the assembled/composed scene output is a VPS-owned asset by
  reference (P2).
- **BL5 — Gate-guarded handoff:** the composed scene reaches L5 assembly and the mandatory manual
  review gate; nothing publishes without it (P6).
- **BL6 — Implementation-independent:** the layer constrains *shape and invariant*, not
  realization — no APIs, scripts, add-ons, or render logic (P7).

---

## 2. Asset Ingestion Model

Ingestion brings VPS-owned assets into the scene-assembly context **by reference only** (BL2).

- **IN1 — Reference intake:** visual (B4) and audio (B5) assets are ingested as **VPS-owned
  references + provenance**; never copied, embedded, or converted into owned originals.
- **IN2 — Provenance-preserving:** each ingested reference retains its provenance chain (A4 / A7
  TR); ingestion adds an ingestion-lineage marker, not a new owner.
- **IN3 — Sync-metadata intake:** B5 sync metadata and timeline anchors are ingested **by
  reference** to inform arrangement (§5), never re-owned (B5 SY1).
- **IN4 — Neutral descriptor:** ingested references are described abstractly (kind/role of asset),
  with **no** Blender data-block, format, or API detail (BL6).
- **IN5 — Validation on intake:** ingestion validates that references are well-formed and
  VPS-owned before assembly (gate, §3); malformed/unauthorized references are rejected.
- **IN6 — No mutation:** ingestion never mutates a referenced asset; any needed transformation is
  a downstream, execution-requested, VPS-owned derivation (P2), not an in-layer edit.

---

## 3. Scene Assembly Lifecycle

The lifecycle describes the **states of a scene assembly** — architectural states, not Blender
scene data, operators, or render steps (BL6). Each transition is gate-guarded.

```
  INGESTED ─▶ ARRANGED(by reference) ─▶ TIMELINE-COORDINATED ─▶ COMPOSED-REQUEST ─▶ CAPTURED(result ref) ─▶ SCENE-REGISTERED(VPS-owned) ─▶ HANDED-OFF(L5)
     │             │                          │                      │                   │                        │                          │
   [Gi]          [Ga]                       [Gt]                   [Gc]                [Gk]                     [Gr]                       [Gh]
     │             │                          │                      │                   │                        │
  (bad ref)   (unarrangeable)          (sync unresolved)      (Runtime governs)     (capture fault)         (ownership breach)
     ▼             ▼                          ▼                      ▼                   ▼                        ▼
  REJECTED     RETURNED                 SYNC-UNRESOLVED         CONTAINED (P1)       RECOVER (§7)             CONTAINED (P2)
```

| State | Role | Authority/Ownership |
|-------|------|---------------------|
| **Ingested** | VPS-owned references admitted (§2) | VPS owns assets; Tool Stack references |
| **Arranged** | Declarative arrangement of references into a scene structure | Tool Stack owns arrangement metadata |
| **Timeline-coordinated** | Timeline relations established by reference (§5) | Tool Stack owns timeline metadata |
| **Composed-request** | Composition/render **requested** via the B2 slot under Runtime authority | **Runtime** governs execution (P1) |
| **Captured** | Composed output received **by reference** with provenance | **Runtime-owned** result (ref) |
| **Scene-registered** | Composed output coordinated as a **VPS-owned asset by reference** | **VPS owns** the scene output (P2) |
| **Handed-off** | VPS-owned composed scene reference handed to L5 | Tool Stack coordinates; gate at L5 (P6) |

**Lifecycle rules:**
- SL1 — States are strictly ordered; no state is skipped and none proceeds before its gate passes.
- SL2 — No state performs rendering; "Composed-request" *requests* execution, the Runtime governs
  it, the Blender occupant (behind B2) performs it.
- SL3 — All arrangement, timeline, and output data is carried **by reference** with provenance
  (SSoT).

---

## 4. Composition Responsibility Model (Responsibility Matrix)

| Concern | Responsible party | BIL relation | Never |
|---------|-------------------|--------------|-------|
| Sequencing assembly states | **Production Tool Stack (BIL)** | owns the coordination | performs rendering |
| Performing composition/render | Blender occupant (behind B2 slot) | requests via adapter | is coupled by API/script here (BL3) |
| Governing execution | **Master Runtime** | requests execution (Composed-request) | re-owns execution (P1) |
| Composition result data | **Master Runtime** | references (Captured) | re-originates results |
| Ingested visual assets | **VPS** (via B4) | references | re-owns/mutates (P2) |
| Ingested audio assets | **VPS** (via B5) | references | re-owns/re-encodes (P2) |
| Composed scene output (asset) | **VPS** | references (Scene-registered) | re-owns/stores as original (P2) |
| Arrangement / scene-structure metadata | **Production Tool Stack (BIL)** | **owns** (by reference) | owns the referenced assets |
| Timeline metadata | **Production Tool Stack (BIL)** | **owns** (by reference) | embeds/owns assets (§5) |
| Sync relations (audio↔visual) | **B5** (defined) → BIL consumes | references | re-defines B5 sync (BL3) |
| Adapter conformance | **B2** | drives as-is | redesigns adapters |
| Policy envelopes / cost-risk | **A8 governance** | operates within | bypasses/optimizes |
| Review approval before publish | **Human reviewer (L5 gate)** | hands off to gate | auto-approves (P6) |

**Responsibility rules:**
- CR1 — The BIL owns only **arrangement/timeline/coordination metadata and lineage** — never the
  tool, results, or assets (SSoT).
- CR2 — Exactly one responsible party per concern (single-ownership, A6 MG2 / A7 EG3).
- CR3 — Responsibilities preserve Runtime authority (P1) and VPS ownership (P2) at every state.

---

## 5. Timeline Coordination Model

Timeline coordination arranges assets along a temporal/logical timeline **by reference** —
declarative, not executed, and never owning the assets it positions (BL2, consistent with B5 SY).

- **TL1 — Timeline is coordination metadata:** the timeline is a Tool-Stack-owned arrangement of
  **references** (which asset appears/plays at which anchor), not an asset and not a render.
- **TL2 — Reference B5 sync-by-reference:** audio↔visual synchronization consumes **B5 sync
  metadata by reference**; the BIL never redefines B5's sync relations (BL3, B5 SY2).
- **TL3 — Anchors by reference:** timeline anchors reference VPS-owned assets / timeline points;
  no asset is embedded into the timeline (SSoT).
- **TL4 — Declarative, not executed:** timeline coordination declares arrangement; it performs no
  mixing, muxing, encoding, or rendering (P7); any realization is an execution-requested,
  Runtime-governed, VPS-owned derivation.
- **TL5 — Conflicts surfaced, not auto-resolved:** timeline/sync conflicts are surfaced
  (SYNC-UNRESOLVED, §3) for governed handling, never resolved by an implicit default.
- **TL6 — Assembly resolves at L5:** final composition of the timeline into a composed scene is an
  L5 assembly concern (A2 L5 / A4 S6), by reference and still subject to the review gate (P6). B6
  *prepares* the coordinated scene; it does not publish.

---

## 6. Ownership Model

Ownership strictly mirrors Stage A SSoT and B1–B5 (A4, A5, B4/B5):

| Element | Owner (SSoT) | BIL relation | Never |
|---------|--------------|--------------|-------|
| Ingested visual/audio assets | **VPS** | references + provenance | re-owns/mutates (P2) |
| Composition result data | **Master Runtime** | references | re-owns/executes (P1) |
| Composed scene output (asset) | **VPS** | references | re-owns/stores as original (P2) |
| Arrangement / scene-structure metadata | **Production Tool Stack (BIL)** | **owns** (by reference) | owns the referenced assets |
| Timeline metadata | **Production Tool Stack (BIL)** | **owns** (by reference) | embeds/owns assets |
| Blender occupant | external, out of scope | integrated anonymously via B2 | coupled by API/script/add-on (BL3) |
| Sync relations | **B5** | references | re-defines |
| Provenance/lineage of assembly | **Production Tool Stack (BIL)** | **owns lineage** | owns underlying result/asset |

**Ownership rules:**
- OWb1 — The BIL owns only arrangement/timeline/coordination metadata and assembly lineage; ingested
  and composed assets are VPS-owned, composition results are Runtime-owned (SSoT).
- OWb2 — One authoritative owner per element; the layer never transfers ownership.
- OWb3 — Every ingested and every composed asset is **always** VPS-owned and surfaced by reference
  (P2, BL2/BL4).

---

## 7. Failure Isolation Model

Failures are **isolated at the integration boundary** — a Blender-occupant fault never propagates
authority, corrupts SSoT, or leaks tool specifics upward (mirrors A5 §9 / B2 §7 / B4 §7 / B5 §8):

| Failure | Isolated at | Effect | Guardrail |
|---------|-------------|--------|-----------|
| Malformed/unauthorized ingested reference | ingestion gate (Gi) | REJECTED | Only VPS-owned refs admitted (IN5, P2) |
| Unarrangeable references | arrange gate (Ga) | RETURNED for revision | No fabricated arrangement (SSoT) |
| Timeline/sync unresolved | timeline gate (Gt) | SYNC-UNRESOLVED; escalate | No implicit default (TL5) |
| Composition request fault | Runtime boundary | CONTAINED; bounded retry of request | Runtime governs; no self-render (P1) |
| Blender occupant fails mid-compose | B2 adapter boundary | non-result signal; substitute/retry | No fabricated scene; B2 unchanged (BL3) |
| Capture fault | capture state (Gk) | RECOVER; re-reference | No invented result data (SSoT) |
| Ownership breach attempt | registration gate (Gr) | CONTAINED; blocked | VPS remains owner (P2, OWb3) |
| Out of policy envelope | policy check (A8) | escalate for governed decision | No silent over-use (A8 UP7) |

**Failure rules:**
- FI1 — A Blender-occupant fault is contained at its B2 adapter boundary; authority/ownership never
  transfers as a workaround.
- FI2 — The layer never fabricates, embeds, or force-composes assets to mask a fault (SSoT).
- FI3 — Failures are provenance-recorded (A7 TR) and reversible (P9); recovery favors substitution/
  rollback.
- FI4 — No failure path bypasses the downstream L5 manual review gate for publishing (P6).

---

## 8. Extension Strategy

The layer grows **by addition within the abstract model**, never by redesign (mirrors A2 §9 /
B2 §8 / B4 §8 / B5 §9):

- **EX1 — Alternative compositor = new B2 adapter:** another scene-assembly/compositor tool is
  integrated as a new conforming B2 adapter occupying the compositor slot — the BIL architecture is
  unchanged (renderer-agnostic at the structural level).
- **EX2 — New asset kind = new ingestion descriptor:** additional ingested asset kinds are added as
  new neutral descriptors (IN4) without changing the lifecycle.
- **EX3 — New timeline/sync rule = additive:** timeline/sync coordination rules are extended
  additively (§5), consuming B5 sync-by-reference unchanged.
- **EX4 — No API/script/add-on specialization:** extension never adds Blender API, script, or
  add-on paths; tool specifics stay behind the B2 adapter (BL3).
- **EX5 — Reversible:** any ingestion descriptor, lifecycle rule, timeline rule, or adapter can be
  retired without cascading redesign (P9).
- **EX6 — Governed:** integration changes are governed, traceable (A7 VC4/CM, A8 envelopes).

---

## 9. Architectural Constraints

Binding on this layer and its consumers:

- **ACb1 — No Blender API definitions:** no operators, data-blocks, or interfaces (BL6).
- **ACb2 — No scripting:** no Python, expressions, or scripts of any kind (BL6).
- **ACb3 — No add-ons:** no plug-ins or extensions (BL6).
- **ACb4 — No rendering implementation:** no engines, passes, samples, codecs, or render logic
  (BL6).
- **ACb5 — No implementation:** shape + invariant only; no code/storage/transport/execution (P7).
- **ACb6 — No redesign of B1–B5:** slots, adapters, translations, and asset/audio pipelines are
  consumed unchanged (BL3).
- **ACb7 — Runtime authority preserved:** composition/render is requested; the Runtime governs
  execution (P1).
- **ACb8 — VPS ownership preserved:** ingested and composed assets are VPS-owned by reference; no
  re-own/mutate/store (P2).
- **ACb9 — SSoT preserved:** one owner per element; assets/results/timeline referenced, not
  re-owned; sync consumed from B5 by reference.
- **ACb10 — Slot-integration & gate fidelity:** Blender integrated only via a B2 slot/adapter; the
  L5 manual review gate is never bypassed; within A8 envelopes and the locked roadmap (P6, P8,
  P10).

---

## 10. Stage B Readiness Assessment (Readiness for B7)

| Readiness Criterion | Status | Notes |
|---------------------|--------|-------|
| Integration layer specification defined | ✅ Ready | §1; coordinate-not-own/render + BL1–BL6. |
| Purpose defined | ✅ Ready | §0–§1. |
| Asset ingestion model defined | ✅ Ready | §2; IN1–IN6, reference-only. |
| Scene assembly lifecycle defined | ✅ Ready | §3; gate-guarded states + SL1–SL3. |
| Composition responsibility matrix defined | ✅ Ready | §4; CR1–CR3. |
| Timeline coordination model defined | ✅ Ready | §5; TL1–TL6, by reference. |
| Ownership model defined | ✅ Ready | §6; OWb1–OWb3, VPS-owned assets. |
| Failure isolation model defined | ✅ Ready | §7; FI1–FI4. |
| Extension strategy defined | ✅ Ready | §8; EX1–EX6, additive. |
| Architectural constraints defined | ✅ Ready | §9; ACb1–ACb10. |
| No Blender API definitions | ✅ Ready | ACb1, BL6. |
| No scripting | ✅ Ready | ACb2. |
| No add-ons | ✅ Ready | ACb3. |
| No rendering implementation | ✅ Ready | ACb4. |
| No implementation | ✅ Ready | Specification only (ACb5). |
| No redesign of B1–B5 | ✅ Ready | ACb6; consumed as-is. |
| Runtime authority preserved | ✅ Ready | ACb7. |
| VPS ownership preserved | ✅ Ready | ACb8, OWb3. |
| Single Source of Truth preserved | ✅ Ready | ACb9, OWb2. |
| Implementation-independent | ✅ Ready | BL6, ACb5. |
| Renderer-agnostic (structural) | ✅ Ready | Blender integrated via B2 slot; substitutable (EX1). |
| No Runtime/VPS redesign | ✅ Ready | Treated as fixed authorities. |
| Ready for B7 | ✅ Ready | VPS-owned composed scene references (+ timeline metadata) handed to L5 provide a stable surface for B7. |
| Aligns with Stage A (A1–A10), B1–B5 | ✅ Ready | Integrates via B2; ingests B4/B5 assets; spans L3→L4→L5. |

**Overall verdict:** ✅ **Integration-layer-ready.** Module B6 specifies a complete,
implementation-independent Blender Integration Layer — reference-only ingestion, gate-guarded scene
assembly, by-reference timeline coordination, VPS-owned composed output, Blender integrated only via
a B2 compositor slot — consistent with Stage A and B1–B5, ready for B7.

---

## 11. Internal Consistency Review (Self-Check)

Verified before finalizing:

- ✅ Defines **no** Blender APIs, operators, or data-block schemas.
- ✅ Defines **no** Python scripts or scripting of any kind.
- ✅ Defines **no** add-ons, plug-ins, or extensions.
- ✅ Defines **no** rendering implementation (no engines/passes/codecs/render logic).
- ✅ Contains **no** implementation (shape + invariant only).
- ✅ Does **not** redesign the Master Runtime, the VPS, or B1–B5 (all consumed as fixed).
- ✅ Preserves **Single Source of Truth**, Runtime authority (P1) — composition requested, results
  Runtime-owned — and **VPS ownership (P2)** — ingested and composed assets VPS-owned by
  reference, never re-owned.
- ✅ Ingestion, arrangement, and timeline coordination are **by reference only**; sync consumed
  from B5 by reference (no embedding, no cross-ownership).
- ✅ Blender is integrated **only** as a B2 compositor-slot occupant, preserving renderer-agnosticism
  structurally (substitutable via EX1); no provider is *selected* by the Tool Stack.
- ✅ Gate-guarded lifecycle; the downstream **manual review gate (P6)** is never bypassed.
- ✅ Introduces **no new architecture** — spans A2 L3→L4→L5 and consumes B1–B5.
- ✅ Consistent with A1–A10, B1–B5, and locked Projects 1–4; provides a stable surface **ready for
  B7**.

Inconsistencies found: none requiring modification of a locked module. Document ready for commit
on `feature/production-tool-stack`.
