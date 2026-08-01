# Visual Production System (VPS)

## Stage A — Module A3: Repository Structure

> **Document type:** Architecture design (repository organization only)
> **Project:** Visual Production System (VPS)
> **Roadmap position:** Stage A · Module A3 — follows the locked *A1 — Vision & Philosophy* and *A2 — System Architecture*
> **Depends on / inherits:** `VPS_Vision_and_Philosophy.md` (constitution) and `VPS_System_Architecture.md` (four-layer architecture)
> **Status:** Proposed — defines the target repository organization for all Stage B modules
> **Scope discipline:** This document defines **how the repository is organized** — its hierarchy, ownership, naming, and governance. It intentionally contains **no asset definitions, no production workflows, and no runtime behavior/implementation.** It describes the *target directory organization* the VPS will adopt; it does not create those directories or place any content in them.

---

## 0. Purpose of This Document

A1 defined *why* the VPS exists; A2 defined *how it is structured* into four layers. A3 defines *where everything lives* — the physical repository organization that makes the A2 architecture visible, enforceable, and durable on disk.

The repository layout is not cosmetic. In a system whose founding law is **single source of truth**, the directory structure is the primary mechanism that *physically prevents* duplicate ownership: if there is exactly one correct place for a thing to live, it cannot be defined twice. This document turns the A2 ownership model into a filesystem contract.

Everything here is a direct application of the locked disciplines: **asset-first**, **single source of truth**, **runtime-driven**, **repository-driven**, **renderer-agnostic**, **AI-model agnostic**, **deterministic**, and **evolve by extension, not rewrite**.

---

## 1. Repository Structure (Principles)

The VPS occupies a single, self-contained root within the C-Cloning repository. Its internal organization obeys four rules:

1. **One layer → one hierarchy.** Each of the four locked A2 layers owns exactly one top-level directory hierarchy. No layer's content lives outside its hierarchy, and no hierarchy is shared by two layers.
2. **Cross-cutting concerns are separated, not scattered.** Concerns that legitimately span layers (contracts, configuration, validation, documentation) live in their own dedicated hierarchies owned by VPS governance — never duplicated inside a layer.
3. **Data grows as data, not as code.** The Asset and Knowledge hierarchies are designed to grow without bound as governed content, while logic-bearing regions stay stable.
4. **The tree encodes the dependency direction.** The layout mirrors the A2 downward dependency graph, so reading the repository reveals the architecture.

---

## 2. Directory Tree (Target)

```text
vps/                              # VPS root — self-contained subsystem
│
├── asset/                        # [LAYER 1] Asset Layer — single source of truth for asset definitions
│   ├── registry/                 #   authoritative identity registry (define-once index of asset identities)
│   ├── definitions/              #   canonical asset definitions (content organized by kind — kinds are Stage B work)
│   └── README.md                 #   ownership + rules for this hierarchy (no asset content defined here in A3)
│
├── knowledge/                    # [LAYER 2] Knowledge Layer — everything *about* assets (by reference only)
│   ├── metadata/                 #   descriptive metadata records (reference assets by identity)
│   ├── relationships/            #   relationship graph between asset identities
│   ├── compatibility/            #   compatibility rules
│   ├── index/                    #   search/lookup indices
│   ├── versions/                 #   version registry: which asset/definition version is authoritative
│   └── README.md
│
├── composition/                  # [LAYER 3] Composition Layer — Runtime output -> scene graph, selection, package
│   ├── scene-graph/              #   scene-graph definitions/models (structure only; not workflows)
│   ├── selection/                #   asset-selection strategy definitions
│   ├── package/                  #   production-package assembly definitions (the immutable hand-off shape)
│   └── README.md
│
├── production/                   # [LAYER 4] Production Layer — renderer-agnostic core + renderer plugins
│   ├── core/                     #   renderer-agnostic production core
│   ├── adapters/                 #   per-renderer adapter plugins (one subdirectory per supported renderer)
│   └── README.md
│
├── contracts/                    # [CROSS-CUTTING] versioned inter-layer + Runtime contracts (owned by governance)
│   ├── runtime/                  #   Master Runtime integration contract(s)
│   ├── inter-layer/              #   contracts between the four layers
│   └── renderer/                 #   the renderer-adapter contract (stable plugin boundary)
│
├── config/                       # [CROSS-CUTTING] governed configuration (volatile choices, externalized)
│   ├── renderers/                #   which renderers are enabled (references adapters; defines no renderer here)
│   ├── models/                   #   AI-model selection/config (model-agnostic; swappable)
│   └── environments/             #   per-environment governed settings
│
├── validation/                   # [CROSS-CUTTING] validation rules that guard determinism + single-source
│   ├── schemas/                  #   structural validation rules for each hierarchy's data
│   ├── ownership/                #   duplicate-ownership / single-source-of-truth checks
│   └── contracts/                #   contract-conformance checks (versioned)
│
├── versioning/                   # [CROSS-CUTTING] repository-level version policy + change records
│   ├── policy/                   #   semantic-versioning policy for contracts, assets, definitions
│   └── changelog/                #   append-only change records (audit trail)
│
└── docs/                         # [CROSS-CUTTING] VPS documentation (the A-modules and successors live here)
    ├── stage-a/                  #   A1, A2, A3 and future Stage A docs
    └── stage-b/                  #   Stage B design docs (added as Stage B proceeds)
```

> **Note on the current repository:** the locked A-module documents (`VPS_Vision_and_Philosophy.md`, `VPS_System_Architecture.md`, and this file) currently sit at the C-Cloning repository root. `docs/stage-a/` is their designated *target* home; relocating them is a governed, additive move to be scheduled without breaking links — it is **not** performed in A3 (A3 commits only this document).

---

## 3. Layer-to-Directory Mapping

Each locked A2 layer maps to **exactly one** directory hierarchy (satisfies the quality gate "every layer owns exactly one directory hierarchy"):

| A2 Layer | Owns hierarchy | Owns (per A2 data ownership) |
|----------|----------------|------------------------------|
| **1 · Asset Layer** | `vps/asset/` | Canonical asset *definitions* + identity registry (single source of truth for *what an asset is*) |
| **2 · Knowledge Layer** | `vps/knowledge/` | Metadata, relationships, compatibility, index, version registry, search — all *by reference* to asset identities |
| **3 · Composition Layer** | `vps/composition/` | Scene-graph, selection, and production-package *definitions* (derived-artifact shapes) |
| **4 · Production Layer** | `vps/production/` | Renderer-agnostic core + per-renderer adapters and their outputs |

**Cross-cutting hierarchies** (`contracts/`, `config/`, `validation/`, `versioning/`, `docs/`) are **not** owned by any layer; they are owned by **VPS governance**. This preserves "no duplicate ownership": a layer never owns a contract or config that another layer also owns — those shared concerns are lifted out into singly-owned governance hierarchies.

The tree also encodes the A2 dependency direction: `composition/` consumes `knowledge/` which references `asset/`; `production/` consumes the package shape defined in `composition/package/` through the `contracts/` boundary — never the reverse.

---

## 4. Directory Responsibilities

- **`vps/asset/`** — Holds the one authoritative definition of each reusable asset and the identity registry that guarantees define-once. It answers *"what is this asset."* It holds no metadata, no relationships, no rendering.
- **`vps/knowledge/`** — Holds all descriptive and relational knowledge about assets, always referencing them by identity. It answers *"what exists, how things relate, what is compatible, which version, how to find it."* It stores no asset definitions.
- **`vps/composition/`** — Holds the definitions of the derived artifacts (scene graph, selection, production package). It answers *"how a Runtime request becomes an immutable production package."* It defines no assets and knows nothing renderer-specific.
- **`vps/production/`** — Holds the renderer-agnostic core and the pluggable per-renderer adapters. It answers *"how a production package becomes tool-specific output."* It makes no selection decisions and defines no assets.
- **`vps/contracts/`** — Holds the versioned boundaries between layers and with the Runtime, including the renderer-adapter contract. The single home for every interface.
- **`vps/config/`** — Holds externalized, governed, volatile choices (enabled renderers, model selection, environment settings). Behavior that may change lives here, not in layer logic.
- **`vps/validation/`** — Holds the rules that guard the invariants: structural correctness, single-source-of-truth / no-duplicate-ownership, and contract conformance.
- **`vps/versioning/`** — Holds the version policy and the append-only change/audit record for the repository.
- **`vps/docs/`** — Holds VPS documentation, organized by stage; the designated home for the A-modules and their successors.

---

## 5. Naming Standard

Naming exists to make ownership and intent unambiguous and to keep the repository stable as it grows.

- **Directories:** lower-case `kebab-case`, singular for a concept-owner (`asset/`, `knowledge/`), plural for a collection of like items (`adapters/`, `schemas/`, `relationships/`).
- **Layer roots** are named exactly for their A2 layer (`asset`, `knowledge`, `composition`, `production`) so the mapping is self-evident.
- **Cross-cutting roots** are named for the concern (`contracts`, `config`, `validation`, `versioning`, `docs`), never for a layer.
- **Renderer adapters:** `production/adapters/<renderer-name>/` — one directory per supported renderer, name = the renderer's stable identifier. Adding a renderer is adding a directory, never editing the core.
- **Identity over path.** Assets are addressed by their stable Asset-Layer *identity*, not by their file path, so content may be reorganized within `asset/definitions/` without breaking references.
- **Documentation files:** the existing convention is preserved — module docs use `VPS_<Topic>.md` at their location; stage docs group under `docs/stage-<x>/`.
- **No abbreviations that hide ownership**, and **no name reused across two hierarchies** (prevents accidental dual ownership).
- **Reserved:** a directory name may map to exactly one owner; reusing a layer name inside a cross-cutting hierarchy for a *different* purpose is prohibited.

---

## 6. Versioning Strategy (Directory)

Versioning is repository-driven and audit-friendly, and preserves deterministic reproduction (A1/A2).

- **Authoritative version registry lives in `knowledge/versions/`.** It records which version of each asset/definition is authoritative — the single source of truth for "which version applies." No other hierarchy claims this.
- **Contracts are semantically versioned under `contracts/`.** Each contract carries an explicit version so layers evolve independently; consumers opt into versions.
- **Policy lives in `versioning/policy/`.** It states the semantic-versioning rules for contracts, asset definitions, and packages.
- **Change history lives in `versioning/changelog/` as an append-only audit trail.** History is added to, not rewritten — supporting traceability and deterministic reconstruction.
- **Definitions are immutable per version.** A change produces a new version rather than mutating an existing one, so any past production can be reproduced from recorded versions.
- **Git provides code history; the version registry provides semantic authority.** The two are complementary: Git tracks changes; `knowledge/versions/` states which semantic version is canonical.

---

## 7. Repository Constraints

The organization is bound by, and demonstrably satisfies, the locked rules:

| # | Constraint | How the layout satisfies it |
|---|-----------|-----------------------------|
| RC-1 | **Follows the four-layer architecture** | `asset/`, `knowledge/`, `composition/`, `production/` map 1:1 to the A2 layers (§3). |
| RC-2 | **Single source of truth** | Exactly one home per concept; version authority centralized in `knowledge/versions/` (§4, §6). |
| RC-3 | **Supports unlimited asset growth** | `asset/` and `knowledge/` grow as governed data, addressed by identity, not by fixed paths (§1, §5). |
| RC-4 | **Prevents duplicate ownership** | One layer → one hierarchy; cross-cutting concerns lifted into singly-owned governance dirs (§3); enforced by `validation/ownership/`. |
| RC-5 | **Supports deterministic Runtime execution** | Everything needed is repository-resident; immutable versioned definitions enable reproduction (§6). |
| RC-6 | **Supports future automation** | Config externalized (`config/`), contracts explicit (`contracts/`), validation automatable (`validation/`). |
| RC-7 | **Supports future renderer plugins** | `production/adapters/<renderer>/` + `contracts/renderer/` — add a renderer without touching the core (§5). |
| RC-8 | **Minimizes future restructuring** | Stable roots + growth-as-data + additive expansion rules (§8) keep the top-level tree fixed. |

---

## 8. Expansion Strategy

Growth happens **inside existing hierarchies or by adding leaves behind existing contracts** — never by reshaping the top-level tree.

- **New asset kinds** → new subtrees under `asset/definitions/` + corresponding records under `knowledge/`. Top-level tree unchanged.
- **New renderers** → new `production/adapters/<renderer>/` + an entry in `config/renderers/`. Core untouched.
- **New AI models** → new entry under `config/models/`; model-agnostic, swappable. No structural change.
- **New knowledge dimensions** → new subtree under `knowledge/` (e.g., an additional relationship category), consumed via versioned contracts.
- **New composition strategies** → new subtree under `composition/selection/` or `composition/scene-graph/`.
- **New stages/modules of documentation** → new `docs/stage-<x>/` subtree.
- **Governing rule:** expansion is **additive**. Removing or relocating a top-level hierarchy requires a governed amendment to this document (§9), because it would change ownership.

---

## 9. Repository Governance

- **This document is the repository constitution's structural clause.** The layout defined here is authoritative; changes to top-level ownership require amending A3.
- **Ownership is explicit.** Each hierarchy carries a `README.md` stating its owner (a layer or governance) and its rules, so ownership is discoverable in-place.
- **Single-source enforcement is automatable.** `validation/ownership/` defines the checks that fail the build if a concept is defined in two places or a datum has two owners.
- **Contract changes are versioned and reviewed.** No layer may depend on another's internals; only on `contracts/`. Contract edits follow `versioning/policy/`.
- **Additive-by-default.** New directories may be added under the rules of §8 without amendment; removals/relocations of top-level hierarchies may not.
- **Audit trail is append-only.** `versioning/changelog/` records structural changes for traceability.
- **Alignment gate.** Any repository change must remain consistent with A1 (philosophy), A2 (architecture), and A3 (this layout); inconsistency blocks the change.

---

## 10. Repository Readiness Assessment

| Dimension | Question | Assessment |
|-----------|----------|------------|
| **A1 alignment** | Does the layout honor the constitution? | **Yes** — asset-first (`asset/` is foundational), single-source (one home per concept), repository-driven, renderer/model-agnostic (isolated in `production/adapters/`, `config/`). |
| **A2 alignment** | Does the layout mirror the four-layer architecture? | **Yes** — 1:1 layer-to-hierarchy mapping; tree encodes the downward dependency direction. |
| **One layer → one hierarchy** | Does each layer own exactly one directory hierarchy? | **Yes** — `asset/`, `knowledge/`, `composition/`, `production/`; cross-cutting concerns are governance-owned, not layer-owned. |
| **No duplicate ownership** | Can a concept be owned twice? | **No** — one home per concept; version authority centralized; enforced by `validation/ownership/`. |
| **Stage B support** | Does it hold all planned Stage B modules? | **Yes** — each Stage B module lands inside exactly one existing hierarchy without structural change. |
| **Unlimited growth** | Can assets/knowledge grow without limit? | **Yes** — data-not-code growth, identity-addressed, additive expansion. |
| **Automation & plugins** | Ready for automation and renderer plugins? | **Yes** — externalized `config/`, explicit `contracts/`, adapter-per-renderer, automatable `validation/`. |
| **Restructuring risk** | Is future restructuring minimized? | **Yes** — stable top-level roots; all known change axes absorbed additively. |

**Readiness verdict:** **READY.** The repository organization is complete, internally consistent, aligned with A1 and A2, and free of duplicate ownership. Stage B modules may be created inside their designated hierarchies without restructuring.

---

## 11. Internal Quality Review (self-check performed before finalization)

- ✅ **Aligns with Stage A1.** Verified — layout enforces asset-first, single source of truth, repository-driven, renderer- and model-agnostic isolation, and additive evolution.
- ✅ **Aligns with Stage A2.** Verified — `asset/ knowledge/ composition/ production/` map 1:1 to the four locked layers, and the tree encodes the A2 downward dependency direction with contracts at the boundaries.
- ✅ **Every layer owns exactly one directory hierarchy.** Verified — four layer roots, each singly owned; cross-cutting concerns are lifted into governance-owned hierarchies so no layer double-owns them.
- ✅ **Supports all future Stage B modules.** Verified — every anticipated Stage B module (asset model/registry, knowledge/registry, composition, renderer adapters) has exactly one correct home already present.
- ✅ **Future restructuring minimized.** Verified — stable top-level roots, data-as-data growth, and strictly additive expansion rules; structural change requires a governed amendment.
- ✅ **Scope discipline held.** Verified — no assets defined, no production workflows, no runtime behavior/implementation; A3 describes organization only and commits a single document.

No inconsistencies remained at finalization.

---

## 12. Relationship to Remaining Modules

A3 provides the *home* for work that later modules will fill; it designs none of that content:

- **Anticipated remaining Stage A work:** a **Contracts & Interfaces** module (the versioned boundaries that will populate `vps/contracts/`) is the natural next architecture-phase step before Stage B implementation begins. Its exact identifier/sequence is set by the locked VPS roadmap; A3 does not itself declare the roadmap.
- **Stage B (built inside the hierarchies defined here):** Asset Layer model/registry → `vps/asset/`; Knowledge Layer model/registry/search → `vps/knowledge/`; Composition Layer → `vps/composition/`; Production Layer core + adapters → `vps/production/`.

A3 guarantees each of these already has exactly one correct location and one owner.

---

*End of Stage A · Module A3 — Repository Structure. This document defines the target repository organization for the Visual Production System and inherits the locked A1 and A2 modules.*
