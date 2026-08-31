# v26 — Video & Animation Prompt ("The Ferry") · **SHORTS 9:16**

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

**Cast:** `CHAR_CHIEF_v1` (rotund warden, `POP_TEAL` jacket, `BRAND_YELLOW` buttons + medal sash, peaked cap with badge, `PAPER` gloves, `smug`) · `CHAR_PIP_v1` (tiny, `PAPER` body, `POP_TEAL` scarf every shot) · `CROWD_ponducks_v1` (desaturated duck silhouettes, **no individual faces**, calm and patient, never out-competing the leads). **Cap + sash + medals never leave CHIEF; he stays dry throughout.**

**Water rule:** the pond is a **flat `SKY` shape with a single hard `INK` waterline** — no gradient, no
transparency, no reflection, no ripple texture. Movement is shown with **2–3 flat `INK` chevron wake lines**
behind a hull. When a hull stops, the chevrons are simply **absent**. Nothing is ever splashed onto a
character.

**The buoyancy rule (the whole episode):** the hull has **five load states**, and the only thing that
changes between them is the **gap between the gunwale and the waterline**:
`L0` empty, gunwale high · `L1` loaded, gap halved · `L2` gunwale near the line · `L3` gunwale **flush with
the water** (boardable) · `L4` waterline **at the `ALERT_RED` load line**, hull stopped.
The gap only ever shrinks. The wake chevron count shrinks with it: 3 → 3 → 2 → 1 → **0**.

**Environment** `BG_pond_v1`
```
BG_pond_v1: flat-2D pond crossing, composed for 9:16. A PAPER jetty occupies the lower third of frame; a
wide flat SKY pond with one hard INK waterline fills the middle; a PAPER far bank sits across the top with
flat POP_TEAL foliage masses behind it. Desaturated duck silhouettes lounge on the near bank like people.
Quiet, lower-contrast than the cast, generous negative space, no text.
```
**Continuity:** the jetty, the far bank and the `ALERT_RED` load line on the hull hold fixed positions
throughout. The gunwale gap only shrinks. C8 settles to the exact C1b framing.

---

## Per-shot prompts + direction

### C1 — 0:00–0:01.5 · ECU.EYE.STATIC · cold payoff
```
{style prefix} Extreme close-up, 9:16: an ASPHALT boat gunwale sitting FLUSH with a flat SKY water surface
that has a single hard INK waterline, with a desaturated duck silhouette ALREADY MID-STEP over the gunwale,
one webbed foot planted on the wood and the other still lifted. No pond, no faces, no context, no character
entering frame. Tight, high contrast, motion already underway.
```
- 45 frames, static, motion underway on frame 1. **No music.** No splash — the water surface stays intact.

### C1b — 0:01.5–0:02 · MED.FLAT.STATIC · goal diagram
```
{style prefix} Flat dead-centre schematic, 9:16: a boat hull shown IN SECTION with a bold horizontal
ALERT_RED LOAD LINE across it, a neat stack of PAPER cargo drawn clearly BELOW that line, and a large
POP_TEAL TICK beside it. Plain PAPER background, no characters, no text. Schematic, instantly readable in
one pass.
```
- Nothing moves, 15 frames. Music **enters**. One flat sparkle on the load line.

### C2 — 0:02–0:06 · MED.EYE.PUSHIN · rewind/setup
```
{style prefix} Medium 9:16 at a PAPER jetty on a flat SKY pond. Two hulls tied alongside: a SMALL PAPER
raft and a BIG ASPHALT boat carrying a bold ALERT_RED load line on its side. Tiny PIP (PAPER body, POP_TEAL
scarf, neutral) sets two light PAPER bundles onto the raft and steps aboard — it rides HIGH, gunwale well
clear of the water. Beside him CHIEF (POP_TEAL jacket, BRAND_YELLOW medal sash, peaked cap with badge,
gloating) is PILING PAPER CARGO CRATES into the big boat, whose hull already sits lower. Desaturated duck
silhouettes lounge on the near bank like people. Load state L1. Three flat INK wake chevrons behind the raft.
```
- Motion: PIP two bundles (4-frame each); CHIEF three crates (fast). Camera: push-in 100%→110% ending on the gunwale-to-water gap. **No FX on the cargo.**

### C3 — 0:06–0:11 · WIDE.EYE.STATIC · escalation 1
```
{style prefix} Wide 9:16. Tiny PIP's small PAPER raft has cast off and is gliding out across the flat SKY
pond, riding HIGH and dry, three flat INK wake chevrons behind it. At the jetty CHIEF is adding two more
PAPER cargo crates to the big ASPHALT boat; its gunwale has dropped visibly toward the bold ALERT_RED load
line. He is gesturing at his own cargo and dismissively at PIP's two bundles, gloating, EYELINE ON PIP not
on the waterline. Load state L2.
```
- Motion: PIP glides (loop); CHIEF two crates; **4-frame hold as the gunwale reaches the line.** Wake chevrons: raft 3, boat 0 (still moored).

### C4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight) · escalation 2
```
{style prefix} Medium-wide 9:16. CHIEF has piled more PAPER cargo into the big ASPHALT boat and its GUNWALE
IS NOW LEVEL WITH the flat SKY water — a step rather than a wall. Behind him at the stern, ONE desaturated
duck silhouette has STEPPED ABOARD and settled. CHIEF is triumphant, chest out, and is NOT looking back.
Out on the pond tiny PIP glances at the boarding duck, worried. Load state L3.
```
- Motion: two crates; **3-frame hold as the first duck's foot lands on the gunwale.** No splash.

### C5 — 0:16–0:22 · FULL.LOW.PUSHIN → HOLD · full commit
```
{style prefix} Low hero angle, 9:16. CHIEF has shoved off and the big ASPHALT boat is SURGING AHEAD of
PIP's small PAPER raft with two flat INK bow-wave chevrons, and he plants an enormous triumphant pose —
chest out, chin high, medals catching, FX_sparkle accents. He is clearly winning the crossing. CRITICAL:
the framing is kept FORWARD and must EXCLUDE the stern — the viewer must not yet see the boarded ducks.
Load state L3.
```
- The pose **freezes** ~1.5 s. Music **cuts mid-phrase at 0:16** on the lock. Wake chevrons: boat 2, raft 1.

### C6 — 0:22–0:27 · WIDE.EYE.STATIC→TILT · pattern break
```
{style prefix} 9:16, quiet. Duck silhouettes are STEPPING OVER the low ASPHALT gunwale one after another
and settling in the stern — the hull sitting lower with each one, and the flat INK wake chevrons behind it
reducing from two to one to none. CHIEF still frozen in his triumphant pose forward, beginning to falter as
he looks down at his own waterline. Out on the pond tiny PIP's PAPER raft still rides high, hopeful. Load
state moving L3 toward L4. No sparkle, no effects beyond the chevrons.
```
- Motion: **three discrete duck boardings** (~1.4 s apart), each with a hull settle increment and one fewer wake chevron. Camera: static wide, then slow tilt to the stern at ~0:26.

### C7 — 0:27–0:31 · WIDE.EYE.PUNCHIN → SETTLE · role reversal
```
{style prefix} Punch-in 9:16. The big ASPHALT boat has settled until the flat SKY waterline sits EXACTLY at
its bold ALERT_RED LOAD LINE and it has STOPPED DEAD mid-pond — ZERO wake chevrons, completely motionless,
a floating platform occupied by a row of patient desaturated duck silhouettes. CHIEF sits forward, face
shocked and panicked, cap and sash and medals all still on and COMPLETELY DRY. At the same moment tiny
PIP's small PAPER raft glides PAST him and touches the PAPER far bank, and PIP steps ashore, gleeful. The
water surface is unbroken — no splash, no swamping. Flat FX_impact_star at the waterline meeting the line.
```
- Motion: hull settles to `L4` and stops (8 frames), three-stage face snap, raft passes and lands. Camera: punch-in on the waterline/load-line meeting, settle wide; **0.5 s freeze** on stopped-CHIEF and landed-PIP in one frame.

### C8 — 0:31–0:32 · WIDE → MED (== C1b) · payoff/loop
```
{style prefix} 9:16. CHIEF sits motionless mid-pond in the stopped ASPHALT boat beneath a row of patient
desaturated duck silhouettes, cap still on, COMPLETELY DRY, sheepish. On the PAPER far bank tiny PIP is
TOSSING HIM THE RAFT'S TOW LINE — plainly, no smirk — then gives a small friendly wave to camera, relieved.
Framing then settles into the EXACT C1b schematic composition: the hull in section with its bold ALERT_RED
load line, cargo drawn BELOW the line, and the POP_TEAL tick.
```
- Motion: rope toss arc (6 frames), PIP wave, one duck settle. **No sparkle on PIP.** Settle to C1b framing as the final frame.

---

## Transitions & cut map
| Between | Type |
|---|---|
| C1→C1b | hard cut (payoff → rule) |
| C1b→C2 | hard cut (rewind) |
| C2→C3→C4 | hard cut |
| **C5 internal 0:16** | **music cut only, no visual cut** — the lapping continues |
| C5→C6 | hard cut |
| C6→C7 | hard cut into punch-in |
| **C7 internal** | 0.5 s freeze on stopped-CHIEF + landed-PIP |
| C7→C8 | hard cut |
| C8→loop | hard cut, seam to C1 |

No dissolves, fades, wipes, glitch, zoom-blur or camera rotation.

> **The key craft note:** the whole episode is carried by **one measurement — the gap between gunwale and
> waterline.** Chart it shot by shot as `L0`→`L4` and never let it rebound. The wake chevron count is the
> second half of the same instrument: 3 → 3 → 2 → 1 → 0. When the chevrons hit zero the audience
> understands he has stopped without being told, and the load line explains why.

---

## Handoff checklist
- [ ] 9:16 / 1080×1920, ≈32 s, timecodes exact.
- [ ] C1 tight, duck **mid-step**, no entrance, no static wide.
- [ ] C1b diagram wordless: hull section + `ALERT_RED` load line + cargo below + `POP_TEAL` tick.
- [ ] **Load state charted `L0`→`L4` and monotonic.** Scrub for any frame where the gunwale rises.
- [ ] **Wake chevron count tracks the load:** 3 → 3 → 2 → 1 → 0. Zero chevrons in C7 and C8.
- [ ] `ALERT_RED` load line in the same position on the hull in every shot where the hull is visible.
- [ ] Both hulls in the same frame in C2–C4.
- [ ] **C5 framing excludes the stern.** Show it to a cold viewer and confirm they cannot pre-solve it.
- [ ] Water is one flat `SKY` shape with a single hard `INK` waterline — no gradient, transparency, reflection or ripple texture.
- [ ] **The water surface is never broken.** No splash, no swamping, no water over the gunwale, no capsize.
- [ ] CHIEF keeps cap + sash + medals and is **completely dry in every frame including C7–C8.**
- [ ] Ducks are desaturated silhouettes with no faces, calm throughout, boarding of their own accord. **None harmed, herded, startled or in danger.**
- [ ] Colour tokens only — water `SKY`, boat `ASPHALT`, raft/jetty/cargo/banks `PAPER`, foliage `POP_TEAL`, load line `ALERT_RED`. **No "brown", "wood", "green" or "white" anywhere.**
- [ ] Zero baked text; no English colour words in any prompt above.
- [ ] Final frame matches C1b with cargo below the line.
