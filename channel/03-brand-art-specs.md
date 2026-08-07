# Brand Art Specs — icon, banner, watermark, wordmark

> **What this file is:** exact technical specs plus ready-to-paste generation prompts.
> **What it is not:** the finished image files. I can't generate images — you run the prompts below in
> your image generator ([Stage 1.5 tool stack](../docs/11-stage-1_5-business-decisions.md)) and drop
> the outputs into `channel/assets/`.

All visual decisions defer to the
[Visual Identity Lock](../production/design/VISUAL_IDENTITY_LOCK.md). Nothing here overrides it.

## Palette reference (from the locked Visual Identity Lock)

| Token | Hex | Use in brand art |
|---|---|---|
| `INK` | `#1A1A1A` | All outlines, wordmark fill |
| `BRAND_YELLOW` | `#FFD400` | Icon background, primary accent |
| `PAPER` | `#FFF7E0` | Banner field, PIP's body |
| `TEAL` | `#2FB6A3` | PIP's scarf, the left `P` |
| `ALERT_RED` | `#E4322B` | Sparingly — accents only |

Outline weight, flat rendering (no gradients, no drop shadows, no light source), and chunky
proportions are **locked** — see the
[Visual Identity Lock rendering rules](../production/design/VISUAL_IDENTITY_LOCK.md).

---

## 1. Channel icon (profile picture)

The single highest-leverage asset you own. It appears next to every Short in the feed at roughly
thumbnail-of-a-thumbnail size, so it must survive brutal downscaling.

| Spec | Value |
|---|---|
| Upload size | **800 × 800 px**, square |
| Displayed as | A **circle**, baseline render 98 × 98 px (higher-res served on retina) |
| Format | PNG (or non-animated GIF). No animation. |
| File size | Keep under 4 MB — in practice this will be well under 200 KB |
| Safe zone | Keep everything critical inside a **centred circle at ~90% of the canvas** — the corners get cropped away |

**Design (locked by the [Series Bible](../V1/08-series-bible.md): "feature PIP … in the channel icon"):**

- PIP's **head and shoulders only**, centred, filling ~75% of the circle.
- Flat `PAPER` head, `INK` outline at the locked weight, two large `INK` eyes, `TEAL` scarf visible
  at the bottom edge.
- Solid `BRAND_YELLOW` background. No gradient, no vignette, no border ring.
- Expression: warm, slightly hopeful — the "before the twist" look, not the shocked one. This is the
  face people should feel affection for.
- **No text.** The `IPPA` wordmark will not read at 98 px and stealing space from PIP's face makes
  both illegible.

**Generation prompt:**

```
Flat 2D vector cartoon channel icon, square 1:1, centered composition.
Subject: head and shoulders of a small round friendly cartoon character —
perfectly round off-white head (#FFF7E0), two large solid black oval eyes,
tiny simple smile, wearing a teal scarf (#2FB6A3) visible at the bottom edge.
Warm, hopeful, gentle expression.
Style: flat color only, NO gradients, NO shading, NO drop shadows, NO texture,
NO light source. Uniform thick black outline (#1A1A1A) on every shape.
Chunky simplified proportions, high contrast, bold and readable at very small sizes.
Background: solid flat brand yellow (#FFD400), edge to edge, no border, no ring.
Character fills about 75 percent of the frame, centered, with even margin.
Must remain legible when scaled down to 98x98 pixels and cropped to a circle.
```

**Acceptance test:** scale your export to 48 × 48 px and look at it. If you can't tell it's a
character with a scarf, reject it and simplify further.

---

## 2. Channel banner

One image, sliced differently per device. The full 2560 × 1440 is only ever seen on TV; mobile sees
the narrow centre strip.

| Spec | Value |
|---|---|
| Upload size | **2560 × 1440 px** (recommended) |
| Minimum | 2048 × 1152 px |
| **Text/logo safe area** | **1546 × 423 px**, centred |
| Ultra-safe area | ~1235 × 338 px centred — keep truly critical elements here |
| Format | JPG, PNG, non-animated GIF, or BMP |
| File size | Under 6 MB |

**Layout:**

| Zone | Contents |
|---|---|
| **Centre (inside 1546 × 423)** | The `IPPA` wordmark, large, `INK` on `PAPER`. Tagline **The jerk always gets it.** beneath it, much smaller. Nothing else. |
| **Left of safe area** | PIP, full body, small, looking right toward the wordmark |
| **Right of safe area** | CHIEF, full body, larger, chest out, smug, looking left — and *not* noticing the tow hook / hazard entering from the far right edge |
| **Full field** | Flat `PAPER` background, one wide `BRAND_YELLOW` horizontal band behind the wordmark |

The composition *is* the format: underdog on one side, arrogance on the other, karma arriving
off-frame. A visitor understands the channel before reading a word.

**Generation prompt:**

```
Flat 2D vector cartoon YouTube banner, wide landscape 16:9, 2560x1440.
Background: solid flat cream (#FFF7E0) with one wide horizontal brand-yellow
band (#FFD400) running across the vertical center.
LEFT THIRD: a small round friendly cartoon character, off-white body, large
black eyes, teal scarf (#2FB6A3), standing, facing right, hopeful expression.
RIGHT THIRD: a larger rotund pompous cartoon officer character, teal jacket,
peaked cap, yellow medal sash, tiny mustache, chest puffed out, smug closed-eye
expression, facing left. Behind him at the extreme right edge, a black tow-hook
shape entering the frame that he has not noticed.
CENTER: leave completely empty for text overlay. No characters, no props, no
detail in the central horizontal strip.
Style: flat color only, NO gradients, NO shading, NO drop shadows, NO texture.
Uniform thick black outlines (#1A1A1A). Chunky simplified proportions.
Generous negative space. High contrast.
```

Then add the wordmark and tagline as **vector text in the centre**, not as part of the generated
image — generators render text unreliably, and you need it crisp and exactly centred.

---

## 3. Wordmark

| Spec | Value |
|---|---|
| Letterforms | `IPPA`, all caps, heavy weight, **rounded** terminals — soft closed curves, matching the locked "friendly, advertiser-safe signature" |
| Fill | `INK` on light fields; `PAPER` when reversed out of `BRAND_YELLOW` |
| Tracking | Slightly loose — the two adjacent `P`s need breathing room |
| The gag | The two central `P`s are **mirrored back-to-back**. Left `P` bowl tinted `TEAL` (PIP), right `P` bowl tinted `BRAND_YELLOW` (CHIEF's sash). |
| Never | No gradients, no bevel, no outline-on-outline, no italic, no drop shadow |

Produce two lockups and keep both:

1. **Horizontal** — `IPPA` on one line. Banner, headers, end cards.
2. **Stacked** — `IPPA` over the tagline. Merch, thumbnails, square crops.

Choose a heavy geometric rounded sans as the base (the free **Nunito ExtraBold** or **Baloo 2** are
both good starting points), then manually mirror the second `P`. Don't pay for a typeface at Phase 1.

---

## 4. Video watermark

| Spec | Value |
|---|---|
| Size | 150 × 150 px |
| Format | PNG with transparency |
| File size | Under 1 MB |
| Design | The mirrored double-`P` monogram in solid `INK`. Not PIP's face — too detailed at this size. |

> **Honest note:** the branding watermark generally does **not** appear during Shorts playback. For a
> Shorts-only Phase 1 channel this is close to a no-op. Set it once so it's ready for the Phase 2
> long-form expansion ([Future Expansion](../docs/32-future-expansion.md)) and don't spend design
> time on it now.

---

## 5. Thumbnails

Shorts in the Shorts feed use a frame from the video, not a custom thumbnail — but the thumbnail
still governs how the video appears on your **channel page**, in search, and in suggested feeds.

Follow the existing [thumbnail spec](../production/templates/thumbnail-spec.md) and the
[A1 publish package](../production/A1-first-video/08-publish-package.md) worked example. Summary:

- Export one 1080 × 1920 vertical still, plus a 1280 × 720 centre crop for the channel grid.
- Grab a frame from the tension beat, **not** the reveal — never spoil the twist.
- Optional text: ≤ 3 words, `INK` on a `BRAND_YELLOW` pill, never covering a face.
- Feature PIP or CHIEF's shocked face.

---

## File organisation

```
channel/assets/
├── icon/       IPPA_icon_800.png
├── banner/     IPPA_banner_2560x1440.png
├── wordmark/   IPPA_wordmark_horizontal.svg
│               IPPA_wordmark_stacked.svg
│               IPPA_monogram_PP.svg
└── watermark/  IPPA_watermark_150.png
```

Keep editable sources (`.svg`, `.afdesign`, `.fig`) alongside exports. Per the
[Visual Identity Lock naming rules](../production/design/VISUAL_IDENTITY_LOCK.md), brand art sits
outside the per-video `IPPA_[####]…` namespace — it is channel-level, not episode-level.
