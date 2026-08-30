# v20 — Video & Animation Prompt ("The Inspection") · **SHORTS 9:16**

> Compact-package file 2: per-shot image prompts **and** motion/camera/FX. Locks to `01-video-script.md`.

**Render spec:** 1080×1920 · 30 fps · ~32 s · flat-2D house style · hard cuts only *(one exception: C6's continuous pull-back)* · no camera rotation · no blur/glow/gradients · loop seam (final frame == C1b).

## 0. Style prefix
```
Flat-color 2D cartoon, thick uniform INK #1A1A1A outlines (never pure #000000), no gradients,
minimal single-tone shading, high-contrast clean vector look, 9:16 vertical, mobile-legible.
Proportions: chunky 2-2.5 head heights — PIP ~2, CHIEF ~2.5.
Palette ONLY: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text. Advertiser-safe, no gore.
```

**Cast:** `CHAR_CHIEF_v1` (rotund warden, `POP_TEAL` jacket, `BRAND_YELLOW` buttons + medal sash, peaked cap with badge, `PAPER` gloves, `smug`) · `CHAR_PIP_v1` (tiny, `PAPER` body, `POP_TEAL` scarf every shot, `worried` default). **Cap + sash + medals never leave CHIEF.**

**Environment** `BG_checkpoint_v1`
```
BG_checkpoint_v1: flat-2D checkpoint gate, composed for 9:16. A plain ASPHALT gate wall spans the
middle of frame with a single rectangular opening framed in bold ALERT_RED — the SLOT. An ASPHALT
post beside it holds a stamp on a hinged arm. ASPHALT ground below, flat SKY strip above, flat
desaturated depot shapes behind. Quiet, lower-contrast than the cast, generous negative space, no text.
```
**Continuity:** the slot's screen position and its `ALERT_RED` outline width are identical in C1b, C2, C3, C4, C6, C7, C8. Cart load only ever increases before C7. The crate stays wedged from C4 to C8.

---

## Per-shot prompts + direction

### C1 — 0:00–0:01.5 · ECU.EYE.STATIC · cold payoff
```
{style prefix} Extreme close-up, 9:16: a PAPER crate JAMMED HARD into a rectangular slot framed in bold
ALERT_RED, its corners visibly compressed, caught MID-JAM, with a cart handle already past it on the
near side. Flat ASPHALT gate wall around the slot. No location, no faces, no character entering frame.
Tight, high contrast, straining.
```
- 45 frames, static, motion underway on frame 1. FX: flat `FX_strainline_v1` at the crate corners. **No music.**

### C1b — 0:01.5–0:02 · MED.FLAT.STATIC · goal diagram
```
{style prefix} Flat dead-centre schematic, 9:16, split into two halves. LEFT: a rectangular slot
outlined in bold ALERT_RED with a simple cart silhouette sitting comfortably INSIDE the outline, and a
large POP_TEAL TICK mark beside it. RIGHT: the same cart silhouette with a PAPER crate stacked on top so
it clearly OVERLAPS and exceeds the ALERT_RED outline, with a large ALERT_RED CROSS beside it. Plain
PAPER background, no characters, no text. Schematic, unmistakable, readable in one pass.
```
- Nothing moves, 15 frames. Music **enters**. One flat sparkle on the tick.

### C2 — 0:02–0:06 · MED.EYE.PUSHIN · rewind/setup
```
{style prefix} Medium 9:16 at a checkpoint gate. Two carts approach the same ALERT_RED-framed slot.
Tiny PIP (PAPER body, POP_TEAL scarf, neutral) wheels a neat, modestly loaded cart that sits well below
the slot's outline. Beside him CHIEF (POP_TEAL jacket, BRAND_YELLOW medal sash, peaked cap with badge,
gloating) is LIFTING A PAPER CRATE ONTO THE TOP of his own cart to make it grander — the added height
now reaching toward the top of the slot outline behind them. Unemphasised, casual.
```
- Motion: PIP steady roll; CHIEF 4-frame lift + 2-frame settle. Camera: push-in 100%→110% ending on the crate's top edge against the slot outline. **No FX on the seed.**

### C3 — 0:06–0:11 · WIDE.EYE.STATIC · escalation 1
```
{style prefix} Wide 9:16. PIP's modest cart has rolled CLEANLY through the ALERT_RED-framed slot,
untouched, and stands complete on the far side with every item aboard. On the near side CHIEF is adding
another PAPER item to his stack, which now sits clearly ABOVE the top of the slot outline, gloating.
```
- Motion: PIP's cart clears (4-frame hold as it passes); CHIEF adds one item (3-frame). FX: `FX_motionlines_v1` on the roll.

### C4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight) · escalation 2
```
{style prefix} Medium-wide 9:16. CHIEF has shoved his overloaded cart INTO the ALERT_RED-framed slot and
is FORCING it through, shoulder down, straining, flat strain lines around the cart body. The cart is
squeezing through, but at the slot's far lip the stacked PAPER crate has begun to CATCH, corners
compressing. CHIEF's eyeline is FORWARD, on the stamp waiting on its ASPHALT post — he does not look
back at the crate. Tiny PIP watching from the far side, worried.
```
- Motion: forcing shove (continuous); the crate catch is one visible 3-frame compression. Camera: slight push-in 100%→104%.

### C5 — 0:16–0:22 · FULL.LOW.PUSHIN → HOLD · full commit
```
{style prefix} Low hero angle, 9:16. CHIEF stands in an enormous triumphant pose having just thumped the
stamp down, holding up his docket bearing a large POP_TEAL TICK, chest out, chin high, medals catching,
FX_sparkle accents. He has officially passed. CRITICAL: the framing is TIGHT on CHIEF and the stamp post
and must EXCLUDE the slot and everything behind him — the viewer must not yet be able to see the wedged
crate or his empty cart.
```
- The pose **freezes** ~1.5 s. Music **cuts mid-phrase at 0:16** on the stamp thump. Camera: low push-in settling into the hold.

### C6 — 0:22–0:27 · WIDE.EYE.PULLOUT · pattern break (the reveal begins)
```
{style prefix} 9:16, tense and quiet. A slow continuous PULL-BACK from the tight shot: CHIEF still
holding the POP_TEAL-ticked docket aloft, his triumphant grin beginning to falter into confusion; as the
frame widens, the ALERT_RED-framed slot behind him starts to enter view and the silhouette of the wedged
PAPER crate becomes visible at its far lip. Tiny PIP's eyeline is going PAST CHIEF toward the slot,
worried. No sparkle, no effects.
```
- Motion: three faltering beats (~1.4 s apart). **Camera: one continuous PULLOUT — do not cut into this.** The reveal is the move.

### C7 — 0:27–0:31 · WIDE.EYE.PUNCHIN → SETTLE · false victory revealed
```
{style prefix} Full-width 9:16. The PAPER crate is STILL WEDGED in the ALERT_RED-framed slot at the far
lip. CHIEF's cart is through the gate and COMPLETELY EMPTY. Beside it, tiny PIP's modest cart stands
intact with every item still aboard. CHIEF is looking from his valid POP_TEAL-ticked docket to his empty
cart to the stuck crate, face shocked and panicked, cap and sash and medals all still on. PIP gleeful.
Flat FX_impact_star at the crate. The tick is plainly real and plainly worthless.
```
- Motion: three-stage face snap (4 frames each); docket-to-cart-to-crate eyeline. Camera: punch-in on the wedged crate, settle wide; **0.5 s freeze** on empty-cart-plus-tick beside PIP's full cart.

### C8 — 0:31–0:32 · WIDE → MED (== C1b) · payoff/loop
```
{style prefix} 9:16. CHIEF stands holding a valid POP_TEAL-ticked docket over a completely empty cart,
cap still on, sheepish. Tiny PIP has wheeled his own cart back a pace and is LIFTING THE WEDGED PAPER
CRATE FREE of the slot, setting it into CHIEF's empty cart — plainly, no smirk — then gives a small
friendly wave to camera, relieved. Framing then settles into the EXACT C1b schematic composition,
showing the slot outline with the cart fitting inside it and the POP_TEAL TICK.
```
- Motion: crate lift (6 frames), set down, PIP wave. **No sparkle on PIP.** Settle to C1b framing as the final frame.

---

## Transitions & cut map
| Between | Type |
|---|---|
| C1→C1b | hard cut (payoff → rule) |
| C1b→C2 | hard cut (rewind) |
| C2→C3→C4 | hard cut |
| **C5 internal 0:16** | **music cut only, no visual cut** |
| **C5→C6** | **NO CUT — continuous PULLOUT.** The reveal is the camera move |
| C6→C7 | hard cut into punch-in |
| **C7 internal** | 0.5 s freeze on the empty cart + valid tick |
| C7→C8 | hard cut |
| C8→loop | hard cut, seam to C1 |

No dissolves, fades, wipes, glitch, zoom-blur or camera rotation.

> **The key craft note:** C5 must **hide** the geometry and C6 must **reveal** it, in one unbroken move.
> If you cut between them the joke still works but loses its best quality — the sense that the answer was
> behind him the whole time and the camera was simply too close to show it.

---

## Handoff checklist
- [ ] 9:16 / 1080×1920, ≈32 s, timecodes exact.
- [ ] C1 tight, mid-motion, no entrance.
- [ ] C1b is a **fit/no-fit pair** with `POP_TEAL` tick and `ALERT_RED` cross — decided in one pass.
- [ ] Slot screen position and outline width identical in C1b, C2, C3, C4, C6, C7, C8.
- [ ] **C5 framing genuinely excludes the slot.** Show it to a cold viewer and confirm they cannot predict C7.
- [ ] **C5→C6 is one continuous pull-back, not a cut.**
- [ ] Cart load monotonic C2→C4; the crate stays wedged C4→C8.
- [ ] CHIEF keeps cap + sash + medals throughout.
- [ ] Colour tokens only — **no "green" tick, no "white", no "wood" crate**.
- [ ] Ad-safety: crates are light `PAPER`, nothing falls on anyone, no crushing.
- [ ] Zero baked text; no English colour words in any prompt above.
- [ ] Final frame matches C1b.
