# v5 — Image-Generation Reference ("The Case of the Missing Pie") · **LONG FORM 16:9**

> Everything the image AI needs for v5: locked house style, characters, their reactions, the
> surroundings, and a **ready-to-paste prompt for each of the 16 shots** (aligned to the master
> timeline in `01-video-script.md`). For the full reusable vocabulary see the repo-root
> [`IMAGE-GEN-REFERENCE.md`](../IMAGE-GEN-REFERENCE.md); this file is the v5-specific subset.

---

## 0. Global style prefix — PREPEND TO EVERY PROMPT (do not edit)
```
Flat-color 2D cartoon, thick uniform black outlines, no gradients, minimal single-tone shading,
chunky 2.5-head proportions, high-contrast, clean vector look, 16:9 HORIZONTAL 1920x1080.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text unless specified. Advertiser-safe, no gore.
```

> **⚠️ This is the first 16:9 episode.** v1–v4 were 9:16 vertical. Reuse the same character sheets, but
> **recompose every shot for horizontal framing**: use the width for side-by-side staging (suspect on one
> side, CHIEF on the other), keep headroom tight, and place the seed props in the horizontal thirds rather
> than stacked vertically. Do not simply letterbox the vertical designs.

**Consistency rule:** reuse the `CHAR_CHIEF_v1` / `CHAR_PIP_v1` / `CHAR_BUD_v1` reference sheets from
v1–v4 — attach them as reference images/seeds on every shot so the cast stays on-model across the series.

---

## 1. Characters (lock these; reuse every shot)

**CHIEF — self-appointed detective / Bully-Antagonist** (`CHAR_CHIEF_v1`)
```
Short rotund puffed-up warden-type, ~2.5 heads tall, big head, small legs, chest out, chin high.
POP_TEAL #2FB6A3 jacket with gold buttons, oversized peaked cap with a badge, a diagonal
BRAND_YELLOW #FFD400 sash covered in medals, oversized white gloves, bushy brows, tiny mustache,
permanent smug half-smile, small eyes, face PAPER #FFF7E0, INK #1A1A1A outline.
v5 additions (props, not costume): an oversized magnifying glass and a tiny notebook.
Silhouette signature (NEVER omit, NEVER transfer): cap + sash + medals. Default face: smug.
```

**PIP — falsely accused / Hero-Underdog** (`CHAR_PIP_v1`)
```
Tiny soft rounded underdog, ~2 heads tall, big head, oversized expressive eyes, tiny mouth, soft
brows, little stub limbs, gentle timid slouch. Body PAPER #FFF7E0, simple tee, a tiny POP_TEAL
#2FB6A3 scarf (signature — present in EVERY shot), INK #1A1A1A outline. Default face: worried.
v5 detail: a few small biscuit crumbs on the scarf from S10 onward (his "evidence").
```

**BUD — Animal class, PIP's companion** (`CHAR_BUD_v1`) — ⚠️ proposed, not locked
```
Tiny scruffy round dog, ~1.5 heads tall, shorter than PIP. Soft PAPER #FFF7E0 body, one POP_TEAL
#2FB6A3 collar (his only signature marking), big friendly INK eyes, small floppy ears, stubby waggy
tail, three or four shape masses total, INK outline. Completely WORDLESS. Never harmed or distressed.
v5: on a short lead clipped to a post — the lead is a plot point (too short to reach the table).
```

**MITTENS — market cat, Guest class** (`CHAR_MITTENS_v1`) — ⚠️ proposed, not locked
```
Very small round cat, ~1 head tall — deliberately smaller than the pie plate, which is the joke.
ASPHALT #6E7076 body with a PAPER chest patch, two flat INK eyes, tiny triangular ears, a thin
curling tail, four shape masses total, INK outline. Permanently blank, unimpressed expression.
Completely WORDLESS. Never harmed or distressed.
```

**Market crowd — Crowd class** (`CROWD_market_v1`)
```
A handful of assorted market-goers rendered as simple, DESATURATED, silhouette-level shapes with
minimal internal detail. They watch, lean in, and react as a mass. They must NEVER out-compete the
leads. No individual faces, no model sheets.
```

> **Costume lock:** CHIEF's cap/sash/medals are **costume, not props** — never removed, never transferred.
> This matters in v5: the reveal receptacle is his **evidence box**, never his hat.

---

## 2. Reactions used in v5 (face + body per shot)

| Shot | CHIEF | PIP | BUD / MITTENS |
|---|---|---|---|
| S1 | `shocked` → `recoil` (theatrical gasp, glove up) | — | — |
| S2 | `smug` → `strut` (sets down ledger + box) | `neutral` → `sit` (eating biscuit) | BUD dozing · MITTENS sitting |
| S3 | `smug` → `hold` (magnifier + notebook pose) | `neutral` → `sit` | both idle |
| S4 | `gloating` → `point` (whole-arm accusation) | `curious` → `leanin` | BUD asleep |
| S5 | `confused` → `ponder` (measuring the lead) | `worried` → `leanin` | BUD unbothered |
| S6 | `deadpan` → `hold` (crossing off) | `neutral` → `sit` | BUD yawns hugely |
| S7 | `gloating` (bigger) → `point` (up on a crate) | `worried` → `leanin` | MITTENS blank stare |
| S8 | `confused` → `ponder` (tape measure mime) | `worried` → `leanin` | MITTENS indifferent |
| S9 | `indignant` → `hold` (crossing off, mustache twitch) | `worried` → `shrink` | MITTENS paw-lick, turns away |
| S10 | `shocked` → `leanin` (biggest gasp, lens first) | `worried` → `recoil` (frozen mid-bite) | BUD ears up |
| S11 | `gloating` → `point` (professor at the corkboard) | `teary` → `shrink` | BUD worried |
| S12 | `triumphant` (L3) → `victory` (stamp raised high) | `teary` (L3) → `shrink` (tiny ball) | BUD whines · crowd inhale |
| S13 | `gloating` → `victory` hold (lifts stamp higher) | `determined` → `reach` (points past him) | BUD, then MITTENS, then crowd turn to look |
| S14 | `smug` → `confused` → `worried` (drains across 10 s) | `neutral` → `stand` (calm, still pointing) | all watching |
| S15 | `shocked` → `panicked` (3-stage snap, drops stamp) | `gleeful` → `celebrate` | BUD tail wag · MITTENS blank |
| S16 | `sheepish` → `slump` (holding his own box) | `relieved` → `relaxed` + `wave` | BUD munching a slice |

---

## 3. Surroundings / environment (v5 location)

**Market Square** (`BG_market_v1`) — new asset, built for 16:9
```
BG_market_v1: wide flat-2D open-air market square, composed for 16:9 HORIZONTAL. Centre: a wooden pie
stall with a POP_TEAL #2FB6A3 striped awning and a plain wooden table. Left: low wooden crates (PIP's
seat) and a post (BUD's lead). Right: stacked crates (MITTENS's perch). Ground: flat ASPHALT #6E7076
cobbles with simple INK joint lines. Background: flat desaturated market stalls, bunting, and a few
silhouette-level market-goers, all low-contrast. Sky: flat SKY #BFE3F2 strip along the top.
Deliberately plain and quiet, lower-contrast than the cast, generous negative space, no text.
Time: bright flat midday, clear.
```
- **Sub-views:** `BG_market_wide_v1` (full square) · `BG_market_stall_v1` (stall + table, the crime scene) · `BG_market_behind_v1` (behind/below the stall — where the box and the filling trail live) · `BG_market_plate_v1` (ECU plate plate for S1/S16).
- **Depth layers:** fg = crates + the stall table edge; mg = the cast, stall, awning; bg = flat stalls, bunting, crowd silhouettes, sky.
- **Continuity locks (critical):**
  - The **stall table's tilt increases progressively** — level at 0:03, a few degrees at S2, slightly more each act, clearly askew by S14. Chart it shot by shot and never let it un-tilt.
  - The **ledger stays propped against the same table leg** and the **evidence box stays in the same spot on the ground** from S2 to S15, in every shot where that area is in frame.
  - The **filling trail** grows: a smear on the back edge (S6) → a drip forming (S9) → a visible run down the leg (S12) → a complete trail into the box (S14–S15).
  - S16's final frame must match **S1's ECU plate framing** exactly (loop seam).

---

## 4. Props (v5 set)
| Prop | ID | Note |
|---|---|---|
| Pie + plate | `PROP_pie_v1`, `PROP_plate_v1` | The "victim." Plate is empty in S1 and S16-open; the pie reappears in the box at S15 |
| **Heavy ledger** | `PROP_ledger_v1` | **SEED A** — chunky `ASPHALT` book. Propped against the table leg at 0:05. The actual cause |
| **Evidence box** | `PROP_evidencebox_v1` | **SEED B** — open wooden crate-box on the ground behind the stall. Where the pie lands |
| Magnifying glass | `PROP_magnifier_v1` | CHIEF's detective prop; his eye reads comically huge through it |
| Notebook | `PROP_notebook_v1` | Two suspects get crossed off; no readable text, just `INK` scribble marks |
| Tape measure | `PROP_tape_v1` | The cat-vs-plate gag in S8 |
| Corkboard + string | `PROP_corkboard_v1` | Photos, pins and `ALERT_RED` string only — **no words** |
| Giant stamp | `PROP_stamp_v1` | **Reused from v1** — the series callback; leaves an `ALERT_RED` mark, never a word |
| BUD's lead | `PROP_lead_v1` | Short, taut; the physical alibi |
| Biscuit + crumbs | `PROP_biscuit_v1` | PIP's innocent snack, the false evidence |
| **Filling trail** | `PROP_fillingtrail_v1` | Progressive smear/drip/run. The visual arrow of the whole mystery |
| FX | `FX_sparkle_v1`, `FX_impact_star_v1` (S15), `FX_motionlines_v1`, `FX_dustpuff_v1`, `FX_shocklines_v1` (new, flat `ALERT_RED` radiating comic shock lines) | benign, flat, no blur/glow |

**Palette discipline:** `BRAND_YELLOW` is the **pie** — the single dominant focal hit in any frame it
appears in, which makes the S15 reveal pop instantly. `ALERT_RED` is reserved for the **corkboard string,
the stamp mark and shock lines** — it always signals "accusation." The ledger and box stay neutral
`ASPHALT`/wood so they read as *background clutter* on first watch, which is exactly what the twist needs.

---

## 5. Per-shot render prompts (paste-ready)

**S1 — Cold-open hook (0:00–0:03) · ECU→MED.EYE.PULLOUT**
```
{style prefix} Extreme close-up, 16:9, of an EMPTY round pie plate sitting on a plain wooden market stall
table — one small crumb and a faint smear of golden filling on it, nothing else in frame. Flat, stark,
high contrast. Then framing widens to include, at frame right, the face of a pompous rotund cartoon
CHIEF (POP_TEAL jacket, oversized peaked cap with badge, diagonal BRAND_YELLOW medal sash, tiny mustache)
mouth open in an enormous theatrical gasp, eyes wide, one oversized white glove raised. No text.
```

**S2 — Scene + the two seeds (0:03–0:07) · WIDE.EYE.STATIC**
```
{style prefix} Wide 16:9 flat-2D open-air market square. Centre: a wooden pie stall with a POP_TEAL
striped awning and a plain wooden table holding the empty pie plate. Frame left: tiny PIP (PAPER body,
POP_TEAL scarf) sitting on a low crate eating a small biscuit; beside him BUD, a tiny scruffy round dog
with a POP_TEAL collar, dozing on a SHORT TAUT LEAD clipped to a post. Frame right: MITTENS, a very small
ASPHALT cat with a PAPER chest patch, sitting blankly on stacked crates. CHIEF stands at the stall with
his boot on a crate, and — casually, without looking — is LEANING A HEAVY DARK LEDGER AGAINST THE STALL
TABLE'S LEG (the table is now tipped a few degrees) while SETTING AN OPEN WOODEN EVIDENCE BOX DOWN ON THE
GROUND BEHIND THE STALL. Both objects clearly visible but incidental. Desaturated market stalls, bunting
and silhouette-level market-goers in the background. No text.
```

**S3 — The question (0:07–0:12) · MED.EYE.PUSHIN**
```
{style prefix} Medium 16:9. CHIEF striking a grand detective pose at the market stall — an oversized
magnifying glass held up so one eye appears comically huge and distorted through the lens, a tiny
notebook in his other glove, chin high, chest out, supremely self-important. Behind him the tipped stall
table and, low in frame, the open evidence box on the ground. Desaturated crowd silhouettes leaning in to
watch. No text.
```

**S4 — Accusation 1 (0:12–0:17) · MED.EYE.WHIP-PAN**
```
{style prefix} Medium 16:9 two-shot. CHIEF spun to frame left, pointing his whole arm and one oversized
white glove dramatically at BUD, medals jangling, face gloating and triumphant, magnifying glass in the
other hand. BUD is fast asleep on his short lead by the post, tail twitching, completely unaware. Tiny
PIP watching from his crate, curious. No text.
```

**S5 — Disproof 1 (0:17–0:23) · ECU→MED.EYE.PULLOUT**
```
{style prefix} 16:9. Extreme close-up through a magnifying glass lens on BUD's muzzle — completely
SPOTLESS and clean, no crumbs at all. Framing then widens to show BUD's SHORT LEAD pulled taut from his
collar to the post, ending far short of the stall table, with a clear visible gap between dog and table.
CHIEF crouched beside him, grin sagging into confusion, measuring the gap with two gloved fingers. No text.
```

**S6 — Micro-payoff 1 (0:23–0:28) · MED.EYE.STATIC**
```
{style prefix} Medium 16:9. CHIEF crossing a line out in his tiny notebook with an enormous theatrical
flourish, deadpan and frustrated. Beside him BUD has woken up and is mid-ENORMOUS YAWN, utterly
unimpressed. Behind CHIEF's shoulder, PARTLY OCCLUDED BY HIS ELBOW, a thin smear of golden pie filling is
just visible on the back edge of the tipped stall table. The tilt of the table is slightly greater than
before. No text.
```

**S7 — Accusation 2 (0:28–0:33) · LOW.WIDE → MED**
```
{style prefix} 16:9 low hero angle for maximum pomposity: CHIEF has stepped UP ONTO A CRATE and is
pointing operatically across frame at MITTENS with both his glove and his magnifying glass, chest thrown
out, utterly theatrical. Cut-in framing: MITTENS, a very small ASPHALT cat with a PAPER chest patch,
sitting perfectly still on stacked crates, staring back with a completely blank unimpressed expression.
No text.
```

**S8 — Disproof 2 (0:33–0:39) · MED-WIDE.EYE.STATIC**
```
{style prefix} Medium-wide 16:9. CHIEF holding a stretched tape measure between MITTENS and the round pie
plate — the cat is COMICALLY SMALLER than the plate, an obvious size mismatch. CHIEF looks at the tape,
then the cat, then the tape again, exasperated, and mimes trying to carry a huge round pie with tiny
paws. MITTENS sits utterly indifferent. Behind them the tipped stall table. No text.
```

**S9 — Micro-payoff 2 (0:39–0:44) · MED.EYE.STATIC**
```
{style prefix} Medium 16:9. CHIEF scratching a second crossing-out into his notebook, mustache twitching
with indignant frustration; the notebook shows two INK scribble crossings and no answers. MITTENS calmly
licking one paw and turning away. IN THE BACKGROUND, roughly HALF OCCLUDED BY A CRATE: the stall table's
tilt is now clearly greater, and a single drop of golden filling is forming on its lowest back edge. No text.
```

**S10 — Accusation 3 (0:44–0:50) · PUSHIN → MED**
```
{style prefix} 16:9. Slow push-in onto tiny PIP sitting on his crate, frozen mid-bite of a small biscuit,
with a few small crumbs clearly visible on his POP_TEAL scarf, eyes going wide with alarm. CHIEF advances
on him from frame right, magnifying glass thrust forward, face electrified with the biggest gasp yet, eyes
enormous. Flat ALERT_RED shock lines radiating behind CHIEF's head. No text.
```

**S11 — The absurd case (0:50–0:56) · MED-WIDE.EYE.PUSHIN**
```
{style prefix} Medium-wide 16:9. CHIEF gesturing like a professor at a corkboard he has slammed up beside
the stall: pinned to it are small PICTURES ONLY — a portrait of PIP, one of BUD, one of MITTENS, one of
the empty pie plate — connected by a mad web of ALERT_RED string, every single thread converging on PIP's
picture. NO WORDS OR TEXT anywhere on the board, only images, pins and string. CHIEF tapping the board
importantly. Tiny PIP below, shrinking, teary. No text.
```

**S12 — Peak injustice (0:56–1:02) · LOW.MED.STATIC**
```
{style prefix} 16:9 dramatic low angle. CHIEF raising an enormous comic rubber stamp loaded with an
ALERT_RED mark HIGH above his head, face in an over-the-top triumphant grin, about to bring it down. At
the very bottom of frame, tiny PIP curled into a small frightened ball, huge teary eyes, POP_TEAL scarf,
utterly helpless. BUD whining at the edge of frame; desaturated crowd silhouettes holding their breath.
REFLECTED IN THE STAMP'S POLISHED METAL SURFACE, small but present: a smear of golden filling and the
corner of the open evidence box. No text.
```

**S13 — The quiet point (1:02–1:08) · MED.EYE.STATIC**
```
{style prefix} Medium 16:9 two-shot. Tiny PIP, cornered and calm, not pleading — simply raising one small
arm and POINTING steadily past CHIEF toward the back of the stall, face determined. CHIEF, mid-gloat,
isn't even looking at him and is lifting the giant stamp EVEN HIGHER. In the background BUD's head has
turned to follow PIP's finger, MITTENS has turned to look, and two desaturated crowd silhouettes have
also turned — everyone is looking where PIP is pointing except CHIEF. No text.
```

**S14 — The silence (1:08–1:18) · MED→WIDE.EYE.TRACK**
```
{style prefix} 16:9 continuous tracking shot along CHIEF's eyeline, tense and quiet. CHIEF has finally
lowered the stamp and is following PIP's finger, his face draining from smug to confused to horrified.
The camera travels: the visibly TIPPED stall table, then a clear TRAIL OF GOLDEN FILLING running down its
back edge, over the lip, down the table leg, onto the cobbles — and settling on CHIEF'S OWN OPEN WOODEN
EVIDENCE BOX sitting on the ground. Dreadful, slow, unbroken. PIP calm and still pointing. No text.
```

**S15 — The reveal (1:18–1:25) · ECU→WIDE.EYE.PULLOUT**
```
{style prefix} 16:9. Extreme close-up inside CHIEF's open wooden evidence box: a whole intact golden
BRAND_YELLOW pie sitting neatly inside it, one slice-shaped dent where it landed. Then a full PULL-BACK
revealing the entire geometry in one frame: the HEAVY DARK LEDGER propped against the stall table's leg,
the table tipped askew because of it, the trail of filling running from the empty plate down into the box
like an arrow. CHIEF's face in shocked panic, the giant stamp slipping from his glove and thudding onto
his own boot leaving an ALERT_RED mark; the corkboard's red strings sagging. PIP gleeful and vindicated,
BUD tail wagging. Big flat FX_impact_star. No text.
```

**S16 — Payoff / loop seam (1:25–1:30) · WIDE → ECU (== S1)**
```
{style prefix} 16:9. Wide market square matching the earlier staging: PIP calmly setting the recovered
golden pie back onto its round plate on the (now righted) stall table and handing CHIEF his own empty
wooden evidence box. CHIEF stands holding it, mortified and sheepish, cap drooping, an ALERT_RED stamp
mark on his boot, still wearing his sash and medals. BUD happily munching one slice; MITTENS licking a
crumb; desaturated crowd silhouettes applauding PIP. PIP turns and gives a small friendly wave to camera
with a relieved smile. Framing then settles into an EXTREME CLOSE-UP of the pie plate IDENTICAL to the
opening shot. No text.
```

---

## Renderer notes
- **16:9 horizontal throughout** — recompose, don't letterbox. Use the width for side-by-side suspect/accuser staging.
- **Chart the table tilt shot by shot** (level → few degrees at S2 → progressively more → clearly askew at S14). It must never decrease. This is the spine of the mystery.
- **The ledger and the box never move** from S2 to S15. Same leg, same patch of ground, every time either is in frame.
- **The filling trail grows monotonically:** smear (S6) → forming drip (S9) → run down the leg (S12) → complete trail (S14–S15).
- **Seed glimpses must be genuinely subtle** — occluded by an elbow (S6), half-hidden by a crate (S9), reflected in metal (S12). If a first-time viewer spots them easily, occlude further. If a rewatching viewer can't find them, the replay payoff fails. Aim for "obvious only in hindsight."
- **Zero baked-in text anywhere** — the corkboard uses photos/pins/string, the notebook uses scribbles, the stamp leaves a mark.
- Crowd stays **Crowd-class**: desaturated, silhouette-level, no individual faces.
- Never transfer CHIEF's cap/sash/medals; never drop PIP's teal scarf or BUD's teal collar.
- No blur, glow, gradients or realistic lighting. No camera rotation.
- **SC6 stays bloodless:** the entire crime is a missing pie. No violence, menace or threat.
- **Advertiser-safe:** CHIEF is humiliated, never harmed. PIP is frightened but never actually punished, and is vindicated. BUD and MITTENS are relaxed, unharmed and wordless throughout.
