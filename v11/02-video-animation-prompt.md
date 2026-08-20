# v11 - Video-Generation Script / Prompt ("The Express Lane") - **SHORTS 9:16**

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or equivalent). It specifies **motion, camera angles, transitions, cut timing,
> motion-graphics and on-screen FX per shot**, so the generated output needs **minimal editing** -
> ideally just top-and-tail + audio layup. Everything aligns to the master timeline in
> `01-video-script.md` and audio in `03-audio-bgm-sfx-reference.md`.

**Global render spec:** **1080x1920 (9:16 vertical)** - 30 fps - ~32 s (~960 frames) - flat-2D cartoon
house style (thick uniform black outlines, no gradients, chunky 2.5-head proportions) - snappy pose-to-pose
with strong holds - **hard cuts only** (no dissolves/fades) - **no camera rotation/orbit, no handheld** -
**no blur/glow/gradients** - loop seam (C8 == C1).

**Motion philosophy:** limited animation - hold poses on comedy beats, animate in short bursts. v11's
structure builds tension through **counting** (the item counter is the ticking time bomb) then delivers
the collapse through a blunt mechanical enforcement (the barrier drops). Resist over-animating PIP - his
stillness is the contrast.

Two contrasting motion languages:
- **CHIEF:** big theatrical scanning motions, triumphant item-tossing, increasingly cocky poses at each number, frantic button-mashing and barrier-pulling when trapped.
- **PIP:** nearly motionless throughout. Four actions total: gets shoved (C1), waits patiently (C2-C5), raises an eyebrow (C6), walks to open register, scans one item, walks out (C7), waves (C8).

> **The one rule that cannot break:** the **green "OPEN" light** on the right register must be visible
> in C1 (glowing quietly in the background) and must be the register PIP uses in C7. The audience must
> be able to verify the fair-play contract on replay.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** - subject motion - camera - transitions/FX - cut.

### SHOT 1 - 0:00-0:02 - WIDE.EYE.STATIC
- **Motion:** CHIEF rams into frame from the left with an overloaded shopping cart (items piled high, 2-3 items fall off in a 4-frame scatter). He bumps PIP aside (3-frame stumble). He swerves the cart under the "EXPRESS - 10 ITEMS OR FEWER" sign (SEED B) and parks at the left register. The right register's green "OPEN" light (SEED A) glows steadily in the background.
- **Camera:** locked wide. 6-frame settle hold so both seeds register - the sign overhead and the green OPEN light on the unused register.
- **Motion graphics/FX:** a small `BRAND_YELLOW` glow on the register screen as CHIEF approaches; the green "OPEN" light is a flat green circle, unemphasized. Items falling off the cart are flat colored shapes.
- **Transition out:** hard cut.

### SHOT 2 - 0:02-0:06 - MED.EYE.PUSHIN(slow)
- **Motion:** CHIEF grabs items from his cart and scans them one by one across the flat-panel scanner. Each scan triggers a 2-frame screen update. Counter: "1" (3-frame hold), "2" (3-frame hold), "3" (3-frame hold). He barely looks at the scanner - his eyes are on PIP, smugly.
- **Camera:** slow push-in (100% to 108% over 4 s), ending framed on the counter "ITEMS: 3" and CHIEF's smug profile.
- **FX:** small flat green circle burst on each successful scan; counter numbers pop in; `BRAND_YELLOW` screen glow steady.
- **Transition out:** hard cut.

### SHOT 3 - 0:06-0:11 - CLOSE-MED.EYE.STATIC
- **Motion:** CHIEF's hands move faster (4-frame scan cycles now instead of 6). Items fly across the scanner in a blur of motion lines. Counter: 4 (pop)... 5 (pop)... 6 (pop)... 7 (pop). The "10 ITEMS OR FEWER" sign is visible at the top of the frame, glowing softly. One item nearly misses the scanner and CHIEF catches it mid-air (3-frame grab) without stopping.
- **Camera:** static close-medium focused on the counter and CHIEF's scanning hands; 3-frame hold on each number.
- **Motion graphics/FX:** flat motion lines on each scanned item; counter numbers pop with small flat bursts; sign overhead has a subtle constant glow (not pulsing yet).
- **Transition out:** hard cut.

### SHOT 4 - 0:11-0:16 - WIDE.EYE.STATIC -> PUSHIN(slight)
- **Motion:** Counter shows 8 (beep)... 9 (beep)... **10** (the 10th beep has a 4-frame `BRAND_YELLOW` flash across the screen and the sign above pulses once in sync - a WARNING, 4-frame glow cycle). CHIEF does not notice either flash - he is already reaching into his cart for the next item, grinning wide.
- **Camera:** static wide for the first half; slight push-in (100% to 103%) on the second half, framing CHIEF reaching for item 11 with the "10" counter and the warning-pulsing sign behind him.
- **Motion graphics/FX:** counter numbers 8, 9 pop normally; "10" gets a `BRAND_YELLOW` full-screen flash (4 frames); the overhead sign glows brighter for 4 frames; CHIEF's reaching hand has a small motion line.
- **Transition out:** hard cut.

### SHOT 5 - 0:16-0:22 - MED.LOW.STATIC -> HOLD
- **Motion:** CHIEF scans item 11 (2-frame scan motion). The screen IMMEDIATELY flashes `ALERT_RED` with "OVER LIMIT" (2-frame pop). A **red barrier arm** drops from above into the exit lane (6-frame drop, mechanical motion). An alarm beacon on top of the register starts spinning (continuous rotation). CHIEF freezes (4-frame from motion to locked pose), item still in hand, his grin collapsing to horror.
- **Camera:** medium shot, slight low angle. The red barrier arm cutting across the frame and the "OVER LIMIT" screen dominate. CHIEF is trapped between barrier and cart.
- **Motion graphics/FX:** `ALERT_RED` full-screen flash; "OVER LIMIT" text (diegetic, on the machine screen); flat red barrier arm (solid color with black outline, no gradient); spinning beacon is a simple flat shape rotating. No sparkle.
- **AUDIO CUE (critical):** music **CUTS TO SILENCE on the frame of the barrier drop (0:16)**, leaving the mechanical CLUNK exposed.
- **Transition out:** hard cut.

### SHOT 6 - 0:22-0:27 - MED.EYE.STATIC
- **Motion:** CHIEF tries to fix it: (1) Re-scans item 11 (3-frame scan motion) - screen flashes "OVER LIMIT" again (2-frame flash with buzz). (2) Jabs touchscreen buttons (6-frame rapid tapping) - no response, screen stays red. (3) Grabs barrier arm with both white gloves and pulls (6-frame strain, comic veins/effort lines on arms) - barrier holds firm (2-frame click but no movement). He slumps against it (4-frame deflation). In the background, the right register's green "OPEN" light blinks gently. PIP raises one eyebrow (2-frame).
- **Camera:** static two-shot (CHIEF trapped at express lane left, PIP and open register right); 3-frame hold on each "OVER LIMIT" flash.
- **Motion graphics/FX:** "OVER LIMIT" flash (flat red); flat effort lines on barrier pull; the green "OPEN" light blinks (2-frame on, 8-frame off). No sparkle - restraint carries the dread.
- **Transition out:** hard cut.

### SHOT 7 - 0:27-0:31 - MED.EYE.PUNCHIN -> SETTLE
- **Motion (beat 1, 0:27-0:29):** PIP calmly walks to the right register (4-frame walk x3 steps). He places his single milk carton on the scanner (3-frame place). One clean scanner **beep** (2-frame green flash on screen). Screen shows "ITEMS: 1 - TOTAL: $2.49 - THANK YOU" in green (4-frame hold). The right exit gate opens smoothly (4-frame slide).
- **Motion (beat 2, 0:29-0:31):** PIP picks up a small bag (2-frame), walks through the open gate (6-frame walk). CHIEF's jaw drops (3-frame snap down). He is still behind the red barrier, surrounded by his overflowing cart. The express lane screen still shows "OVER LIMIT." PIP's expression shifts subtly from calm to gleeful (4-frame transition).
- **Camera:** quick punch-in on PIP's milk carton hitting the scanner (~6 frames), then settle back to wide; **0.5 s freeze on PIP walking through the gate with CHIEF still trapped** (the screenshot-able punchline).
- **Motion graphics/FX:** one clean flat green circle burst on the scan; screen text in green (diegetic); smooth gate slide; `FX_impact_star_v1` on the beep. No sparkle on PIP.
- **AUDIO CUE:** music **SLAMS back** at 0:27 on PIP's first footstep; the single scanner **beep at 0:28 is crisp and satisfying** (file 03).
- **Transition out:** hard cut.

### SHOT 8 - 0:31-0:32 - WIDE.EYE.STATIC (== SHOT 1)
- **Motion:** PIP walks away with his small bag (exiting right, 4-frame walk). CHIEF is still trapped behind the red barrier arm, slumped, overflowing cart beside him. The express lane screen shows "OVER LIMIT." The "10 ITEMS OR FEWER" sign glows above. One item falls off CHIEF's cart (4-frame topple). PIP turns and waves to camera (3-frame wave).
- **Camera:** return to the **exact SHOT-1 framing** - same background plate, same two registers, same sign. Only the red barrier and PIP's absence from the queue differ.
- **Motion graphics/FX:** one flat colored item shape toppling off the cart; screen still flashing "OVER LIMIT" (continuous); no residual FX on the final frame (loop must be clean after the item falls).
- **Transition out:** **hard cut** <=1 s after the wave, seaming back to SHOT 1.

---

## B) Transitions & cut map (quick reference)
| Between | Type | Notes |
|---|---|---|
| C1->C2->C3->C4 | hard cut | snappy 2-5 s clips |
| C4->C5 | hard cut | into the lockout |
| **C5 internal (0:16)** | **music cut only - no visual change** | pattern break by removing the score on the barrier drop |
| C5->C6 | hard cut | to the desperate fix attempts |
| C6->C7 | hard cut into **punch-in** | the twist |
| **C7 internal (0:29)** | 0.5 s freeze | PIP walking out / CHIEF still trapped |
| C7->C8 | hard cut | payoff |
| C8->(loop) | hard cut, seam to C1 | replay re-reads the sign and the green OPEN light |

**No** dissolves, fades, wipes, glitch, zoom-blur, or camera rotation anywhere. Effects are limited to:
flat circle bursts (green/red), flat screen text (diegetic only), flat barrier arm, spinning beacon,
blinking light, motion lines, impact-star, and the listed holds/freezes.

---

## C) Optional single "master prompt" (for one-shot generators)
```
{style: flat-color 2D cartoon, thick uniform black outlines, no gradients, chunky 2.5-head proportions,
palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076, ALERT_RED
#E4322B, POP_TEAL #2FB6A3 - 9:16 VERTICAL}
A ~32s 9:16 flat-2D cartoon comedy short, 30fps, hard cuts only, no camera rotation, no blur or glow.
Recurring cast: CHIEF, a pompous rotund braggart in a teal jacket with an oversized peaked cap and a yellow
medal sash, white gloves; PIP, a tiny underdog with a teal scarf. Setting: a PAPER-coloured self-checkout
store interior with two registers side by side - left one under an "EXPRESS - 10 ITEMS OR FEWER" sign,
right one with a green "OPEN" light.
Story in 8 beats:
(0-2s) WIDE static: CHIEF rams an OVERLOADED CART (items spilling) past PIP and muscles into the express
lane under the "10 ITEMS OR FEWER" sign. PIP holds ONE MILK CARTON. Right register's green OPEN light
glows in background.
(2-6s) MED slow push-in: CHIEF scans items cockily. Counter: 1, 2, 3. He smirks at PIP.
(6-11s) CLOSE-MED static: CHIEF scans faster. Counter: 4, 5, 6, 7. Sign visible overhead. Each beep
louder than the last.
(11-16s) WIDE: Counter hits 8, 9, 10. At "10" the screen flashes BRAND_YELLOW warning. Sign pulses once.
CHIEF doesn't notice - already reaching for item 11.
(16-22s) MED low angle: CHIEF scans item 11. Screen flashes ALERT_RED "OVER LIMIT." A RED BARRIER ARM
drops blocking the exit. Alarm beacon spins. CHIEF freezes. MUSIC CUTS TO SILENCE.
(22-27s) MED static two-shot: CHIEF re-scans (OVER LIMIT again), jabs buttons (no response), pulls
barrier (won't budge). Green OPEN light blinks on right register, unnoticed. PIP raises eyebrow.
(27-31s) MED punch-in: PIP walks to right register, places ONE MILK CARTON on scanner - ONE CLEAN BEEP.
Screen: "ITEMS: 1 - THANK YOU." Gate opens. PIP walks through. CHIEF jaw drops, still trapped. 0.5s
freeze on the contrast.
(31-32s) WIDE, framing identical to opening: PIP walks away with small bag. CHIEF still trapped behind
barrier, cart overflowing. "OVER LIMIT" still on screen. PIP waves. One item falls off cart. Hard cut.
ZERO overlaid text (sign and screen text are diegetic set pieces). CHIEF never loses cap/sash/medals.
PIP never gloats. The twist is CHIEF's own greed (30+ items in a 10-item lane) triggering the machine's
built-in limit. Advertiser-safe: CHIEF is merely trapped behind a gate and embarrassed - no injury.
```

---

## D) Handoff / minimal-edit checklist
- [ ] **Rendered 9:16 / 1080x1920**, total ~32 s, on the locked 8-clip skeleton.
- [ ] Assemble C1->C8 with **hard cuts**; add no transitions.
- [ ] Insert the holds/freezes: C1 6-frame settle - C3 3-frame per number - C4 4-frame warning flash - C5 barrier drop (6-frame) - C6 3-frame per "OVER LIMIT" flash - C7 **0.5 s contrast freeze**.
- [ ] **Verify Seed A:** the green "OPEN" light is visible in C1 background and is the register PIP uses in C7.
- [ ] **Verify Seed B:** the "10 ITEMS OR FEWER" sign is visible from C1 and makes the lockout inevitable.
- [ ] **Verify the trigger:** the lockout is caused by CHIEF's own greed (scanning more than 10 items in a 10-item lane) - no external sabotage.
- [ ] Verify PIP is **patient and kind** throughout - never aggressive, simply walks to the open register.
- [ ] Confirm the **music cuts at 0:16 with no visual cut**, and only the alarm beacon click and mechanical sounds remain through 0:27.
- [ ] Confirm the **C7 single clean beep** is the most satisfying sound - one cheerful scan vs. all the harsh buzzers and mechanical locks.
- [ ] Verify loop seam: overlay C8 on C1 - background plate, framing, register positions must match.
- [ ] Lay VO (if used) and BGM/SFX (file 03) onto the fixed timecodes - everything is pre-synced.
- [ ] Final QC: no overlaid text (sign and screen are diegetic props within the scene), no blur/glow, cast on-model, CHIEF merely trapped and embarrassed, advertiser-safe.
