# C-Cloning — Image-Generation Reference (Reusable Descriptions)

> **Purpose:** A single, paste-ready cheat sheet of every **recurring** description you feed an
> image-generation AI — characters, expressions, poses, props, environments, camera framing, and the
> locked house style. Pick the pieces you need, paste them into your generator, and you get on-model,
> consistent output every time.
>
> **How to use:** Always start with **§1 the Style Prefix**, then add the **character(s)** (§3), their
> **expression** (§4) + **pose** (§5), any **props** (§6), a **background** (§7), and a **camera
> framing** (§8). §9 has full copy-paste recipes that combine them.
>
> Distilled from the locked design bibles and the cast model sheets. Everything here is the
> *canonical, reusable* layer — reuse it, never reinvent it. When this sheet and a bible disagree,
> **the bible wins** and this sheet is the bug.
>
> **Upstream sources (now in-repo — these were dangling references before the base fix):**
> [Visual Identity Lock](production/design/VISUAL_IDENTITY_LOCK.md) ·
> [Character Bible](production/design/CHARACTER_BIBLE.md) ·
> [Expression Library](production/design/EXPRESSION_LIBRARY.md) ·
> [Pose Library](production/design/POSE_LIBRARY.md) ·
> [Prop Library](production/design/PROP_LIBRARY.md) ·
> [Environment Bible](production/design/ENVIRONMENT_BIBLE.md) ·
> [Camera & Cinematography Bible](production/design/CAMERA_CINEMATOGRAPHY_BIBLE.md) ·
> [Animation Language](production/design/ANIMATION_LANGUAGE_MOTION_SYSTEM.md) ·
> cast sheets: [PIP](production/characters/pip.md) · [CHIEF](production/characters/chief.md)

---

## 1. Style Prefix — ALWAYS prepend this (do not edit)

Pick the prefix that matches the **format of the package you are building**. The two prefixes are
identical except for the aspect clause — everything else is locked.

**Shorts (9:16) — the default:**
```
Flat-color 2D cartoon, thick uniform INK #1A1A1A outlines (never pure black #000000), no gradients,
minimal single-tone shading, chunky 2-to-2.5-head proportions per the character sheet,
high-contrast, clean vector look, 9:16 vertical 1080x1920, mobile-legible.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text unless specified. Advertiser-safe, no gore.
```

**Long form (16:9):**
```
Flat-color 2D cartoon, thick uniform INK #1A1A1A outlines (never pure black #000000), no gradients,
minimal single-tone shading, chunky 2-to-2.5-head proportions per the character sheet,
high-contrast, clean vector look, 16:9 horizontal 1920x1080, legible at small size.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text unless specified. Advertiser-safe, no gore.
```

> **Why two prefixes:** the standards require long form to be **16:9 horizontal** — any vertical or
> square video under 3 minutes is auto-classified as a Short. A single hardcoded `9:16` prefix
> silently mis-renders every long-form package (this is what happened to `v5`).

> **Per-character proportions:** the prefix gives the *band*, the character sheet gives the *value* —
> **PIP ≈ 2 heads**, **CHIEF ≈ 2.5 heads** (§3). Never flatten both to one number; the height
> difference is the status contrast the comedy depends on.

**Global look rules baked into every image:**
- Uniform **thick black outline** (~6–8 px at 1080×1920), `INK #1A1A1A` — never pure black, never colored.
- **Flat color, zero gradients**, at most one flat hard-edged shadow tone per shape. No textures, glow, bloom, or blur.
- **Rounded shapes by default**; sharp/angular only as a deliberate authority/threat accent.
- **One clear subject** per frame, generous negative space, subject centered in the safe band. *Shorts (9:16):* keep key elements out of the top ~15% / bottom ~20% (UI chrome). *Long form (16:9):* keep them out of the bottom ~12% (player bar) and clear of the thumbnail crop.
- **Mute-first:** the pose + expression alone must convey the beat with no sound and no text.
- **Silhouette test:** fill the subject 100% black — it must still be recognizable.

---

## 2. Brand Palette (the only colors allowed)

| Token | Hex | Use |
|---|---|---|
| `INK` | `#1A1A1A` | All outlines, pupils, hard stamps/text |
| `BRAND_YELLOW` | `#FFD400` | **Primary accent** — hero props (boot/stamp), highlights, one focal hit per frame |
| `PAPER` | `#FFF7E0` | Warm neutral base — light backgrounds, character bodies, negative space |
| `POP_TEAL` | `#2FB6A3` | Secondary accent — cast wardrobe link (CHIEF jacket, PIP scarf) |
| `ALERT_RED` | `#E4322B` | Tension/hazard — no-parking zone, alarms, "TOWED" marks |
| `SKY` | `#BFE3F2` | Sky / open space (desaturated environment token) |
| `ASPHALT` | `#6E7076` | Ground / pavement (desaturated environment token) |

Only `BRAND_YELLOW`, `POP_TEAL`, and `ALERT_RED` may be used as saturated accents. No neon, no realistic skin tones, no off-palette color, no colored outlines. Backgrounds stay desaturated so the cast pops.

---

## 3. Characters (locked reference designs)

Reuse these exactly every time. Store each character once as `CHAR_[NAME]_v1` and attach it as a reference image/seed on every subsequent generation.

### PIP — the underdog / protagonist (`CHAR_PIP_v1`)
> Small, kind underdog the audience roots for; the victim who is vindicated by the twist. Never the aggressor.

```
CHAR_PIP_v1: tiny soft rounded underdog, ~2 heads tall, big head, oversized expressive eyes, tiny
mouth, soft brows, little stub limbs, gentle slouch / timid stance. Body PAPER #FFF7E0, simple tee,
a tiny POP_TEAL #2FB6A3 scarf (signature accent — present in EVERY shot), INK #1A1A1A outline.
Reads "small and harmless" in silhouette. Default resting face: worried.
```
- **Silhouette signature (mandatory every shot):** the `POP_TEAL` scarf.
- **Owns props:** tiny scooter (`PROP_pip_scooter_v1`), coin purse (`PROP_pip_coins_v1`).
- **Never** struts, points aggressively, or dominates — PIP endures, then reacts with relief.

### CHIEF — the antagonist / authority figure (`CHAR_CHIEF_v1`)
> Pompous, vain power-abuser whose overconfidence triggers his own comeuppance. The recurring foil.

```
CHAR_CHIEF_v1: short rotund puffed-up warden, ~2.5 heads tall, big head, small legs, chest out,
chin high, stiff heels-together strut. POP_TEAL #2FB6A3 warden jacket with BRAND_YELLOW #FFD400
buttons, oversized peaked cap with a badge, a diagonal BRAND_YELLOW #FFD400 sash covered in
BRAND_YELLOW medals (vanity tell), oversized PAPER #FFF7E0 gloves, bushy brows, tiny mustache,
permanent smug half-smile, small eyes, face PAPER #FFF7E0, INK #1A1A1A outline.
Reads "self-important official" in silhouette. Default face: smug.
```
> **Palette note (resolves a long-standing contradiction):** CHIEF's buttons were previously specced
> as "gold" and his gloves as "white" — both **off-palette**, and white is explicitly forbidden by
> §10. They are now `BRAND_YELLOW` and `PAPER`. His cap/sash/medals/buttons form **one costume-yellow
> cluster**; the "one `BRAND_YELLOW` focal hit per frame" rule in §6 governs **props**, not costume,
> so the hero prop still needs to be the brightest *new* yellow the eye lands on in any frame.
- **Silhouette signature (mandatory every shot):** cap + sash + medals (these are costume, part of the character — never omit or slim him down).
- **Owns props:** giant rubber stamp (`PROP_stamp_v1`), wheel boot (`PROP_boot_v1`), oversized ticket pad (`PROP_ticketpad_v1`), his scooter (`PROP_chief_scooter_v1`).
- **Only breaks** from smug to shocked → panicked at the twist.

**Status contrast rule:** in any shared shot, CHIEF always reads *bigger / higher / more open*; PIP always reads *smaller / lower / more closed*.

---

## 4. Expressions / Reactions (canonical faces — pick one, never invent)

Rules: **eyes carry ~70% of the read**, `INK` pupils, mouth stays small/secondary (mute-first), bold brows amplify. Asset ID = `CHAR_[NAME]_expr_[name]`. Three intensity levels: **L1 subtle · L2 standard (default) · L3 comic peak** (big held "hero" beat, benign FX allowed).

### PIP's emotional band (soft, sympathetic, benign)
| Expression | Face description to paste |
|---|---|
| `neutral` | Calm, soft small smile, eyes relaxed |
| `worried` *(resting)* | Big anxious eyes, tiny frown, slight hunch |
| `teary` | Glossy watery big eyes, quivering tiny mouth — cute, not distressing |
| `hopeful` | Looking up, small hopeful spark in the eyes, tiny open mouth |
| `gleeful` | Wide happy eyes, big cheerful grin (usually L3) |
| `relieved` | Relaxed smile, eyes softly closed |
| `wave` *(signature button)* | `relieved` face paired with a small friendly hand wave to camera |

PIP arc across a video: **worried → teary → hopeful → gleeful → relieved (wave)**. PIP never plays smug/gloating/triumphant/indignant.

### CHIEF's emotional band (the pride ladder, then the fall)
| Expression | Face description to paste |
|---|---|
| `smug` *(resting)* | Half-lidded eyes, asymmetric raised brow, smug half-smile, chin up |
| `gloating` | Active grin, narrowed eyes, brows up, openly enjoying his power |
| `triumphant` *(L3 peak)* | Chest-out beaming pride, eyes bright, big grin, `FX_sparkle_v1` allowed |
| `shocked` | Eyes blown wide, brows shot up, mouth open in a gasp |
| `panicked` | Squeezed/huge eyes, flustered open mouth, sweat bead, comic alarm |
| `deadpan` | Flat, half-lidded, unimpressed underreaction |

CHIEF turn (the twist) uses the **3-stage snap**: `smug → shocked → panicked`. CHIEF never plays teary/hopeful/relieved.

**Other canonical names available when a story needs them** (mint editorially, reuse the exact name, never a synonym): `confused, curious, sheepish, suspicious, thinking, weary, determined, eager, indignant, fond, delighted`.

**Advertiser-safe ceiling:** fear = comic panic, anger = indignant huff, sadness = cute/teary. Escalate scale and comedy, never distress.

---

## 5. Poses / Body Language (canonical bodies — pick one, never invent)

Rules: **one clear line of action**, arms read **outside** the body silhouette, hands legible, weight/center-of-gravity clearly placed, silhouette reads the beat filled 100% black. Asset ID = `CHAR_[NAME]_pose_[name]`. Same L1/L2/L3 intensity model — **match the pose intensity to the paired expression**.

| Pose | Family | Body description to paste | Natural expression |
|---|---|---|---|
| `idle` | Base | Neutral resting stance | worried / smug |
| `stand` | Base | Upright, arms near body | neutral |
| `wait` | Base | Standing, slight shift, waiting | neutral / worried |
| `walk` | Locomotion | Mid-stride walk | neutral |
| `run` | Locomotion | Fast run, lean forward | panicked / eager |
| `strut` | Locomotion | Chest out, chin up, heels-together proud walk, high CoG | smug (CHIEF) |
| `jump` | Locomotion | Both feet off ground, lifted | gleeful |
| `fall` | Locomotion | Off-balance, tipping over | shocked / panicked |
| `sit` | Base | Seated | any |
| `point` | Gesture | One arm extended wide to point/accuse, clear diagonal | gloating / smug |
| `hold` | Gesture | Holding a prop in the oversized hand, outside the silhouette | any (prop-dependent) |
| `reach` | Gesture | Reaching toward something, CoG lifting | hopeful |
| `wave` | Gesture | Small friendly hand wave to camera | relieved / neutral |
| `bow` | Gesture | Bending forward | sheepish / gloating |
| `leanin` | Reaction | Head tilts up/forward, curious lean | curious / hopeful |
| `ponder` | Reaction | Hand near chin, thinking | thinking |
| `recoil` | Reaction | Weight thrown back, flinch | shocked |
| `shrink` | Reaction | Compact C-curve, shoulders up around head, arms clutched in, weight back — timid cower | worried / teary |
| `flail` | Reaction | Limbs flailing, off-balance, comic panic | panicked |
| `celebrate` | Payoff | Open, lifted, wide arms, small shoulder-jump | gleeful |
| `victory` | Payoff | Hero pose, arms/prop raised, max open negative space, podium | triumphant |
| `slump` | Payoff | Collapsed down, weight dropped, defeated | teary / defeated |
| `relaxed` | Payoff | Shoulders dropped-open, calm upright | relieved |

- **PIP plays** (low amplitude): `idle, shrink, slump, leanin, reach, celebrate, relaxed, wave`. Arc: `idle → shrink → slump → leanin → celebrate → relaxed+wave`.
- **CHIEF plays** (big amplitude): `strut, stand, point, hold, victory` then collapse `recoil → flail`. Dominance ladder: `strut → point/hold → victory → recoil → flail`.
- **Composite buttons:** PIP's `wave` = `CHAR_PIP_pose_wave` (gesture) + `CHAR_PIP_expr_relieved` (face).

**Pose + expression pairing** (same beat, same intensity):
| Story beat | Face | Pose |
|---|---|---|
| Establish underdog | `worried` | `idle` / `shrink` |
| Establish authority | `smug` | `strut` / `stand` |
| Bully acts | `gloating` | `point` / `hold` |
| Injustice peaks | `teary` | `slump` |
| The turn arrives | `hopeful` | `leanin` / `reach` |
| Peak arrogance | `triumphant` | `victory` |
| Twist hits (antagonist) | `shocked` → `panicked` | `recoil` → `flail` |
| Payoff (underdog) | `gleeful` | `celebrate` |
| Warm button | `relieved` | `relaxed` + `wave` |

---

## 6. Props (reusable objects — pick from catalog, never invent ad hoc)

Rules: **2–4 flat shapes**, one iconic read, comedy-scaled (not realistic), scale ratio to owner **locked** across all shots, uniform `INK` outline, palette-only. `BRAND_YELLOW` is reserved for the hero prop / karma device (one yellow focal hit per frame). Asset ID = `PROP_[name]_v#`.

| Prop | ID | Description to paste |
|---|---|---|
| Giant rubber stamp | `PROP_stamp_v1` | Comically oversized rubber stamp, chunky handle, hard rectangular head (sharp = authority). CHIEF's power object; becomes the karma device used *on* him. Hero prop, can take the `BRAND_YELLOW` hit. |
| Wheel boot / immobilizer | `PROP_boot_v1` | `BRAND_YELLOW` wheel-clamp immobilizer, chunky rounded clamp. Hero karma device. |
| Oversized ticket pad | `PROP_ticketpad_v1` | Comically large ticket pad, tears sheets with a flourish. |
| Ticket sheet | `PROP_ticket_v1` | Single flat ticket sheet; stacks into a ticket pile for a gag. |
| CHIEF's scooter | `PROP_chief_scooter_v1` | CHIEF's scooter — the **seed**: parked in the no-parking zone in frame 1. |
| PIP's tiny scooter | `PROP_pip_scooter_v1` | Small soft scooter, reads tiny; the vehicle unjustly booted. |
| PIP's coin purse | `PROP_pip_coins_v1` | Small coin purse; fumbles coins at the meter (innocence beat). |
| Tow truck | `PROP_towtruck_v1` | Chunky tow truck — impartial justice arriving. |
| Podium + flag | `PROP_podium_v1` | Small podium with a tiny flag; for the victory/flex beat. |

- **Costume ≠ prop:** CHIEF's cap/sash/medals/gloves and PIP's scarf are part of the character, not props.
- **Set dressing ≠ prop:** ground, sky, walls, painted markings are `BG_` (see §7).
- **On-frame text** (e.g. a "TOWED" mark) is the `UI_` namespace; **effects** are `FX_` (e.g. `FX_sparkle_v1`, `FX_impact_star_v1`, `FX_motionlines_v1`).

---

## 7. Environments / Backgrounds (reusable locations — quieter than the cast)

Rules: a few **large flat shapes** (ground + backdrop + 1–3 set pieces), built in **three flat planes** (fg / mg-stage / bg), consistent ground line, **always more desaturated + lower-contrast than the cast**, no readable text, no incidental characters, no gradients. Asset ID = `BG_[location]_v#`. Depth via flat plane + scale, never perspective blur.

### Parking Lot (the first/hero location) — `BG_parkinglot_v1`
```
BG_parkinglot_v1: wide flat-2D open orderly public parking lot. Ground ASPHALT #6E7076, backdrop
flat SKY #BFE3F2, a parking meter and painted parking lines (INK), an ALERT_RED #E4322B no-parking
zone marking in the lower-right. Deliberately plain, rule-governed, "petty authority's turf".
Desaturated, generous negative space, no characters, no text. Default: afternoon, clear (bright flat midday).
```
- **Sub-views:** `BG_parkinglot_meter_v1` (meter area), `BG_noparking_zone_v1` (the `ALERT_RED` seed marking).
- **Depth layers:** fg = no-parking zone + ground; mg = meter, lines, the cast + podium spot; bg = flat empty `SKY`.
- **Continuity:** the no-parking zone holds the **same lower-right screen position** across shots; the closing shot reuses the exact opening plate for the loop seam.

### Weather / time states (flat token swaps + flat overlay shapes — never gradients)
- **Time:** morning · afternoon (default) · golden hour · sunset · overcast · night (swap sky/ground tokens + flat sky elements; one time-of-day per video; loop-seam must match).
- **Weather:** clear (default) · cloudy (flat cloud shapes) · overcast (flatter grey-blue sky) · rain (flat diagonal `INK` streaks behind cast) · wind (static lean + `FX_motionlines_v1`) · fog (one pale flat overlay on bg only) · snow (pale ground + flat dots) · storm (comic flat `BRAND_YELLOW` lightning, sparing). Weather sits behind the cast, low-contrast; one state per video.

### Available location categories (build once through the same rules when needed)
Urban · Commercial/Retail · Workplace/Institutional (office, DMV — "petty authority" turf) · School · Residential · Parks/Nature · Recreation (beach, gym, zoo, pool) · Transit · Public Space · **Abstract void** (`BG_void` — plain `PAPER` limbo for reaction close-ups, thumbnails, wallpapers).

---

## 8. Camera / Framing (shot grammar — describe shots in these tokens)

Default to **`WIDE`/`FULL` at `EYE` angle, `STATIC`**. Tighter/angled/moving shots are deliberate beats. Frame in the package's locked aspect (**9:16 for Shorts, 16:9 for long form**), one clear subject, no depth-of-field blur, no lens distortion (a "close-up" = tighter crop + bigger subject, background stays flat and in focus).

**Framing (distance):** `EWIDE` (extreme wide) · `WIDE` (establishing) · `FULL` (full body) · `MED` (two-shot) · `MCU` · `CU` (reaction close-up / thumbnail hero) · `ECU` · `REACT` (reaction insert) · `CUT` (cutaway/reveal).

**Angle:** `EYE` (neutral default) · `LOW` (hero angle — inflates power/ego, use on CHIEF's flex) · `HIGH` (smallness/vulnerability, sparing on PIP) · `TOP` · `OTS` · `POV` · `DUTCH` (brief comedic tilt).

**Movement (≤1 per shot, mostly `STATIC`):** `STATIC` (default) · `PUSHIN` (slow build) · `PUNCHIN` (fast snap on the twist — signature) · `REVEAL` (bring an element in) · `PULLOUT` · `PAN` · `TILT` · `TRACK` · `WHIP`. **Disallowed:** orbit/rotation, handheld simulation.

**Framing-for-status:** `LOW` + larger scale = dominant (CHIEF); `HIGH` + small scale + isolating space = vulnerable (PIP); `EYE` = honest default; tight `CU` when the face must carry the beat.

**Shot descriptor notation:**
```
SHOT <n> = <FRAMING>.<ANGLE>.<MOVEMENT>
           BG:<location BG_ id + time/weather>
           CAST:<CHAR + pose + expr (+ intensity)>
           PROPS:<PROP_ ids>
           BEAT:<beat>   CONTINUITY:<seed / loop note>
```
Example: `SHOT 5 = FULL.LOW.PUSHIN | BG: BG_parkinglot_v1 (afternoon, clear) | CAST: CHAR_CHIEF_v1 pose=victory_l3 expr=triumphant_l3 | PROPS: PROP_stamp_v1 (raised), PROP_podium_v1; FX_sparkle_v1 | BEAT: ego peak | CONTINUITY: seed scooter held lower-right`.

---

## 9. Copy-Paste Prompt Recipes

Combine §1 + the parts you need. Attach the character reference sheet/seed for any recurring cast member.

### A. Build a character reference once
```
Flat-color 2D cartoon, thick uniform INK #1A1A1A outlines (never pure black #000000), no gradients,
minimal single-tone shading, chunky 2-to-2.5-head proportions per the character sheet,
high-contrast, clean vector look, 9:16 vertical 1080x1920, mobile-legible.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text unless specified. Advertiser-safe, no gore.
Character turnaround (front, 3/4, side) of CHIEF at ~2.5 heads tall: short rotund puffed-up warden,
POP_TEAL warden jacket + BRAND_YELLOW buttons, oversized peaked cap with badge, diagonal
BRAND_YELLOW sash with medals, oversized PAPER gloves, tiny mustache, smug half-smile.
Plus a 6-expression sheet: neutral, smug, shocked, gleeful, panicked, deadpan.
Consistent proportions across all poses.
```
> For PIP, use the same recipe but state **~2 heads tall** and swap in his `POP_TEAL` scarf and the
> PIP expression set (neutral, worried, teary, hopeful, gleeful, relieved).
Store as `CHAR_CHIEF_v1`. (Same pattern for PIP.)

### B. A single acting beat (character + pose + expression)
```
{style prefix}
SUBJECT: CHAR_PIP_v1, expression=hopeful (L2), keep POP_TEAL scarf
FRAMING: MED.EYE.STATIC
ACTION/POSE: leanin — head tilts up, small reach toward incoming payoff, CoG lifting
PROPS: none
BACKGROUND: BG_parkinglot_v1 (afternoon, clear), desaturated, quieter than subject
FX: none
ON-FRAME TEXT: none
CONTINUITY: PIP at consistent ground line, scarf present
```

### C. Character + prop interaction
```
{style prefix}
SUBJECT: CHAR_CHIEF_v1, expression=gloating, keep cap+sash+medals
FRAMING: FULL.LOW.PUSHIN
ACTION/POSE: hold — brandishing the giant stamp in the oversized glove, arm reads outside silhouette
PROPS: PROP_stamp_v1 (hero prop, BRAND_YELLOW focal hit)
BACKGROUND: BG_parkinglot_v1 (afternoon, clear)
FX: none
CONTINUITY: chief scooter seed held lower-right in no-parking zone
```

### D. Reaction close-up (thumbnail hero)
```
{style prefix}
SUBJECT: CHAR_PIP_v1 close-up face + upper body, expression=gleeful (L3), big cheerful grin, wide eyes
FRAMING: CU.EYE.STATIC
BACKGROUND: BG_void (plain PAPER limbo) or simple desaturated parking lot
FX: FX_sparkle_v1 (optional, benign, L3 only)
ON-FRAME TEXT: none
```

### E. Empty location plate
```
{style prefix}
Wide flat-2D BG_parkinglot_v1: ASPHALT ground, flat SKY backdrop, parking meter + painted lines,
ALERT_RED no-parking zone lower-right. Afternoon, clear. Layered flat depth (fg/mg/bg),
generous negative space, no characters, no text, quieter/desaturated vs. any subject.
```

---

## 10. Universal DO / DON'T (quality gate before accepting any image)

**Always:** prepend the style prefix + palette · attach the character reference for locked cast · keep signature silhouettes (CHIEF cap+sash+medals, PIP scarf) · uniform `INK` outline · one clear subject + negative space · keep seed props in fixed position + match first/last frame for loops · verify the beat reads muted from the pose alone.

**Never:** gradients, glow/bloom, blur, or texture · pure black `#000000` or pure white `#FFFFFF` · off-palette/neon color or colored outlines · redraw/restyle a locked cast member · change locked proportions, slim a character, or drop signature props · realistic lighting/3D/photographic detail · clutter the background or let it out-contrast the subject · rely on on-frame text to tell the story.

**Advertiser-safe always:** no gore, no cruelty, no humiliating the underdog; karma lands on the arrogant, never the weak; fear = comic panic, sadness = cute, anger = indignant huff.
