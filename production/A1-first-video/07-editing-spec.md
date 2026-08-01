# A1 — Editing Specification (Stage 6 output)

Timeline and edit decisions for assembling A1. Uses the reusable
[editing-timeline template](../templates/editing-timeline-template.md). Compiled 1:1 from the
[script](02-script.md) and [animation spec](05-animation-spec.md).

## Timeline (1080×1920, 30 fps, ~32 s)

| Clip | In–Out | Source shot | Transition in | Notes |
|---|---|---|---|---|
| C1 | 0:00–0:02 | Shot 1 | hard cut | Hold composition; seed visible |
| C2 | 0:02–0:06 | Shot 2 | hard cut | Slow push-in |
| C3 | 0:06–0:11 | Shot 3 | hard cut | Impact hold on boot clamp |
| C4 | 0:11–0:16 | Shot 4 | hard cut | Ticket pile pop-ins |
| C5 | 0:16–0:22 | Shot 5 | hard cut | Music drops to silence here |
| C6 | 0:22–0:27 | Shot 6 | hard cut | Truck enters bg |
| C7 | 0:27–0:31 | Shot 7 | **quick punch-in** | Twist; hold "TOWED" frame ~0.5 s |
| C8 | 0:31–0:32 | Shot 8 | hard cut | Button wave; loop seam; hard cut out |

## Cut style
- **Hard cuts only** — no dissolves/fades (matches the snappy comedy pacing and the hard-cut ending rule).
- One **speed ramp**: brief punch-in on C7 for the twist impact.
- One **freeze**: ~0.5 s hold on the "TOWED" stamp frame (screenshot-able punchline).

## Captions / subtitles
- **On-screen dialogue captions: none** (0 spoken words).
- **Accessibility/SFX captions:** optional, off by default. If enabled for reach, add minimal
  bracketed SFX cues (e.g., `[STAMP]`, `[TOWED!]`) styled in `INK` on a `PAPER` pill, bottom-center,
  never covering faces or the seed. Keep ≤2 words. (Caption automation is roadmap item #6 in
  [Stage 2](../../docs/12-stage-2-channel-operating-system.md); for A1 do it manually or skip.)

## Loop seam (verify before export)
- Overlay the final exported frame on the first frame — they must match (same camera, background,
  no leftover FX). If they drift, re-render Shot 8 to the Shot-1 plate.

## Replay-cue check
- Seed (no-parking scooter) present and readable in C1; payoff clear in C7. ✔

## Export handoff
Locked timeline → [08-publish-package](08-publish-package.md) for metadata, then export settings in
the [n8n publishing guide](../tools/n8n-publishing.md).
