# v21 — Video & Animation Prompt ("The Upgrade") · **SHORTS 9:16**

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

**Cast:** `CHAR_CHIEF_v1` (rotund warden, `POP_TEAL` jacket, `BRAND_YELLOW` buttons + medal sash, peaked cap with badge, `PAPER` gloves, `smug`) · `CHAR_PIP_v1` (tiny, `PAPER` body, `POP_TEAL` scarf every shot, `worried` default). **Cap + sash + medals never leave CHIEF.**

**Morph rule (the core craft of this episode):** the balloon is a **flat `BRAND_YELLOW` shape with an `INK` outline**, never glossy, never gradient-shaded. The transformation is achieved by **progressively removing outline detail and rounding the silhouette** — lobes merge into curves, limbs merge into the body, the muzzle flattens — in discrete stages. Six morph states are required:
`M0` crisp small lion · `M1` grand lion · `M2` huge lion · `M3` mane rounded off · `M4` legs merged · `M5` featureless blob.
**No burst state exists. There is no pop, no debris, no shred.**

**Environment** `BG_balloonstand_v1`
```
BG_balloonstand_v1: flat-2D fairground balloon-sculpture stand, composed for 9:16. A PAPER counter across
the lower-middle of frame under a POP_TEAL striped awning. On the counter a hand pump with a round
pressure gauge mounted on it, the gauge face carrying a bold ALERT_RED max line across its upper arc, and
an ALERT_RED release-valve lever on its side. A rack of uninflated PAPER balloons behind. Background flat
desaturated fairground shapes and a flat SKY strip. Quiet, lower-contrast than the cast, no text.
```
**Continuity:** the gauge's screen position and its `ALERT_RED` max line are identical in C1b, C2, C3, C4, C6, C8. The needle only ever rises before C8. The morph never reverses.

---

## Per-shot prompts + direction

### C1 — 0:00–0:01.5 · ECU.EYE.STATIC · cold payoff
```
{style prefix} Extreme close-up, 9:16: a flat BRAND_YELLOW balloon-sculpture lion's MANE caught ALREADY
MID-SWELL — the sculpted lobes stretching smooth and merging into one another, one ear rounding away,
INK outlines under visible tension with flat strain marks. No stand, no faces, no character entering
frame. Tight, high contrast, motion already underway.
```
- 45 frames, static. **No music.** FX: flat `FX_strainline_v1` on the rubber.

### C1b — 0:01.5–0:02 · MED.FLAT.STATIC · goal diagram
```
{style prefix} Flat dead-centre schematic, 9:16: a round PAPER pressure gauge with an INK needle resting
at the low end and a bold ALERT_RED MAX LINE drawn across its upper arc. Beside it a small pictogram —
one puff symbol, an INK equals sign, one balloon-twist knot symbol. Plain PAPER background, no
characters, no text. Schematic, instantly readable.
```
- Nothing moves, 15 frames. Music **enters**. One flat sparkle on the max line.

### C2 — 0:02–0:06 · MED.EYE.PUSHIN · rewind/setup
```
{style prefix} Medium 9:16 at a balloon-sculpture stand with a POP_TEAL striped awning. Tiny PIP (PAPER
body, POP_TEAL scarf, neutral) holds a CRISP SMALL flat BRAND_YELLOW balloon LION with clean sculpted
lobes, happy with it. Beside him CHIEF (POP_TEAL jacket, BRAND_YELLOW medal sash, peaked cap with badge,
gloating) sneers at its size, has seized the hand pump, and is JAMMING THE ALERT_RED RELEASE-VALVE LEVER
SHUT with one PAPER glove while beginning to pump. The round gauge with its ALERT_RED max line is
visible on the pump, needle low. The jammed lever is clear but unemphasised.
```
- Motion: PIP holds still; CHIEF 3-frame valve jam + pump cycle begins. Camera: push-in 100%→110% ending on the jammed lever. **No FX on the seed.**

### C3 — 0:06–0:11 · MED.EYE.STATIC · escalation 1
```
{style prefix} Medium 9:16. CHIEF's balloon sculpture has grown into a GRAND flat BRAND_YELLOW LION with
a full sculpted mane, clearly larger than PIP's small one, and he is gesturing at his own then
dismissively at PIP's, gloating, EYELINE ON PIP not on the gauge. The pump's round gauge shows the INK
needle climbed past the halfway point, still below the ALERT_RED max line. Tiny PIP neutral, holding his
crisp small lion.
```
- Motion: pump cycle; needle ticks up in 3 discrete steps. Camera: static; 4-frame hold as it passes midpoint.

### C4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight) · escalation 2
```
{style prefix} Medium-wide 9:16. CHIEF pumps two-handed, chest out, triumphant. His flat BRAND_YELLOW
LION is now HUGE but still recognisably a magnificent sculpted lion. The pump's gauge needle has CROSSED
the bold ALERT_RED MAX LINE and is still climbing; the ALERT_RED release valve is visibly jammed shut so
nothing vents. He is not looking at the gauge. Tiny PIP looking worried. Flat strain marks appearing on
the balloon's INK outline.
```
- Motion: needle crosses the line (3-frame hold on the crossing); morph state `M2`. FX: `FX_strainline_v1` begins.

### C5 — 0:16–0:22 · FULL.LOW.PUSHIN → HOLD · full commit
```
{style prefix} Low hero angle, 9:16. CHIEF hoists an ENORMOUS and genuinely IMPRESSIVE flat BRAND_YELLOW
balloon LION overhead in a huge triumphant pose — full sculpted mane, four clear legs, a proper muzzle,
crisp INK outlines — chest out, chin high, medals catching, FX_sparkle accents. It is a real sculpture
and it is magnificent. The pump is still running behind him, gauge needle far past the ALERT_RED max line.
```
- Morph state `M2` at its best. The pose **freezes** ~1.5 s. Music **cuts mid-phrase at 0:16**; the pump keeps running.

### C6 — 0:22–0:27 · MED.EYE.STATIC→TILT · pattern break
```
{style prefix} 9:16, tense and quiet. The enormous flat BRAND_YELLOW balloon LION is DEFORMING feature by
feature: the sculpted mane lobes have rounded off into one smooth curve, one leg has merged into the
body, and the muzzle is flattening away — the INK outline losing detail with each stage. CHIEF is still
frozen in his triumphant pose, oblivious. The pump still running, ALERT_RED valve still jammed. Tiny PIP
looking up, worried. No sparkle, no effects beyond flat strain marks.
```
- Motion: **three discrete morph stages** `M3` → `M4` → (start of `M5`), ~1.4 s apart. Camera: static, then slow tilt up to the sculpture at ~0:25.

### C7 — 0:27–0:31 · MED.EYE.PUNCHIN → SETTLE · visual transformation
```
{style prefix} Punch-in 9:16. The sculpture has become a SMOOTH, ENORMOUS, COMPLETELY FEATURELESS flat
BRAND_YELLOW BLOB with a single clean INK outline — no mane, no legs, no face, faintly wobbling.
IMPORTANT: it has NOT burst — there is NO pop, no shreds, no debris, no burst shapes anywhere. CHIEF is
turning it over looking for a face on it, expression shocked and panicked, cap and sash and medals all
still on. Beside him tiny PIP's crisp small flat BRAND_YELLOW LION is perfect and unchanged, gleeful.
```
- Morph state `M5`. Motion: the last feature smooths away (8 frames), then a slow blob wobble. Camera: punch-in on the final smoothing, settle wide; **0.5 s freeze** on blob-beside-lion.

### C8 — 0:31–0:32 · WIDE → MED (== C1b) · payoff/loop
```
{style prefix} 9:16. CHIEF holds the giant featureless flat BRAND_YELLOW blob, cap still on, sheepish.
Tiny PIP is HOLDING OUT his own crisp small BRAND_YELLOW lion toward him — offering it plainly, no smirk
— and gives a small friendly wave to camera, relieved. Framing then settles into the EXACT C1b schematic
composition: the round gauge with its INK needle back at REST below the bold ALERT_RED max line, and the
one-puff-one-twist pictogram beside it.
```
- Motion: PIP extends the lion (6 frames), wave; the blob gives one slow wobble. **No sparkle on PIP.** Settle to C1b framing as the final frame.

---

## Transitions & cut map
| Between | Type |
|---|---|
| C1→C1b | hard cut (payoff → rule) |
| C1b→C2 | hard cut (rewind) |
| C2→C3→C4 | hard cut |
| **C5 internal 0:16** | **music cut only, no visual cut** — the pump keeps running |
| C5→C6 | hard cut |
| C6→C7 | hard cut into punch-in |
| **C7 internal** | 0.5 s freeze on blob-beside-lion |
| C7→C8 | hard cut |
| C8→loop | hard cut, seam to C1 |

No dissolves, fades, wipes, glitch, zoom-blur or camera rotation.

> **The key craft note:** the transformation must be **continuous and silent**, achieved by *subtracting
> outline detail*, never by a burst. A pop would be a single loud event; a slow smoothing is six seconds
> of dread the audience can see coming and the character cannot. It is also the ad-safety choice — no
> bang, no startle, nothing that reads as breakage.

---

## Handoff checklist
- [ ] 9:16 / 1080×1920, ≈32 s, timecodes exact.
- [ ] C1 tight, mid-morph, no entrance.
- [ ] C1b diagram wordless; the gauge + max line make "too much" a perception.
- [ ] Gauge screen position and max-line height identical in C1b, C2, C3, C4, C6, C8.
- [ ] Needle rise monotonic C3→C6; morph monotonic `M0`→`M5`, never reversing.
- [ ] **The C5 lion is genuinely impressive** — a real sculpture, crisp outlines, four legs, a muzzle.
- [ ] **No burst state rendered anywhere.** No pop, shreds, debris or burst shapes in any frame.
- [ ] CHIEF keeps cap + sash + medals throughout.
- [ ] Colour tokens only — balloons `BRAND_YELLOW`, max line and valve `ALERT_RED`, awning `POP_TEAL`. **No "rubber red", no "white", no "gold".**
- [ ] Zero baked text; no English colour words in any prompt above.
- [ ] Final frame matches C1b with the needle at rest.
