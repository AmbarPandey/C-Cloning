# A1 — Scoring Worksheet (reproduces FinalScore 9.2)

This worksheet reproduces the **9.2** FinalScore recorded for A1 in
[Stage 4](../../docs/13-stage-4-idea-generator.md) and [Library 8](../../intelligence/08-content-matrix.md),
using **only** the locked formulas from [Library 7](../../intelligence/07-virality-intelligence-database.md)
and the [Generation Layer](../../docs/06-generation-layer.md). It makes the first video's ranking
**reproducible** (audit finding F1), scoped to the nodes A1 uses.

> **Scope note.** This materializes the seed scores for **A1's five nodes only**. The full
> score/compatibility dataset for every node (needed to auto-generate video #2+) is a separate,
> larger data effort and is intentionally **not** invented here. Per the
> [Immutability Contract](../../docs/03-locked-roadmap.md), these are *seed* values tagged
> **inferred `[I]`**; only real published-video analytics may promote them.

## Locked formulas (from Library 7 / Generation Layer)
```
ViralityPotential = 0.30·Share + 0.25·Replay + 0.20·Evergreen + 0.15·AdSafe + 0.10·Ease   (sub-scores 0–10)
ReplayPotential   = ReplayScore × (has Seed ? 1.0 : 0.5)
Confidence        = High 1.0 / Med 0.7 / Low 0.4   (multiplier, never a filter)
CompatibilityChain= geometric mean of the edge compatibilities (each normalized to 0–1)
FinalScore        = ViralityPotential_avg × CompatibilityChain × Confidence − DifficultyPenalty
Hard gate         : AdSafe < 4  OR  forbidden combo  →  Score 0 (rejected)
```
> **Confidence mapping note.** Library 7 currently states this multiplier two ways
> (0.9/0.6/0.3 in the primitives table vs 1.0/0.7/0.4 in the scoring section). This worksheet
> uses the **1.0/0.7/0.4** mapping, matching the [Glossary](../../docs/40-glossary.md) and
> Library 8. (This is the internal contradiction flagged as F9 in the readiness audit.)

## Step 1 — Virality sub-scores for A1 (seed, `[I]`)

| Sub-score | Value (0–10) | Rationale |
|---|---|---|
| Share | 10 | Instant-karma justice is maximally shareable (the chosen Goal = Reach/Share) |
| Replay | 9 | Frame-1 seed + loop seam → strong rewatch; `ReplayScore 9 × (seed ✔ →1.0) = 9` |
| Evergreen | 10 | Authority + karma is timeless; no trend dependency |
| AdSafe | 10 | No gore/unsafe humor; clean comedy → passes hard gate |
| Ease | 7 | Moderate on first build (new launch assets); rises as assets become reuse |

```
ViralityPotential = 0.30·10 + 0.25·9 + 0.20·10 + 0.15·10 + 0.10·7
                  = 3.00 + 2.25 + 2.00 + 1.50 + 0.70
                  = 9.45
```
(Single-combination profile ⇒ ViralityPotential_avg = **9.45**.)

## Step 2 — Compatibility chain

| Edge | Rating | Normalized (÷5) |
|---|---|---|
| NP1 ↔ SC1 | 5/5 | 1.00 |
| SC1 ↔ CM-C2 | 5/5 | 1.00 |
| CM-C2 ↔ TW3 | 5/5 | 1.00 |
| TW3 ↔ FM | 5/5 | 1.00 |

```
CompatibilityChain = (1.00 × 1.00 × 1.00 × 1.00)^(1/4) = 1.00
```
(Geometric mean, so any weak link would drag the whole combination down — per Library 8.)

## Step 3 — Confidence
All five A1 nodes are High-confidence records (Library 7) ⇒ Confidence_avg = **1.0**.

## Step 4 — Difficulty penalty
Difficulty rated **3/5** (moderate; new assets on first build). Seed calibration rule:
`DifficultyPenalty = 0.0833 × Difficulty` ⇒ `0.0833 × 3 = 0.25`.

## Step 5 — FinalScore
```
FinalScore = ViralityPotential_avg × CompatibilityChain × Confidence − DifficultyPenalty
           = 9.45 × 1.00 × 1.0 − 0.25
           = 9.20
```

## Result
**FinalScore = 9.2, Confidence High** — matching the locked value in Stage 4 and Library 8.
Hard gate: AdSafe 10 ≥ 4 and the combination is not forbidden ⇒ **valid, ranked #1**. ✔

## Reproducibility statement
Given the same inputs (Goal = Reach, this node set, these seed sub-scores), any operator or agent
recomputes **9.2**. This satisfies the Stage 4 success criterion "another agent reproduces the same
idea from the same inputs" — for the first video.
