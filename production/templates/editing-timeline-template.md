# Template — Editing Timeline

Reusable editing structure for any Short. Filled example:
[A1 editing spec](../A1-first-video/07-editing-spec.md).

## Sequence settings
- 1080×1920, 30 fps, target 25–40 s (Shorts spec, [Stage 2](../../docs/12-stage-2-channel-operating-system.md)).

## Timeline table (fill)
| Clip | In–Out | Source shot | Transition in | Notes |
|---|---|---|---|---|
| C1 | 0:00–0:0? | Shot 1 | hard cut | Hook; seed visible |
| … | … | … | hard cut | … |
| C(last) | …–end | Shot N | hard cut | Button; **loop seam**; hard cut out |

## Cut rules
- **Hard cuts only** (no dissolves/fades). Snappy comedy pacing.
- Allow at most one **punch-in / speed ramp** — reserve it for the twist.
- Allow at most one **freeze** — reserve it for the screenshot-able punchline.

## Captions (optional)
- No dialogue captions if the video is mute-first.
- Optional SFX/accessibility captions: ≤2 words, `INK` on `PAPER` pill, bottom-center, never over
  faces or the seed. (Caption automation is [Stage 2](../../docs/12-stage-2-channel-operating-system.md)
  roadmap item #6.)

## Loop-seam check (mandatory)
- [ ] Overlay final frame on first frame — identical camera/background, no residual FX.
- [ ] Re-render the final shot to the opening plate if they drift.

## Replay-cue check
- [ ] Seed readable early.
- [ ] Seed payoff clear at the twist.

## Export handoff
- Locked timeline → [metadata template](metadata-template.md) → publish.
