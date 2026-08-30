# Image Generator — Usage Guide

Generate the flat-2D characters, props, and backgrounds. The generator is the top-tier image tool
chosen in [Stage 1.5](../../docs/11-stage-1_5-business-decisions.md) ("style-locked flat art").

## Inputs
- The [Visual Identity Lock](../design/VISUAL_IDENTITY_LOCK.md) — the master visual standard every
  output must pass (see its [Quality Checklist](../design/VISUAL_IDENTITY_LOCK.md#quality-checklist)).
- The [visual-prompt template](../templates/visual-prompt-template.md) (style prefix + slots).
- The [cast style guide](../characters/cast-style-guide.md) palette tokens.
- Character [model sheets](../characters/README.md).

## Workflow
1. **Build cast once.** Use the character-asset prompt (visual-prompt template §4) to create each
   fixed cast member's turnaround + 6-expression sheet. Save as `CHAR_[NAME]_v1`.
2. **Pin the style.** Reuse the exact style prefix + palette hexes on every generation so outputs
   match. If the tool supports a style/reference image, feed it the approved cast sheet.
3. **Generate props & backgrounds** from the [asset manifest](../A1-first-video/04-asset-manifest.md),
   one asset per generation, on transparent or flat background as needed.
4. **Generate scene stills** from the per-shot prompts in the [storyboard](../A1-first-video/03-storyboard.md).
5. **QC** each asset against the style-guide consistency checklist (silhouette, palette, outline weight).

## Consistency tips
- Same seed/reference across a character's expressions to hold identity.
- Keep the no-parking/seed element in the same screen position across continuity shots.
- Reject and regenerate any asset with gradients, drifted hues, or inconsistent line weight.

## Retry / fallback (when a generation is off-model)
| Symptom | Action |
|---|---|
| Off-palette colors | Re-run with hex values restated + "flat color, no gradient" emphasized |
| Character identity drift | Re-run using the approved cast sheet as a reference image; fix seed |
| Extra unwanted text | Add "no text" to the prompt; inpaint/crop out |
| Too detailed / shaded | Restate "minimal single-tone shading, thick outlines" |
| 3 failed attempts | Escalate to manual vector cleanup of the closest result |

## Output
Style-locked PNGs, named per the [Stage 2](../../docs/12-stage-2-channel-operating-system.md)
convention, added to the reusable asset library → consumed by [Anijam](anijam-usage.md).
