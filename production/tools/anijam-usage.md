# Anijam AI — Usage Guide

Render the storyboard stills into animated shots. Anijam is the locked animation/consistency/lip-sync
tool ([Stage 1.5](../../docs/11-stage-1_5-business-decisions.md), [D-20](../../docs/21-decision-log.md)):
"end-to-end script→screen with a timeline editor."

## Inputs
- Scene stills + character/prop assets from the [image generator](image-generator-usage.md).
- The [animation spec](../A1-first-video/05-animation-spec.md) (motion, camera, timing, loop).
- The [storyboard](../A1-first-video/03-storyboard.md) (framing, positions, key action per shot).

## Workflow
1. **Import assets** (cast, props, backgrounds) into the Anijam project; keep asset IDs as layer names.
2. **Set project** to 1080×1920, 30 fps.
3. **Per shot:** place the storyboard still, set the camera move (mostly static; push-in on S2/S5;
   punch-in on the twist S7), and animate the single key action pose-to-pose.
4. **Expressions:** swap the character expression asset at the beat it changes (e.g., CHIEF
   smug→shocked→panicked at S7). Do not redraw — swap from the expression pack.
5. **Lip-sync:** **disable** for A1 (0 spoken words). Enable only for future dialogue videos, driven
   by the [ElevenLabs](elevenlabs-usage.md) VO track.
6. **Holds:** honor the comedy holds from the animation spec (victory-pose hold S5; "TOWED" punch
   hold S7).
7. **Loop seam:** render Shot 8 to match Shot 1's exact framing/plate.

## Consistency (Animation QC gate)
- Verify every shot against the [style-guide checklist](../characters/cast-style-guide.md): silhouette,
  palette, outline weight, proportions, signature props.
- This is one of the two protected human roles ([daily workflow](../../docs/30-daily-workflow.md)).

## Retry / fallback
| Symptom | Action |
|---|---|
| Character drifts between frames | Re-anchor to the cast asset; reduce auto-interpolation |
| Motion too floaty | Reduce in-betweens; sharpen pose-to-pose holds |
| Loop seam mismatch | Re-render final shot from the Shot-1 plate |
| Camera move too strong | Revert to static; comedy reads best locked |

## Output
8 rendered shots (or one sequence) → handed to the editor per the
[editing spec](../A1-first-video/07-editing-spec.md).
