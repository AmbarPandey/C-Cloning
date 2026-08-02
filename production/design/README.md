# Design — Identity Core & Channel-Wide Standards

This folder holds the **Identity Core** — the two locked root documents that every creative asset
inherits from — plus the channel-wide standards that grow beneath them. It is distinct from
[`../characters/`](../characters/) (cast-scoped model sheets) and
[`../A1-first-video/`](../A1-first-video/) (a filled, per-video artifact).

## The Identity Core (two roots)
- **[BRAND_BIBLE.md](BRAND_BIBLE.md)** — the single source of truth for *who the channel is*: purpose,
  mission, vision, values, personality, audience, emotional design, storytelling philosophy, content
  pillars, brand recognition, voice, consistency rules, and the creative decision framework. Governs
  **meaning, story, and voice**.
- **[VISUAL_IDENTITY_LOCK.md](VISUAL_IDENTITY_LOCK.md)** — the single source of truth for *how
  everything looks*: shape, line, color, lighting, composition, background, rendering,
  brand-recognition visuals, the pre-approval quality checklist, and change control. Governs
  **appearance**.

> On a **visual** question the Visual Identity Lock wins; on a **brand/story/voice** question the Brand
> Bible wins. The Brand Bible inherits its visual layer from the Lock — see the
> [dependency graph](BRAND_BIBLE.md#relationship-with-existing-documents).

## Planned children (each inherits from BOTH roots; not yet created)
Character Bible · Expression Library · Pose Library · Prop Library · Environment Bible · Camera
Language · Animation Language · Prompt Framework · Image/Wallpaper prompt sets. Each must open with an
inheritance banner referencing the Brand Bible (meaning/story/voice) and the Visual Identity Lock
(appearance). See [Brand Bible → future documents](BRAND_BIBLE.md#relationship-with-existing-documents)
and [Visual Identity Lock → Future Compatibility](VISUAL_IDENTITY_LOCK.md#future-compatibility).

## Relationship to the rest of the repo
- The Brand Bible **operationalizes** the [Project Vision](../../docs/01-project-vision.md),
  [Stage 1.5 Channel DNA](../../docs/11-stage-1_5-business-decisions.md),
  [Stage 2](../../docs/12-stage-2-channel-operating-system.md), and
  [Intelligence Libraries 1–6](../../intelligence/README.md) without re-deciding anything.
- The Visual Identity Lock elevates the cast-scoped
  [Cast Style Guide](../characters/cast-style-guide.md) to a channel-wide standard, is encoded into
  prompts by the [visual-prompt template](../templates/visual-prompt-template.md), and is enforced per
  tool by the [image generator guide](../tools/image-generator-usage.md).
- Both **defer to** the locked stages/libraries for business, SOP, and storytelling mechanics rather
  than repeating them.
