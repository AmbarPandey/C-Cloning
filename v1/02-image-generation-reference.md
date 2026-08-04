# v1 — Image-Generation Reference ("The Wrong Scooter")

> Everything the image AI needs for v1: locked house style, characters, their reactions, the
> surroundings, and a **ready-to-paste prompt for each of the 8 shots** (aligned to the master
> timeline in `01-video-script.md`). For the full reusable vocabulary see the repo-root
> [`IMAGE-GEN-REFERENCE.md`](../IMAGE-GEN-REFERENCE.md); this file is the v1-specific subset.

---

## 0. Global style prefix — PREPEND TO EVERY PROMPT (do not edit)
```
Flat-color 2D cartoon, thick uniform black outlines, no gradients, minimal single-tone shading,
chunky 2.5-head proportions, high-contrast, clean vector look, 9:16 vertical, mobile-legible.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text unless specified. Advertiser-safe, no gore.
```
**Consistency rule:** generate each character once as a reference sheet, then attach it as a
reference image/seed on every shot so the model stays on-model.

---

## 1. Characters (lock these; reuse every shot)

**CHIEF — antagonist / smug warden** (`CHAR_CHIEF_v1`)
```
Short rotund puffed-up warden, ~2.5 heads tall, big head, small legs, chest out, chin high.
POP_TEAL #2FB6A3 warden jacket with gold buttons, oversized peaked cap with a badge, a diagonal
BRAND_YELLOW #FFD400 sash covered in medals, oversized white gloves, bushy brows, tiny mustache,
permanent smug half-smile, small eyes, face PAPER #FFF7E0, INK #1A1A1A outline.
Silhouette signature (NEVER omit): cap + sash + medals. Default face: smug.
```

**PIP — protagonist / tiny underdog** (`CHAR_PIP_v1`)
```
Tiny soft rounded underdog, ~2 heads tall, big head, oversized expressive eyes, tiny mouth, soft
brows, little stub limbs, gentle timid slouch. Body PAPER #FFF7E0, simple tee, a tiny POP_TEAL
#2FB6A3 scarf (signature — present in EVERY shot), INK #1A1A1A outline. Default face: worried.
```

**Status rule:** in shared shots CHIEF always reads bigger/higher/more open; PIP smaller/lower/more closed.

---

## 2. Reactions used in v1 (face + body per beat)

| Clip | CHIEF face → pose | PIP face → pose |
|---|---|---|
| C1 | `smug` → `strut` | `worried` → `idle` (fumbling coins) |
| C2 | `gloating` → `hold` (draws stamp/pad) | `worried` → `shrink` |
| C3 | `smug` → `hold` (stamp + boot) | `teary` → `slump` |
| C4 | `triumphant`(gloat) → `stand` (medal polish) | `defeated/teary` → `slump` |
| C5 | `triumphant` (L3) → `victory` (stamp to sky) | — (off-frame or tiny, low corner) |
| C6 | `smug`/oblivious → `victory` hold | `hopeful` → `leanin` |
| C7 | `shocked` → `panicked` (3-stage snap) → `flail`/`recoil` | `gleeful` (L3) → `celebrate` |
| C8 | shrinking away (hung on scooter) | `relieved` → `relaxed` + `wave` |

---

## 3. Surroundings / environment (v1 location)

**Parking Lot** (`BG_parkinglot_v1`)
```
Wide flat-2D open orderly public parking lot. Ground ASPHALT #6E7076, backdrop flat SKY #BFE3F2,
a parking meter left, painted INK parking lines, an ALERT_RED #E4322B NO-PARKING zone in the
lower-right foreground. Deliberately plain and rule-governed. Desaturated, quieter/lower-contrast
than the cast, generous negative space, no incidental characters, no text. Time: bright flat afternoon, clear.
```
- **Continuity locks:** the red no-parking zone (with CHIEF's scooter) holds the **same lower-right screen position** across C1, C6, C7. C8 reuses the exact C1 plate for the loop seam.
- **Depth:** fg = no-parking zone + ground; mg = meter, lines, cast, podium; bg = flat empty sky.

---

## 4. Props (v1 set)
| Prop | ID | Note |
|---|---|---|
| CHIEF's scooter (the seed) | `PROP_chief_scooter_v1` | Parked in the red zone in C1; towed in C7 |
| PIP's tiny scooter | `PROP_pip_scooter_v1` | Booted in C3; freed in C8 |
| PIP's coin purse | `PROP_pip_coins_v1` | Fumbled at the meter in C1 |
| Giant rubber stamp | `PROP_stamp_v1` | CHIEF's power object; turned against him in C7 (hero prop, `BRAND_YELLOW` hit) |
| Oversized ticket pad | `PROP_ticketpad_v1` | Drawn in C2 |
| Ticket sheets | `PROP_ticket_v1` | Pile grows in C3–C4 |
| Yellow wheel boot | `PROP_boot_v1` | Clamped in C3; pops off in C8 |
| Tow truck | `PROP_towtruck_v1` | Enters C6; tows in C7 |
| Podium + flag | `PROP_podium_v1` | Victory flex in C5 |
| "TOWED" stamp mark | `UI_towed_v1` | **Only** on-frame text in the whole video (C7) |
| FX | `FX_sparkle_v1` (C5), `FX_impact_star_v1` (C7), `FX_motionlines_v1` (C3/C7) | benign, flat |

---

## 5. Per-shot render prompts (paste-ready)

**Shot C1 — Hook + seed (0:00–0:02) · WIDE.EYE.STATIC**
```
{style prefix} Wide vertical parking lot, ASPHALT ground, SKY top, parking meter left. Tiny PIP
(PAPER body, POP_TEAL scarf, big worried eyes) fumbling a coin purse at the meter beside his tiny
scooter. A pompous round warden CHIEF (POP_TEAL jacket, oversized peaked cap + badge, diagonal
BRAND_YELLOW medal sash, tiny mustache, smug) strutting in from the left, chest out. Lower-right
foreground: an ALERT_RED "NO PARKING" painted zone containing CHIEF's parked scooter. Balanced,
calm composition. This exact framing repeats at the end.
```

**Shot C2 — Setup (0:02–0:06) · MED.EYE.PUSHIN**
```
{style prefix} Medium two-shot. CHIEF grinning, pulling an oversized ticket pad and a giant rubber
stamp from his jacket, pointing at PIP's tiny scooter tire a hair over a white line. PIP shrinking, worried.
```

**Shot C3 — Escalation 1 (0:06–0:11) · MED.EYE.STATIC**
```
{style prefix} CHIEF slapping a paper ticket onto PIP's tiny scooter and clamping a bright
BRAND_YELLOW wheel boot on its wheel with a flourish, blowing on the stamp like a gunslinger.
PIP teary. FX_motionlines on the stamp.
```

**Shot C4 — Escalation 2 (0:11–0:16) · MED-WIDE.EYE.PUSHIN(slight)**
```
{style prefix} Medium-wide. A comical mountain of paper tickets piled on PIP's little scooter.
CHIEF standing proud, polishing his BRAND_YELLOW medals, chin up. PIP slumped, defeated.
```

**Shot C5 — Anticipation / peak overconfidence (0:16–0:22) · FULL.LOW.PUSHIN**
```
{style prefix} Low hero angle. CHIEF standing on a small podium, one tiny flag planted, striking an
over-the-top victory pose with the giant stamp raised triumphantly to the sky. Proud gleam,
FX_sparkle accents. Dramatic empty negative space around him.
```

**Shot C6 — Pattern break (0:22–0:27) · WIDE.EYE.STATIC (deep focus)**
```
{style prefix} Wide with flat depth. CHIEF frozen mid-victory-pose in foreground-center, oblivious.
In the background-right a cartoon TOW TRUCK rolls in, hook arm swinging toward the ALERT_RED
NO-PARKING zone (NOT toward PIP). PIP off to the side, eyes widening with hope.
```

**Shot C7 — Twist / instant karma (0:27–0:31) · WIDE.EYE.PUNCHIN**
```
{style prefix} Punch-in wide. The tow truck's hook clamps CHIEF'S OWN scooter in the NO-PARKING
zone; the truck's arm wields CHIEF's own giant stamp to slam a huge ALERT_RED "TOWED" mark on it.
CHIEF yanked off the podium, face snapping shocked/panicked, arms flailing. PIP gleeful. Big
comedic FX_impact_star burst behind the stamp. Only on-frame text: "TOWED".
```

**Shot C8 — Payoff / loop seam (0:31–0:32) · WIDE.EYE.STATIC (== C1)**
```
{style prefix} Wide composition IDENTICAL to shot C1 framing. CHIEF shrinking into the distance
right, hanging off his towed scooter, medals jangling. PIP center, calmly peeling the popped-off
boot from his scooter, giving a small friendly wave to camera, relieved smile. Calm resolved mood.
```

---

## Renderer notes
- C1 and C8 **must** share identical framing/composition (loop seam).
- Keep CHIEF's scooter in the same screen position in C1, C6, C7 (seed continuity).
- On-frame text allowed **only** on the "TOWED" stamp (C7).
- Never restyle/reproportion the cast or drop signature items (CHIEF cap+sash+medals, PIP scarf).
