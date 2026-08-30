# Base Audit — findings from the branch sweep

Audit of all 21 branches, focused on `Execution` and the ten `shorts/v*` branches.
Everything below is verified against the repository, not inferred.

---

## 1. The root cause

**Nothing in this repository had ever been merged.** Twelve pull requests were open, zero had ever
landed, and they formed a chain that was never walked:

```
PR #1   docs/project-architecture ──────────────► main
PR #2   feat/first-video-a1-artifacts ──────────► docs/project-architecture
PR #6   channel/ippa-identity-and-setup ───────► feature/production-foundation-docs
PR #5   live-wallpaper ─────────────────────────► Execution
PR #7-16  shorts/v8 … shorts/v17 (ten PRs) ────► Execution
```

`main` held exactly one file — a README containing the words `# C-Cloning`.

The decisive fact is this: **`Execution`'s merge base with the foundation chain is the initial
commit.** The two histories never touched. So the branch where every video was actually written did
not contain — and had never contained — `intelligence/`, `production/design/`, or
`production/characters/`.

That is not a filing problem. It is the direct cause of the content drift in section 3:

> `.kiro/steering/video-generation-standards.md` on `Execution` opens by instructing the author to
> *"Read the Content Matrix funnel (`intelligence/08-content-matrix.md`) and the VID-Graph decision
> engine (`intelligence/07-virality-intelligence-database.md`)"*.
>
> **Neither path existed on that branch.** Every episode from `v8` onward was written by someone
> following an instruction that could not be followed, against a scenario library they could not
> open. They did the reasonable thing and invented plausible-looking IDs.

The drift is dateable. `v1`–`v7` (through 19 Aug) are fully conformant. `v8`–`v17` — all ten
committed on 20 Aug in a single batch — are not.

---

## 2. What the base fix does

All twelve stranded merges were replayed onto one branch. **Every one was conflict-free**; the only
overlapping file in the entire set was `README.md`, and `Execution` had never modified it.

| Step | Branches | Effect |
|---|---|---|
| Foundation | `channel/ippa-identity-and-setup` | Lands the whole chain at once — it already contained `docs/project-architecture`, `feat/first-video-a1-artifacts` and `feature/production-foundation-docs` in full |
| Catalogue | `shorts/v8` … `shorts/v17` | Ten episode packages, 30 files |
| Asset | `live-wallpaper` | `v1/07-live-wallpaper/` |

Result: **171 files, one branch, all 17 episodes, and every canon reference resolving.**

Base files were then repaired (section 4) and two missing artifacts created:
[`intelligence/09-freshness-log.md`](intelligence/09-freshness-log.md) and this audit.

### Deliberately left out

`feature/production-tool-stack`, `feature/visual-production-system`, `feature/master-runtime` and
`feature/master-runtime-implementation` — 70+ architecture and runtime specification documents with
**no pull request at any point**. They describe a future automation subsystem, not the creative canon,
and folding them into the production base is a call for you to make rather than a cleanup.

---

## 3. Episode metadata defects

The steering file's first rule is that an idea must be *computed* from the intelligence layer and
never invented. Measured against the libraries that are now in the repo:

| Video | Declared scenario | Reality | Declared comedy | Reality |
|---|---|---|---|---|
| v8 | `SC9 Tech/Gadgets` | ID valid, name is `Technology/Social` | `CM-C4 Own Tool Backfire` | `C4` is **False Victory** |
| v9 | `SC7 Dining/Restaurant` | `SC7` is **Danger/Survival** | `CM-C2 Politeness Wins` | `C2` is **Overconfidence Collapse** |
| v10 | `SC4 Workplace/Office` | `SC4` is **Family/Domestic** | `CM-C4 Own Tool Backfire` | `C4` is **False Victory** |
| v11 | `SC11 Shopping/Queue` | **`SC11` does not exist** | `CM-C3 Own Greed Backfire` | `C3` is **Instant Karma** |
| v12 | `SC17 Elevator` | **does not exist** | `CM-C4 Own Tool Backfire` | `C4` is **False Victory** |
| v13 | `SC13 Fishing` | **does not exist** | `CM-C3 Instant Karma` | correct |
| v14 | `SC19 Beach/Sand Castle` | **does not exist** | `CM-C4 Own Tool Backfire` | `C4` is **False Victory** |
| v15 | `SC20 Laundromat` | **does not exist** | `CM-C4 Own Tool Backfire` | `C4` is **False Victory** |
| v16 | `SC16 Library` | **does not exist** | `CM-C4 Own Tool Backfire` | `C4` is **False Victory** |
| v17 | `SC22 Kite Flying` | **does not exist** | `CM-C4 Own Tool Backfire` | `C4` is **False Victory** |

The Scenario Library defines **`SC1`–`SC10` and nothing else.** Seven episodes cite IDs outside that
range and three more attach a real ID to the wrong family.

The underlying mistake is conceptual: **the scenario axis was treated as a location.** "Laundromat",
"Library", "Elevator", "Kite Flying" are settings. `SC1`–`SC10` are *psychological situation families*
— Authority, Service Exchange, Competition, Everyday Friction. A laundromat is not a new scenario; it
is `SC8 Everyday Friction` with the camera pointed somewhere new.

### Comedy core and twist core collapsed into one

`C4` **is** False Victory and `C3` **is** Instant Karma. So four episodes declare the same core twice
and call it two axes — which means the Rule of One failed silently while the header claimed the
constraint engine had passed:

| Video | Declared | Actually |
|---|---|---|
| v7 | `CM-C3 Instant Karma` → `TW3 Instant Karma` | one core, named twice |
| v8 | `CM-C4` (= False Victory) → `TW4 False Victory` | one core, named twice |
| v10 | `CM-C4` (= False Victory) → `TW4 False Victory` | one core, named twice |
| v13 | `CM-C3 Instant Karma` → `TW3 Instant Karma` | one core, named twice |

`v7` is the earliest instance, which means this specific defect **predates** the `v8` batch.

### Other traceability gaps

- **No package reproduces the score.** All ten state a bare `FinalScore` between 8.3 and 8.6 with
  `Confidence High`; none show `VP`, the compatibility chain, the confidence weight or the difficulty
  penalty, so no number is checkable. The tight clustering with no supporting arithmetic is itself the
  tell.
- **Mode B is missing.** The rule is ~1 exploration per 5 deterministic ideas. The catalogue holds 16
  Mode A and **1** Mode B (`v5`) — roughly two explorations short.
- **The idea ledger skips `A7`.** `v7` took `A6` because `v5` consumed `B1`. The batch then set
  `idea = video number`, so `v8` became `A8` and `A7` was never issued.
- **Goal is mislabelled catalogue-wide.** All ten declare goal `Reach`, yet every one plants seeds and
  closes on a loop-to-opening-frame — that is `Replay` behaviour, which per the Content Matrix
  requires an explicit `TM3 Seed Callback`. Only `v5` declares `TM3`.
- **No `README.md`** in any of `v8`–`v17`.

### Proposed remapping — needs your sign-off

Mechanically correcting an invalid ID is safe; **choosing which real family replaces it is an
editorial call**, so nothing below has been applied.

| Video | Setting | Proposed | Consequence |
|---|---|---|---|
| v9 | Restaurant, waiter serves PIP | `SC2` Service Exchange | free |
| v10 | Office, printer monopoly | `SC1` Authority | free |
| v11 | Self-checkout express lane | `SC2` Service Exchange | **collides with v6** (`NP3 × SC2`) |
| v12 | Lift vs stairs | `SC8` Everyday Friction | free (`NP1 × SC8` — check against v7) |
| v13 | Pond, tackle box | `SC3` Competition | free |
| v14 | Beach, sand fortress | `SC8` Everyday Friction | collides with v15/v16 under `NP3` |
| v15 | Laundromat, all dryers | `SC8` Everyday Friction | collides with v14/v16 under `NP3` |
| v16 | Library, book tower | `SC8` Everyday Friction | collides with v14/v15 under `NP3` |
| v17 | Hilltop, kite duel | `SC3` Competition | **collides with v3** (`NP3 × SC3`) |

This is the real cost of the invented IDs: **they were not cosmetic, they defeated the freshness
rule.** While `SC11`/`SC19`/`SC20`/`SC22` sat outside the register every pair looked novel. Resolve
them honestly and `v14`, `v15` and `v16` all reduce to `NP3 × SC8` — the same pair three times in one
batch — and `v17` duplicates `v3`.

Fixing the labels therefore also means **re-deciding the pattern** on some of these episodes. That is
a content decision, not a data cleanup, which is why it is parked here.

---

## 4. Base-file defects — fixed in this change

`IMAGE-GEN-REFERENCE.md` contradicted itself in four places. Because it is the paste-ready sheet that
feeds the image generator directly, each contradiction was reaching the renderer verbatim.

| Defect | Was | Now |
|---|---|---|
| Aspect ratio | §1 style prefix hardcoded `9:16 vertical`, and the standards require long form to be **16:9** or YouTube reclassifies it as a Short. `v5` is long form. | Two prefixes, one per format |
| Proportions | Prefix said `chunky 2.5-head` for everyone; §3 specs **PIP ≈ 2**, **CHIEF ≈ 2.5**. Flattening them erases the status contrast the comedy runs on. | Band in the prefix, value in the character sheet |
| Outline colour | Prefix said `thick uniform black outlines`; §1 and §10 both forbid pure black and require `INK #1A1A1A` | Prefix names `INK` and excludes `#000000` |
| CHIEF's costume | §3 and §9 specced **gold buttons** and **white gloves** — off-palette, and §10 forbids pure white outright | `BRAND_YELLOW` buttons, `PAPER` gloves |

A fifth tension was resolved rather than edited away: `BRAND_YELLOW` is reserved for "one focal hit
per frame", yet CHIEF's sash and medals are permanently `BRAND_YELLOW`. Costume yellow is now
explicitly exempt — the rule governs **props**.

`.kiro/steering/video-generation-standards.md` gained the guardrails that would have caught section 3:
a closed ID registry with the valid ranges and verbatim names, the rule that scenario is a family and
not a location, a `comedy core ≠ twist core` check, both package shapes documented honestly instead of
one aspirational table, and a pre-commit quality gate.

---

## 5. Canon violations inside the scripts — not fixed

Creative content, so flagged rather than edited.

**`v17` breaks the costume lock.** The steering file states CHIEF's cap, sash and medals are costume,
"never removed, never transferred". `v17` has *"medals flying off his sash"*, *"cap flies off"*,
*"cap floating in mud"*, and closes on *"a final gust blows CHIEF's cap out of the puddle"*. The
audience loses his silhouette signature at the exact moment they need to read him.

**`v17` also pushes past the advertiser-safe ceiling.** *"He wraps the string around his wrist"*, then
is *"TOWED horizontally"*, *"hanging from the string wrapped around his wrist"*, before being
*"catapulted face-first"*. Karma landing on the arrogant is correct; a line cinched round a wrist and
a body dragged across a field reads as genuine peril rather than comic indignity.

**Off-palette colours are written directly into the scripts** — the generator will render what it is
told:

| | `green` | `white` | `brown` | `brass` | `gold` | `orange` |
|---|---|---|---|---|---|---|
| v8 | 9 | 2 | | 5 | | |
| v10 | 1 | 1 | | | | |
| v11 | **13** | | | | | |
| v13 | 1 | | | | | |
| v14 | 1 | | | | | |
| v15 | 2 | 2 | | | | 2 |
| v16 | 2 | 4 | | | 1 | |
| v17 | 2 | 4 | **6** | 1 | 1 | |

`v9` and `v12` are clean. Most are one-word fixes — a green tick is `POP_TEAL`, a red X is
`ALERT_RED`, mud and brass are `ASPHALT`, icing and cloud are `PAPER`.

**Non-canonical emotion names.** The Expression Library says to reuse exact names, never synonyms.
The batch timeline tables use `terrified`, `ragdolled`, `strained-confident`, `aggressive`,
`startled`, `calm`, `patient`, `kind`, `content`, `excited`, `defeated`, `mortified` — none of which
are canon, and `terrified` sits outside CHIEF's permitted band entirely. An uncanonical name means
there is no model sheet to render, so the beat is unbuildable as written.

**`v17`'s timeline contradicts itself.** Its retention table places "the drag and launch" at 0:22–0:27
and "the twist" at 0:27–0:31, but clip `C5` (0:16–0:22) already contains the string snap and CHIEF
airborne, and `C6` (0:22–0:27) contains the mud impact. Since every file in a package is meant to lock
to one master timeline, the audio and animation documents inherit the discrepancy.

---

## 6. Structural hazard introduced by the merge

Consolidation surfaced a collision that could not appear while the branches were apart: **`V1/` and
`v1/` now both exist.**

- `V1/` — legacy 9-file package from the foundation branch (`01-script.md`, `02-characters-and-reactions.md`, …)
- `v1/` — the live 7-file package from `Execution`

Linux keeps them distinct. **macOS and Windows will not** — checking this branch out on a
case-insensitive filesystem merges or corrupts the two directories.

This needs a decision before the branch is used on a laptop. `V1/` looks superseded by `v1/`, in
which case the fix is to delete it or rename it to something like `archive/v1-legacy/`. Confirm before
anything is removed.

---

## 7. Open decisions

| # | Decision | Why it is yours |
|---|---|---|
| 1 | Merge target — should this land on `Execution`, or should `Execution` become `main`? | `main` is empty and is the default branch; every PR targets `Execution`. The convention and the configuration disagree. |
| 2 | Apply the section 3 remapping? | Correcting the labels forces a pattern change on `v11`, `v14`–`v17` |
| 3 | Resolve `V1/` vs `v1/` | Deletes or renames content |
| 4 | Close the twelve superseded PRs? | They are all contained in this branch once it lands |
| 5 | Fix the `v17` costume and safety beats? | Rewrites a shipped script |
| 6 | Sweep the palette words in the eight affected scripts? | Mechanical, ~40 substitutions, but it is creative text |
| 7 | Adopt the four orphaned architecture branches, or archive them? | 70+ documents, no PR, unclear whether still live |
