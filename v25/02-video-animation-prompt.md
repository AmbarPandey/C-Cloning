# v25 — Video & Animation Prompt ("The Tie-Breaker") · **SHORTS 9:16**

> Compact-package file 2: per-shot image prompts **and** motion/camera/FX. Locks to `01-video-script.md`.

**Render spec:** 1080×1920 · 30 fps · ~32 s · flat-2D house style · hard cuts only · no camera rotation ·
no blur/glow/gradients · loop seam (final frame == C1b).

## 0. Style prefix
```
Flat-color 2D cartoon, thick uniform INK #1A1A1A outlines (never pure #000000), no gradients,
minimal single-tone shading, high-contrast clean vector look, 9:16 vertical, mobile-legible.
Proportions: chunky 2-2.5 head heights — PIP ~2, CHIEF ~2.5.
Palette ONLY: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text. Advertiser-safe, no gore.
```

**Cast:** `CHAR_CHIEF_v1` (rotund warden, `POP_TEAL` jacket, `BRAND_YELLOW` buttons + medal sash, peaked cap with badge, `PAPER` gloves, `smug`) · `CHAR_PIP_v1` (tiny, `PAPER` body, `POP_TEAL` scarf every shot). **Cap + sash + medals never leave CHIEF.**

**The two-token rule (essential):** CHIEF's tiles are **`PAPER`**; PIP's tiles are **`POP_TEAL`**. This is
not decoration — it is what makes the crossing point and the ending legible in a single glance, muted, at
phone size. Never mix the two sets.

**Chain rule:** toppling is rendered as **discrete flat tile states** (upright → 45° → flat), never as a
blur or a smear. A running chain is a visible *wave* of angled tiles with hard-edged `FX_motionlines_v1`
ticks at the contact point.

**Environment** `BG_dominotable_v1`
```
BG_dominotable_v1: flat-2D contest table, composed for 9:16. A plain ASPHALT tabletop fills the middle of
frame. A bold ALERT_RED FINISH LINE runs across it with a BRAND_YELLOW PRIZE MARKER standing upright on
the line. Plain PAPER wall behind, flat desaturated hall shapes. Quiet, lower-contrast than the cast,
generous negative space, no text.
```
**Continuity:** the finish line, the marker's position and **the crossing point** hold fixed screen
positions from C2 to C8. Run length only ever increases before C5. Once toppling begins nothing is re-set
until C8. C8 settles to the exact C1b framing.

---

## Per-shot prompts + direction

### C1 — 0:00–0:01.5 · ECU.EYE.STATIC · cold payoff
```
{style prefix} Extreme close-up, 9:16: a single PAPER domino tile caught ALREADY MID-TOPPLE, leaning
sideways at about 45 degrees, its edge about to strike a POP_TEAL tile standing at right angles to it.
Contact has NOT happened yet. Flat ASPHALT tabletop beneath. No table edges, no faces, no context, no
character entering frame. Tight, high contrast, motion already underway.
```
- 45 frames, static, motion underway on frame 1. FX: one flat `FX_motionlines_v1` tick. **No music.**

### C1b — 0:01.5–0:02 · MED.FLAT.STATIC · goal diagram
```
{style prefix} Flat dead-centre schematic, 9:16: a bold ALERT_RED FINISH LINE with a BRAND_YELLOW PRIZE
MARKER standing upright on it, and beside it a simple pictogram — a short row of tiles, an INK arrow, the
line, and a large POP_TEAL TICK. Plain PAPER background, no characters, no text. Schematic, readable in
one pass.
```
- Nothing moves, 15 frames. Music **enters**. One flat sparkle on the tick.

### C2 — 0:02–0:06 · MED.EYE.PUSHIN · rewind/setup
```
{style prefix} Medium 9:16 on a flat ASPHALT contest table. A bold ALERT_RED finish line crosses it with
a BRAND_YELLOW prize marker standing on the line. Tiny PIP (PAPER body, POP_TEAL scarf, neutral) is laying
a SHORT STRAIGHT run of POP_TEAL tiles toward the line. Beside him CHIEF (POP_TEAL jacket, BRAND_YELLOW
medal sash, peaked cap with badge, gloating) is laying a GRAND LOOPING arc of PAPER tiles — and his sweep
passes DIRECTLY OVER PIP'S ROW, with two PAPER tiles placed at the CROSSING POINT. The crossing is clearly
visible but unemphasised. PIP glances at it and carries on.
```
- Motion: PIP lays 4 tiles (even, 4-frame each); CHIEF lays 6 (fast). Camera: push-in 100%→110% ending on the crossing point. **No FX on the seed.**

### C3 — 0:06–0:11 · WIDE.EYE.STATIC · escalation 1
```
{style prefix} Wide 9:16. Tiny PIP has finished and stepped back from a short straight run of just FOUR
POP_TEAL tiles. CHIEF is still building his PAPER run — a spiral, a small ramp, a fan of tiles — laughing
at PIP's four, gloating. The ALERT_RED finish line, the BRAND_YELLOW marker and the crossing point over
PIP's row all visible.
```
- Motion: PIP steps back (4-frame hold); CHIEF lays a spiral + ramp. FX: none beyond tile placement.

### C4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight) · escalation 2
```
{style prefix} Medium-wide 9:16. CHIEF's PAPER run is now enormous and elaborate, filling most of the flat
ASPHALT table with spirals, a ramp and a fan, still passing over PIP's four POP_TEAL tiles at the crossing
point. He is gesturing grandly at his own construction and dismissively at PIP's four tiles, triumphant.
PIP worried. The ALERT_RED line and BRAND_YELLOW marker ahead.
```
- Motion: three new sections added (~1.6 s apart), 3-frame hold each.

### C5 — 0:16–0:22 · FULL.LOW.PUSHIN → HOLD · full commit
```
{style prefix} Low hero angle, 9:16. CHIEF's PAPER chain is RUNNING — a visible wave of tiles toppling
through the spiral, up the ramp and across the fan as discrete flat angled states with hard-edged
FX_motionlines ticks at the contact point. It REACHES the bold ALERT_RED finish line FIRST and KNOCKS THE
BRAND_YELLOW PRIZE MARKER OVER. CHIEF plants an enormous triumphant pose, chest out, chin high, medals
catching, FX_sparkle accents. He has won.
```
- Motion: the run travels (continuous), the marker falls, then the pose **freezes** ~1.5 s. Music **cuts mid-phrase at 0:16 on the flick.**

### C6 — 0:22–0:27 · WIDE.EYE.STATIC→TILT · pattern break
```
{style prefix} 9:16, quiet. CHIEF's PAPER chain HAS NOT STOPPED — the wave of toppling tiles continues on
PAST the ALERT_RED finish line and is travelling back across the flat ASPHALT table toward the CROSSING
POINT over PIP's four POP_TEAL tiles. CHIEF still frozen in his triumphant pose, his eyes beginning to
follow the run, faltering. Tiny PIP looking up, hopeful. No sparkle, no effects beyond the motion ticks.
```
- Motion: **three discrete stretches of run** (~1.4 s apart) closing on the crossing. Camera: static wide, then slow tilt to the crossing at ~0:26.

### C7 — 0:27–0:31 · MED.EYE.PUNCHIN → SETTLE · irony reversal
```
{style prefix} Punch-in 9:16. CHIEF's PAPER chain has reached the crossing point and KNOCKED PIP'S FIRST
POP_TEAL TILE. PIP's four POP_TEAL tiles are firing in sequence — and they topple the BRAND_YELLOW PRIZE
MARKER OVER ONTO PIP'S SIDE of the bold ALERT_RED finish line. CHIEF's face is shocked and panicked as he
tracks the fall, cap and sash and medals all still on. Tiny PIP gleeful. Both chains now lying flat across
the table. Flat FX_impact_star at the crossing contact.
```
- Motion: crossing contact (4 frames), PIP's four tiles fire in sequence (5 frames each), marker falls to PIP's side. Camera: punch-in on the crossing, follow the four tiles, settle wide; **0.5 s freeze** on the prize on PIP's side with both chains flat.

### C8 — 0:31–0:32 · WIDE → MED (== C1b) · payoff/loop
```
{style prefix} 9:16. Tiny PIP holds the BRAND_YELLOW prize marker, relieved, and is reaching over to STAND
ONE OF CHIEF'S FALLEN PAPER TILES BACK UPRIGHT — plainly, no smirk — then gives a small friendly wave to
camera. CHIEF stands over his flattened PAPER run, cap still on, sheepish. Framing then settles into the
EXACT C1b schematic composition: the ALERT_RED finish line, the BRAND_YELLOW prize marker standing upright
on it, and the POP_TEAL tick pictogram.
```
- Motion: tile stood upright (5 frames), PIP wave. **No sparkle on PIP.** Settle to C1b framing as the final frame.

---

## Transitions & cut map
| Between | Type |
|---|---|
| C1→C1b | hard cut (payoff → rule) |
| C1b→C2 | hard cut (rewind) |
| C2→C3→C4 | hard cut |
| **C5 internal 0:16** | **music cut on the flick, no visual cut** — the run continues |
| C5→C6 | hard cut |
| C6→C7 | hard cut into punch-in |
| **C7 internal** | 0.5 s freeze on the prize on PIP's side |
| C7→C8 | hard cut |
| C8→loop | hard cut, seam to C1 |

No dissolves, fades, wipes, glitch, zoom-blur or camera rotation.

> **The key craft note:** the chain must be **traceable end to end.** The camera has to follow the run's
> actual path — through the spiral, over the line, back across the table, into the crossing, along PIP's
> four tiles, into the prize — without jumping. This is the episode's whole replay mechanism: on rewatch the
> viewer wants to check that the path was really there from C2, and it must survive that check.

---

## Handoff checklist
- [ ] 9:16 / 1080×1920, ≈32 s, timecodes exact.
- [ ] C1 tight, mid-topple, **contact not yet made**, no entrance.
- [ ] C1b diagram wordless: line + marker + chain-reaches-line pictogram.
- [ ] **Two-token rule enforced everywhere:** CHIEF `PAPER`, PIP `POP_TEAL`. Never mixed.
- [ ] Finish line, marker position and **crossing point** hold fixed screen positions C2→C8.
- [ ] Both runs in the same frame aiming at the same line (C2–C4).
- [ ] Run length monotonic C2→C4; nothing re-set once toppling begins until C8.
- [ ] **CHIEF's run genuinely reaches the line first and topples the marker** in C5.
- [ ] **The chain path is continuous and traceable** — no camera jumps across the run in C5, C6 or C7.
- [ ] Toppling rendered as **discrete flat tile states**, never blur or smear.
- [ ] CHIEF keeps cap + sash + medals throughout.
- [ ] Colour tokens only — CHIEF tiles `PAPER`, PIP tiles `POP_TEAL`, line `ALERT_RED`, marker `BRAND_YELLOW`, table `ASPHALT`. **No "white", no "wood", no "black".**
- [ ] Ad-safety: light tiles on a table, nothing falls on anyone, no breakage.
- [ ] Zero baked text; no English colour words in any prompt above.
- [ ] Final frame matches C1b with the marker standing again.
