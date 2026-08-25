# v9 - Video-Generation Script / Prompt ("The Last Slice") - **SHORTS 9:16**

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or equivalent). It specifies **motion, camera angles, transitions, cut timing,
> motion-graphics and on-screen FX per shot**, so the generated output needs **minimal editing** -
> ideally just top-and-tail + audio layup. Everything aligns to the master timeline in
> `01-video-script.md` and audio in `03-audio-bgm-sfx-reference.md`.

**Global render spec:** **1080x1920 (9:16 vertical)** - 30 fps - ~32 s (~960 frames) - flat-2D cartoon
house style (thick uniform black outlines, no gradients, chunky 2.5-head proportions) - snappy pose-to-pose
with strong holds - **hard cuts only** (no dissolves/fades) - **no camera rotation/orbit, no handheld** -
**no blur/glow/gradients** - loop seam (C8 == C1).

**Motion philosophy:** limited animation - hold poses on comedy beats, animate in short bursts. v9's
comedy comes from **excessive effort vs. zero effort**. CHIEF is always moving, always building, always
leaving. PIP performs exactly one action in the entire video: he raises his hand. That single still moment
is funnier than all of CHIEF's business combined.

Two contrasting motion languages:
- **CHIEF:** big sweeping arm gestures, theatrical bottle placements, warning finger-points, a confident walk away, an elaborate topping-selection routine - maximalist.
- **PIP:** near-perfectly still for 22 seconds. Then: one raised hand. That is all.

> **The one rule that cannot break:** the **bottle fortress is never disturbed.** It stands from C3 to C8,
> undisturbed and useless. The joke is that the defense was perfect - but the "attack" came from asking
> politely, which bypasses all barriers. If a single bottle falls, the joke breaks.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** - subject motion - camera - transitions/FX - cut.

### SHOT 1 - 0:00-0:02 - WIDE.EYE.STATIC
- **Motion:** CHIEF's gloved hand enters frame and **slams** a `ALERT_RED` ketchup bottle down next to a shared plate (fast 3-frame slam, small table shake on impact - the plate and slice jiggle 2 frames). PIP, across the table, leans forward slightly (2-frame lean). In the background, the waiter shifts weight (2-frame settle - just enough to register as alive).
- **Camera:** locked wide. 6-frame settle hold so both seeds register - the waiter standing ready and the topping bar at the counter.
- **Motion graphics/FX:** a small impact ring (2-frame flat circle) under the bottle on slam; slight table jiggle. No emphasis on the waiter or topping bar.
- **Transition out:** hard cut.

### SHOT 2 - 0:02-0:06 - MED.EYE.PUSHIN(slow)
- **Motion:** CHIEF places a second bottle (`BRAND_YELLOW` mustard, 3-frame place), then a third (`ALERT_RED` hot sauce, 3-frame place), forming a wall. After each placement he turns to PIP with a progressively wider grin (3-frame head-turns). PIP glances at the slice (2-frame look down), then his eyes drift upward and to the right toward the waiter behind CHIEF (3-frame eye movement).
- **Camera:** slow push-in (100% to 108% over 4 s), ending framed on the three bottles in a row with the pizza slice visible between them like prison bars.
- **FX:** small flat impact rings on each bottle placement (diminishing); the bottles cast no shadows (flat style).
- **Transition out:** hard cut.

### SHOT 3 - 0:06-0:11 - WIDE.EYE.STATIC
- **Motion:** CHIEF adds four more items in quick succession: salt shaker (3-frame), pepper mill (4-frame, taller), napkin dispenser (3-frame, sideways), a sugar container (3-frame, filling the last gap). Each placement more theatrical than the last - the final one with an exaggerated arm-sweep and a step back to admire (6-frame step-back + hands-on-hips hold). The waiter remains visible, standing ready, notepad held.
- **Camera:** static wide; 3-frame hold on each new item placed; 6-frame hold on the completed fortress with CHIEF admiring it.
- **Motion graphics/FX:** `FX_sparkle_v1` self-satisfaction accent on the final hold; no FX on individual placements.
- **Transition out:** hard cut.

### SHOT 4 - 0:11-0:16 - WIDE.EYE.STATIC -> PUSHIN(slight)
- **Motion:** CHIEF's head turns toward the topping bar at the counter (3-frame turn, eyes widening). He raises a warning finger at PIP (3-frame raise + 2 wags). Then he turns and **walks away** - a confident 6-step strut toward the counter (12-frame total walk). PIP watches him go (4-frame head-track), then looks at the fortress (2-frame), then looks at the waiter (2-frame).
- **Camera:** static wide for the warning, then slight push-in (100% to 103%) following CHIEF's departure, ending with the table (PIP + fortress + waiter) centered in frame.
- **Motion graphics/FX:** `FX_motionlines_v1` on the confident strut; the warning finger gets a small 1-frame emphasis line. The cake/slice inside the fortress is clearly visible - unguarded.
- **Transition out:** hard cut.

### SHOT 5 - 0:16-0:22 - WIDE.EYE.STATIC (split composition)
- **Motion:** Background: CHIEF at the counter, selecting toppings with exaggerated care - picking up an olive, examining it, placing it precisely on his plate (3-frame pick, 2-frame examine, 2-frame place - repeated for each item). He never turns around. Foreground: the table - the bottle fortress standing tall, the slice inside it, PIP sitting perfectly still. A held tableau for ~4 seconds before C6's action begins.
- **Camera:** static wide; the split between foreground table and background counter is the frame design. No movement.
- **Motion graphics/FX:** distant tiny sparkle on each topping CHIEF selects (barely visible - his personal delusion of importance). No FX at the table.
- **AUDIO CUE (critical):** music **CUTS TO SILENCE on the frame CHIEF starts selecting toppings (0:16)**. Only faint restaurant ambience remains.
- **Transition out:** hard cut.

### SHOT 6 - 0:22-0:27 - MED.EYE.STATIC
- **Motion:** PIP **raises his hand** (one smooth 4-frame raise - the only significant animation PIP performs in the entire video). The waiter walks over in 3 calm steps (6-frame walk). The waiter picks up the pizza slice with a small spatula (3-frame lift), places it on a fresh small plate (2-frame set), and places the plate in front of PIP (3-frame serve + small nod). PIP takes a polite bite (3-frame). The fortress remains **completely undisturbed** - but the shared plate inside it is now **empty**.
- **Camera:** static medium on the table; 4-frame hold on the moment the slice leaves the shared plate (the "heist" frame); 4-frame hold on the empty plate inside the fortress.
- **Motion graphics/FX:** absolutely no emphasis FX. The scene is deliberately quiet and ordinary - the waiter serving food is the most normal thing in the world, and that normalcy is the joke.
- **Transition out:** hard cut.

> **PIP's raised hand is the single most important frame in the video.** One hand, palm up, polite. It
> should take exactly as long to animate as one of CHIEF's bottle-slam motions - but it accomplishes
> everything CHIEF's 20 seconds of fortress-building could not.

### SHOT 7 - 0:27-0:31 - MED-WIDE.EYE.PUNCHIN -> SETTLE
- **Motion (beat 1, 0:27-0:29):** CHIEF walks back triumphantly holding his toppings plate high (4-frame strut return, plate held like a trophy). He reaches the table. He sees the fortress - still standing, intact (2-frame look, smile starts). He leans forward and looks *inside* the fortress (4-frame lean) - **the shared plate is empty** (2-frame hold on his face processing this).
- **Motion (beat 2, 0:29-0:31):** He snaps his head to PIP (2-frame snap) - who is calmly chewing the last bite, one hand dabbing his mouth with a napkin. CHIEF's face runs the **3-stage snap:** triumphant -> confused -> shocked (3-frame, 2-frame, 3-frame). His toppings plate tilts in his loosening grip and the olives, peppers, and cheese scatter across the table in a 4-frame cascade.
- **Camera:** quick punch-in on CHIEF's face as he looks inside the fortress (~6 frames), then settle back to wide; **0.5 s freeze on CHIEF holding the empty toppings plate beside PIP finishing the last bite** (the screenshot-able punchline).
- **Motion graphics/FX:** the toppings scatter is flat colored shapes (small circles for olives, strips for peppers, shreds for cheese) bouncing in 2-3 frame arcs; one olive rolls to the table edge and drops off (3-frame roll + 2-frame fall); `FX_impact_star_v1` on the olive's table-edge drop.
- **AUDIO CUE:** music **SLAMS back** at 0:27 on CHIEF's return; the topping **scatter** is a satisfying cascade of tiny sounds.
- **Transition out:** hard cut.

### SHOT 8 - 0:31-0:32 - WIDE.EYE.STATIC (== SHOT 1)
- **Motion:** Same table. The bottle fortress still standing (undisturbed, useless, absurd). The shared plate inside it completely empty. PIP dabs his mouth with a napkin (2-frame dab), then waves (3-frame wave). CHIEF slumps beside the table, holding his now-empty toppings plate, staring at the empty shared plate. The waiter is still standing in the background, smiling. One last olive rolls off the table edge (3-frame roll + drop).
- **Camera:** return to the **exact SHOT-1 framing** - same background plate, same table, same waiter position. Only the empty shared plate, scattered toppings, and PIP's satisfied dab differ.
- **Motion graphics/FX:** one small olive rolling off (flat green circle); no sparkle on PIP; no residual FX on the final frame (loop must be clean).
- **Transition out:** **hard cut** <=1 s after the wave, seaming back to SHOT 1.

---

## B) Transitions & cut map (quick reference)
| Between | Type | Notes |
|---|---|---|
| C1->C2->C3->C4 | hard cut | snappy 2-5 s clips |
| C4->C5 | hard cut | into the split composition (CHIEF at counter / table) |
| **C5 internal (0:16)** | **music cut only - no visual change** | pattern break by removing the score as CHIEF starts selecting |
| C5->C6 | hard cut | to PIP's hand-raise and the waiter's service |
| C6->C7 | hard cut into **punch-in** | CHIEF's return and the twist |
| **C7 internal (0:29)** | 0.5 s freeze | CHIEF shocked / PIP finishing the last bite |
| C7->C8 | hard cut | payoff |
| C8->(loop) | hard cut, seam to C1 | replay re-reads the waiter and the topping bar |

**No** dissolves, fades, wipes, glitch, zoom-blur, or camera rotation anywhere. Effects are limited to:
flat impact rings, motion lines, sparkle (CHIEF only), flat colored food shapes (toppings scatter),
impact-star, and the listed holds/freezes.

---

## C) Optional single "master prompt" (for one-shot generators)
```
{style: flat-color 2D cartoon, thick uniform black outlines, no gradients, chunky 2.5-head proportions,
palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076, ALERT_RED
#E4322B, POP_TEAL #2FB6A3 - 9:16 VERTICAL}
A ~32s 9:16 flat-2D cartoon comedy short, 30fps, hard cuts only, no camera rotation, no blur or glow.
Recurring cast: CHIEF, a pompous rotund braggart in a teal jacket with an oversized peaked cap and a yellow
medal sash, white gloves; PIP, a tiny underdog with a teal scarf. Setting: a small PAPER-coloured
restaurant table with a shared plate holding ONE PIZZA SLICE. A WAITER stands in the background. A TOPPING
BAR is visible at the counter.
Story in 8 beats:
(0-2s) WIDE static: CHIEF slams a ketchup bottle possessively next to the shared plate with one pizza slice.
PIP sits across the table. Waiter visible in background.
(2-6s) MED slow push-in: CHIEF places two more bottles, building a WALL between PIP and the pizza. Grins at
PIP. PIP glances at the slice, then toward the waiter.
(6-11s) WIDE: CHIEF adds four more items (salt, pepper, napkin dispenser, sugar) building an elaborate
FORTRESS around the plate. Steps back to admire. Waiter still in background, ready.
(11-16s) WIDE: CHIEF spots the topping bar at the counter, eyes wide. Points warningly at PIP (DON'T
TOUCH), then WALKS AWAY toward the counter to get toppings. PIP watches him go, looks at fortress, looks at
waiter.
(16-22s) WIDE split composition: Background - CHIEF at counter carefully selecting toppings. Foreground -
table with bottle fortress, slice inside, PIP sitting still. MUSIC CUTS TO SILENCE.
(22-27s) MED static: PIP RAISES HIS HAND. The waiter calmly walks over, picks up the slice, places it on a
fresh plate, and serves it to PIP. PIP takes a polite bite. The fortress is UNDISTURBED - the shared plate
inside is now EMPTY. CHIEF still at counter, oblivious.
(27-31s) MED-WIDE punch-in: CHIEF returns triumphantly with toppings plate. Sees fortress intact (smiles).
Looks INSIDE - EMPTY PLATE. Looks at PIP - calmly chewing last bite. CHIEF's toppings scatter off his
tilting plate. 0.5s freeze on contrast.
(31-32s) WIDE, framing identical to opening: bottle fortress still standing (useless). PIP dabs mouth with
napkin. CHIEF slumps. Waiter smiles in background. PIP waves. Last olive rolls off table. Hard cut.
ZERO on-screen text anywhere. CHIEF never loses cap/sash/medals. PIP never gloats - he is simply polite.
The BOTTLE FORTRESS IS NEVER KNOCKED OVER - it stands untouched the entire time. The twist is that CHIEF's
own overreach (leaving to get toppings) created the opportunity, and the simplest action (asking politely)
bypassed all his defenses. Advertiser-safe: food humor only, no aggression.
```

---

## D) Handoff / minimal-edit checklist
- [ ] **Rendered 9:16 / 1080x1920**, total ~32 s, on the locked 8-clip skeleton.
- [ ] Assemble C1->C8 with **hard cuts**; add no transitions.
- [ ] Insert the holds/freezes: C1 6-frame settle - C3 3-frame per item + 6-frame fortress complete - C6 4-frame slice-leaving + 4-frame empty plate - C7 **0.5 s contrast freeze**.
- [ ] **Verify Seed A:** the waiter is visible standing ready in C1, C2, C3, and serves in C6, and is smiling in C8.
- [ ] **Verify Seed B:** the topping bar is visible in C1 and is where CHIEF goes in C4-C5.
- [ ] **Verify the fortress NEVER falls or is disturbed.** It stands from C3 to C8, every bottle in place. This is essential.
- [ ] **Verify PIP's hand-raise** is the only significant action PIP performs - one clean 4-frame raise.
- [ ] Verify the trigger: CHIEF's own departure (overreach - wanting toppings) created the opening.
- [ ] Verify PIP **never touches the fortress** - the waiter picks up the slice normally from the plate.
- [ ] Confirm the **music cuts at 0:16 with no visual cut**, and only faint ambience remains through 0:27.
- [ ] Confirm the toppings scatter is visible and satisfying in C7 - small flat shapes cascading.
- [ ] Verify loop seam: overlay C8 on C1 - table, background, waiter position must match.
- [ ] Lay VO and BGM/SFX (file 03) onto the fixed timecodes.
- [ ] Final QC: no baked text, no blur/glow, cast on-model, food only, advertiser-safe, PIP polite and kind.
