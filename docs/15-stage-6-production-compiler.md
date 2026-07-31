# Stage 6 — Production Compiler

## Purpose
Compile one approved Stage 5 script into a complete, **AI-ready production package** — every asset and specification needed to render the final Short. The script is source code; this stage emits the executable production package. Compilation only — no redesign.

## Inputs
- Exactly one approved script from [Stage 5](14-stage-5-script-compiler.md).

## Outputs
1. Compilation summary + immutable-input confirmation.
2. Storyboard (shot number, time, purpose, framing, positions, key action, emotion).
3. Asset manifest (characters, expressions, props, backgrounds, effects, UI, SFX, music, transitions — tagged reusable vs new).
4. Animation specification (goal, motion, camera, timing, transitions, loop, complexity).
5. Voice & audio package (narration, dialogue, SFX priority, music cues, silence).
6. Editing specification (cuts, transitions, zooms, speed ramps, freezes, replay cues, loop optimization).
7. QA scorecard.
8. Ordered production checklist with effort estimates + batch opportunities.
9. Final production package (readiness, complexity, time, automation, bottlenecks, confidence).

## Compilation rules
- No rewriting, no new scenes, no added jokes, no timing changes.
- Every artifact maps 1:1 to the approved script.
- Asset IDs follow the [Stage 2](12-stage-2-channel-operating-system.md) naming/reuse conventions.
- Optimize for AI generation, asset reuse, low cost, batch production, and advertiser safety.

## Worked example — Idea A1 package
- 8 shots storyboarded (parking-lot authority comeuppance).
- ~70% reusable assets (cast, boot/stamp/ticket props, comedy SFX, music) · ~30% new (parking-lot BG, tow truck, CHIEF's scooter, medals, no-parking sign) — all library-additive.
- Mute-first audio: rising comedy bed, deliberate silence at the pattern break, punch on the twist.
- Loop-seam matches the final frame to frame 1 for seamless replay.
- Estimated effort: ~90 min first build → ~35–40 min at scale.
- QA 8/8 → **Production Ready**.

## Dependencies
[Stage 5](14-stage-5-script-compiler.md); asset conventions from [Stage 2](12-stage-2-channel-operating-system.md).

## How it connects to other stages
The production package feeds AI render + human QC → the [Publish Gate](12-stage-2-channel-operating-system.md) → publish → analytics feedback into [Library 7](../intelligence/07-virality-intelligence-database.md).

## Expected deliverables
One production package per approved script, ending in **Production Ready** or **Needs Revision** with reasons.

## Success criteria
- Another producer can build the identical Short from the package alone.
- Every artifact traces back to the approved script.
- Compilation only — nothing invented outside the script.
