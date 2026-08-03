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

## Standards built on the Identity Core
- **[CHARACTER_BIBLE.md](CHARACTER_BIBLE.md)** — the permanent **character system**: taxonomy,
  lifecycle, asset & naming standards, prompt standards, quality checklist, validation workflow, the
  full **PIP** profile (first implementation), and a reusable future-character template. Inherits from
  **both** roots; parents the character-scoped libraries below. Implemented by the model sheets in
  [`../characters/`](../characters/README.md).
- **[EXPRESSION_LIBRARY.md](EXPRESSION_LIBRARY.md)** — the canonical **emotional language**: the emotion
  taxonomy + controlled expression-name vocabulary, three intensity levels, universal facial-acting
  standards, per-character overrides (full PIP), expression asset IDs, prompt standards, and
  reuse/approval rules. Inherits from the two roots + the Character Bible; feeds the Pose Library,
  Animation Language, Wallpaper/Prompt Framework, and shot generation.
- **[POSE_LIBRARY.md](POSE_LIBRARY.md)** — the canonical **body-language system**: the pose taxonomy +
  controlled pose-name vocabulary, three intensity levels, universal body-language rules (line of
  action, weight, balance, silhouette), pose+expression pairing, per-character overrides (full PIP),
  pose asset IDs, prompt standards, and reuse/approval rules. Inherits from the two roots + the
  Character Bible + the Expression Library; owns the *static pose* and defers motion/timing to the
  future Animation Language. The Expression Library explains the face; this explains the body.
- **[PROP_LIBRARY.md](PROP_LIBRARY.md)** — the canonical **object system**: the prop taxonomy +
  classification, object-design standards (scale, complexity, line, color, wear/damage, reuse),
  character ownership of objects, interaction rules (holding/using/driving/hand placement/scale
  consistency/pose compatibility), prop asset IDs, prompt standards, and reuse/approval rules. Inherits
  from the two roots + the Character Bible + the Pose Library; owns the *static object + interaction*
  and defers set dressing to the Environment Bible and prop motion to the future Animation
  Language. The Pose Library explains the body; this explains the objects it holds.
- **[ENVIRONMENT_BIBLE.md](ENVIRONMENT_BIBLE.md)** — the canonical **world system**: the environment
  taxonomy + classification, depth-layering standard, environmental assets & `BG_` naming, the weather
  and time systems (expressed within the flat no-gradient law), environmental storytelling, character/
  prop/vehicle interaction with the world, a worked **Parking Lot** location profile, and a Future
  Location Template. Inherits from all six foundation docs; owns *fixed set dressing / locations* and
  defers movable objects to the Prop Library, shot grammar to the Camera Bible, and motion to
  the future Animation Language. Treats every location as a reusable production asset.
- **[CAMERA_CINEMATOGRAPHY_BIBLE.md](CAMERA_CINEMATOGRAPHY_BIBLE.md)** — the canonical **visual
  storytelling language**: the camera (shot-type) taxonomy, the camera-movement taxonomy, cinematographic
  composition extensions (rule of thirds, headroom, look/lead room, eye-line, depth staging), a
  compositional (non-optical) lens language, shot sequencing/coverage of the beat arc, camera-to-
  character/environment/prop framing rules, and a shot-descriptor notation. Inherits from all seven
  foundation docs; owns the *within-shot framing + move vocabulary* and defers cuts/transitions to the
  Editing workflow and move timing/motion to the future Animation Language.

## Planned children (each inherits from the roots + Character Bible where characters apply; not yet created)
Animation Language · Prompt Framework · Image/Wallpaper prompt sets. Each must open with an inheritance
banner referencing the Brand Bible (meaning/story/voice), the Visual Identity Lock (appearance), and —
where they apply — the Character Bible, Expression Library, Pose Library, Prop Library, Environment
Bible, and Camera & Cinematography Bible. See
[Character Bible → future documents](CHARACTER_BIBLE.md#relationship-with-existing-documents),
[Expression Library → future integration](EXPRESSION_LIBRARY.md#future-integration),
[Brand Bible → future documents](BRAND_BIBLE.md#relationship-with-existing-documents), and
[Visual Identity Lock → Future Compatibility](VISUAL_IDENTITY_LOCK.md#future-compatibility).

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
