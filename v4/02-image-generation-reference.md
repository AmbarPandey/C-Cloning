# v4 — Image-Generation Reference ("The Wrong Side of the Fence")

> Everything the image AI needs for v4: locked house style, characters, their reactions, the
> surroundings, and a **ready-to-paste prompt for each of the 8 shots** (aligned to the master
> timeline in `01-video-script.md`). For the full reusable vocabulary see the repo-root
> [`IMAGE-GEN-REFERENCE.md`](../IMAGE-GEN-REFERENCE.md); this file is the v4-specific subset.

---

## 0. Global style prefix — PREPEND TO EVERY PROMPT (do not edit)
```
Flat-color 2D cartoon, thick uniform black outlines, no gradients, minimal single-tone shading,
chunky 2.5-head proportions, high-contrast, clean vector look, 9:16 vertical, mobile-legible.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text unless specified. Advertiser-safe, no gore.
```
**Consistency rule:** reuse the same `CHAR_CHIEF_v1` / `CHAR_PIP_v1` reference sheets generated for
v1–v3 — attach them as reference images/seeds on every shot so the cast stays on-model across the series.

**Heat and shade without gradients:** the house style forbids gradients, glow and blur. Render the
sun/shade split as **two hard-edged flat zones with a crisp dividing line on the ground**, and render
heat as **flat chevron/squiggle shapes** rising off the sunny ground — never a blur, haze or glow filter.

---

## 1. Characters (lock these; reuse every shot)

**CHIEF — Bully / Antagonist** (`CHAR_CHIEF_v1`)
```
Short rotund puffed-up warden-type, ~2.5 heads tall, big head, small legs, chest out, chin high.
POP_TEAL #2FB6A3 jacket with gold buttons, oversized peaked cap with a badge, a diagonal
BRAND_YELLOW #FFD400 sash covered in medals, oversized white gloves, bushy brows, tiny mustache,
permanent smug half-smile, small eyes, face PAPER #FFF7E0, INK #1A1A1A outline.
Silhouette signature (NEVER omit, NEVER transfer): cap + sash + medals. Default face: smug.
```

**PIP — Hero / Underdog** (`CHAR_PIP_v1`)
```
Tiny soft rounded underdog, ~2 heads tall, big head, oversized expressive eyes, tiny mouth, soft
brows, little stub limbs, gentle timid slouch. Body PAPER #FFF7E0, simple tee, a tiny POP_TEAL
#2FB6A3 scarf (signature — present in EVERY shot), INK #1A1A1A outline. Default face: worried.
```

**BUD — Animal class, PIP's companion** (`CHAR_BUD_v1`) — ⚠️ **new, proposed, not yet locked**
```
Tiny scruffy round dog, ~1.5 heads tall, shorter than PIP. Soft PAPER #FFF7E0 body with one
POP_TEAL #2FB6A3 collar (his only signature marking), big friendly INK eyes, small floppy ears,
a stubby waggy tail, three or four shape masses total, INK #1A1A1A outline. Expressive but
completely WORDLESS. Never harmed, never caged, never distressed. Default: relaxed and friendly.
```

**Park animals — Crowd class** (`CROWD_parkanimals_v1`)
```
Assorted small park animals lounging exactly like people — one reclining, one sipping from a cup,
one holding a tiny newspaper, one asleep. Rendered as simple, DESATURATED, silhouette-level shapes
with minimal internal detail. They establish the "animals as people" world and must NEVER
out-compete PIP, BUD or CHIEF for attention. No individual faces or model sheets.
```

> **Costume lock:** CHIEF's cap/sash/medals are **costume, not props** — they stay on him throughout
> (drooping cap in C8 is allowed; removal is not).

**Status rule:** CHIEF reads bigger/stiffer/more decorated throughout. His status does not invert by
scale in v4 — it inverts by **position**: he ends up outside the fence in the sun while the small,
soft characters are inside the cool green.

---

## 2. Reactions used in v4 (face + body per beat)

| Clip | CHIEF face → pose | PIP face → pose | BUD |
|---|---|---|---|
| C1 | `smug` → `strut` (stops, stares at the shade) | `neutral` → `sit` (content on the bench) | relaxed, two tail wags |
| C2 | `gloating` → `hold` (hauling/slamming the first panel) | `worried` → `stand` (straightens up) | head tilt |
| C3 | `gloating` → `hold` (rhythmic slamming) | `worried` → `shrink` (edges back) | worried ear-droop |
| C4 | `triumphant` → `hold` (hangs the padlock, claps gloves) | `worried` → `leanin` | sits, watching |
| C5 | `triumphant` (L3) → `victory` (fists on hips, admiring) | — (out of frame; framing is tight) | — |
| C6 | `smug` → `confused` → `worried` (grin falters, sweat bead) | `hopeful` → `leanin` | ears prick |
| C7 | `shocked` → `panicked` (3-stage snap) → `flail` (rattles fence) | `gleeful` (L3) → `reach` (clicks the lock) | nudges the gate shut with his nose |
| C8 | `sheepish` → `slump` (wilting, cap drooping) | `relieved` → `relaxed` + `wave` | one tail wag |

---

## 3. Surroundings / environment (v4 location)

**Hot Park — two-zone** (`BG_park_v1`) — new asset
```
BG_park_v1: wide flat-2D public park, split into two hard-edged zones by a crisp INK line drawn on
the ground. LEFT THIRD (the shade): a lush garden with POP_TEAL #2FB6A3 foliage canopy overhead, a
small stone water fountain, a little bench, and a flat cool single-tone shadow covering the ground.
RIGHT TWO-THIRDS (the sun): bare, flat, pale PAPER #FFF7E0 ground, nothing on it, under a big flat
BRAND_YELLOW #FFD400 sun disc high in a flat SKY #BFE3F2 sky, with flat heat-shimmer chevron shapes
rising off the ground. Desaturated background: a simple low park railing and a few flat bush shapes.
Deliberately plain and quiet, lower-contrast than the cast, generous negative space, no text.
```
- **Sub-views:** `BG_park_wide_v1` (both zones + boundary), `BG_park_shade_v1` (garden interior), `BG_park_wallface_v1` (tight plate of the finished wall face for C5).
- **Depth layers:** fg = the shade/sun ground edge + fence line; mg = the cast, bench, fountain, fence; bg = flat railing, bushes, sky, sun.
- **Continuity (critical):** the **shade/sun ground edge holds the exact same screen position in every shot**, and the sun disc never moves. C8 reuses the exact C1 plate for the loop seam.
- **The one rule that cannot break:** **CHIEF must be on the sunny side of that ground edge in every single frame of the video.** The entire twist depends on it having been true from the start.

---

## 4. Props (v4 set)
| Prop | ID | Note |
|---|---|---|
| **Fence panel** | `PROP_fencepanel_v1` | **The seed** — a leaning stack of plain `ASPHALT` panels in frame 1; ~12 get placed |
| **Padlock** | `PROP_padlock_v1` | **The hero prop + callback seed** — chunky `ALERT_RED` padlock; hangs on the post in C1, on the gate in C4, clicked shut in C7 |
| Gate | `PROP_gate_v1` | The one swinging panel BUD nudges shut |
| Bench | `PROP_bench_v1` | PIP and BUD's spot in the shade |
| Fountain | `PROP_fountain_v1` | Small stone fountain; the cool-side audio/visual anchor |
| Newspaper / cup | `PROP_animalprops_v1` | Tiny props that make the animals read as *people* (SC10) |
| FX | `FX_heatchevron_v1` (new, flat heat shapes), `FX_dustpuff_v1`, `FX_motionlines_v1`, `FX_sparkle_v1` (C5), `FX_impact_star_v1` (C7) | benign, flat, no blur/glow |

**Palette discipline:** `BRAND_YELLOW` is the **sun** — one big dominant focal hit, and thematically the
consequence. `ALERT_RED` is reserved exclusively for the **padlock**, so red always means "locked out."
`POP_TEAL` is the shade/foliage plus the cast's signature markings, which visually links PIP, BUD and the
cool green as one "team." The fence stays neutral `ASPHALT` so it never competes with the padlock.

---

## 5. Per-shot render prompts (paste-ready)

**Shot C1 — Hook + seed (0:00–0:02) · WIDE.EYE.STATIC**
```
{style prefix} Wide vertical flat-2D park split into two hard-edged zones by a crisp INK line on the
ground. LEFT: a lush shady garden, POP_TEAL foliage canopy, a small stone fountain, a little bench, flat
cool shadow on the ground; several small park animals lounging exactly like people (one reclining, one
sipping a cup, one with a tiny newspaper) as quiet DESATURATED silhouette-level shapes. On the bench sit
tiny PIP (PAPER body, POP_TEAL scarf, content) and BUD, a tiny scruffy round dog with a POP_TEAL collar.
RIGHT: bare pale PAPER ground, empty, under a big flat BRAND_YELLOW sun in a flat SKY sky, with flat
heat-shimmer chevron shapes rising. On the boundary between the zones: a leaning stack of plain ASPHALT
fence panels and a chunky ALERT_RED padlock hanging on a post. Entering from the sunny right: a pompous
round CHIEF (POP_TEAL jacket, peaked cap with badge, diagonal BRAND_YELLOW medal sash, tiny mustache,
smug) strutting in and staring at the shade. CHIEF is on the SUNNY side of the ground line. Calm
balanced composition. This exact framing repeats at the end. No text.
```

**Shot C2 — Setup (0:02–0:06) · MED.EYE.PUSHIN**
```
{style prefix} Medium two-shot across the shade/sun boundary line. CHIEF, standing on the bare sunny
side, sneers at tiny PIP who is sitting in the cool shade, and hauls the first plain ASPHALT fence panel
across, slamming it upright into the ground along the boundary with a flat dust puff. PIP straightens up,
worried; BUD tilts his head. The ALERT_RED padlock still hangs on its post. CHIEF remains on the sunny
side. No text.
```

**Shot C3 — Escalation 1 (0:06–0:11) · WIDE.EYE.STATIC**
```
{style prefix} Wide. A row of five or six plain ASPHALT fence panels now stands along the shade/sun
boundary, sealing the shady garden off, with flat dust puffs at their bases. CHIEF, on the bare sunny
side, is gleefully slamming another panel into place. Inside the shade, PIP and BUD edge backward, worried,
and two of the lounging park animals lift their heads to watch. CHIEF remains on the sunny side. No text.
```

**Shot C4 — Escalation 2 (0:11–0:16) · MED-WIDE.EYE.PUSHIN(slight)**
```
{style prefix} Medium-wide. The fence has doubled in height — a second row of plain ASPHALT panels
stacked on the first, absurdly overbuilt for a garden fence. CHIEF, on the bare sunny side, is hanging
the chunky ALERT_RED padlock onto the final gate panel with a small metallic sparkle glint, chin high and
triumphant, dusting off his oversized white gloves. Glimpses of the cool POP_TEAL garden visible through
the gate gap. CHIEF remains on the sunny side. No text.
```

**Shot C5 — Anticipation / the proud pose (0:16–0:22) · MCU.LOW.PUSHIN**
```
{style prefix} TIGHT low hero-angle medium-close shot of CHIEF only, fists planted on his hips, chest
out, chin high, beaming with self-satisfaction at his finished fence, FX_sparkle accents around him. The
plain ASPHALT fence panels fill the frame behind him as a flat wall face. CRITICAL: the framing is
deliberately tight and crops out the ground line, the shade, the garden and the animals — the viewer must
NOT be able to tell which side of the fence he is standing on. Keep heat chevrons minimal and low in
frame. No text.
```

**Shot C6 — Pattern break / the reveal (0:22–0:27) · WIDE.EYE.PULLOUT**
```
{style prefix} Full wide reveal shot. The tall ASPHALT fence now rings the lush POP_TEAL shady garden —
and CHIEF is standing OUTSIDE it, completely alone on the bare, blazing PAPER sunny side, the crisp
shade/sun ground line running right at his boots, flat BRAND_YELLOW sun overhead, flat heat chevrons
rising all around him. His proud grin is faltering into confusion and a single sweat bead pops. INSIDE
the fence, in the cool shade: PIP looking up hopefully, BUD with ears pricked, and all the lounging park
animals, plus the fountain. The geometry of his mistake is the subject of the shot. No text.
```

**Shot C7 — Twist / irony reversal (0:27–0:31) · MED.EYE.PUNCHIN**
```
{style prefix} Punch-in medium. BUD the little dog nudges the swinging gate panel shut with his nose,
matter-of-factly, and tiny PIP stretches up on tiptoes to click the chunky ALERT_RED padlock closed FROM
THE INSIDE, beaming gleefully. On the other side, out in the blazing sun, CHIEF's face is shocked and
panicked as he grips and rattles the fence, flat heat chevrons at maximum rising off his cap, flat
FX_impact_star on the padlock click. Behind PIP the lounging park animals settle back down, completely
unbothered, in the cool POP_TEAL shade. CHIEF is outside the fence on the sunny side. No text.
```

**Shot C8 — Payoff / loop seam (0:31–0:32) · WIDE.EYE.STATIC (== C1)**
```
{style prefix} Wide composition IDENTICAL in framing, background plate, horizon and shade/sun ground-line
position to shot C1. CHIEF is now wilting outside his own tall magnificent ASPHALT fence on the bare
blazing sunny side — shoulders sagging, oversized cap drooping over his eyes, gloves hooked on the fence,
sheepish, flat heat chevrons rising around him, still wearing his sash and medals. INSIDE, in the cool
POP_TEAL shade: PIP sitting back on the little bench with BUD beside him, giving a small friendly wave to
camera with a relieved smile, the lounging park animals and the trickling fountain around them. Calm
resolved mood. No text.
```

---

## Renderer notes
- **The one invariant:** CHIEF is on the **sunny side of the ground line in every single frame**. Check every shot. If he is ever inside the shade, the twist is broken and the video is unusable.
- C1 and C8 **must** share an identical background plate, framing, horizon **and shade/sun edge position** (loop seam) — only the fence, padlock state and cast positions change.
- **C5 must hide the geometry.** Crop out the ground line, the garden and the animals. If a cold viewer can predict the reveal from C5, retighten it.
- **C6 must show the geometry.** It is the only shot whose true subject is the layout rather than a character.
- The padlock must be the same `ALERT_RED` object in C1 (post), C4 (hung on gate), C7 (clicked shut).
- Park animals stay **Crowd-class**: desaturated, silhouette-level, no individual faces — present to establish the SC10 world, never to compete for attention.
- **BUD is wordless, never harmed, never caged or distressed.** His single action is the gate nudge; he is not the joke.
- **Zero on-frame text** anywhere in v4 — the padlock and the shade edge carry all the meaning.
- Never transfer CHIEF's cap/sash/medals; never drop PIP's teal scarf or BUD's teal collar; never restyle or reproportion the cast.
- No blur, glow, gradients or realistic lighting; heat is flat chevron shapes, shade is one flat tone.
- **Advertiser-safe:** CHIEF is hot and embarrassed — **not** harmed, sunburnt, dehydrated or in distress. No animal is harmed, caged or upset; the animals are relaxed throughout.
