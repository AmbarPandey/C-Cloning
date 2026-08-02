# Design — Channel-Wide Visual Standards

This folder holds the **channel-wide visual standards** that govern *every* image ever produced for
C-Cloning — as distinct from [`../characters/`](../characters/) (cast-scoped model sheets) and
[`../A1-first-video/`](../A1-first-video/) (a filled, per-video artifact).

## Files
- **[VISUAL_IDENTITY_LOCK.md](VISUAL_IDENTITY_LOCK.md)** — the **single source of truth** for the
  visual language: purpose, philosophy, principles, shape/line/color systems, lighting, composition,
  background, rendering, brand-recognition and consistency rules, the pre-approval quality checklist,
  and change control. **Nothing visual is created without following it.**

## Planned children (each inherits from the lock; not yet created)
Character Bible · Expression Library · Pose Library · Prop Library · Environment Bible · Camera
Language · Animation Language · Prompt Framework · Image/Wallpaper prompt sets. See
[Future Compatibility](VISUAL_IDENTITY_LOCK.md#future-compatibility) for how each must reference the
lock instead of restating rules.

## Relationship to the rest of the repo
- Elevates the art rules first expressed in the cast-scoped
  [Cast Style Guide](../characters/cast-style-guide.md) to a channel-wide standard.
- Encoded into prompts by the [visual-prompt template](../templates/visual-prompt-template.md) and
  enforced per tool by the [image generator guide](../tools/image-generator-usage.md).
- Defers to [Stage 1.5](../../docs/11-stage-1_5-business-decisions.md) and
  [Stage 2](../../docs/12-stage-2-channel-operating-system.md) for business/SOP rules rather than
  repeating them.
