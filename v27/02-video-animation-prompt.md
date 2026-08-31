# v27 — Video & Animation Prompt ("The Chock") · **SHORTS 9:16**

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

**The slope rule (non-negotiable):** the street's **ground line runs at a consistent visible angle** in every
single shot — roughly 12–15° — and everything resting on it is drawn true to that angle. A flat-looking
street kills the entire episode, because gravity is the only force in it. Draw a `ASPHALT` kerb line and
`INK` paving joints along the slope so the angle is unmistakable even in close-ups.

**The tilt ladder:** the crate has **five states**, differing only in how far it leans on its prop:
`T0` flat and chocked (PIP's, all episode) · `T1` propped, slight uphill tilt · `T2` stack at the rim, tilt
increased · `T3` heaped, downhill edge clearly unsupported and overhanging · `T4` tipped, load gone.
`T1`→`T3` only ever increases. PIP's crate stays `T0` in every frame.

**Rolling rule:** fruit are flat `ALERT_RED` circles with `INK` outlines. Rolling is shown with **discrete
rotation states plus 2–3 flat `INK` arc lines behind each fruit** — never blur, never a smear. Fruit always
travel **downhill and out of frame, away from both characters.**

**Environment** `BG_slopedstreet_v1`
```
BG_slopedstreet_v1: flat-2D sloped market street, composed for 9:16. A PAPER fruit stall stands on the
uphill side of frame with a canopy; the ASPHALT street runs downhill across the frame at a consistent
visible angle with INK paving joints and a ASPHALT kerb line marking the slope. A slope arrow and a chock
pictogram are painted on the stall front. Flat desaturated buildings behind, flat SKY strip above. Quiet,
lower-contrast than the cast, generous negative space, no text.
```
**Continuity:** the slope angle, the stall position and the painted pictogram hold fixed positions
throughout. Crate tilt only increases. C8 settles to the exact C1b framing.

---

## Per-shot prompts + direction

### C1 — 0:00–0:01.5 · ECU.EYE.STATIC · cold payoff
```
{style prefix} Extreme close-up, 9:16: THREE flat ALERT_RED round fruit ALREADY ROLLING away from camera
down a sloped ASPHALT street at a clear visible angle, each with two or three flat INK arc lines behind it
showing rotation, gathering speed. The lip of an empty PAPER crate just visible at the top edge of frame.
INK paving joints run along the slope. No stall, no faces, no context, no character entering frame. Tight,
high contrast, motion already underway.
```
- 45 frames, static, motion underway on frame 1. **No music.** Fruit travel **away** from camera, never toward it.

### C1b — 0:01.5–0:02 · MED.FLAT.STATIC · goal diagram
```
{style prefix} Flat dead-centre schematic, 9:16: a downhill SLOPE ARROW, a simple crate drawn resting on
that slope with a wedge-shaped CHOCK tucked under its DOWNHILL edge holding it still, and a large POP_TEAL
TICK beside it. Plain PAPER background, no characters, no text. Schematic, instantly readable in one pass.
```
- Nothing moves, 15 frames. Music **enters**. One flat sparkle on the chock.

### C2 — 0:02–0:06 · MED.EYE.PUSHIN · rewind/setup
```
{style prefix} Medium 9:16 at a PAPER fruit stall on a clearly sloped ASPHALT street with INK paving joints.
Two PAPER crates sit on the slope, each with a wedge chock beside it. Tiny PIP (PAPER body, POP_TEAL scarf,
neutral) has slid HIS chock under his crate's DOWNHILL edge so it sits flat and still, and is being handed
two flat ALERT_RED apples. Beside him CHIEF (POP_TEAL jacket, BRAND_YELLOW medal sash, peaked cap with
badge, gloating) has PULLED HIS OWN CHOCK OUT and wedged it under his crate's UPHILL edge as a PROP, tilting
the crate up so it will hold a taller stack — its downhill edge now unsupported. One chock, doing the wrong
job. Casual, unemphasised. Crate state T1.
```
- Motion: PIP chock slide (4 frames) + two apples; CHIEF chock pull and re-wedge (3 frames). Camera: push-in 100%→110% ending on the chock now propping instead of chocking. **No FX on the seed.**

### C3 — 0:06–0:11 · WIDE.EYE.STATIC · escalation 1
```
{style prefix} Wide 9:16 on the sloped ASPHALT street. Tiny PIP has stepped back beside his FLAT, CHOCKED,
motionless PAPER crate holding two flat ALERT_RED apples. At the stall CHIEF's TILTED crate is receiving
three more ALERT_RED fruit and the stack is rising above the crate's rim; the crate leans further on its
single wedge prop, downhill edge clear of the ground. He gestures at his own stack and dismissively at PIP's
two apples, gloating, EYELINE ON PIP not on the chock. Crate state T2.
```
- Motion: three fruit placed (4-frame each); **4-frame hold as the stack passes the rim.** PIP's crate is dead still.

### C4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight) · escalation 2
```
{style prefix} Medium-wide 9:16. CHIEF's PAPER crate is heaped with an absurd mound of flat ALERT_RED round
fruit far above its rim, and the crate is now clearly BALANCED on the single wedge prop with its DOWNHILL
EDGE OVERHANGING the sloped ASPHALT street, unsupported. He is directing the stacking with both PAPER
gloves, chest out, triumphant, and is NOT looking down at the chock. Tiny PIP beside his flat chocked crate,
worried. Flat strain lines at the crate's leaning corner. Crate state T3.
```
- Motion: three fruit land (~1.6 s apart), 3-frame hold each; tilt increases with each. FX: `FX_strainline_v1` at the prop.

### C5 — 0:16–0:22 · FULL.LOW.PUSHIN → HOLD · full commit
```
{style prefix} Low hero angle, 9:16. CHIEF hoists the heaped PAPER crate of flat ALERT_RED fruit OVERHEAD in
an enormous triumphant pose, chest out, chin high, medals catching, FX_sparkle accents, while a POP_TEAL
TICK is stamped onto his docket — served first, officially. CRITICAL: the framing is kept HIGH and must
EXCLUDE the chock and the crate's base — the viewer must not yet see what the crate is standing on.
```
- The pose **freezes** ~1.5 s. Music **cuts mid-phrase at 0:16** on the tick. Camera: low push-in settling into the hold.

### C6 — 0:22–0:27 · MED.EYE.STATIC→TILT-DOWN · pattern break
```
{style prefix} 9:16, quiet. CHIEF's heaped PAPER crate has settled further on its single wedge prop — flat
strain lines at the leaning corner, one flat ALERT_RED fruit visibly SHIFTED at the top of the mound, and
the wedge CHOCK has SLID a hair downhill on the ASPHALT paving. His triumphant pose is beginning to falter
as he feels the weight move. Tiny PIP beside his flat chocked crate, looking up, hopeful. The slope angle
clearly visible. No sparkle, no effects beyond strain lines.
```
- Motion: **three discrete increments** (~1.4 s apart): crate creak-and-tilt · one fruit shifts · chock slides. Camera: static, then **slow tilt DOWN to the chock** at ~0:25 — the first look at the base since C4.

### C7 — 0:27–0:31 · WIDE.EYE.PUNCHIN → WHIP-TILT → SETTLE · false victory
```
{style prefix} Punch-in 9:16. The wedge CHOCK has slid out, the PAPER crate has TIPPED off it and its
downhill edge dropped — and the ENTIRE LOAD of flat ALERT_RED round fruit is ROLLING AWAY DOWN the sloped
ASPHALT street in a long stream, each fruit with flat INK arc lines behind it, heading downhill and OUT of
frame AWAY from both characters. CHIEF is left holding an EMPTY PAPER crate in one glove and a perfectly
valid POP_TEAL-TICKED docket in the other, face shocked and panicked, cap and sash and medals still on.
Beside him tiny PIP's FLAT CHOCKED crate sits motionless with its TWO ALERT_RED apples — the only full crate
left on the street. Crate state T4. Flat FX_impact_star where the chock gave way.
```
- Motion: chock gives (4 frames), crate tips (6 frames), fruit stream downhill and exit frame. Camera: punch-in on the chock, **whip-tilt following the fruit downhill**, settle wide; **0.5 s freeze** on empty-crate-plus-tick beside PIP's two apples. **No fruit may travel toward either character.**

### C8 — 0:31–0:32 · WIDE → MED (== C1b) · payoff/loop
```
{style prefix} 9:16. CHIEF stands on the sloped ASPHALT street holding an EMPTY PAPER crate and a valid
POP_TEAL-ticked docket, cap still on, sheepish. Tiny PIP is taking his TWO flat ALERT_RED apples and PUTTING
THEM INTO CHIEF'S CRATE, and handing him back the wedge CHOCK — plainly, no smirk — then gives a small
friendly wave to camera, relieved. Framing then settles into the EXACT C1b schematic composition: the slope
arrow, a crate with the chock correctly under its DOWNHILL edge, and the POP_TEAL tick.
```
- Motion: two apples transferred (5 frames), chock handed over, PIP wave. **No sparkle on PIP.** Settle to C1b framing as the final frame.

---

## Transitions & cut map
| Between | Type |
|---|---|
| C1→C1b | hard cut (payoff → rule) |
| C1b→C2 | hard cut (rewind) |
| C2→C3→C4 | hard cut |
| **C5 internal 0:16** | **music cut only, no visual cut** — the creak continues |
| C5→C6 | hard cut |
| C6→C7 | hard cut into punch-in |
| **C7 internal** | whip-tilt down the slope + 0.5 s freeze |
| C7→C8 | hard cut |
| C8→loop | hard cut, seam to C1 |

No dissolves, fades, wipes, glitch, zoom-blur or camera rotation.

> **The key craft note:** the episode has exactly **one** force in it — gravity — and exactly **one** object
> creating the fault. So the slope angle and the chock's position must be legible in every frame. If a
> viewer at any point cannot see (a) which way is downhill and (b) where the chock is, the ending becomes an
> accident instead of a consequence. Draw the kerb and the paving joints in the close-ups too.

---

## Handoff checklist
- [ ] 9:16 / 1080×1920, ≈32 s, timecodes exact.
- [ ] C1 tight, fruit **already rolling and moving away from camera**, no entrance.
- [ ] C1b diagram wordless: slope arrow + chock under the **downhill** edge + `POP_TEAL` tick.
- [ ] **Slope angle consistent and visible in every shot**, including close-ups (kerb line + paving joints).
- [ ] **One chock only.** The chock that leaves the downhill edge in C2 is the same one propping the uphill edge, sliding in C6 and handed back in C8. Never draw a second chock or an extra prop.
- [ ] Crate tilt charted `T1`→`T4` and monotonic; **PIP's crate stays `T0` and motionless in every frame.**
- [ ] Stack height monotonic C2→C5.
- [ ] **C5 framing excludes the chock and the crate base.** Show it to a cold viewer and confirm they cannot pre-solve it.
- [ ] C6's tilt-down is the first look at the base since C4.
- [ ] Rolling shown as **discrete rotation states + flat arc lines** — no blur, no smear.
- [ ] **No fruit travels toward either character, strikes anyone, or is stepped on.** All fruit exit frame downhill and away.
- [ ] CHIEF keeps cap + sash + medals throughout.
- [ ] The `POP_TEAL` tick on the docket is **visible and intact in C5, C7 and C8** — the win must stay real.
- [ ] Colour tokens only — fruit `ALERT_RED`, street `ASPHALT`, stall/crates/chock `PAPER`, tick `POP_TEAL`. **No "red apples", "brown", "wood" or "green" anywhere.**
- [ ] Zero baked text; no English colour words in any prompt above.
- [ ] Final frame matches C1b with the chock correctly placed.
