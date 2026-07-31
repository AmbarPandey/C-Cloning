# Prompt Contract — Production Compilation (Stage 6)

Interface for compiling one approved script into an AI-ready production package. See [Stage 6](../docs/15-stage-6-production-compiler.md).

## Input
- Exactly **one** approved Stage 5 script (immutable).

## Output sections
1. Compilation summary + immutable-input confirmation.
2. Storyboard (shot, time, purpose, framing, positions, key action, emotion).
3. Asset manifest (characters, expressions, props, backgrounds, effects, UI, SFX, music, transitions — tagged reusable vs new).
4. Animation specification (goal, motion, camera, timing, transitions, loop, complexity).
5. Voice & audio package (narration, dialogue, SFX priority, music cues, silence).
6. Editing specification (cuts, transitions, zooms, speed ramps, freezes, replay cues, loop optimization).
7. QA scorecard.
8. Ordered production checklist with effort estimates + batch opportunities.
9. Final production package (readiness, complexity, time, automation, bottlenecks, confidence).

## Rules
- No rewriting, new scenes, added jokes, or timing changes.
- Every artifact maps 1:1 to the approved script.
- Asset IDs follow [Stage 2](../docs/12-stage-2-channel-operating-system.md) naming/reuse conventions.
- Conclude with **Production Ready** or **Needs Revision** + reasons.
