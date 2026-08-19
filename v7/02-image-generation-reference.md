# v7 — Image-Generation Reference ("The Big One") · **SHORTS 9:16**

> Everything the image AI needs for v7: locked house style, characters, their reactions, the
> surroundings, and a **ready-to-paste prompt for each of the 8 shots** (aligned to the master
> timeline in `01-video-script.md`). For the full reusable vocabulary see the repo-root
> [`IMAGE-GEN-REFERENCE.md`](../IMAGE-GEN-REFERENCE.md); this file is the v7-specific subset.

---

## 0. Global style prefix — PREPEND TO EVERY PROMPT (do not edit)
```
Flat-color 2D cartoon, thick uniform black outlines, no gradients, minimal single-tone shading,
chunky 2.5-head proportions, high-contrast, clean vector look, 9:16 vertical, mobile-legible.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text unless specified. Advertiser-safe, no gore.
```
**Consistency rule:** reuse the `CHAR_CHIEF_v1` / `CHAR_PIP_v1` sheets from v1–v6 — attach them as
reference images/seeds on every shot so the cast stays on-model across the series.

### ⚠️ Water and rain in this house style
The style forbids gradients, blur, glow and transparency. **All water is a hard-edged flat `SKY` shape:**
- **Rain** = short straight flat `SKY` dashes at a consistent angle. Never streaked, never blurred.
- **Trickle** = one thin continuous flat `SKY` ribbon with an `INK` outline.
- **Pour** = the same ribbon, thicker.
- **Pool inside the canopy** = a flat `SKY` shape whose area grows in visible stages.
- **The dump** = one large flat `SKY` mass with an `INK` outline.
- **Splashes** = small flat starburst/teardrop shapes. No spray, no particles, no mist.
- **Wet character** = flat drooping shape changes and a few flat drip shapes. **No shine, no gloss, no highlights.**

**Compose vertically, deliberately.** 9:16 is ideal for this story — stack the frame:
**broken gutter (top) → sagging canopy (upper-middle) → CHIEF (middle) → pavement and puddle (bottom).**
The eye should travel *down the path the water will take.*

---

## 1. Characters (lock these; reuse every shot)

**CHIEF — Bully / Antagonist** (`CHAR_CHIEF_v1`)
```
Short rotund puffed-up warden-type, ~2.5 heads tall, big head, small legs, chest out, chin high.
POP_TEAL #2FB6A3 jacket with gold buttons, oversized peaked cap with a badge, a diagonal
BRAND_YELLOW #FFD400 sash covered in medals, oversized white gloves, bushy brows, tiny mustache,
permanent smug half-smile, small eyes, face PAPER #FFF7E0, INK #1A1A1A outline.
Silhouette signature (NEVER omit, NEVER transfer): cap + sash + medals. Default face: smug.
v7 SOAKED STATE (C7-C8 only): all the same shapes, but drooping — hair flattened into a flat wet
mass, cap slumped over one eye, mustache limp and pointing down, sash sodden and hanging, medals
tilted, jacket hem drooping, a few flat drip shapes falling from his chin and cap brim. NO gloss,
NO shine, NO highlights. Same character, same colours, just sagged.
```

**PIP — Hero / Underdog** (`CHAR_PIP_v1`)
```
Tiny soft rounded underdog, ~2 heads tall, big head, oversized expressive eyes, tiny mouth, soft
brows, little stub limbs, gentle timid slouch. Body PAPER #FFF7E0, simple tee, a tiny POP_TEAL
#2FB6A3 scarf (signature — present in EVERY shot), INK #1A1A1A outline. Default face: worried.
v7 note: PIP stays COMPLETELY DRY for the entire video, including C7 and C8 — not one drop on him.
He makes exactly three movements: he is shoved (C1), he raises a hand to warn (C6), and he offers
his umbrella (C8). He NEVER gloats, smirks or points.
```

> **Costume lock:** CHIEF's cap/sash/medals are **costume, not props** — never removed, never transferred.
> Sodden and drooping is allowed and encouraged; removal is not.

**Status rule:** CHIEF reads bigger, louder and more decorated throughout, and holds the far larger object.
His status inverts by **condition**: he ends the video drenched and hunched under his victim's tiny
umbrella, having been offered kindness rather than defeated.

---

## 2. Reactions used in v7 (face + body per beat)

| Clip | CHIEF face → pose | PIP face → pose |
|---|---|---|
| C1 | `smug` → `strut` (shoves PIP aside) | `worried` → `recoil` (staggers, recovers) |
| C2 | `gloating` → `hold` (snaps the big umbrella open) | `neutral` → `stand` (calmly takes the small one) |
| C3 | `gloating` → `strut`→`hold` (plants under the gutter, twirls) | `neutral` (content) → `stand` |
| C4 | `triumphant` → `hold` (grand gestures, gloating) | `neutral` (content) → `stand` (placid blink) |
| C5 | `triumphant` (L3) → `victory` (fists on hips, chin high) | — (low/out of frame) |
| C6 | `smug` → `hold` (raises a glove: *don't interrupt*) | `worried` → `reach` (warns) → `stand` (steps back) |
| C7 | `triumphant` → `shocked` → `panicked` (3-stage snap) → `slump` | `gleeful` (L3) → `stand` (dry, delighted) |
| C8 | `sheepish` → `slump` (hunched under a tiny umbrella) | `relieved` → `reach` (offers umbrella) + `wave` |

---

## 3. Surroundings / environment (v7 location)

**Rainy Shop Front** (`BG_shopfront_v1`) — new asset
```
BG_shopfront_v1: flat-2D street shop front, composed for 9:16 VERTICAL. A PAPER #FFF7E0 shop wall
with a simple doorway occupies the middle of frame; ASPHALT #6E7076 pavement across the lower third
with simple INK joint lines. Above the doorway: a plain ASPHALT gutter with a visible BREAK and an
ALERT_RED rust crack at one point, positioned upper-middle of frame — water drips from this exact
point, and a small flat splash mark on the pavement directly below shows where it lands. Beside the
door: a simple umbrella stand. Background: flat desaturated street shapes and a flat overcast
SKY #BFE3F2 strip at the top. Rain as short straight flat SKY dashes at a consistent angle.
Quiet, lower-contrast than the cast, generous negative space, no text.
```
- **Sub-views:** `BG_shopfront_wide_v1` (full front, C1/C3/C8) · `BG_shopfront_stand_v1` (umbrella stand, C2) · `BG_shopfront_gutter_v1` (tight on the gutter + canopy, C5/C6).
- **Depth layers:** fg = pavement, puddle, splash mark; mg = the cast, umbrellas, doorway; bg = flat street, overcast sky.
- **Continuity locks (critical):**
  - **The broken gutter holds the exact same screen position in every shot** where the upper frame is visible (C1, C3, C4, C5, C6, C8), and its **splash mark on the pavement never moves** — that mark is what proves CHIEF chose to stand there.
  - **CHIEF must be standing inside that splash mark from C3 to C7.** No drift.
  - **Rain intensity increases monotonically:** light (C1) → medium (C2–C3) → heavy (C4–C7) → easing slightly (C8). Never lighter than the previous shot before C8.
  - C8 reuses the exact C1 plate for the loop seam.

---

## 4. Props (v7 set)
| Prop | ID | Note |
|---|---|---|
| **Broken gutter** | `PROP_gutter_v1` | **SEED A** — plain `ASPHALT` guttering with a break and an `ALERT_RED` rust crack. The water source. Needs drip / trickle / pour states |
| **Giant umbrella** | `PROP_umbrella_big_v1` | **SEED B + hero prop** — enormous `BRAND_YELLOW` canopy, unmistakably a **deep bowl**. Needs 6 states: closed, open-taut, sag-1, sag-2, sag-3 (distended), and limp-inverted |
| **Tiny umbrella** | `PROP_umbrella_small_v1` | Small, **flat/shallow** `POP_TEAL` canopy — the visual opposite of the big one. Its flatness is why it works |
| Umbrella stand | `PROP_umbrellastand_v1` | Simple stand holding both in C1 |
| Water pool (in canopy) | `PROP_canopypool_v1` | Flat `SKY` shape, 3 growing sizes matching the sag stages |
| Water mass (the dump) | `PROP_watermass_v1` | One large flat `SKY` shape with `INK` outline, for C7 |
| Puddle | `PROP_puddle_v1` | Shallow flat `SKY` puddle at his feet in C8, with 2 ripple rings |
| FX | `FX_raindash_v1` (new), `FX_splashpop_v1` (new), `FX_strainline_v1` (new), `FX_motionlines_v1`, `FX_sparkle_v1` (C5), `FX_impact_star_v1` (C7) | benign, flat, no blur/glow |

**Palette discipline:** `BRAND_YELLOW` is **the giant umbrella** — the object of his greed and the single
dominant focal hit in every frame, which makes the sag impossible to miss. `POP_TEAL` is PIP's umbrella and
his scarf, visually linking the small, sensible things. `ALERT_RED` appears **only** on the gutter's rust
crack — the one hazard marker in the frame, consistent with the series convention that red marks the thing
that betrays him. All water is `SKY`. The building is `PAPER`, pavement `ASPHALT`.

---

## 5. Per-shot render prompts (paste-ready)

**Shot C1 — Hook + seed (0:00–0:02) · WIDE.EYE.STATIC**
```
{style prefix} Wide vertical 9:16 flat-2D rainy street shop front. A PAPER shop wall with a simple doorway
in the middle of frame, ASPHALT pavement across the lower third. Upper-middle of frame: a plain ASPHALT
gutter above the doorway with a visible BREAK and an ALERT_RED rust crack, with a single flat SKY-blue
water drop falling from it and a small flat splash mark on the pavement directly below. Light rain as short
straight flat SKY dashes. Beside the door, an umbrella stand holding TWO umbrellas: one ENORMOUS
BRAND_YELLOW umbrella whose canopy is clearly a DEEP BOWL shape, and one TINY FLAT POP_TEAL umbrella.
A pompous round CHIEF (POP_TEAL jacket, oversized peaked cap with badge, diagonal BRAND_YELLOW medal sash,
tiny mustache, smug) is striding in from the left and SHOVING tiny PIP (PAPER body, POP_TEAL scarf, big
worried eyes) aside with one oversized white glove, his eyes on the big umbrella. Flat desaturated street
and overcast SKY behind. This exact framing repeats at the end. No text.
```

**Shot C2 — Setup (0:02–0:06) · MED.EYE.PUSHIN**
```
{style prefix} Medium 9:16 two-shot at the umbrella stand. CHIEF has just SNAPPED THE ENORMOUS
BRAND_YELLOW UMBRELLA OPEN with a big flourish — the canopy is unmistakably a DEEP BOWL, wide and
concave — and is gloating down at tiny PIP, chest out. PIP, unbothered, has calmly opened the TINY FLAT
POP_TEAL umbrella, which is shallow and almost flat by comparison. A few flat SKY raindrops bouncing off
the taut yellow canopy. Medium rain as flat SKY dashes. The broken gutter still dripping above. No text.
```

**Shot C3 — Escalation 1 (0:06–0:11) · WIDE.EYE.STATIC**
```
{style prefix} Wide vertical 9:16. Thickening rain as denser flat SKY dashes. CHIEF has planted himself
DIRECTLY BENEATH THE BROKEN GUTTER, standing squarely on the splash mark, twirling the enormous
BRAND_YELLOW umbrella and gloating across at PIP, chin high, NOT looking up. From the gutter's break above
and behind his head, a thin continuous flat SKY-blue RIBBON of water is running down INTO his big bowl-
shaped canopy. Tiny PIP stands a few steps clear under his small flat POP_TEAL umbrella, dry and content.
No text.
```

**Shot C4 — Escalation 2 (0:11–0:16) · MED-WIDE.EYE.PUSHIN(slight)**
```
{style prefix} Medium-wide 9:16. Heavy rain as dense flat SKY dashes. The broken gutter is now POURING — a
thick flat SKY ribbon — straight into CHIEF's enormous BRAND_YELLOW canopy, which is VISIBLY SAGGING: the
fabric bowed deeply downward, a large flat SKY pool of water clearly visible inside it, and the umbrella's
shaft beginning to LEAN under the weight. CHIEF is gesturing grandly at his own umbrella and then
dismissively at PIP's tiny one, chest out, triumphant, and STILL NOT LOOKING UP. Tiny PIP stands perfectly
dry under his small flat POP_TEAL umbrella, blinking placidly. No text.
```

**Shot C5 — Anticipation (0:16–0:22) · FULL.LOW.PUSHIN**
```
{style prefix} Low hero angle, vertical 9:16. CHIEF plants an enormous triumphant pose — chest out, chin
high, one oversized glove on his hip, medals gleaming, self-satisfied FX_sparkle accents around him.
Directly above him and DOMINATING THE TOP THIRD OF FRAME, the giant BRAND_YELLOW canopy is hugely
DISTENDED and straining, a heavy flat SKY pool of water bulging inside it, the shaft bowing, with a couple
of flat strain lines on the taut fabric — and the gutter's thick flat SKY ribbon still pouring into it,
indifferent. Heavy rain. He is not looking up. No text.
```

**Shot C6 — Pattern break (0:22–0:27) · MED.EYE.STATIC→TILT**
```
{style prefix} Vertical 9:16, tense and quiet. The giant BRAND_YELLOW canopy is at its absolute limit —
fabric taut with flat strain lines, shaft clearly bending, one or two flat SKY drops escaping over the
rim. Tiny PIP has stepped forward and RAISED ONE SMALL HAND to warn him, mouth open. CHIEF, without even
looking at him, has raised one oversized white glove in a dismissive DON'T-INTERRUPT gesture while still
holding his proud pose. PIP is glancing up at the bulging canopy. Heavy rain. No sparkle, no effects
beyond the strain lines. No text.
```

**Shot C7 — Twist / instant karma (0:27–0:31) · MED.EYE.PUNCHIN**
```
{style prefix} Punch-in medium, vertical 9:16. CHIEF has SWEPT the enormous BRAND_YELLOW umbrella DOWN AND
FORWARD to point mockingly at PIP — and the entire reservoir has cascaded out of the tipping canopy as ONE
LARGE FLAT SKY-BLUE WATER MASS with an INK outline, straight down OVER HIS OWN HEAD, with a flat starburst
splash on the pavement. CHIEF is completely DRENCHED: hair flattened into a flat wet mass, oversized cap
slumped over one eye, mustache limp and pointing down, sash sodden and hanging, medals tilted, jacket hem
drooping, a few flat drip shapes falling from his chin — NO gloss, NO shine, NO highlights, just sagged
shapes. His face is shocked and panicked. Two steps away, tiny PIP is COMPLETELY DRY and untouched under
his small flat POP_TEAL umbrella, delighted. Flat FX_impact_star at the ground impact. No text.
```

**Shot C8 — Payoff / loop seam (0:31–0:32) · WIDE.EYE.STATIC (== C1)**
```
{style prefix} Wide vertical 9:16 composition IDENTICAL in framing, background plate, gutter position and
pavement splash mark to shot C1. Drenched CHIEF stands in a shallow flat SKY puddle with two small ripple
rings, hunched and sheepish, hair flat, cap drooping over one eye, sash sodden, still wearing his medals,
the emptied giant BRAND_YELLOW umbrella hanging LIMP AND INVERTED from his glove. Beside him, tiny PIP is
HOLDING OUT his small flat POP_TEAL umbrella toward him — offering it plainly and kindly, no smirk, no
gloating — and CHIEF is hunching under it, far too big for it, mortified. PIP turns and gives a small
friendly wave to camera with a relieved smile. One last flat SKY drop falling from the broken gutter above.
Rain easing slightly. Calm resolved mood. No text.
```

---

## Renderer notes
- C1 and C8 **must** share an identical background plate, framing, gutter position **and pavement splash mark** (loop seam) — only the rain state, the umbrellas and the cast's condition change.
- **The position invariant is the whole video:** CHIEF stands on the gutter's splash mark from C3 to C7. Mark it on the ground plate and check every frame.
- **CHIEF never looks up before C7.** Not one frame. His obliviousness is the joke.
- **The sag is monotonic:** three visible stages in C4, maximum in C5–C6, never rebounding. The pool's area inside the canopy must always match the sag.
- **The canopy's bowl depth must be unmistakable in C2** — if it reads as a normal flat umbrella, the ending isn't fair.
- **All water is hard-edged flat `SKY` shapes.** No blur, no transparency, no gradients, no particle spray, no mist. Cartoon water here is a *shape*.
- **Soaked CHIEF has no gloss or shine** — wetness is conveyed purely by drooping shapes and a few flat drip shapes.
- **PIP is bone dry in every frame, including C7**, and **never gloats**: no smirk, no pointing, no sparkle. In C8 his kindness must read as ordinary, not saintly.
- **Zero baked-in text anywhere.**
- Never transfer CHIEF's cap/sash/medals; never drop PIP's teal scarf; never restyle or reproportion the cast.
- No camera rotation.
- **Advertiser-safe:** CHIEF is merely **wet and embarrassed** — render no shivering, chattering, coughing, illness or distress. No lightning, no storm menace, no slipping or falling injury. The shove in C1 must read as comic and soft, never violent. Rain is cheerful weather, not a threat.
