# Template — Visual / Render Prompt

Reusable prompt structure for generating any character, prop, background, or scene still in the
locked flat-2D style. Fills audit finding **F3**. See a filled example in the
[A1 storyboard](../A1-first-video/03-storyboard.md).

> **The style prefix and palette below encode the [Visual Identity Lock](../design/VISUAL_IDENTITY_LOCK.md).**
> This template is the *how-to-prompt* surface of that standard — do not diverge from the lock's
> [Color System](../design/VISUAL_IDENTITY_LOCK.md#color-system) or
> [Rendering Rules](../design/VISUAL_IDENTITY_LOCK.md#rendering-rules) here.

## 1. Style prefix (always prepend — do not edit)
```
Flat-color 2D cartoon, thick uniform black outlines, no gradients, minimal single-tone shading,
chunky 2.5-head proportions, high-contrast, clean vector look, 9:16 vertical, mobile-legible.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text unless specified. Advertiser-safe, no gore.
```

## 2. Fill slots
```
{style prefix}
SUBJECT:      <who/what — reference the character asset ID + expression, e.g. CHAR_CHIEF_v1 smug>
FRAMING:      <wide establishing | medium two-shot | low hero angle | punch-in | ...>
POSITIONS:    <left/center/right, foreground/background; who is where>
ACTION/POSE:  <the single key action in this shot>
PROPS:        <prop asset IDs present, e.g. PROP_stamp_v1, PROP_boot_v1>
BACKGROUND:   <BG asset ID or description>
FX:           <FX asset IDs, e.g. FX_impact_star_v1 — or none>
ON-FRAME TEXT:<exact text or "none">
CONTINUITY:   <elements that must match other shots, e.g. seed position, loop seam>
```

## 3. Rules
- **One key action per prompt.** Multiple actions → split into multiple shots.
- **Reference existing asset IDs** for any recurring character/prop so the generator (or you)
  reuses the locked design rather than reinventing it.
- **Mute-readable:** the pose alone must convey the beat.
- **Text only where specified** (most shots: none).
- **Continuity fields are mandatory** for seed shots and the loop seam (first/last frame).

## 4. Character-asset prompt (for building a new cast member once)
```
{style prefix}
Character turnaround (front, 3/4, side) of <NAME>: <build/silhouette>, <outfit + palette tokens>,
<signature props>, default expression <expr>. Plus a 6-expression sheet:
neutral, smug, shocked, gleeful, panicked, deadpan. Consistent proportions across all poses.
```
Store the result as `CHAR_[NAME]_v1` per the [naming convention](../characters/README.md).
