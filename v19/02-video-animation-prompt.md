# v19 — Video & Animation Prompt ("The Deep End") · **SHORTS 9:16**

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

**Cast:** `CHAR_CHIEF_v1` (rotund warden, `POP_TEAL` jacket, `BRAND_YELLOW` buttons + medal sash, peaked cap with badge, `PAPER` gloves, `smug`) · `CHAR_PIP_v1` (tiny, `PAPER` body, `POP_TEAL` scarf every shot, `worried` default). **Cap + sash + medals never leave CHIEF, including C7–C8.**

**Mud rule:** mud is a **hard-edged flat `ASPHALT` shape** with an `INK` outline. Never "brown", never textured, never glossy. Displacement = flat crescent shapes. Mud-caked CHIEF = flat `ASPHALT` patches over his existing shapes, **no shine**.

**Environment** `BG_mudpatch_v1`
```
BG_mudpatch_v1: flat-2D outdoor mud crossing, composed for 9:16. A wide flat ASPHALT mud patch runs
across the middle of frame between two PAPER banks. Five POP_TEAL planks lie across it in a row. A
bold ALERT_RED X is painted on the mud surface at the middle. A graduated depth stick with INK marks
stands beside the X. Background: flat desaturated field shapes and a flat SKY strip. No text.
```
**Continuity:** the X, the depth stick and the plank positions hold fixed screen positions C1b→C8. The rig only ever settles further. C8 settles to the exact C1b framing with the plank restored.

---

## Per-shot prompts + direction

### C1 — 0:00–0:01.5 · ECU.EYE.STATIC · cold payoff
```
{style prefix} Extreme close-up, 9:16: a bold ALERT_RED painted X on a flat ASPHALT mud surface, with
a boot sole ALREADY DESCENDING into frame toward it and the flat ASPHALT mud parting beneath in
hard-edged crescent shapes. No horizon, no context, no character entering frame. Tight, high contrast.
```
- 45 frames, static, motion underway on frame 1. FX: flat `FX_mudcrescent_v1`. **No music.**

### C1b — 0:01.5–0:02 · MED.FLAT.STATIC · goal diagram
```
{style prefix} Flat dead-centre schematic, 9:16: a wide flat ASPHALT mud patch with FIVE POP_TEAL
planks laid across it in a row, one bold ALERT_RED X painted on the mud beneath the MIDDLE plank, and
a graduated depth stick with INK measurement marks standing beside the X showing how deep it goes.
Plain PAPER background, no characters, no text. Clean, schematic, instantly readable.
```
- Nothing moves, 15 frames. Music **enters**. One flat sparkle on the X.

### C2 — 0:02–0:06 · MED.EYE.PUSHIN · rewind/setup
```
{style prefix} Medium 9:16 at the near bank. Tiny PIP (PAPER body, POP_TEAL scarf, neutral) stepping
onto the first POP_TEAL plank. Behind him CHIEF (POP_TEAL jacket, BRAND_YELLOW medal sash, peaked cap
with badge, gloating) is HAULING THE MIDDLE PLANK OUT of the crossing and shouldering it away, leaving
a plank-shaped GAP directly over the now-uncovered ALERT_RED X. Unemphasised, casual.
```
- Motion: PIP one step; CHIEF 4-frame haul + shoulder. Camera: push-in 100%→110% ending on the uncovered X. **No FX on the seed.**

### C3 — 0:06–0:11 · WIDE.EYE.STATIC · escalation 1
```
{style prefix} Wide 9:16. CHIEF has wedged the stolen POP_TEAL plank across a flat ASPHALT stone at
the bank to make a see-saw, and is testing it, gloating. Out on the crossing, tiny PIP walks calmly
along the second and third planks, determined. The plank-shaped GAP and the ALERT_RED X clearly
visible in the middle of the mud.
```
- Motion: see-saw balances (4-frame hold); PIP two unhurried steps. FX: `FX_motionlines_v1` on the plank drop.

### C4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight) · escalation 2
```
{style prefix} Medium-wide 9:16. CHIEF's contraption has grown absurd: the POP_TEAL plank see-saw now
on TWO flat ASPHALT stones, with a PAPER crate as a counterweight and an ASPHALT pole braced against
it, teetering. He gestures proudly at his engineering, then dismissively at PIP, triumphant. PIP is
most of the way across the planks, determined. The GAP and the ALERT_RED X still visible below.
```
- Motion: three parts pop on (~1.6 s apart), 3-frame hold each; rig sway cycle begins. FX: `FX_wobble_v1`, medal glint ~0:15.

### C5 — 0:16–0:22 · FULL.LOW.PUSHIN → HOLD · full commit
```
{style prefix} Low hero angle, 9:16. CHIEF stands at the raised end of his teetering contraption,
CLEAR ABOVE the flat ASPHALT mud, arms spread wide in an enormous triumphant pose, chest out, medals
catching, FX_sparkle accents. He has beaten the crossing. Directly below the rig's pivot point sits
the plank-shaped GAP and the bold ALERT_RED X. Dramatic empty SKY around him.
```
- The pose **freezes** ~1.5 s. Music **cuts mid-phrase at 0:16** on the lock. Camera: low push-in settling into the hold.

### C6 — 0:22–0:27 · MED.EYE.STATIC→TILT · pattern break
```
{style prefix} 9:16, tense and quiet. CHIEF's contraption has visibly SETTLED, tilting toward the
plank-shaped GAP in the crossing, with flat strain lines on the plank and the ASPHALT pole slipping.
Tiny PIP, nearly at the far bank, has glanced back, worried. Below the pivot: the GAP and the bold
ALERT_RED X, with the graduated depth stick beside it. No sparkle, no effects beyond strain lines.
```
- Motion: **three discrete settle increments**, ~1.4 s apart. Camera: static, then slow tilt down to the gap and X at ~0:25.

### C7 — 0:27–0:31 · MED.EYE.PUNCHIN → SETTLE · literal outcome
```
{style prefix} Punch-in 9:16. The contraption has PIVOTED INTO THE GAP and lowered CHIEF almost gently
straight down onto the bold ALERT_RED X — he is sunk into the flat ASPHALT mud to exactly the depth
marked on the graduated depth stick standing beside him, which is in frame for comparison. Flat
ASPHALT mud patches on his jacket and face; his oversized peaked cap is STILL ON, sash and medals
still on, drooping and mud-caked, expression panicked; NO gloss, NO shine. On the far bank, tiny PIP
is clean and gleeful. Flat FX_mudcrescent burst at the surface. Mud is shallow — it reaches his sash,
no higher.
```
- Motion: the pivot is **slow and almost gentle** (the joke, and the ad-safety guardrail) — 14 frames. Camera: punch-in on the pivot, settle wide; **0.5 s freeze** on CHIEF-beside-depth-stick.

### C8 — 0:31–0:32 · WIDE → MED (== C1b) · payoff/loop
```
{style prefix} 9:16. CHIEF sunk to his sash in the flat ASPHALT mud on the ALERT_RED X, cap still on,
mud-caked, sheepish. On the far bank tiny PIP is LAYING THE REMOVED POP_TEAL PLANK BACK DOWN across
the mud within CHIEF's reach — offering it plainly, no smirk — and gives a small friendly wave to
camera, relieved. Framing then settles into the EXACT C1b schematic composition, five planks restored
across the mud with the ALERT_RED X and depth stick.
```
- Motion: plank laid (6 frames), PIP wave, one flat mud bubble. **No sparkle on PIP.** Settle to the C1b framing as the final frame.

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
| **C7 internal** | 0.5 s freeze on CHIEF + depth stick |
| C7→C8 | hard cut |
| C8→loop | hard cut, seam to C1 |

No dissolves, fades, wipes, glitch, zoom-blur or camera rotation.

---

## Handoff checklist
- [ ] 9:16 / 1080×1920, ≈32 s, timecodes exact.
- [ ] C1 tight, mid-motion, no entrance.
- [ ] C1b diagram wordless; the **depth stick** is what converts "deep" into a perception.
- [ ] X and depth-stick screen positions identical in C1b, C6, C7, C8.
- [ ] Gap created in C2 is the pivot point in C7 — visually the same gap.
- [ ] Rig settle monotonic; parts only ever added, never removed, before C7.
- [ ] CHIEF keeps cap + sash + medals in C7 and C8.
- [ ] Mud is flat `ASPHALT` shapes; **no "brown" anywhere**; no gloss on mud-caked CHIEF.
- [ ] **Ad-safety:** descent is slow and gentle, mud reaches the sash at most, no height, no submersion, no limb entanglement, PIP never at risk.
- [ ] Zero baked text; no English colour words in any prompt above.
- [ ] Final frame matches C1b with the plank restored.
