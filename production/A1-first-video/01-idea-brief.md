# A1 — Idea Brief (Stage 4 output)

The exact, immutable brief emitted by `matrix.select(Reach)`. This is the *source code* the
Script Compiler consumes. Format matches the [Idea-Generation contract](../../prompts/idea-generation.md).

```
Business Goal    : Reach
Target Behavior  : Share
Narrative Pattern: NP1 — Comeuppance (exactly 1)
Scenario         : SC1 — Authority
Comedy Mechanic  : CM-C2 — Overconfidence (Collapse)
Twist (core)     : TW3 — Instant Karma      (modifier: none)
Formula          : FM — Plot-Twist (fixed)
Premise          : A smug authority-figure cast member abuses power over a smaller Pal;
                   their own overconfident final flex instantly backfires and punishes them.
Expected Outcome : High shareability via satisfying justice (karma) + globally legible,
                   language-free visual comedy; strong replay from a frame-1 seed.
Compatibility    : NP1↔SC1 = 5/5 · SC1↔CM-C2 = 5/5 · CM-C2↔TW3 = 5/5 · TW3↔FM = 5/5
Confidence       : High
Priority         : 1 (top of Mode-A default production queue)
FinalScore       : 9.2   (see 09-scoring-worksheet.md)
```

## Decision path (traceable)
`Reach → Share → NP1 Comeuppance → SC1 Authority → CM-C2 Overconfidence → TW3 Instant Karma → FM Plot-Twist`

This is exactly the path recorded in [Library 8](../../intelligence/08-content-matrix.md)
(`matrix.select(Reach) … = Idea A1, FinalScore 9.2, Confidence H`) and
[Stage 4](../../docs/13-stage-4-idea-generator.md).

## Immutability
Per the [Immutability Contract](../../docs/03-locked-roadmap.md), the seven locked fields above
(goal, behavior, pattern, scenario, comedy, twist, formula) may **not** be changed by any
downstream artifact. The script and production package only *compile* them.

## Why this is the first video
- Highest FinalScore in the queue (9.2), High confidence → lowest-risk debut.
- Uses only the two launch cast members (CHIEF, PIP) → minimal new-asset cost.
- 0 spoken words → no localization barrier → maximum global reach (the chosen Goal).
