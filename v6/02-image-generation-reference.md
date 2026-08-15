# v6 — Image-Generation Reference ("One Sweet, One Coin") · **SHORTS 9:16**

> Everything the image AI needs for v6: locked house style, characters, their reactions, the
> surroundings, and a **ready-to-paste prompt for each of the 8 shots** (aligned to the master
> timeline in `01-video-script.md`). For the full reusable vocabulary see the repo-root
> [`IMAGE-GEN-REFERENCE.md`](../IMAGE-GEN-REFERENCE.md); this file is the v6-specific subset.

---

## 0. Global style prefix — PREPEND TO EVERY PROMPT (do not edit)
```
Flat-color 2D cartoon, thick uniform black outlines, no gradients, minimal single-tone shading,
chunky 2.5-head proportions, high-contrast, clean vector look, 9:16 vertical, mobile-legible.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text unless specified. Advertiser-safe, no gore.
```
**Back to vertical:** v5 was the 16:9 long-form episode; v6 returns to **9:16**. Reuse the
`CHAR_CHIEF_v1` / `CHAR_PIP_v1` / `CHAR_BUD_v1` sheets as reference images/seeds on every shot.

**Compose vertically, deliberately.** 9:16 is the perfect shape for this story — stack the frame:
**sweets mountain (upper third) → balance scale (middle third) → purse and counter (lower third)**. The
eye should travel *up and down the price*, which is exactly what the episode is about.

---

## 1. Characters (lock these; reuse every shot)

**CHIEF — Bully / Antagonist, the customer** (`CHAR_CHIEF_v1`)
```
Short rotund puffed-up warden-type, ~2.5 heads tall, big head, small legs, chest out, chin high.
POP_TEAL #2FB6A3 jacket with gold buttons, oversized peaked cap with a badge, a diagonal
BRAND_YELLOW #FFD400 sash covered in medals, oversized white gloves, bushy brows, tiny mustache,
permanent smug half-smile, small eyes, face PAPER #FFF7E0, INK #1A1A1A outline.
Silhouette signature (NEVER omit, NEVER transfer): cap + sash + medals. Default face: smug.
```

**PIP — Hero / Underdog, the stall keeper** (`CHAR_PIP_v1`)
```
Tiny soft rounded underdog, ~2 heads tall, big head, oversized expressive eyes, tiny mouth, soft
brows, little stub limbs, gentle timid slouch. Body PAPER #FFF7E0, simple tee, a tiny POP_TEAL
#2FB6A3 scarf (signature — present in EVERY shot), INK #1A1A1A outline. Default face: worried.
v6 note: PIP is BEHIND the counter throughout and is almost completely STILL. He makes exactly two
moves in the whole video — one polite point at the rate sign (C2) and one small wave (C8).
```

**BUD — Animal class, PIP's companion** (`CHAR_BUD_v1`) — ⚠️ proposed, not locked
```
Tiny scruffy round dog, ~1.5 heads tall, shorter than PIP. Soft PAPER #FFF7E0 body, one POP_TEAL
#2FB6A3 collar, big friendly INK eyes, small floppy ears, stubby waggy tail, three or four shape
masses total, INK outline. Completely WORDLESS. Never harmed or distressed.
v6: appears only in C8, to receive the returned mountain of sweets. Warm, non-plot-critical.
```

> **Costume lock:** CHIEF's cap/sash/medals are **costume, not props** — never removed, never transferred.
> A slightly drooping cap in C8 is allowed.

**Status rule:** CHIEF reads bigger/louder/more decorated throughout, and he is the only one who moves
much. His status inverts not by scale but by **quantity** — he ends the video holding the single smallest
object in it, while the tiny dog gets the mountain.

---

## 2. Reactions used in v6 (face + body per beat)

| Clip | CHIEF face → pose | PIP face → pose | BUD |
|---|---|---|---|
| C1 | `smug` → `strut` (slams purse, seizes cup) | `worried` → `stand` (behind counter) | — |
| C2 | `gloating` → `hold` (scooping, waving PIP off) | `worried` → `reach` (one polite point at the sign) | — |
| C3 | `gloating` → `hold` (careless scooping) | `worried` → `stand` (two flicked glances) | — |
| C4 | `triumphant` → `hold` (two-handed shovelling, gloating over the pile) | `worried` (alarmed) → `stand` | — |
| C5 | `triumphant` (L3) → `victory` (slam + palm out) | — (low/out of frame) | — |
| C6 | `smug` → `confused` → `worried` (grin dies in 3 stages, sweat bead) | `neutral` → `reach` (calmly tips the purse) | — |
| C7 | `shocked` → `panicked` (3-stage snap) → `flail` (frantic removal) | `gleeful` → `stand` (then beams) | — |
| C8 | `sheepish` → `slump` (staring at one sweet) | `relieved` → `relaxed` + `wave` | dives in, tail wagging |

---

## 3. Surroundings / environment (v6 location)

**Fairground Sweet Stall** (`BG_sweetstall_v1`) — new asset
```
BG_sweetstall_v1: flat-2D fairground sweet stall, composed for 9:16 VERTICAL. A PAPER #FFF7E0 wooden
counter runs across the lower-middle of frame. Above it a POP_TEAL #2FB6A3 striped awning. Behind the
counter: a row of simple glass jars filled with BRAND_YELLOW #FFD400 sweets, and a stack of plain cups
arranged smallest to largest. Centre of the counter: a two-pan brass BALANCE SCALE in ASPHALT #6E7076
metal, with a central beam and two shallow pans on chains — no dial, no numbers, no text. Propped
against the stall front: a small PAPER sign bearing only a PICTOGRAM — one sweet shape, an INK equals
sign, one coin shape. Background: flat desaturated fairground shapes (a distant tent, simple bunting)
and a flat SKY #BFE3F2 strip at the top. Quiet, lower-contrast than the cast, no text.
```
- **Sub-views:** `BG_sweetstall_wide_v1` (full stall, C1/C8) · `BG_sweetstall_counter_v1` (counter + scale, C2–C4) · `BG_sweetstall_scale_v1` (tight on the balance scale, C5–C7).
- **Depth layers:** fg = counter edge, purse, rate sign; mg = scale, cups, cast; bg = jars, awning, flat fairground, sky.
- **Continuity locks (critical):**
  - The **rate pictogram stays in the same spot on the stall front** and at the same size in every shot where the stall front is visible.
  - The **balance scale never moves** on the counter; only its pans move.
  - **Pan positions must always be physically consistent with the pile size.** This is the video's logic and viewers will check it on replay.
  - C8 reuses the exact C1 plate for the loop seam.

---

## 4. Props (v6 set)
| Prop | ID | Note |
|---|---|---|
| **Balance scale** | `PROP_balancescale_v1` | The star of the episode — two pans, a beam, no numbers. Moves in discrete mechanical increments |
| **Rate pictogram sign** | `PROP_ratesign_v1` | **SEED A** — one sweet, `INK` equals sign, one coin. Textless, universal |
| **Coin purse** | `PROP_purse_v1` | **SEED B** — huge, ostentatious, `ALERT_RED`. Contains exactly **one** coin |
| Coin | `PROP_coin_v1` | A single `BRAND_YELLOW` coin. The pivot of the whole story |
| Sweets | `PROP_sweets_v1` | Chunky rounded `BRAND_YELLOW` sweets; needs a loose-pile variant and a single-sweet variant |
| Cups | `PROP_cups_v1` | A stack, smallest to largest. CHIEF takes the largest |
| Scoop | `PROP_scoop_v1` | Abandoned at C4 in favour of both hands |
| Sweet jars | `PROP_jars_v1` | Behind the counter; set dressing |
| BUD's big cup | `PROP_bigcup_v1` | Receives the returned mountain in C8 |
| FX | `FX_motionlines_v1`, `FX_sparkle_v1` (C5, C8), `FX_impact_star_v1` (C7), `FX_dustpuff_v1` (purse slam, pan crash) | benign, flat, no blur/glow |

**Palette discipline:** `BRAND_YELLOW` is **the sweets and the coin** — the object of greed and the thing
that limits it are the *same colour*, which is the visual thesis of the episode in one decision. Keep them
the only saturated yellow in frame. `ALERT_RED` is reserved exclusively for the **purse** — red is the
thing that betrays him. The scale stays neutral `ASPHALT` so it reads as an impartial machine.

---

## 5. Per-shot render prompts (paste-ready)

**Shot C1 — Hook + seed (0:00–0:02) · WIDE.EYE.STATIC**
```
{style prefix} Wide vertical 9:16 flat-2D fairground sweet stall. A PAPER wooden counter across the
lower-middle of frame, POP_TEAL striped awning above, glass jars of BRAND_YELLOW sweets and a stack of
cups (smallest to largest) behind it. Centre of the counter: a two-pan brass BALANCE SCALE in ASPHALT
metal with two shallow pans on chains, no numbers. Propped on the stall front: a small PAPER sign showing
ONLY A PICTOGRAM — one sweet shape, an INK equals sign, one coin shape. Behind the counter stands tiny PIP
(PAPER body, POP_TEAL scarf, big worried eyes). Arriving at the counter, a pompous round CHIEF (POP_TEAL
jacket, oversized peaked cap with badge, diagonal BRAND_YELLOW medal sash, tiny mustache, smug) has just
SLAMMED a huge ostentatious ALERT_RED coin purse down on the counter and is seizing the LARGEST cup from
the stack. Flat desaturated fairground and SKY behind. This exact framing repeats at the end. No text.
```

**Shot C2 — Setup (0:02–0:06) · MED.EYE.PUSHIN**
```
{style prefix} Medium 9:16 two-shot across the counter. CHIEF scooping BRAND_YELLOW sweets into his large
cup with a scoop, gloating, not looking at PIP. Tiny PIP behind the counter has raised one small hand and
is politely POINTING at the pictogram sign on the stall front. CHIEF waves him off dismissively with an
oversized white glove. His elbow has knocked the huge ALERT_RED purse so that IT HAS TIPPED OPEN, clearly
showing that it is NEARLY EMPTY inside — just one coin visible. The purse is not highlighted or emphasised
in any way; it simply happens to be open. Balance scale on the counter beside them. No text.
```

**Shot C3 — Escalation 1 (0:06–0:11) · MED.EYE.STATIC**
```
{style prefix} Medium 9:16. CHIEF mid-scoop, careless and wide-armed, as the pile of BRAND_YELLOW sweets
mounds up above the rim of his cup with a few loose sweets bouncing onto the PAPER counter. Flat
FX_motionlines on his arm swing. Tiny PIP behind the counter, still and worried, glancing between the
growing pile and the brass balance scale. The pictogram sign visible on the stall front. No text.
```

**Shot C4 — Escalation 2 (0:11–0:16) · MED-WIDE.EYE.PUSHIN(slight)**
```
{style prefix} Medium-wide 9:16. CHIEF has abandoned the scoop and is SHOVELLING BRAND_YELLOW sweets with
BOTH HANDS, building an absurd overflowing mountain of sweets far above the rim of the cup, with sweets
cascading down onto the counter. He is gloating over the top of the pile at tiny PIP, chest out, chin high,
triumphant. PIP looks alarmed. Thick flat FX_motionlines on the shovelling. One sparkle glint on a medal.
No text.
```

**Shot C5 — Anticipation (0:16–0:22) · FULL.LOW.PUSHIN**
```
{style prefix} Low hero angle, vertical 9:16. CHIEF has SLAMMED the overflowing cup of BRAND_YELLOW sweets
down onto the LEFT PAN of the brass balance scale — the mountain of sweets towering in the upper third of
frame — and has thrust his other oversized glove out, palm up, waiting to be told the total. Chest out,
chin high, utterly certain, self-satisfied FX_sparkle accents around him. The scale's pans have begun to
move. Flat dust puff at the base of the slam. No text.
```

**Shot C6 — Pattern break (0:22–0:27) · MED.EYE.STATIC→TILT**
```
{style prefix} Vertical 9:16, tense and quiet. Tiny PIP has calmly lifted the huge ALERT_RED coin purse and
turned it upside down above the scale's RIGHT PAN — and EXACTLY ONE small BRAND_YELLOW coin has dropped
out and is landing in the pan. The heavily loaded sweets pan has CRASHED to the bottom of its travel while
the coin pan flies up, wildly unbalanced. CHIEF's grin has died: he stares at the empty purse, mouth open,
one sweat bead on his temple. Flat FX_motionlines on the crashing pan. No text.
```

**Shot C7 — Twist / irony reversal (0:27–0:31) · MED.EYE.PUNCHIN**
```
{style prefix} Punch-in medium, vertical 9:16. CHIEF frantically scooping handfuls of BRAND_YELLOW sweets
BACK OUT of the pan, arms a blur of flat motion lines, face shocked and panicked, the pile shrinking
rapidly. The two pans of the brass balance scale have crept level. Final state: the scale hangs PERFECTLY
BALANCED with ONE SINGLE BRAND_YELLOW SWEET in the left pan against ONE BRAND_YELLOW COIN in the right
pan. Small flat FX_impact_star at the moment of balance. Tiny PIP beaming gleefully behind the counter.
The pictogram sign visible on the stall front. No text.
```

**Shot C8 — Payoff / loop seam (0:31–0:32) · WIDE.EYE.STATIC (== C1)**
```
{style prefix} Wide vertical 9:16 composition IDENTICAL in framing, background plate and counter line to
shot C1. CHIEF now stands holding ONE TINY BRAND_YELLOW SWEET pinched between two oversized white gloves,
staring down at it, mortified and sheepish, cap drooping slightly, still wearing his sash and medals; the
huge ALERT_RED purse lies flat and empty on the counter. Beside him, tiny PIP has tipped the entire
returned mountain of sweets into a big cup and set it on the ground for BUD, a tiny scruffy dog with a
POP_TEAL collar, who is happily diving into it, tail wagging. PIP turns and gives a small friendly wave to
camera with a relieved smile. A small sparkle on BUD's overflowing cup. Calm resolved mood. No text.
```

---

## Renderer notes
- C1 and C8 **must** share an identical background plate, framing and counter line (loop seam) — only the scale state, the purse and what each character holds change.
- **Pan physics is the video's logic.** In every shot, the pan positions must be consistent with how much is in them: heavily down in C5–C6, creeping level in C7, perfectly level at the end. Viewers will check this on replay.
- **The pile is monotonic:** it grows every beat from C2 to C5 and shrinks every beat in C7. Never let it flicker.
- The scale moves in **discrete mechanical increments**, never a smooth glide — it should read as arithmetic being performed.
- **Seed A** (rate pictogram) must be legible in C1 but rendered as ordinary stall signage — no highlight, no sparkle, no framing emphasis.
- **Seed B** (the open, nearly-empty purse at ~0:04) must be *clearly visible but unemphasised*. If a first-time viewer spots it easily, occlude it further; if a rewatching viewer can't find it, it fails. Aim for "obvious only in hindsight."
- **Zero baked-in text anywhere** — the rate is a pictogram and the scale has no numbers. This is what makes the episode work in every language.
- Never transfer CHIEF's cap/sash/medals; never drop PIP's teal scarf or BUD's teal collar; never restyle or reproportion the cast.
- Keep PIP **still**. His two small movements (the point, the wave) are the only ones he gets, and their scarcity is what makes them land.
- No blur, glow, gradients or realistic lighting. No camera rotation.
- **Advertiser-safe:** CHIEF is embarrassed by his own greed, never harmed. **Do not render anything that reads as mocking poverty** — the joke is a show-off with a flashy empty purse (vanity), and he is never denied anything he needs. BUD is happy and unharmed throughout.
