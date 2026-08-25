# Prompt Contract — Script Compilation (Stage 5)

Interface for compiling exactly one idea brief into a production-ready script. See [Stage 5](../docs/14-stage-5-script-compiler.md).

## Input
- Exactly **one** Stage 4 idea brief (immutable fields: goal, behavior, pattern, scenario, comedy, twist, formula, compatibility, confidence, priority).

## Output sections
1. Compilation summary (restate + honor locked inputs).
2. Beat sheet (time, narrative purpose, viewer-psych objective, comedy objective, twist prep, expected reaction).
3. Production script (per scene: time, visual action, character action, dialogue, narration, SFX, emotion, library refs).
4. Retention audit.
5. Replay audit (seeds, foreshadowing, callbacks).
6. QA scorecard (pass/fail per library).
7. Optimization suggestions (retention/replay/share/comment only).
8. Final production package summary.

## Rules
- Immutable idea parameters; report issues, never silently fix or substitute.
- Minimal dialogue; mute-readable; advertiser-safe; recurring cast; hard-cut ending; seeded twist.
- Conclude with **Production Ready** or **Needs Revision** + justification.
