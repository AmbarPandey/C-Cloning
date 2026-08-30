# v18 — Video & Animation Prompt ("The Last Drop") · **SHORTS 9:16**

> Compact-package file 2: carries **both** the paste-ready per-shot image prompts **and** the motion,
> camera, transition and FX direction. Locks to the master timeline in `01-video-script.md`.

**Render spec:** 1080×1920 (9:16) · 30 fps · ~32 s · flat-2D house style · hard cuts only ·
no camera rotation · no blur/glow/gradients · loop seam (final frame == C1b).

## 0. Style prefix — prepend to every prompt
```
Flat-color 2D cartoon, thick uniform INK #1A1A1A outlines (never pure #000000), no gradients,
minimal single-tone shading, high-contrast clean vector look, 9:16 vertical, mobile-legible.
Proportions: chunky 2-2.5 head heights — PIP ~2, CHIEF ~2.5.
Palette ONLY: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text. Advertiser-safe, no gore.
```

**Cast (reuse the v1–v7 reference sheets as seeds):**
- **CHIEF** `CHAR_CHIEF_v1` — rotund puffed-up warden, ~2.5 heads, `POP_TEAL` jacket with `BRAND_YELLOW` buttons, oversized peaked cap with badge, diagonal `BRAND_YELLOW` medal sash, `PAPER` gloves, tiny mustache, `smug`. **Cap + sash + medals never leave him, including C7–C8.**
- **PIP** `CHAR_PIP_v1` — tiny soft underdog, ~2 heads, `PAPER` body, `POP_TEAL` scarf every shot, big eyes, `worried` default.

**Water rule:** all liquid is a **hard-edged flat `SKY` shape** with an `INK` outline — column, puddle, dome, mass. Never blurred, never transparent, no spray or mist. Wet CHIEF = drooping shapes only, **no gloss or shine**.

**Environment** `BG_kitchen_v1`
```
BG_kitchen_v1: flat-2D domestic kitchen, composed for 9:16. A PAPER counter runs across the
lower-middle of frame. Behind it a plain PAPER wall with one ASPHALT shelf on a visible ASPHALT
L-bracket. On the counter: a tall PAPER jug, two identical PAPER glasses, and a stack of PAPER bowls
beside the bracket. Desaturated, lower-contrast than the cast, generous negative space, no text.
```
**Continuity locks:** the jug, the bowl stack and the bracket hold fixed screen positions from C2 to C7. The bowl lean and the puddle edge **only ever increase**. C8 settles to the exact C1b framing.

---

## Per-shot prompts + direction

### SHOT C1 — 0:00–0:01.5 · ECU.EYE.STATIC · cold payoff
```
{style prefix} Extreme close-up, 9:16, of a tall PAPER jug's spout ALREADY TIPPING, with a thick
hard-edged flat SKY-blue column of liquid mid-fall out of it, INK outlined. At the very bottom edge
of frame, the brim of an oversized peaked cap with a badge. No room visible, no context, no character
entering. Tight, high contrast, motion already underway.
```
- **Motion:** the column is falling on frame 1. Nothing enters. 45 frames, no camera move.
- **FX:** two flat `FX_splashpop_v1` shapes at the bottom edge. No music (file 03 cue 1).
- **Out:** hard cut.

### SHOT C1b — 0:01.5–0:02 · MED.FLAT.STATIC · goal diagram
```
{style prefix} Flat dead-centre diagram shot, 9:16. A tall PAPER jug shown side-on with a crisp
horizontal ALERT_RED FILL LINE across it and a bold BRAND_YELLOW ARROW pointing directly at that line.
Below the jug stand TWO IDENTICAL empty PAPER glasses, each carrying the same ALERT_RED line. Plain
PAPER background, no room, no characters, no text. Clean, schematic, instantly readable.
```
- **Motion:** none. Held 15 frames.
- **FX:** one flat sparkle as the arrow reads. Music **enters** on this cut.
- **Out:** hard cut.

### SHOT C2 — 0:02–0:06 · MED.EYE.PUSHIN · rewind/setup
```
{style prefix} Medium 9:16 two-shot at a PAPER kitchen counter. Tiny PIP (PAPER body, POP_TEAL scarf,
neutral) pours carefully into his glass. Beside him CHIEF (POP_TEAL jacket, BRAND_YELLOW buttons,
oversized peaked cap with badge, diagonal BRAND_YELLOW medal sash, PAPER gloves, gloating) grips the
tall jug two-handed and, turning to gloat at PIP, has KNOCKED A STACK OF PAPER BOWLS so it LEANS
against an ASPHALT shelf bracket behind him. The leaning stack is clearly visible but unemphasised.
```
- **Motion:** PIP one careful pour (4-frame settle). CHIEF turns, elbow knocks the stack (3-frame knock + 2-frame lean settle).
- **Camera:** slow push-in 100%→110%, ending on the leaning stack.
- **FX:** none on the seed — no sparkle, no highlight. It must look accidental.
- **Out:** hard cut.

### SHOT C3 — 0:06–0:11 · MED.EYE.STATIC · escalation 1
```
{style prefix} Medium 9:16. PIP's glass is filled exactly to its ALERT_RED line and he has stopped,
neutral, hand off the jug. CHIEF is pouring PAST the jug's ALERT_RED fill line, looking at PIP and not
at his glass, gloating. A thin hard-edged flat SKY overflow runs down the side of his glass onto the
PAPER counter as a small flat puddle shape. The leaning bowl stack and ASPHALT bracket behind him.
```
- **Motion:** continuous pour; the puddle appears as one small flat shape. **CHIEF's eyeline stays on PIP.**
- **Camera:** locked; 4-frame hold as the overflow touches the counter.
- **FX:** flat drip shapes, `FX_motionlines_v1` on the pour.
- **Out:** hard cut.

### SHOT C4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight) · escalation 2
```
{style prefix} Medium-wide 9:16. CHIEF pours two-handed; his glass is an impossible DOME of flat SKY
liquid held above the rim. A flat SKY PUDDLE has spread across the PAPER counter in visible stages,
its leading edge advancing toward the base of the leaning PAPER bowl stack. He gestures at his own
glass and dismissively at PIP's modest one, triumphant, and is NOT looking down. PIP looks worried.
```
- **Motion:** puddle grows in **three discrete stages** (~1.6 s apart), each a larger flat shape. Dome builds.
- **Camera:** slight push-in 100%→104%; 3-frame hold per stage.
- **FX:** `FX_motionlines_v1`, one sparkle glint off a medal at ~0:15.
- **Out:** hard cut.

### SHOT C5 — 0:16–0:22 · FULL.LOW.PUSHIN → HOLD · full commit
```
{style prefix} Low hero angle, 9:16. CHIEF raises the impossibly brimming glass of flat SKY liquid in
a huge triumphant toast, chest out, chin high, medals catching, FX_sparkle accents around him. He has
completely won. Below and behind, the flat SKY puddle's leading edge sits one bowl-width from the
leaning PAPER bowl stack. PIP small and low in frame.
```
- **Motion:** the toast rises and **freezes** ~1.5 s. The dome wobbles once.
- **Camera:** low hero push-in settling into the hold.
- **AUDIO:** music **cuts mid-phrase at 0:16** on the frame the toast locks.
- **Out:** hard cut.

### SHOT C6 — 0:22–0:27 · MED.EYE.STATIC→TILT · pattern break
```
{style prefix} 9:16, tense and quiet. The flat SKY puddle's leading edge has REACHED the base of the
leaning stack of PAPER bowls, and the bottom bowl has visibly SHIFTED off-square. The stack leans
further toward the ASPHALT shelf bracket. CHIEF still frozen in his toast above, oblivious. PIP
looking up at the stack, worried. No sparkle, no effects.
```
- **Motion:** **three discrete ceramic slips**, ~1.4 s apart, each increasing the lean.
- **Camera:** static, then slow tilt to the stack at ~0:25.
- **FX:** flat stress lines only.
- **Out:** hard cut.

### SHOT C7 — 0:27–0:31 · WIDE.EYE.PUNCHIN → WHIP-TILT · chain payoff
```
{style prefix} Punch-in 9:16 showing a FOUR-STAGE CHAIN in one continuous action: the stack of PAPER
bowls slides off the counter; it strikes the ASPHALT shelf bracket; the bracket jolts and the ASPHALT
shelf tips; the tall PAPER jug walks off the edge and empties over CHIEF as ONE LARGE HARD-EDGED FLAT
SKY MASS with an INK outline. CHIEF is drenched — hair flattened to a flat mass, cap slumped over one
eye but STILL ON, sash sodden, medals tilted, mustache limp, panicked; NO gloss, NO shine. His glass
knocked level and emptying. Two steps away PIP is completely dry and gleeful. Flat FX_impact_star at
the ground.
```
- **Motion:** the four stages must be **individually legible** — 8 frames each, no overlap.
- **Camera:** punch-in on stage 1, whip-tilt following the chain, settle wide; **0.5 s freeze** on wet/dry contrast.
- **FX:** `FX_motionlines_v1` per stage, flat splash burst, optional 1-frame flash.
- **Out:** hard cut.

### SHOT C8 — 0:31–0:32 · WIDE → MED (== C1b) · payoff/loop
```
{style prefix} 9:16. Drenched CHIEF stands holding an EMPTY PAPER glass, cap drooping over one eye but
still on, sash sodden, sheepish. Tiny PIP quietly SLIDES HIS OWN FULL GLASS across the PAPER counter
toward him — offering it plainly, no smirk — and gives a small friendly wave to camera, relieved.
Framing then settles into the EXACT C1b diagram composition: the jug side-on with its ALERT_RED fill
line and BRAND_YELLOW arrow, now with one full glass and one empty glass beneath it.
```
- **Motion:** glass slide (6 frames), PIP wave, one last flat drip off CHIEF's cap brim.
- **Camera:** wide, then settle to the **exact C1b framing** as the final frame.
- **FX:** none residual — the loop must be clean. **No sparkle on PIP.**
- **Out:** hard cut, seaming to C1.

---

## Transitions & cut map
| Between | Type |
|---|---|
| C1→C1b | hard cut (payoff → rule) |
| C1b→C2 | hard cut (the rewind) |
| C2→C3→C4 | hard cut |
| **C5 internal 0:16** | **music cut only, no visual cut** |
| C5→C6 | hard cut |
| C6→C7 | hard cut into punch-in |
| **C7 internal** | whip-tilt + 0.5 s freeze |
| C7→C8 | hard cut |
| C8→loop | hard cut, seam to C1 |

No dissolves, fades, wipes, glitch, zoom-blur or camera rotation.

---

## Handoff checklist
- [ ] 9:16 / 1080×1920, ≈32 s, timecodes exact.
- [ ] **C1 is tight and already in motion**; no character enters frame anywhere in C1.
- [ ] C1b is a clean wordless diagram, held 15 frames.
- [ ] Bowl stack, bracket and jug hold fixed screen positions C2→C7.
- [ ] Puddle stages monotonic; bowl lean monotonic.
- [ ] All four chain stages individually readable in C7.
- [ ] CHIEF keeps cap + sash + medals in C7 and C8.
- [ ] All liquid is flat hard-edged `SKY` shapes; no gloss on wet CHIEF.
- [ ] Zero baked text; no English colour words used in any prompt above.
- [ ] Final frame matches C1b exactly.
