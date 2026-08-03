# A1 — Animation Specification (Stage 6 output)

Motion, camera, timing, and loop spec for rendering A1 in [Anijam](../tools/anijam-usage.md).
Compiled 1:1 from the [script](02-script.md) and [storyboard](03-storyboard.md). No new beats.

> Motion timing, holds, transitions, and loop logic follow the
> [Animation Language & Motion System](../design/ANIMATION_LANGUAGE_MOTION_SYSTEM.md) (the canonical
> motion vocabulary and [runtime semantics](../design/ANIMATION_LANGUAGE_MOTION_SYSTEM.md#runtime-semantics)).

## Global
- **Resolution / fps:** 1080×1920, 30 fps. **Total:** ~32 s (≈960 frames).
- **Animation style:** snappy pose-to-pose, strong holds on comedy beats; limited in-betweens (flat 2D).
- **Complexity:** Low–Medium (mostly 2D transforms + swaps; one vehicle move).

## Per-scene motion

| Scene | Time | Camera | Character motion | Prop/FX motion | Hold/beat |
|---|---|---|---|---|---|
| 1 | 0–2 s | Static wide | CHIEF strut cycle in; PIP coin fumble loop | Meter idle | 6-frame hold on full composition (lets seed register) |
| 2 | 2–6 s | Slow push-in | CHIEF draw-weapon flourish | Stamp/pad slide out | Hold on grin |
| 3 | 6–11 s | Static | Stamp slam; boot clamp | `FX_motionlines` on stamp; boot snap | 4-frame impact hold on boot clamp |
| 4 | 11–16 s | Slight push | Medal-polish loop | Tickets pile (pop-in ×3) | Hold on paper mountain |
| 5 | 16–22 s | Low-angle rise | Pose snap to hero stance | `FX_sparkle` on stamp | **Long hold** (~1.5 s) on victory pose |
| 6 | 22–27 s | Static wide, deep focus | CHIEF frozen; PIP head-turn | Tow truck drives in bg→hook swings | Suspense hold as hook aligns |
| 7 | 27–31 s | Quick punch-in then settle | CHIEF yank + flail; face 3-stage snap (smug→shocked→panicked) | Hook clamp; stamp slams "TOWED"; `FX_impact_star` | **Punch hold** (~0.5 s) on "TOWED" frame |
| 8 | 31–32 s | Return to shot-1 framing | CHIEF shrink away; PIP peel boot + wave | Boot pop-off | Settle to exact frame-1 composition |

## Camera
- Mostly locked/static (mute-first clarity). Only two moves: gentle push-in (S2, S5) and a quick
  punch-in on the twist (S7). No handheld, no rotation.

## Lip-sync
- **None** — A1 has 0 spoken words. Disable Anijam lip-sync; mouths animate only for expression
  (e.g., CHIEF's open-mouth shock in S7).

## Loop optimization (critical)
- **Seam:** the last rendered frame of Scene 8 must be visually identical to the first frame of
  Scene 1 (same camera, same background, no residual FX). Verify by overlaying frame 960 on frame 1.
- **Tail:** hard cut, ≤1 s after the button wave.

## Timing guardrails (from Stage 2)
- Shot length 2–4 s ✔ · Hook 0–2 s ✔ · Twist lands 27–31 s (within the 28–36 s window) ✔
- Words/sec: N/A (0 words) — comedy carried visually ✔
