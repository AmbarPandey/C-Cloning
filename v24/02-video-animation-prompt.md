# v24 — Video & Animation Prompt ("The Fast Lane") · **SHORTS 9:16**

> Compact-package file 2: per-shot image prompts **and** motion/camera/FX. Locks to `01-video-script.md`.

**Render spec:** 1080×1920 · 30 fps · ~32 s · flat-2D house style · hard cuts only · **no camera rotation**
*(the door rotates; the camera never does)* · no blur/glow/gradients · loop seam (final frame == C1b).

## 0. Style prefix
```
Flat-color 2D cartoon, thick uniform INK #1A1A1A outlines (never pure #000000), no gradients,
minimal single-tone shading, high-contrast clean vector look, 9:16 vertical, mobile-legible.
Proportions: chunky 2-2.5 head heights — PIP ~2, CHIEF ~2.5.
Palette ONLY: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text. Advertiser-safe, no gore.
```

**Cast:** `CHAR_CHIEF_v1` (rotund warden, `POP_TEAL` jacket, `BRAND_YELLOW` buttons + medal sash, peaked cap with badge, `PAPER` gloves, `smug`) · `CHAR_PIP_v1` (tiny, `PAPER` body, `POP_TEAL` scarf every shot). **Cap + sash + medals never leave CHIEF; askew is allowed, removal is not.**

**Rotation rule (new for the series):** speed is shown with **flat repeated ghost wing shapes** and
hard-edged `FX_motionlines_v1` arcs — never motion blur, never a smear filter. Glass is a flat `SKY` panel
with an `INK` outline; the cast is always fully visible through it, never distorted or tinted.

**Environment** `BG_revolvingdoor_v1`
```
BG_revolvingdoor_v1: flat-2D shopfront with a revolving door, composed for 9:16. A PAPER shopfront wall
spans the frame with a circular ASPHALT door housing centre, four ASPHALT wings inside it and flat SKY
glass panels. A curved INK direction arrow is painted on the housing above the door. ASPHALT pavement
below, flat SKY strip above, flat desaturated street shapes behind. Quiet, lower-contrast than the cast,
no text.
```
**Continuity:** the door housing, the painted direction arrow and the two openings (pavement side, inside)
hold fixed screen positions throughout. **The door only ever turns in the arrow's direction.** The crate
stays wedged from C2 to C8. C8 settles to the exact C1b framing.

---

## Per-shot prompts + direction

### C1 — 0:00–0:01.5 · ECU.EYE.STATIC · cold payoff
```
{style prefix} Extreme close-up, 9:16: CHIEF (POP_TEAL jacket, BRAND_YELLOW medal sash, oversized peaked
cap with badge askew but ON) caught ALREADY MID-ROTATION and travelling BACKWARDS, heels skidding, one
PAPER glove braced, with a flat ASPHALT revolving-door wing sweeping across frame behind him and flat
FX_motionlines arcs showing the direction of travel. No building, no context, no character entering frame.
Tight, high contrast, motion already underway.
```
- 45 frames, static, motion underway on frame 1. **No music.**

### C1b — 0:01.5–0:02 · MED.FLAT.STATIC · goal diagram
```
{style prefix} Flat dead-centre schematic, 9:16: a revolving-door hub seen FROM ABOVE with four ASPHALT
wings, a bold curved INK DIRECTION ARROW around the hub showing which way it turns, and beside it a
pictogram of ONE simple figure inside ONE compartment. Plain PAPER background, no characters, no text.
Schematic, instantly readable in one pass.
```
- Nothing moves, 15 frames. Music **enters**. One flat sparkle on the arrow.

### C2 — 0:02–0:06 · MED.EYE.PUSHIN · rewind/setup
```
{style prefix} Medium 9:16 at a revolving door in a PAPER shopfront. Tiny PIP (PAPER body, POP_TEAL scarf,
neutral) has stepped into one compartment and stands still with his hands at his sides, waiting. In the
NEXT compartment CHIEF (POP_TEAL jacket, BRAND_YELLOW medal sash, peaked cap with badge, gloating) has
shoved in and WEDGED A PAPER CRATE CORNER-TO-CORNER ACROSS HIS COMPARTMENT so it cannot clear, and is
setting both PAPER gloves on the ASPHALT wing ready to push. The curved INK direction arrow is visible on
the housing. The wedged crate is clear but unemphasised.
```
- Motion: PIP steps in and stops; CHIEF's crate wedge (4 frames). Camera: push-in 100%→110% ending on the wedged crate. **No FX on the seed.**

### C3 — 0:06–0:11 · WIDE.EYE.STATIC · escalation 1
```
{style prefix} Wide 9:16. The ASPHALT revolving door is turning in the direction of the painted INK arrow.
CHIEF is pushing his wing hard, gloating, and is sweeping PAST the INSIDE opening without stepping off,
gesturing back at PIP through the flat SKY glass. PIP stands perfectly still in his own compartment,
travelling at the same speed with no effort. Flat FX_motionlines arcs on the wings.
```
- Motion: one full smooth rotation; **4-frame hold as he passes the inside opening the first time.** PIP's compartment moves identically.

### C4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight) · escalation 2
```
{style prefix} Medium-wide 9:16. The ASPHALT revolving door is now spinning FAST — shown with flat
repeated ghost wing shapes and thick FX_motionlines arcs, NO blur. CHIEF is shoving with his whole body,
chest out, triumphant, and the WEDGED PAPER CRATE across his compartment is visibly acting as a PADDLE,
driving the rotation on. Tiny PIP stands motionless in his compartment going round at exactly the same
speed, worried. The curved INK arrow visible on the housing.
```
- Motion: **three progressively bigger shoves** (~1.6 s apart), 3-frame hold each; ghost-wing count increases with speed.

### C5 — 0:16–0:22 · FULL.LOW.PUSHIN → HOLD · full commit
```
{style prefix} Low hero angle, 9:16. Mid-rotation inside his compartment, CHIEF plants an enormous
triumphant pose — one PAPER glove raised high, chest out, chin high, medals catching, FX_sparkle accents —
unmistakably the fastest thing in the door. Flat ghost wing shapes and FX_motionlines arcs sweep around
him. The WEDGED PAPER CRATE still across his compartment.
```
- The pose **freezes** ~1.5 s while the door keeps turning around him. Music **cuts mid-phrase at 0:16**.

### C6 — 0:22–0:27 · WIDE.EYE.STATIC→TILT · pattern break
```
{style prefix} 9:16, quiet and relentless. The ASPHALT door carries CHIEF past the INSIDE opening — and the
WEDGED PAPER CRATE holds his compartment shut across it so he cannot get out. His raised arm has lowered
and he is reaching for the opening and missing it. Flat FX_motionlines arcs continue. Tiny PIP in the next
compartment is looking up, hopeful. No sparkle, no effects beyond the motion arcs.
```
- Motion: **three discrete pass-bys of the inside opening** (~1.4 s apart), each with the crate visibly blocking. Camera: static wide, then slow tilt to the crate at ~0:26.

### C7 — 0:27–0:31 · WIDE.EYE.PUNCHIN → SETTLE · role reversal
```
{style prefix} Punch-in 9:16. The ASPHALT revolving door has completed its extra revolution and delivered
CHIEF BACK OUT ONTO THE ASPHALT PAVEMENT, crate and all, exactly where he began — face shocked and
panicked, cap askew but still on, sash and medals still on. At the same moment tiny PIP's compartment has
opened on the INSIDE and he is stepping calmly out, gleeful. The two are separated by the flat SKY glass,
positions exactly swapped: the big one outside, the small one inside. Flat FX_impact_star at the pavement.
```
- Motion: pavement delivery (8 frames), three-stage face snap, PIP steps out. Camera: punch-in on the delivery, settle wide; **0.5 s freeze** on outside-CHIEF / inside-PIP through the glass.

### C8 — 0:31–0:32 · WIDE → MED (== C1b) · payoff/loop
```
{style prefix} 9:16. CHIEF stands on the ASPHALT pavement holding his PAPER crate, cap askew but on,
sheepish. Inside, tiny PIP has reached back and is HOLDING THE ASPHALT DOOR STILL for him — plainly, no
smirk — then gives a small friendly wave to camera, relieved. Framing then settles into the EXACT C1b
schematic composition of the door hub from above with its curved INK direction arrow and one-figure
pictogram.
```
- Motion: PIP steadies the door (4 frames), wave; the door comes to rest. **No sparkle on PIP.** Settle to C1b framing as the final frame.

---

## Transitions & cut map
| Between | Type |
|---|---|
| C1→C1b | hard cut (payoff → rule) |
| C1b→C2 | hard cut (rewind) |
| C2→C3→C4 | hard cut |
| **C5 internal 0:16** | **music cut only, no visual cut** — the door keeps turning |
| C5→C6 | hard cut |
| C6→C7 | hard cut into punch-in |
| **C7 internal** | 0.5 s freeze on the swapped positions through the glass |
| C7→C8 | hard cut |
| C8→loop | hard cut, seam to C1 |

No dissolves, fades, wipes, glitch, zoom-blur or **camera** rotation. The **door** rotates; the camera is
locked in every shot.

> **The key craft note:** the physics must be *legible*, not just fast. Harder push → faster spin → the
> wedged compartment sweeps past the opening without ever clearing it. Hold on each of the three C6
> pass-bys long enough that the viewer can see the crate blocking the exit. If the ending needs explaining,
> the shot count in C6 is too low.

---

## Handoff checklist
- [ ] 9:16 / 1080×1920, ≈32 s, timecodes exact.
- [ ] C1 tight, mid-spin, **travelling backwards**, no entrance.
- [ ] C1b diagram wordless: curved arrow + one-per-compartment pictogram.
- [ ] Door housing, painted arrow and both openings hold fixed screen positions throughout.
- [ ] **The door only ever turns in the arrow's direction.** Never reverses.
- [ ] Crate stays wedged C2→C8, in the same corner-to-corner position.
- [ ] Rotation speed monotonic C3→C6; ghost-wing count scales with speed.
- [ ] **PIP never pushes and never changes speed.**
- [ ] All three C6 pass-bys clearly show the crate blocking the inside opening.
- [ ] Speed rendered as **flat ghost wings + motion arcs only** — no blur, no smear filter.
- [ ] Glass is flat `SKY` with an `INK` outline; the cast is never distorted or tinted through it.
- [ ] CHIEF keeps cap + sash + medals throughout.
- [ ] Colour tokens only — door and pavement `ASPHALT`, glass `SKY`, shopfront and crate `PAPER`. **No "chrome", no "clear glass", no "brown".**
- [ ] Ad-safety: the door never traps, pinches, strikes or closes on anyone; no fingers near hinges, no falls. Speed reads comic, never dangerous.
- [ ] Zero baked text; no English colour words in any prompt above.
- [ ] Final frame matches C1b.
