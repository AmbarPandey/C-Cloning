# v3 — Image-Generation Reference ("One Block Too Many")

> Everything the image AI needs for v3: locked house style, characters, their reactions, the
> surroundings, and a **ready-to-paste prompt for each of the 8 shots** (aligned to the master
> timeline in `01-video-script.md`). For the full reusable vocabulary see the repo-root
> [`IMAGE-GEN-REFERENCE.md`](../IMAGE-GEN-REFERENCE.md); this file is the v3-specific subset.

---

## 0. Global style prefix — PREPEND TO EVERY PROMPT (do not edit)
```
Flat-color 2D cartoon, thick uniform black outlines, no gradients, minimal single-tone shading,
chunky 2.5-head proportions, high-contrast, clean vector look, 9:16 vertical, mobile-legible.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text unless specified. Advertiser-safe, no gore.
```
**Consistency rule:** reuse the same `CHAR_CHIEF_v1` / `CHAR_PIP_v1` reference sheets generated for v1
and v2 — attach them as reference images/seeds on every shot so the cast stays on-model across the series.

**Vertical framing note:** v3 is a *height* story in a 9:16 frame — the tallest shots (C4–C6) must keep
the spire readable by letting it exit the top of frame rather than shrinking the cast. Never crush the
characters to fit the tower in.

---

## 1. Characters (lock these; reuse every shot)

**CHIEF — overreaching braggart / antagonist** (`CHAR_CHIEF_v1`)
```
Short rotund puffed-up warden-type, ~2.5 heads tall, big head, small legs, chest out, chin high.
POP_TEAL #2FB6A3 jacket with gold buttons, oversized peaked cap with a badge, a diagonal
BRAND_YELLOW #FFD400 sash covered in medals, oversized white gloves, bushy brows, tiny mustache,
permanent smug half-smile, small eyes, face PAPER #FFF7E0, INK #1A1A1A outline.
Silhouette signature (NEVER omit, NEVER transfer): cap + sash + medals. Default face: smug.
```

**PIP — careful underdog / protagonist** (`CHAR_PIP_v1`)
```
Tiny soft rounded underdog, ~2 heads tall, big head, oversized expressive eyes, tiny mouth, soft
brows, little stub limbs, gentle timid slouch. Body PAPER #FFF7E0, simple tee, a tiny POP_TEAL
#2FB6A3 scarf (signature — present in EVERY shot), INK #1A1A1A outline. Default face: worried.
```

> **Costume lock:** CHIEF's cap/sash/medals are **costume, not props** — they stay on him even in the
> rubble (cap knocked askew is allowed and encouraged; removal is not).

**Status rule:** CHIEF reads bigger/higher/more open in C1–C6 — and in v3 that is literal, since he
physically climbs above PIP. **This inverts in C7–C8**, where he ends up at ground level buried in
blocks while PIP stands upright beside an intact tower.

---

## 2. Reactions used in v3 (face + body per beat)

| Clip | CHIEF face → pose | PIP face → pose |
|---|---|---|
| C1 | `smug` → `strut` | `worried` → `idle` (sizing up the line) |
| C2 | `gloating` → `hold` (slapping the crooked block down) | `determined` → `ponder` (careful placement) |
| C3 | `gloating` → `hold` (stacking past the line) | `neutral` → `stand` (steps back, content) |
| C4 | `triumphant` → `reach`/`hold` (climbing, planting flag) | `worried` → `leanin` (eyeing the wobble) |
| C5 | `triumphant` (L3) → `victory` (trophy raised at summit) | — (small, low in frame) |
| C6 | `smug`/oblivious → `victory` hold | `hopeful` → `leanin` |
| C7 | `shocked` → `panicked` (3-stage snap) → `flail` (falling) | `gleeful` (L3) → `celebrate` |
| C8 | `sheepish` → `slump` (buried to the neck, cap askew) | `relieved` → `relaxed` + `wave` |

---

## 3. Surroundings / environment (v3 location)

**Contest Yard** (`BG_contestyard_v1`) — new asset
```
BG_contestyard_v1: wide flat-2D open contest yard. Ground flat PAPER #FFF7E0 with a simple INK
groundline, backdrop flat SKY #BFE3F2. Two low ASPHALT #6E7076 platforms side by side in the
mid-ground. Background: a plain low fence line and simple bunting flag shapes, desaturated, NO people
and NO crowd. Deliberately plain and quiet, lower-contrast than the cast, generous negative space,
no text. Default: afternoon, clear (bright flat midday).
```
- **Sub-views:** `BG_contestyard_wide_v1` (both platforms + post), `BG_contestyard_base_v1` (low insert on the crooked block), `BG_contestyard_summit_v1` (sky-heavy plate for the summit shots).
- **Depth layers:** fg = ground + platform edges; mg = the two towers, the measuring post, the cast; bg = flat fence, bunting, sky.
- **Continuity:** the **measuring post with its red band** holds the same screen position and the same band height across C1, C3, C6, C7, C8; the two platforms never move; the horizon line height is constant; C8 reuses the exact C1 plate for the loop seam.
- **No incidental characters ever** — no crowd, no judge on screen (the red line *is* the judge).

---

## 4. Props (v3 set)
| Prop | ID | Note |
|---|---|---|
| Stacking blocks | `PROP_blocks_v1` | Chunky rounded blocks, `PAPER` + `POP_TEAL` only (kept off-yellow so the trophy stays the single focal hit) |
| **Measuring post** | `PROP_measurepost_v1` | **The seed** — `ASPHALT` post with a bright `ALERT_RED` target band and a `BRAND_YELLOW` arrow pointing at it |
| **Crooked block** | `PROP_block_crooked_v1` | The callback seed — visibly off-square at CHIEF's tower base; the block that buckles |
| Giant trophy | `PROP_trophy_v1` | Hero prop, `BRAND_YELLOW`, comically oversized. Reused from v2 |
| Side table | `PROP_table_v1` | Small plain table the trophy starts on |
| CHIEF's summit flag | `PROP_flag_small_v1` | Little flag he plants on top; droops in C8 |
| FX | `FX_motionlines_v1`, `FX_sparkle_v1` (C5), `FX_confetti_v1` (C5), `FX_impact_star_v1` (C7), `FX_dustpuff_v1` (new, C7), `FX_wobble_v1` (new: flat arc lines for the sway/creak) | benign, flat, no blur/glow |

**Palette discipline:** the **trophy and the arrow are the only `BRAND_YELLOW`** in the frame — that keeps
the eye on the prize and the goal. Blocks stay `PAPER`/`POP_TEAL`. `ALERT_RED` is reserved exclusively for
the target band, so red always means "the line."

---

## 5. Per-shot render prompts (paste-ready)

**Shot C1 — Hook + seed (0:00–0:02) · WIDE.EYE.STATIC**
```
{style prefix} Wide vertical flat-2D contest yard, flat PAPER ground, flat SKY backdrop, a plain low
fence and bunting in the background (no crowd). Two low ASPHALT platforms side by side. Between them a
tall ASPHALT measuring post with a bright ALERT_RED horizontal target band at a modest height and a
BRAND_YELLOW arrow pointing directly at that band. A small plain table at the side holds a giant
BRAND_YELLOW trophy. On the left platform: tiny PIP (PAPER body, POP_TEAL scarf, big worried eyes)
standing beside a neat stack of chunky PAPER and POP_TEAL blocks, looking up at the red band. Entering
from the left: a pompous round CHIEF (POP_TEAL jacket, oversized peaked cap with badge, diagonal
BRAND_YELLOW medal sash, tiny mustache, smug) strutting in, chest out. Calm balanced composition.
This exact framing repeats at the end. No text.
```

**Shot C2 — Setup (0:02–0:06) · MED.EYE.PUSHIN**
```
{style prefix} Medium two-shot across both platforms. On the left PIP carefully places a single chunky
block, checking it level, determined and precise. On the right CHIEF sneers at him and slaps his first
block down VISIBLY CROOKED and off-square on his platform, already dropping a second block on top of
it. The crooked block is clearly the weak point. The measuring post with its ALERT_RED band and
BRAND_YELLOW arrow stands between them. No text.
```

**Shot C3 — Escalation 1 (0:06–0:11) · WIDE.EYE.STATIC**
```
{style prefix} Wide. Two block towers rising from the two platforms. PIP's tower is neat and perfectly
plumb, its top block sitting exactly FLUSH with the ALERT_RED target band on the post — PIP steps back,
content, neutral expression. CHIEF's tower already leans slightly and has been stacked straight PAST
the red band, and he is still adding blocks, gloating. No text.
```

**Shot C4 — Escalation 2 (0:11–0:16) · MED-WIDE.EYE.TILT-UP**
```
{style prefix} Medium-wide tilting up. CHIEF's block tower is now an absurd, swaying spire climbing far
above the ALERT_RED band and exiting the top of the frame, with flat FX_wobble arc lines showing the
sway. CHIEF has scrambled to the summit and is planting a little flag, arms wide, triumphant. Tiny PIP
far below beside his short, neat, plumb tower, looking up worried at the wobble. No text.
```

**Shot C5 — Anticipation / the false victory (0:16–0:22) · FULL.LOW.PUSHIN**
```
{style prefix} Low hero angle, sky-heavy. At the summit of his towering block spire CHIEF holds the
giant BRAND_YELLOW trophy raised high in one hand and his little flag in the other, locked in an
enormous over-the-top victory pose, chest out, beaming triumphantly. Flat FX_confetti shapes drifting
down and FX_sparkle accents around him. Everything reads as total victory. Dramatic empty SKY negative
space. No text.
```

**Shot C6 — Pattern break (0:22–0:27) · CU→TILT.LOW.STATIC**
```
{style prefix} Low static insert close on the BASE of CHIEF's tower: the single CROOKED block is
visibly buckling and shifting under the weight, with small flat stress lines and a trickle of dust
particles. The stack of blocks above it leans. Tense and quiet. Include tiny PIP at the edge of frame
looking up, hopeful, eyes widening. High above and small, CHIEF still frozen in his victory pose,
oblivious. Emphasise the failing crooked block as the subject. No text.
```

**Shot C7 — Twist / false victory revealed (0:27–0:31) · WIDE.EYE.PUNCHIN**
```
{style prefix} Punch-in wide. CHIEF's block spire COLLAPSING — chunky blocks cascading outward in a
flat tumble with FX_dustpuff and FX_motionlines, CHIEF falling among them, arms flailing, face
shocked and panicked, his giant BRAND_YELLOW trophy launched out of his hands in an arc. The trophy
lands neatly on top of PIP's short tower, which is STILL STANDING perfectly plumb and flush with the
ALERT_RED target band. PIP gleeful, celebrating. Big flat FX_impact_star behind the collapse. No
blocks touching or endangering PIP. No text.
```

**Shot C8 — Payoff / loop seam (0:31–0:32) · WIDE.EYE.STATIC (== C1)**
```
{style prefix} Wide composition IDENTICAL in framing, background plate and horizon line to shot C1.
CHIEF is now buried up to his neck in a heap of his own chunky collapsed blocks on the right platform,
cap knocked askew, looking sheepish, his little flag drooping beside him — still wearing his sash and
medals. On the left platform PIP stands beside his short, neat, intact tower, still exactly flush with
the ALERT_RED band, the giant BRAND_YELLOW trophy sitting on top of it, giving a small friendly wave
to camera with a relieved smile. Calm resolved mood. No text.
```

---

## Renderer notes
- C1 and C8 **must** share an identical background plate, framing and horizon (loop seam) — only the towers, trophy and cast states change.
- The **red band height must be pixel-consistent** across C1, C3, C6, C7, C8 — the entire twist depends on the audience trusting that line.
- PIP's tower must read as **exactly flush** with the band in C3, C7 and C8 (not near it — flush).
- The **crooked block** must be legibly off-square in C2 and identifiable as the same block in C6 and in the C8 rubble.
- Sell C5 as a **complete, convincing victory** — trophy, confetti, full pose. If it looks tentative, the twist has nothing to invalidate.
- **Zero on-frame text** anywhere in v3 — the red band + arrow carry the goal.
- Never transfer CHIEF's cap/sash/medals; never drop PIP's teal scarf; never restyle or reproportion the cast.
- No blur, glow, gradients or realistic lighting; motion is flat lines + offset ghost silhouettes only.
- **Advertiser-safe:** blocks are soft and chunky, the landing is comic, and **no block ever hits or threatens PIP**. No injury, no pain, no distress — CHIEF is embarrassed, not hurt.
