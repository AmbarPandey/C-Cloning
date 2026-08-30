# v23 — Video & Animation Prompt ("The Evidence") · **SHORTS 9:16**

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

**Cast:** `CHAR_CHIEF_v1` (rotund warden, `POP_TEAL` jacket, `BRAND_YELLOW` buttons + medal sash, peaked cap with badge, **`PAPER` gloves carrying a distinctive `INK` tread pattern**, `smug`) · `CHAR_PIP_v1` (tiny, `PAPER` body, `POP_TEAL` scarf every shot). **Cap + sash + medals never leave CHIEF.**

**The tread rule (the whole episode):** CHIEF's gloves carry one **specific, bold, memorable `INK` tread
pattern** — e.g. three chevrons inside a rounded square. That exact pattern must appear:
1. on the comparison card in C1b, C3, C5, C6, C7, C8
2. on his gloves in **every shot where a glove is visible**, from C2 onward
3. on every print he leaves in the powder
It is never varied, never simplified, never rotated. If the patterns don't match exactly, the twist fails.

**Powder rule:** powder is flat `PAPER` shapes with `INK` outlines — never a gradient, haze, cloud or
particle spray. Coverage grows as **discrete added shapes**, not as opacity.

**Environment** `BG_storeroom_v1`
```
BG_storeroom_v1: flat-2D storeroom, composed for 9:16. A plain ASPHALT shelf spans the middle of frame
holding a few PAPER jars, with one clean empty RING where a jar stood. ASPHALT floor below, plain PAPER
wall behind. Quiet, lower-contrast than the cast, generous negative space, no text.
```
**Continuity:** the empty ring and the shelf hold fixed screen positions C2→C8. Powder coverage only ever
increases before C8. C8 settles to the exact C1b framing.

---

## Per-shot prompts + direction

### C1 — 0:00–0:01.5 · ECU.EYE.STATIC · cold payoff
```
{style prefix} Extreme close-up, 9:16: an oversized PAPER glove's thumb ALREADY PRESSING DOWN into a
dusting of flat PAPER powder on a dark ASPHALT surface, caught mid-press, lifting slightly to reveal a
crisp INK TREAD MARK of three chevrons inside a rounded square. No room, no face, no character entering
frame. Tight, high contrast.
```
- 45 frames, static, motion underway on frame 1. **No music.**

### C1b — 0:01.5–0:02 · MED.FLAT.STATIC · goal diagram
```
{style prefix} Flat dead-centre schematic, 9:16: a PAPER comparison card showing a BOLD INK TREAD PATTERN
of three chevrons inside a rounded square on the left, an INK equals sign, and a simple culprit silhouette
on the right. Beneath, a large POP_TEAL TICK and a large ALERT_RED CROSS as the two verdicts. Plain PAPER
background, no characters, no text. Bold, specific, memorable.
```
- Nothing moves, 15 frames. Music **enters**. Flat sparkle on the card.

### C2 — 0:02–0:06 · MED.EYE.PUSHIN · rewind/setup
```
{style prefix} Medium 9:16 in a flat storeroom. An ASPHALT shelf with PAPER jars and one clean empty RING
where a jar stood. CHIEF (POP_TEAL jacket, BRAND_YELLOW medal sash, peaked cap with badge, gloating) is
tapping out a pinch of flat PAPER powder onto the shelf — and his oversized PAPER GLOVE clearly shows an
INK TREAD PATTERN of three chevrons inside a rounded square, in the same frame as the comparison card he
is holding. Behind him tiny PIP (PAPER body, POP_TEAL scarf, neutral) is crouching to look UNDER the shelf.
The tread on the glove is plainly visible but unemphasised.
```
- Motion: powder tap (3 frames), PIP crouches. Camera: push-in 100%→110% ending with **glove and card both in frame**. **No FX on the glove tread.**

### C3 — 0:06–0:11 · MED.EYE.STATIC · escalation 1
```
{style prefix} Medium 9:16. More flat PAPER powder on the ASPHALT shelf. CHIEF has found a print and is
holding the PAPER comparison card up beside it, comparing the two INK tread patterns, delighted and
gloating. The print in the powder and the pattern on the card visibly agree. Behind and below him tiny PIP
is on hands and knees looking under the shelf, determined. CHIEF's own gloved hand holding the card shows
the same tread.
```
- Motion: card raised (4-frame hold on the comparison). FX: flat powder shapes added.

### C4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight) · escalation 2
```
{style prefix} Medium-wide 9:16. The storeroom is a WHITEOUT of flat PAPER powder shapes across shelf,
floor and jars. CHIEF is working fast, finding print after print — and every surface he has braced or
leaned on now carries the SAME INK TREAD PATTERN of three chevrons in a rounded square. He is triumphant
and is NOT looking at his own hands. Tiny PIP still searching under the shelf, determined.
```
- Motion: **three new prints appear where he just touched** (3-frame hold each). Powder grows in discrete shapes.

### C5 — 0:16–0:22 · FULL.LOW.PUSHIN → HOLD · full commit
```
{style prefix} Low hero angle, 9:16. CHIEF holds the PAPER comparison card and a lifted print TOGETHER
OVERHEAD in an enormous triumphant pose, chest out, chin high, medals catching, FX_sparkle accents — the
two INK tread patterns visibly agree. He has solved it. CRITICAL: the framing must EXCLUDE his other glove
and his lower arms — the viewer must not yet be able to compare the card to his own hand.
```
- The pose **freezes** ~1.5 s. Music **cuts mid-phrase at 0:16**. Camera: low push-in settling into the hold.

### C6 — 0:22–0:27 · MED.EYE.STATIC→TILT · pattern break
```
{style prefix} 9:16, quiet. Flat PAPER powder settling. THREE IDENTICAL INK TREAD PATTERNS are in frame
at once: one on the PAPER comparison card, one pressed into the powder on the ASPHALT shelf edge, and one
on the PAPER GLOVE that is holding the card. CHIEF's triumphant grin is beginning to falter into
confusion as his eye travels down his own arm. Tiny PIP visible low in frame under the shelf.
```
- Motion: **three discrete powder-settle beats** (~1.4 s apart) + faltering. Camera: static, then slow tilt down from card to glove.

### C7 — 0:27–0:31 · MED.EYE.PUNCHIN → SETTLE · hidden cause
```
{style prefix} Punch-in 9:16. CHIEF has turned his PAPER glove over and the INK TREAD PATTERN on it
matches the one on the PAPER comparison card EXACTLY — three chevrons in a rounded square, identical.
Pulled wider: every print across the powdered storeroom is the same pattern, all his. His face is shocked
and panicked, cap and sash and medals still on, powder-dusted. Behind him tiny PIP is calmly LIFTING THE
MISSING PAPER JAR OUT FROM UNDER THE SHELF, gleeful. Flat FX_impact_star at the glove-card match.
```
- Motion: glove turn (6 frames), three-stage face snap, PIP lifts the jar. Camera: punch-in on the match, settle wide; **0.5 s freeze** on CHIEF-with-self-incriminating-card beside PIP-with-jar.

### C8 — 0:31–0:32 · WIDE → MED (== C1b) · payoff/loop
```
{style prefix} 9:16. CHIEF stands holding the PAPER comparison card that matches his own glove, cap still
on, powder-dusted, sheepish. Tiny PIP is SETTING THE PAPER JAR BACK into its clean RING on the ASPHALT
shelf — plainly, no smirk — then gives a small friendly wave to camera, relieved. Framing then settles into
the EXACT C1b schematic composition of the comparison card with its bold INK tread pattern, POP_TEAL tick
and ALERT_RED cross.
```
- Motion: jar set (5 frames), PIP wave. **No sparkle on PIP.** Settle to C1b framing as the final frame.

---

## Transitions & cut map
| Between | Type |
|---|---|
| C1→C1b | hard cut (payoff → rule) |
| C1b→C2 | hard cut (rewind) |
| C2→C3→C4 | hard cut |
| **C5 internal 0:16** | **music cut only, no visual cut** |
| C5→C6 | hard cut |
| C6→C7 | hard cut into punch-in |
| **C7 internal** | 0.5 s freeze on the self-incriminating match |
| C7→C8 | hard cut |
| C8→loop | hard cut, seam to C1 |

No dissolves, fades, wipes, glitch, zoom-blur or camera rotation.

---

## Handoff checklist
- [ ] 9:16 / 1080×1920, ≈32 s, timecodes exact.
- [ ] C1 tight, mid-press, no entrance.
- [ ] **The tread pattern is byte-identical** on the card, on his gloves, and in every print, in every shot. Scrub for any variation — this is the single point of failure.
- [ ] The tread is visible on his glove in **every** shot from C2 onward where a glove is in frame.
- [ ] **C5 framing excludes his other glove and lower arms.** Test on a cold viewer: they must not be able to pre-solve it.
- [ ] Powder coverage monotonic C2→C6; grows as **discrete flat shapes**, never as opacity or haze.
- [ ] Both characters search the same shelf in the same frame.
- [ ] CHIEF keeps cap + sash + medals throughout.
- [ ] **Bloodless `SC6`:** the crime is a jar that rolled. No violence, menace, weapon, restraint or detention rendered anywhere.
- [ ] Colour tokens only — powder and card `PAPER`, shelf and floor `ASPHALT`, tick `POP_TEAL`, cross `ALERT_RED`. **No "white powder", no "grey shelf", no "black".**
- [ ] Zero baked text; the card is pictograms only.
- [ ] Final frame matches C1b.
