# Visual Identity Lock

> **Status:** Locked · **Applies to:** every visual asset ever generated for C-Cloning ·
> **Owner role:** Brand Identity Architect / Animation Style Designer
>
> **This is the single source of truth for the C-Cloning visual language.** No character,
> expression, pose, prop, background, thumbnail, wallpaper, effect, or scene still may be
> generated, rendered, or published unless it obeys this document. If any other document
> disagrees with this one on a *visual* rule, **this document wins** and the other document
> must be corrected (see [Repository Integration](#repository-integration)).
>
> **Paired with the [Brand Bible](BRAND_BIBLE.md).** Together they are the **Identity Core**: this
> document governs *how everything looks*; the Brand Bible governs *who the channel is* (purpose,
> story, personality, voice). On a visual question, this document wins; on a brand/story/voice
> question, the Brand Bible wins.

This lock formalizes and elevates the art direction that was decided in
[Stage 1.5 — Business Decisions](../../docs/11-stage-1_5-business-decisions.md) ("clean flat-color
2D, thick outlines, minimal shading, expression-first characters") and first expressed in the
[Cast Style Guide](../characters/cast-style-guide.md). Where the Cast Style Guide governs the
*characters*, this document governs **all visuals** — characters, props, environments, effects,
UI, thumbnails, and wallpapers — and becomes the parent that every future visual library inherits
from.

---

## Table of contents

1. [Purpose](#purpose)
2. [Design Philosophy](#design-philosophy)
3. [Core Visual Principles](#core-visual-principles)
4. [Shape Language](#shape-language)
5. [Line System](#line-system)
6. [Color System](#color-system)
7. [Lighting Rules](#lighting-rules)
8. [Composition Rules](#composition-rules)
9. [Background Rules](#background-rules)
10. [Rendering Rules](#rendering-rules)
11. [Brand Recognition Rules](#brand-recognition-rules)
12. [Consistency Rules (DO / DON'T)](#consistency-rules)
13. [Quality Checklist](#quality-checklist)
14. [Future Compatibility](#future-compatibility)
15. [Repository Integration](#repository-integration)
16. [Change Control](#change-control)

---

## Purpose

C-Cloning is a **faceless, high-cadence animated-Shorts channel** whose entire moat is a *recurring,
instantly recognizable cast and look* (locked in [Stage 1.5](../../docs/11-stage-1_5-business-decisions.md)
and [Stage 2](../../docs/12-stage-2-channel-operating-system.md)). At the target output of 10–14
Shorts per week, the channel will generate **hundreds, then thousands** of images across many tools,
sessions, and (eventually) many operators. Without a single locked standard, that volume guarantees
visual drift — slightly different yellows, thinner outlines, sneaky gradients, wandering proportions —
and drift is brand death for a faceless channel that has *nothing but its look* to be remembered by.

Visual consistency is critical because:

- **Recognition = subscriptions.** Viewers subscribe to a *look and a cast*, not to a single video.
  The three-second in-feed decision is won by an instantly familiar silhouette and palette. This is
  the same "recurring lovable cast" engine identified in
  [Stage 1](../../docs/10-stage-1-competitor-intelligence.md).
- **Reuse = the cost model.** The
  [Stage 2 reusable-asset economics](../../docs/12-stage-2-channel-operating-system.md) (target ~70%
  asset reuse, sub-30-minute videos) only work if assets are visually interchangeable across videos.
  A locked standard is what makes an asset *reusable* instead of *one-off*.
- **Monetization safety.** The top business risk is
  [demonetization of "AI/reused" content](../../docs/11-stage-1_5-business-decisions.md). A deliberate,
  owned, consistent house style is the evidence of original authorship.
- **Scale without a bottleneck.** A locked standard lets new operators, new tools, and future
  automation ([Stage 2 automation roadmap](../../docs/12-stage-2-channel-operating-system.md)) all
  produce on-brand output without a human re-deciding style each time.

**Rule of thumb:** if a viewer could not tell — from a single muted frame at thumbnail size — that a
new image belongs to this channel, the image has failed this document.

---

## Design Philosophy

**The artistic philosophy: "Loud shapes, quiet detail."** Every frame is built from a few big, bold,
clean shapes that read in a fraction of a second, with detail deliberately withheld so the *joke, the
emotion, and the character* land first. The look is a **modern flat-color 2D cartoon** — the visual
lineage of clean twist-ending comedy channels — engineered for a muted, vertical, thumb-scrolling
feed.

**The emotional experience the visuals should create:**

- **Instant clarity, then delight.** The eye should understand "who, where, and what's happening" in
  under a second, then be rewarded by an expressive, funny beat.
- **Warm, safe, playful.** Rounded forms, a warm paper base, and friendly proportions keep the tone
  light and **advertiser-safe** even when the comedy is a comeuppance. Nothing grim, gory, or harsh.
- **Underdog sympathy vs. smug authority.** The visual system is tuned to make the audience *root*
  (small, soft, warm = likeable) and *anticipate karma* (big, stiff, over-decorated = deserving),
  supporting the [NP1 Comeuppance](../../intelligence/06-narrative-pattern-library.md) engine.

**What makes the visuals instantly recognizable:**

1. **Silhouette-first cast** — chunky, 2–3-heads-tall characters readable in pure black.
2. **Uniform thick black outline** on everything, with no line-weight taper.
3. **Flat color, zero gradients**, on a signature warm-paper background.
4. **A tight, high-contrast brand palette** anchored by `BRAND_YELLOW`.
5. **Mute-first storytelling** — emotion carried by pose + expression, not dialogue.
6. **A recurring cast** (currently [PIP](../characters/pip.md) & [CHIEF](../characters/chief.md))
   whose designs never change between videos.

---

## Core Visual Principles

These are the non-negotiable principles every visual asset serves. The first nine are the requested
baseline; the remainder were discovered from the existing repository and are equally binding.

| # | Principle | What it means in practice |
|---|---|---|
| 1 | **Simplicity** | Few big shapes; withhold detail. If a detail doesn't help the beat, delete it. |
| 2 | **Readability** | Every element reads instantly at 1080×1920 *and* at grid-thumbnail size. |
| 3 | **Consistency** | Same palette, outline, and proportions in every asset, every video, forever. |
| 4 | **Mobile-first** | Design for a small, vertical, muted screen viewed at arm's length. |
| 5 | **Silhouette recognition** | Every character/prop is identifiable in pure black. |
| 6 | **Visual hierarchy** | One clear subject per frame; background yields to foreground. |
| 7 | **Emotional clarity** | The pose + expression must telegraph the feeling with sound off. |
| 8 | **Advertiser-safe** | No gore, no unsafe/hateful humor, no lifted IP — always monetizable. |
| 9 | **Timeless style** | Flat vector look avoids trend-dated 3D/render fads; ages slowly. |
| 10 | **Mute-first storytelling** | The story is 100% clear with audio off (from [Stage 2](../../docs/12-stage-2-channel-operating-system.md)). |
| 11 | **Reuse-first** | Never redraw a locked asset; pull the reference art and swap expression/prop. |
| 12 | **Continuity discipline** | Seeds and the loop seam (first frame = last frame) must match exactly. |
| 13 | **Originality / ownership** | House style and cast are original and owned — the monetization moat. |
| 14 | **Tool-agnostic** | The look must reproduce across any image or image→video tool (palette + reference-locked). |

---

## Shape Language

The cast and world are built from **soft, rounded, chunky geometry**. Shape carries meaning: roundness
reads as warmth/harmlessness, and rigidity reads as pomposity/authority.

**Rounded vs. sharp**
- **Default to rounded.** Bodies, heads, hands, props, and background masses use rounded corners and
  soft, closed curves. This is the channel's friendly, advertiser-safe signature.
- **Sharp/angular is a deliberate accent only** — reserved for *authority, threat, or hostility*
  cues (badges, medals, warning zones, hard "TOWED"-style stamps, hazard chevrons). Sharpness must
  never dominate a frame; it is seasoning, not the meal.

**Geometric language**
- Forms reduce to a small kit of primitives: circle, rounded rectangle, capsule, teardrop, soft
  triangle. Build every asset from this kit so nothing feels stylistically foreign.
- No fine filigree, no realistic anatomy, no intricate mechanical detail.

**Silhouette philosophy**
- **Silhouette is the identity.** Each character must be recognizable as a solid black shape.
  Signature elements that define the silhouette are mandatory in **every** shot — e.g.
  [CHIEF](../characters/chief.md)'s cap + sash + medals, [PIP](../characters/pip.md)'s scarf.
- Test every new asset by filling it 100% black; if it becomes ambiguous or generic, redesign.

**Proportions (locked)**
- Characters are **chunky, ~2.5–3 heads tall** (PIP ~2, CHIEF ~2.5), with an **oversized head and
  hands** for expression and prop gags. These ratios are locked per character in the
  [model sheets](../characters/README.md) and must not drift shot-to-shot.
- Props are scaled for comedy and readability (e.g., "giant" stamp/ticket pad), not realism.

**Visual weight**
- The **subject of the beat is the heaviest element** in the frame (largest, boldest, highest
  contrast). Everything else is lighter and quieter.
- Small + soft + warm = sympathetic weight (underdog). Large + stiff + over-decorated = antagonist
  weight. Use weight to steer the viewer's allegiance.

---

## Line System

The outline is the most recognizable single feature of the channel and is **locked**.

| Attribute | Locked rule |
|---|---|
| **Outline thickness** | Uniform **thick black outline, ~6–8 px at 1080×1920**. Scale proportionally at other resolutions (never thinner in relative terms). |
| **Outline consistency** | The **same** weight on every asset in a frame — character, prop, and background key shapes. No mixing thick-and-thin between assets in the same shot. |
| **Stroke behavior** | **No line-weight taper**, no calligraphic/brush modulation, no sketch/pencil texture. The stroke is even, confident, and vector-clean. |
| **Corner treatment** | **Rounded corners** by default (matches Shape Language). Sharp corners only on the deliberate "authority/threat" accents. |
| **Color** | Outlines are `INK #1A1A1A` — never pure black `#000000`, never a colored outline. Pupils use the same `INK`. |
| **Interior lines** | Minimal. Use interior strokes only to separate overlapping shapes or read a key form; never for surface detail or hatching. |
| **Acceptable variations** | (1) Slightly heavier weight on a hero close-up for punch, kept *uniform within that frame*. (2) Outline may be omitted where a shape sits on a same-value background *only if* the silhouette still reads. (3) FX (impact bursts, motion lines) may use a matching-weight `INK` or `BRAND_YELLOW` stroke. Nothing else is permitted. |

---

## Color System

Color is **locked and role-based**. The palette is split into a fixed **Brand Core** (present across
every video, forever) and an extensible **Environment set** (per-setting, but always desaturated so
the cast pops). This split is what lets the channel visit new settings (beach, office, zoo, gym…) as
the [V1 Series Bible](../../V1/08-series-bible.md) anticipates, without ever diluting brand recognition.

### Official palette — Brand Core (fixed, every video)

| Token | Hex | Role |
|---|---|---|
| `INK` | `#1A1A1A` | All outlines, pupils, hard text/stamps |
| `BRAND_YELLOW` | `#FFD400` | **Primary brand accent** — hero props (boot/immobilizer), highlights, thumbnail pill, channel identity |
| `PAPER` | `#FFF7E0` | Warm neutral base — light backgrounds, character base body, negative space |
| `POP_TEAL` | `#2FB6A3` | Secondary accent — cast wardrobe link (CHIEF jacket, PIP scarf), cohesion cue |
| `ALERT_RED` | `#E4322B` | Tension/hazard accent — no-parking/danger zones, alarms, "TOWED"-style marks |

### Official palette — Environment set (per-setting, extensible, always desaturated)

| Token | Hex | Role |
|---|---|---|
| `SKY` | `#BFE3F2` | Sky / open space / calm backdrops |
| `ASPHALT` | `#6E7076` | Ground / pavement (parking-lot setting) |

> New settings may introduce **additional desaturated environment tokens** (e.g. `SAND`, `OFFICE_WALL`),
> registered here first, so the palette grows in a controlled way. Environment tokens must always be
> **lower saturation and lower contrast than the Brand Core**, so characters and hero props remain the
> most vivid things on screen. Per-location token usage (which tokens each setting uses) is documented
> in the [Environment Bible](ENVIRONMENT_BIBLE.md); this Color System remains the single registry.

### Color hierarchy

1. **`INK`** frames and grounds everything (outlines).
2. **`BRAND_YELLOW`** is the eye magnet — reserve it for the single most important element/beat in the
   frame (usually the hero prop or the payoff). Do not flood a frame with yellow or it stops signaling.
3. **`POP_TEAL`** links the cast together and provides friendly secondary color.
4. **`ALERT_RED`** signals danger/tension/karma — use sparingly for maximum punch.
5. **`PAPER` + Environment tokens** recede into the background so foreground reads.

### Accent colors
`BRAND_YELLOW`, `POP_TEAL`, and `ALERT_RED` are the *only* accent colors. Every saturated hit of color
on screen must be one of these three. This is the discipline that makes frames feel like the same
channel.

### Forbidden colors
- **No gradients** of any kind (see [Rendering Rules](#rendering-rules)).
- **No pure black `#000000`** (use `INK`) and **no pure white `#FFFFFF`** (use `PAPER`).
- **No neon or oversaturated hues** outside the palette; **no realistic skin tones** (characters use
  `PAPER`/palette fills, not human flesh colors).
- **No off-brand accent colors.** If a new hue seems necessary, it must be added to this document
  first via [Change Control](#change-control) — never improvised in a prompt.
- **No colored outlines.** Outlines are always `INK`.

### Emotional use of color
- **`BRAND_YELLOW`** = triumph, spotlight, "look here," the channel's optimistic energy.
- **`POP_TEAL`** = calm, friendliness, the likeable cast.
- **`ALERT_RED`** = threat, wrongdoing, the seed of karma, the payoff.
- **`PAPER`/`SKY`** = safety, openness, breathing room (used generously around the subject).

### Accessibility considerations
- Every foreground element pairs with `INK` outlines, guaranteeing high edge contrast for
  low-vision and small-screen viewing.
- Do **not** rely on color *alone* to carry meaning (supports color-blind viewers and the
  **mute-first** rule): pair color cues with shape, pose, and position (e.g., the hazard zone is red
  *and* an outlined marked box *and* positioned under the offending prop).
- Maintain strong value contrast between subject and background; if converting a frame to grayscale
  makes the subject blend in, increase value separation.

---

## Lighting Rules

The channel uses **flat, ambient, "no light source" rendering.** Lighting is implied by flat shapes,
not simulated.

- **Lighting philosophy:** bright, even, ambient illumination. There is no modeled key light, no ramp,
  no realistic falloff. The image looks like clean vector art, not a rendered 3D scene.
- **Shadows:** at most **one flat, hard-edged shadow tone per shape**, used only where it reads as
  *comedy or volume* (e.g., a contact shadow to plant a character, or a mood shadow creeping in for
  tension). Shadows are a single flat fill, never soft, never blurred, never gradient. Most assets
  need **zero** shadow.
- **Highlights:** flat shapes only — a simple `BRAND_YELLOW` or `PAPER` gleam/spark. No soft glow
  bleed, no bloom. A "shine" is a hard-edged flat shape (e.g., a 4-point sparkle), not a gradient.
- **Gradients:** **forbidden everywhere** (backgrounds, skies, characters, props, FX). A "sky" is a
  flat `SKY` fill, not a blue-to-white ramp.
- **Reflections:** none as realistic mirror/gloss. A reflective read (glossy stamp, shiny medal) is
  suggested with a single flat highlight shape only.
- **Flat rendering rules:** every surface is one flat color (optionally plus its one shadow tone).
  No ambient occlusion, no texture-based lighting, no rim light, no volumetrics.

---

## Composition Rules

Frames are composed for a **vertical 9:16 mobile feed, muted, at a glance.**

- **Framing:** design at **1080×1920 (9:16)**. Use clear shot grammar (wide establishing / medium
  two-shot / low hero angle / punch-in) as documented in the
  [visual-prompt template](../templates/visual-prompt-template.md) and the
  [A1 storyboard](../A1-first-video/03-storyboard.md). **One key action per frame.**
- **Centered / thumb-safe subjects:** keep the primary subject and any critical action within the
  central, thumb-safe band. Assume the **top ~15% and bottom ~20%** may be covered by platform UI
  (captions, handle, buttons) — keep essential info and on-frame text out of those zones.
- **Whitespace / negative space:** use `PAPER`/environment space generously around the subject.
  Negative space *is* composition here — it isolates the beat and boosts readability. Do not fill
  the frame with clutter.
- **Readability on mobile:** every element must survive being viewed a few inches tall. If a detail
  disappears at thumbnail size, it is either enlarged or removed.
- **Visual balance:** balance the heavy subject with calm negative space rather than with competing
  detail. Guide the eye along a single, clear path to the beat.
- **Continuity framing:** seed elements stay in a **fixed screen position** across a video, and the
  **first and last frame must match** (the loop seam) — a locked requirement from the
  [V1 Series Bible](../../V1/08-series-bible.md) and the [editing spec](../A1-first-video/07-editing-spec.md).

---

## Background Rules

Backgrounds exist to **locate the scene and then get out of the way.**

- **Complexity limits:** a background is a few large, flat shapes (ground plane, backdrop, 1–3 set
  pieces). No busy scenery, no crowds, no dense environmental detail.
- **Allowed detail:** only detail that (a) establishes the setting, (b) plants a *seed* for the twist,
  or (c) supports the current beat. Everything else is removed.
- **Color hierarchy:** backgrounds use **desaturated Environment tokens** so the outlined, more
  saturated foreground cast/props always pop. The background must never be brighter or more contrasty
  than the subject.
- **Distraction avoidance:** no background element may out-compete the subject for attention. No
  readable background text, no incidental characters, no eye-catching patterns unless they *are* the
  beat. When in doubt, simplify.

---

## Rendering Rules

The technical output target that makes every tool's result look like the same channel.

- **Vector appearance:** outputs must look **clean-vector / flat-2D**, as if drawn in a vector tool —
  crisp edges, solid fills, uniform outlines. This applies whether the asset came from an image
  generator, a vector tool, or manual cleanup.
- **Flat colors:** every fill is a single solid palette color. No painterly variation within a fill.
- **Texture policy:** **no textures** — no paper grain, canvas, noise, halftone, grunge, or
  photographic texture. Surfaces are perfectly flat.
- **Gradient policy:** **no gradients**, anywhere, ever (restated from Lighting for enforcement).
- **Shading rules:** at most **one flat, hard-edged shadow tone per shape**, and only when it earns
  its place (volume or comedy). Default is no shading.
- **Anti-aliasing expectations:** clean, minimal anti-aliasing on edges (smooth but crisp). **No
  soft/blurry edges, no glow, no bloom, no depth-of-field blur.** Edges stay sharp and deliberate.
- **On-frame text:** avoided by default (mute-first). When required, it is a bold, chunky, `INK`
  word — optionally on a `BRAND_YELLOW` pill — never a fine or decorative typeface. See
  [thumbnail-spec](../templates/thumbnail-spec.md) text rules.
- **Export:** style-locked PNGs (transparent where an asset must composite), named per the asset-ID
  convention below, then added to the reusable library and consumed by
  [Anijam](../tools/anijam-usage.md). See the
  [image generator guide](../tools/image-generator-usage.md) for pinning these values per tool.

---

## Brand Recognition Rules

These elements are **constant across hundreds of videos**. Changing any of them is a brand-level
decision, not a per-video choice (see [Change Control](#change-control)):

1. **The uniform thick `INK` outline** on everything.
2. **Flat color, zero gradients**, clean-vector rendering.
3. **The Brand Core palette** — especially `BRAND_YELLOW` as the signature accent, on the warm
   `PAPER` base.
4. **The recurring cast and their locked silhouettes** — [PIP](../characters/pip.md) (small, round,
   `POP_TEAL` scarf) and [CHIEF](../characters/chief.md) (rotund, cap + `BRAND_YELLOW` medal sash),
   plus future fixed cast. Their designs **never change** between videos
   ([V1 Series Bible](../../V1/08-series-bible.md)).
5. **Chunky 2.5–3-head proportions** and oversized heads/hands.
6. **Mute-first, expression-first storytelling** with the standard expression packs.
7. **The comedic structure of the frame** — one clear subject, generous negative space,
   silhouette-readable staging.
8. **The seamless loop** (first frame = last frame) and the **twist/karma** payoff format.
9. **Thumbnail identity** — the cast's oversized expression + `BRAND_YELLOW` pill (per
   [thumbnail-spec](../templates/thumbnail-spec.md)).

If a stranger scrolling the feed can't attribute a muted frame to this channel within a second via the
above, recognition has failed.

---

## Consistency Rules

Explicit DO / DON'T lists. These are the fast reference for anyone generating an asset.

### Always
- **Always** prepend the locked style prefix and the exact palette hex values to every prompt
  (see [visual-prompt template](../templates/visual-prompt-template.md)).
- **Always** feed the tool the approved character **reference sheet** (as reference/style image or
  fixed seed) when a locked cast member appears.
- **Always** keep each character's silhouette signatures present (CHIEF's cap + sash + medals; PIP's
  scarf).
- **Always** use a uniform `INK` outline of consistent weight across a frame.
- **Always** keep one clear subject and generous negative space.
- **Always** keep seed elements in a fixed position and match the first/last frame for the loop.
- **Always** verify mute-readability: the pose alone must convey the beat.

### Never
- **Never** use gradients, soft glow/bloom, blur, or texture.
- **Never** use pure black `#000000` or pure white `#FFFFFF`.
- **Never** introduce an off-palette or neon color, or a colored outline.
- **Never** redraw or restyle a locked cast member per video — reuse the locked reference.
- **Never** change locked proportions, slim a character down, or drop signature props between shots.
- **Never** add realistic lighting, 3D render looks, or photographic detail.
- **Never** clutter the background or let it out-contrast the subject.
- **Never** rely on on-frame text to explain the story (mute-first); text is a rare, deliberate accent.

### Avoid
- Avoid more than one saturated `BRAND_YELLOW` focal hit per frame (it stops signaling).
- Avoid multiple competing actions in a single frame — split into separate shots.
- Avoid fine interior linework, hatching, or surface detail.
- Avoid placing critical elements or text in the top ~15% / bottom ~20% platform-UI zones.
- Avoid sharp/angular forms except as intentional authority/threat accents.

### Preferred
- Prefer fewer, bigger, bolder shapes over many small ones.
- Prefer expression + pose changes over adding props or detail.
- Prefer reusing a library asset over generating a new one (the [reuse-first](#core-visual-principles) cost moat).
- Prefer regenerating an off-model result over "settling" — consistency is the brand.

---

## Quality Checklist

Run this gate **before approving any generated image** (character, prop, background, scene still,
thumbnail, or wallpaper). One failure = reject and regenerate. This checklist is the visual-layer
companion to the [Stage 2 Publish Gate](../../docs/12-stage-2-channel-operating-system.md) and the
[Cast Style Guide consistency checklist](../characters/cast-style-guide.md).

**Line & shape**
- [ ] Uniform thick `INK` outline; consistent weight across the whole frame; no taper.
- [ ] Rounded-first shapes; any sharp forms are intentional authority/threat accents.
- [ ] Silhouette reads correctly (test by filling the subject black).
- [ ] Proportions match the locked model sheet (head-to-body unchanged).

**Color**
- [ ] Every fill is an exact palette hex (no drifted hues).
- [ ] Only `BRAND_YELLOW` / `POP_TEAL` / `ALERT_RED` used as accents; one primary yellow focal hit.
- [ ] No pure `#000000` / `#FFFFFF`; no off-palette or neon color; outlines are `INK`.
- [ ] Background uses desaturated Environment tokens and stays quieter than the subject.

**Rendering**
- [ ] Flat colors only — no gradients, no textures, no soft glow/bloom/blur.
- [ ] At most one flat hard-edged shadow tone per shape (and only where earned).
- [ ] Clean-vector appearance; crisp anti-aliased edges.

**Composition & readability**
- [ ] One clear subject; generous negative space; balanced.
- [ ] Reads at thumbnail size and on a muted mobile screen.
- [ ] Critical elements/text clear of the top ~15% / bottom ~20% UI zones.
- [ ] Mute-readable: the pose/expression alone conveys the beat.

**Cast & continuity**
- [ ] Locked cast on-model; signature silhouette elements present (cap/sash/medals; scarf).
- [ ] Signature props correct per the model sheet.
- [ ] Seed elements in the fixed position; first/last frame match for the loop (scene stills).

**Brand & safety**
- [ ] Frame is attributable to this channel at a glance.
- [ ] Advertiser-safe; no gore, no unsafe humor, no lifted IP/text/logos.
- [ ] Asset named per the [asset-ID convention](#asset-id-naming) and added to the library.

---

## Future Compatibility

This document is the **root of the visual documentation tree.** Every present and future visual asset
or library must **inherit from and reference** it rather than restating rules.

**How future documents must reference this lock**
- Open with a one-line statement such as:
  *"Governed by the [Visual Identity Lock](../design/VISUAL_IDENTITY_LOCK.md). This document only adds
  \<its specific scope\>; all shape, line, color, lighting, composition, background, and rendering
  rules are inherited."*
- **Do not restate** palette hexes, outline weight, or rendering rules — **link** to the relevant
  section here. If a value is needed inline, link back to the canonical definition so there is exactly
  one source of truth.
- If a future document needs a rule that conflicts with this lock, it must **not** override locally —
  it must propose an update here first via [Change Control](#change-control).

**Planned children that will inherit from this lock** (each is now a sibling document in
[`production/design/`](README.md) — all ✅ created):

| Document | Status |
|---|---|
| [Brand Bible](BRAND_BIBLE.md) | ✅ |
| [Character Bible](CHARACTER_BIBLE.md) | ✅ |
| [Expression Library](EXPRESSION_LIBRARY.md) | ✅ |
| [Pose Library](POSE_LIBRARY.md) | ✅ |
| [Prop Library](PROP_LIBRARY.md) | ✅ |
| [Environment Bible](ENVIRONMENT_BIBLE.md) | ✅ |
| [Camera & Cinematography Bible](CAMERA_CINEMATOGRAPHY_BIBLE.md) | ✅ |
| [Animation Language & Motion System](ANIMATION_LANGUAGE_MOTION_SYSTEM.md) | ✅ |
| [Production Prompt Framework & Runtime Orchestration](PRODUCTION_PROMPT_FRAMEWORK_RUNTIME_ORCHESTRATION.md) | ✅ |
| Image / Wallpaper prompt sets (concrete generated prompts) | planned |

<a id="asset-id-naming"></a>
**Asset-ID naming (inherited channel-wide, from [Stage 2](../../docs/12-stage-2-channel-operating-system.md))**

Every visual asset produced under this lock is named and versioned consistently so it is reusable and
traceable:

| Asset type | Convention | Example |
|---|---|---|
| Character | `CHAR_[NAME]_v#` | `CHAR_PIP_v1` |
| Expression | `CHAR_[NAME]_expr_[name]` | `CHAR_CHIEF_expr_smug` |
| Pose | `CHAR_[NAME]_pose_[name]` | `CHAR_PIP_pose_wave` |
| Prop | `PROP_[name]_v#` | `PROP_stamp_v1` |
| Background | `BG_[name]_v#` | `BG_parkinglot_v1` |
| UI / on-frame | `UI_[name]_v#` | `UI_towed_stamp_v1` |
| Effect | `FX_[name]_v#` | `FX_impact_star_v1` |
| Video (finished) | `IPPA_[####]_[premise]_[platform]_v#` | per Stage 2 |

Bump `_v#` **only** when a locked design genuinely changes (it should not, in Phase 1).

---

## Repository Integration

This lock is designed to slot into the existing architecture without duplicating it. It **elevates**
the art rules that were previously only inside the character-scoped
[Cast Style Guide](../characters/cast-style-guide.md) to a channel-wide standard, and it **defers** to
the existing strategy/SOP documents for business rules rather than repeating them.

**Where it sits.** `production/design/` is the new home for channel-wide **visual standards**
(as opposed to `production/characters/`, which is cast-scoped, and `production/A1-first-video/`, which is
a filled per-video artifact). The planned children above will live here as siblings.

**Documents that should reference this lock (recommended cross-links).** Additive one-line pointers
are being added in this branch to the highest-traffic entry points; the rest are recommendations for
follow-up so we don't over-edit locked docs:

| Document | Relationship | Action |
|---|---|---|
| [`docs/00-index.md`](../../docs/00-index.md) | Master doc map | Add a "Design standards" entry (done in this branch) |
| [`production/README.md`](../README.md) | Production folder map | Add `design/` to layout + quickstart pointer (done) |
| [`production/characters/cast-style-guide.md`](../characters/cast-style-guide.md) | Now a **child** of this lock (cast-scoped) | Add "governed by the Visual Identity Lock" note (done) |
| [`production/templates/visual-prompt-template.md`](../templates/visual-prompt-template.md) | Encodes this lock into prompts | Note the style prefix derives from this lock (done) |
| [`production/tools/image-generator-usage.md`](../tools/image-generator-usage.md) | Enforces this lock per tool | Add the lock to its Inputs (done) |
| [`production/templates/thumbnail-spec.md`](../templates/thumbnail-spec.md) | Inherits palette/rendering | Recommend adding a pointer (follow-up) |
| [`V1/08-series-bible.md`](../../V1/08-series-bible.md) | Restates locked visual style for non-technical creators | Recommend a "power-user" pointer to this lock (follow-up) |

**Reconciliation — palette (important).** The
[Stage 1.5 Channel DNA](../../docs/11-stage-1_5-business-decisions.md) table lists an *early* brand
palette with three hexes that differ from the palette actually used everywhere in the production layer
and V1 package:

| Role | Stage 1.5 (early) | **Canonical (this lock, used in production + V1)** |
|---|---|---|
| Warm base | `#FAF7F0` | **`PAPER #FFF7E0`** |
| Teal accent | `#00C2A8` | **`POP_TEAL #2FB6A3`** |
| Red/coral accent | `#FF4D4D` (coral) | **`ALERT_RED #E4322B`** |
| Yellow / ink | `#FFD400` / `#1A1A1A` | identical ✓ |

The **production values are canonical** because they are the ones consistently used across
[`cast-style-guide.md`](../characters/cast-style-guide.md), every `V1/` file, the
[`visual-prompt-template.md`](../templates/visual-prompt-template.md),
[`image-generator-usage.md`](../tools/image-generator-usage.md),
[`thumbnail-spec.md`](../templates/thumbnail-spec.md), and the
[`asset-manifest.md`](../A1-first-video/04-asset-manifest.md). To respect the locked-decision status of
Stage 1.5, this lock does **not** rewrite that historical table; instead it records the reconciliation
here and **recommends** a one-line pointer be added to the Stage 1.5 palette row directing readers to
this document as the live source of truth (see [Change Control](#change-control)).

---

## Change Control

This is a **locked** document. Because the values here are inherited by every downstream asset, changes
are governed like any other locked decision in the repo (see the
[Locked Roadmap](../../docs/03-locked-roadmap.md) and [Decision Log](../../docs/21-decision-log.md)).

- **Editorial changes** (clarifications, added examples, new cross-links) may be made freely and do
  **not** bump the identity version.
- **Substantive changes** (palette hex, outline weight, proportions, adding/removing an accent color,
  changing a cast silhouette) require:
  1. A rationale recorded in the [Decision Log](../../docs/21-decision-log.md).
  2. A pass through the [Stage 2 5-Gate test](../../docs/12-stage-2-channel-operating-system.md)
     (does it protect speed, reuse, originality/monetization?).
  3. A version bump of this document **and** any affected asset `_v#`.
- **New colors or tokens** must be added to the [Color System](#color-system) here *before* they may
  appear in any prompt or asset.

> **Design consistency is not a preference here — it is the product.** When in doubt, choose the option
> that keeps a future video visually identical to the first one.
