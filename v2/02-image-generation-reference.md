# v2 — Image-Generation Reference ("The Victory Lap")

> Everything the image AI needs for v2: locked house style, characters, their reactions, the new
> surroundings, props, and a **ready-to-paste prompt for each of the 8 shots** (aligned to the master
> timeline in `01-video-script.md`). Series-wide vocabulary lives in the repo-root
> [`IMAGE-GEN-REFERENCE.md`](../IMAGE-GEN-REFERENCE.md); this file is the v2-specific subset.

---

## 0. Global style prefix — PREPEND TO EVERY PROMPT (do not edit)
```
Flat-color 2D cartoon, thick uniform black outlines, no gradients, minimal single-tone shading,
chunky 2.5-head proportions, high-contrast, clean vector look, 9:16 vertical, mobile-legible.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text unless specified. Advertiser-safe, no gore.
```
**Consistency rule:** reuse the same `CHAR_CHIEF_v1` / `CHAR_PIP_v1` reference sheets generated for v1
— attach them as reference images/seeds on every shot so the cast stays on-model across the series.

**Speed without blur:** the house style forbids gradients and blur. Render velocity with **flat motion
lines, repeated flat ghost silhouettes (2–3 offset copies), and hard-edged smear shapes** — never
gaussian/motion blur, never glow.

---

## 1. Characters (identical to v1 — do not restyle)

**CHIEF — self-declared champion / antagonist** (`CHAR_CHIEF_v1`)
```
Short rotund puffed-up warden-type, ~2.5 heads tall, big head, small legs, chest out, chin high.
POP_TEAL #2FB6A3 jacket with gold buttons, oversized peaked cap with a badge, a diagonal
BRAND_YELLOW #FFD400 sash covered in medals, oversized white gloves, bushy brows, tiny mustache,
permanent smug half-smile, small eyes, face PAPER #FFF7E0, INK #1A1A1A outline.
Silhouette signature (NEVER omit, NEVER transfer): cap + sash + medals. Default face: smug.
```

**PIP — underdog challenger / protagonist** (`CHAR_PIP_v1`)
```
Tiny soft rounded underdog, ~2 heads tall, big head, oversized expressive eyes, tiny mouth, soft
brows, little stub limbs, gentle timid slouch. Body PAPER #FFF7E0, simple tee, a tiny POP_TEAL
#2FB6A3 scarf (signature — present in EVERY shot), INK #1A1A1A outline. Default face: worried.
```

> **Costume lock:** CHIEF's cap/sash/medals are **costume**, never props — PIP must never wear them.
> The reversal is carried by **position + transferable props only** (podium, trophy, medal, ribbon).

**Status rule:** CHIEF reads bigger/higher/more open in C1–C6; **this inverts in C7–C8**, where PIP is
higher (on the podium) and more open, and CHIEF is lower, smaller in frame, and closed/slumped.

---

## 2. Reactions used in v2 (face + body per beat)

| Clip | CHIEF face → pose | PIP face → pose |
|---|---|---|
| C1 | `smug` → `strut` (wheeling scooter, trophy under arm) | `worried` → `idle` (on skates) |
| C2 | `gloating` → `point` (after planting trophy, flicking ribbon) | `worried` → `shrink` |
| C3 | `triumphant` → `sit`+`hold` (riding, launch) | `determined` → `walk` (slow roll) |
| C4 | `gloating` (peak) → `sit`+`hold` (stacking boosters) | `determined` → `walk` |
| C5 | `triumphant` (L3) → `victory` (airborne, chest out) | — (tiny, low in frame) |
| C6 | `smug`/oblivious → `victory` hold (shrinking away) | `hopeful` → `leanin` |
| C7 | `shocked` → `panicked` (3-stage snap) → `recoil` | `gleeful` (L3) → `celebrate` |
| C8 | `sheepish` → `slump` | `relieved` → `relaxed` + `wave` |

---

## 3. Surroundings / environment (new v2 location)

**Race Track** (`BG_racetrack_v1`) — new asset
```
Wide flat-2D open race track. Ground ASPHALT #6E7076 lane with simple INK lane lines, backdrop flat
SKY #BFE3F2. Background: flat empty grandstand shapes (NO people, NO crowd) and simple bunting flag
shapes, all desaturated. A checkered start line (INK + PAPER squares) in the near foreground.
Deliberately plain and quiet, lower-contrast than the cast, generous negative space, no text.
Time: bright flat afternoon, clear.
```
- **Sub-views:** `BG_racetrack_start_v1` (start line), `BG_racetrack_finish_v1` (finish tape + podium), `BG_racetrack_wide_v1` (full track for the flight).
- **Continuity locks:** the **low finish tape** and the **podium** hold the same screen position across C1, C6, C7, C8. The horizon line height is constant in every shot. C8 reuses the exact C1 plate.
- **Depth:** fg = start line + ground; mg = cast, tape, podium; bg = flat grandstand + sky.
- **No incidental characters ever** (grandstands stay empty — a locked environment rule).

---

## 4. Props (v2 set)
| Prop | ID | Note |
|---|---|---|
| CHIEF's rocket scooter | `PROP_chief_racer_v1` | Racing variant of his scooter — new |
| Rocket booster | `PROP_booster_v1` | Stackable ×4, `ALERT_RED` body + `BRAND_YELLOW` flame — new |
| PIP's roller skates | `PROP_skates_v1` | Tiny, humble — new |
| **Low finish tape** | `PROP_finishtape_v1` | **SEED A** — checkered tape strung at PIP's chest height. Must read clearly as *low* — new |
| Giant trophy | `PROP_trophy_v1` | Hero prop, `BRAND_YELLOW`, comically oversized — new |
| Champion medal | `PROP_medal_champion_v1` | Transferable award (NOT CHIEF's costume sash) — new |
| **Participation ribbon** | `PROP_ribbon_participation_v1` | **SEED B** — small, drab `ASPHALT`-grey, deliberately pathetic — new |
| Start flag | `PROP_startflag_v1` | Checkered flag, drops in C3 — new |
| Podium | `PROP_podium_v1` | Reused from v1 |
| FX | `FX_motionlines_v1`, `FX_sparkle_v1`, `FX_impact_star_v1`, `FX_confetti_v1` (new), `FX_ghostsmear_v1` (new: flat offset silhouettes for speed) | benign, flat, no blur/glow |

**Palette discipline:** `BRAND_YELLOW` is reserved for the hero prop (the trophy) and booster flames —
keep one dominant yellow focal hit per frame. The participation ribbon must stay drab `ASPHALT` so the
status contrast against the golden trophy is instantly readable.

---

## 5. Per-shot render prompts (paste-ready)

**Shot C1 — Hook + seeds (0:00–0:03) · WIDE.EYE.STATIC**
```
{style prefix} Wide vertical flat-2D race track, ASPHALT lane, flat SKY backdrop, empty flat
grandstand shapes and bunting in the background (no crowd). Checkered start line in the near
foreground. At the line: tiny PIP (PAPER body, POP_TEAL scarf, big worried eyes) standing on small
roller skates. Beside him a pompous round CHIEF (POP_TEAL jacket, oversized peaked cap with badge,
diagonal BRAND_YELLOW medal sash, tiny mustache, smug) strutting in, wheeling a rocket-powered
scooter, a giant BRAND_YELLOW trophy tucked under one arm. Mid-frame at the far end: a checkered
finish tape strung LOW, at PIP's chest height, and a small podium with a drab grey participation
ribbon pinned to it. Calm balanced composition. This exact framing repeats at the end. No text.
```

**Shot C2 — False comfort (0:03–0:07) · MED.EYE.PUSHIN**
```
{style prefix} Medium two-shot at the start line. CHIEF has planted the giant BRAND_YELLOW trophy on
the small podium as if he has already won, and is flicking the drab grey participation ribbon off the
podium with one oversized glove so it flutters toward PIP, while pointing at PIP mockingly, gloating.
PIP shrinking, worried, on his tiny skates. No text.
```

**Shot C3 — Escalation 1 (0:07–0:12) · WIDE.EYE.WHIP→STATIC**
```
{style prefix} Wide track. A checkered start flag drops. CHIEF blasts off on his rocket scooter, a
single ALERT_RED booster firing a BRAND_YELLOW flame, rendered as a flat smear with hard-edged motion
lines and 2-3 offset flat ghost silhouettes (NO blur, NO glow). Tiny PIP just beginning a slow
determined roll on his skates near the start line. Low finish tape still visible far ahead. No text.
```

**Shot C4 — Escalation 2 (0:12–0:18) · MED-WIDE.EYE.PUSHIN(slight)**
```
{style prefix} Medium-wide. CHIEF mid-track on his scooter, comically stacking FOUR ALERT_RED rocket
boosters onto it, BRAND_YELLOW flames blasting, wheels lifting off the ASPHALT, face in a peak gloat,
chest out. Flat motion lines and offset ghost silhouettes convey extreme speed. Far behind, tiny PIP
still rolling steadily, determined. No text.
```

**Shot C5 — Anticipation / peak overconfidence (0:18–0:23) · FULL.LOW.PUSHIN → HOLD**
```
{style prefix} Low hero angle. CHIEF fully AIRBORNE on his four-booster rocket scooter, nose tipped
upward, rising off the track, chest out in an over-the-top victory pose, BRAND_YELLOW flames trailing,
FX_sparkle accents and flat trailing ghost smears. Dramatic empty SKY negative space around him. The
low checkered finish tape sits small and far below-ahead of his flight path. No text.
```

**Shot C6 — Pattern break (0:23–0:27) · WIDE.EYE.STATIC (deep flat focus)**
```
{style prefix} Wide static shot, tense and quiet. The low checkered finish tape stands UNTOUCHED and
intact in the mid-foreground, swaying gently. Above and beyond it, CHIEF is flying away, small,
shrinking toward the horizon, still frozen in his proud victory pose, oblivious. Far to the left,
tiny PIP rolls onward on his skates, looking up with dawning hope, eyes widening. Emphasise that the
tape has NOT been broken. No text.
```

**Shot C7 — Twist / role reversal (0:27–0:31) · MED.EYE.PUNCHIN → PODIUM**
```
{style prefix} Punch-in medium. Tiny PIP rolls into the low checkered finish tape and BREAKS it with
his chest, the tape snapping apart, a burst of flat confetti shapes and a waving checkered flag.
Then: PIP standing proudly up on the small podium, the giant BRAND_YELLOW trophy in his arms and a
champion medal round his neck, beaming gleefully. In the far distance CHIEF has skidded to a stop and
whipped around, face shocked and panicked, arms recoiling. Big flat FX_impact_star behind the tape
snap. No text.
```

**Shot C8 — Payoff / loop seam (0:31–0:33) · WIDE.EYE.STATIC (framing == C1)**
```
{style prefix} Wide composition IDENTICAL in framing, background plate and horizon line to shot C1,
but the roles are SWAPPED. PIP now stands up on the podium holding the giant BRAND_YELLOW trophy,
champion medal on, relieved happy smile, giving a small friendly wave to camera. CHIEF now stands
deflated and slumped down in PIP's old spot at the checkered start line, his four boosters spent and
drooping, looking sheepish — still wearing his cap, sash and medals — with the drab grey
participation ribbon freshly pinned to his chest. Calm resolved mood. No text.
```

---

## Renderer notes
- **C1 and C8 must share an identical background plate, framing and horizon** — only the characters and their props change (the swapped-role loop seam).
- Keep the **low finish tape** unmistakably low (chest height for PIP) in C1, C5, C6 — the whole twist depends on the audience registering it.
- In C6 the tape must read as **visibly intact and untouched**; that stillness is the joke.
- **Never** transfer CHIEF's cap/sash/medals to PIP; **never** drop PIP's teal scarf.
- **Zero on-frame text** anywhere in v2 — checkered patterns carry "start/finish" globally.
- No blur, glow, gradients, or realistic lighting; speed is flat motion lines + offset ghost silhouettes only.
- Grandstands stay **empty** — no incidental characters or crowds.
- Advertiser-safe: CHIEF overshoots and returns unharmed; no crash, damage, or injury.
