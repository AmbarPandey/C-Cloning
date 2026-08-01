# Cast Style Guide

The shared visual grammar for **every** character and asset. Locked to match the art direction
decided in [Stage 1.5](../../docs/11-stage-1_5-business-decisions.md): *clean flat-color 2D,
thick outlines, minimal shading, expression-first characters.*

## Art direction (locked)

| Attribute | Rule |
|---|---|
| Line | Uniform thick black outline (~6–8 px at 1080×1920), rounded corners, no line-weight taper |
| Fill | Flat color, **no gradients**; at most one flat shadow tone per shape |
| Shading | Minimal — a single hard-edged shadow shape only where it reads as comedy/volume |
| Palette | Limited, high-contrast, brand palette below; backgrounds desaturated so characters pop |
| Proportions | Chunky, 2.5–3 heads tall, oversized head + hands for expression and prop gags |
| Faces | Big readable eyes + bold brows; the mouth is secondary (mute-first comedy) |
| Motion feel | Snappy, pose-to-pose; strong silhouettes; readable at thumbnail size |

## Brand palette

| Token | Hex | Use |
|---|---|---|
| `INK` | `#1A1A1A` | Outlines, pupils |
| `BRAND_YELLOW` | `#FFD400` | Brand accent, boot/immobilizer, highlights |
| `PAPER` | `#FFF7E0` | Neutral light background base |
| `SKY` | `#BFE3F2` | Sky / open space |
| `ASPHALT` | `#6E7076` | Parking-lot ground |
| `ALERT_RED` | `#E4322B` | No-parking zone, alarm accents |
| `POP_TEAL` | `#2FB6A3` | Secondary accent |

Full palette is style-locked so every image-gen and Anijam render matches. See the
[image generator guide](../tools/image-generator-usage.md) for how to pin these values.

## Mandatory rules (from Stage 2)
- **Mute-readable:** the story must be 100% clear with sound off. Emotion via pose + expression, not dialogue.
- **Advertiser-safe:** no gore, no unsafe humor, no lifted IP/memes/music.
- **Expression-first:** each character ships with a standard expression pack (below).
- **Reuse-first:** never redesign; pull the locked reference art and swap expressions/props.

## Standard expression pack (every character)
`neutral · smug · shocked · gleeful · panicked · deadpan`
Each expression is a separate exported asset (`CHAR_[NAME]_expr_[name]`) so scenes are assembled by swapping, not redrawing.

## Consistency checklist (used by the Animation QC role)
- [ ] Silhouette matches the model sheet at a glance.
- [ ] Palette tokens exact (no drifted hues).
- [ ] Outline weight consistent across all assets in the scene.
- [ ] Proportions (head-to-body) unchanged shot-to-shot.
- [ ] Signature props present and correct (see each model sheet).
