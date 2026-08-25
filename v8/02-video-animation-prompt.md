# v8 - Video-Generation Script / Prompt ("The Smart Lock") - **SHORTS 9:16**

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or equivalent). It specifies **motion, camera angles, transitions, cut timing,
> motion-graphics and on-screen FX per shot**, so the generated output needs **minimal editing** -
> ideally just top-and-tail + audio layup. Everything aligns to the master timeline in
> `01-video-script.md` and audio in `03-audio-bgm-sfx-reference.md`.

**Global render spec:** **1080x1920 (9:16 vertical)** - 30 fps - ~32 s (~960 frames) - flat-2D cartoon
house style (thick uniform black outlines, no gradients, chunky 2.5-head proportions) - snappy pose-to-pose
with strong holds - **hard cuts only** (no dissolves/fades) - **no camera rotation/orbit, no handheld** -
**no blur/glow/gradients** - loop seam (C8 == C1).

**Motion philosophy:** limited animation - hold poses on comedy beats, animate in short bursts. v8's
structure builds tension through **repetition and escalation** (each lock demo is bigger/smugger) then
delivers the collapse through a simple, quiet action (a small key). Resist over-animating PIP - his
stillness is the contrast.

Two contrasting motion languages:
- **CHIEF:** big theatrical gestures, broad sweeping arms, exaggerated tech-demo poses, finger-wagging.
- **PIP:** nearly motionless throughout. Four actions total: pockets the key (C1), waits patiently (C2-C5), raises an eyebrow (C6), pulls out key and walks through (C7), holds gate open and waves (C8).

> **The one rule that cannot break:** the **backup key** must be visible in C1 (handed to PIP) and must
> reappear in C7 from PIP's scarf. The audience must be able to verify the fair-play contract on replay.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** - subject motion - camera - transitions/FX - cut.

### SHOT 1 - 0:00-0:02 - WIDE.EYE.STATIC
- **Motion:** A delivery driver (flat silhouette, no detail) hands CHIEF a shiny box (3-frame handoff). In the same motion, the driver's other hand extends a **tiny brass key** to PIP, who pockets it into his scarf in a quick 4-frame motion (easy to miss on first watch). CHIEF snatches the box eagerly in a 3-frame grab.
- **Camera:** locked wide. 6-frame settle hold so both seeds register - the key handoff and the cake on the table.
- **Motion graphics/FX:** a small `BRAND_YELLOW` sparkle on the box as CHIEF grabs it; the key has a single-frame metallic glint. The cake on the table has no emphasis - it reads as background.
- **Transition out:** hard cut.

### SHOT 2 - 0:02-0:06 - MED.EYE.PUSHIN(slow)
- **Motion:** CHIEF bolts the smart lock onto the gate in a 6-frame action (drill motion, sparks pop). He leans his face into the scanner (3-frame lean). The lock's screen flashes a **green checkmark** (2-frame pop with a small green circle burst). He spins 180 degrees (4-frame spin) and wags his finger at PIP through the gate bars (3-frame wag cycle x2).
- **Camera:** slow push-in (100% to 108% over 4 s), ending framed on the green checkmark and CHIEF's smug face together.
- **FX:** small flat sparks on bolt installation (3 white dashes); green circle burst on checkmark; `FX_sparkle_v1` on the lock casing.
- **Transition out:** hard cut.

### SHOT 3 - 0:06-0:11 - CLOSE-MED.EYE.STATIC
- **Motion:** CHIEF's gloved finger taps the lock screen (4 taps, each 3 frames). With each tap a new icon appears on-screen in the lock's display: fingerprint icon (pops in), retinal-scan icon (pops in), extended passcode bar (slides in), second face-scan badge (pops in). The lock glows brighter `BRAND_YELLOW` after each addition. CHIEF turns to PIP after each addition with a progressively bigger grin (4 head-turns, 3 frames each).
- **Camera:** static close-medium on the lock face; 3-frame hold on each new icon appearing.
- **Motion graphics/FX:** each icon pops in with a small radial burst (flat, 2-frame); the lock's glow intensifies in 4 stages (subtle flat yellow aura, no gradient, just a wider flat shape).
- **Transition out:** hard cut.

### SHOT 4 - 0:11-0:16 - WIDE.EYE.STATIC -> PUSHIN(slight)
- **Motion:** CHIEF walks through the gate (green beep flash on lock, 2-frame), does a 4-frame celebratory arm-raise on the other side, walks back through (green beep flash, 2-frame), does a little 6-frame victory strut with chest out. The cake is clearly visible on its table each time he passes it.
- **Camera:** static wide for the first pass; slight push-in (100% to 103%) on the second pass, framing CHIEF and the cake together in the final hold.
- **Motion graphics/FX:** two green circle bursts (one per pass); `FX_motionlines_v1` on the strut; the cake has no emphasis.
- **Transition out:** hard cut.

### SHOT 5 - 0:16-0:22 - MED.LOW.PUSHIN -> HOLD
- **Motion:** CHIEF spots the cake (2-frame head-turn), grabs it with both gloves (3-frame reach), and takes an enormous bite (4-frame chomp with exaggerated jaw). **Thick white icing smears across his entire face** in a 3-frame splat - nose, both cheeks, forehead, over one eye, dripping off his chin. He doesn't notice; he holds a triumphant pose with one fist raised (held for ~1.5 s).
- **Camera:** medium shot, slight low angle (hero-angle), gentle push-in settling into a hold. The icing on his face dominates the frame.
- **Motion graphics/FX:** flat white icing shapes smearing across his face (hard-edged, no transparency); a single `FX_sparkle_v1` self-satisfaction accent around his fist. One icing drip (a white flat teardrop) slowly descends from his chin during the hold.
- **AUDIO CUE (critical):** music **CUTS TO SILENCE on the frame of the bite (0:16)**, leaving the squishy chomp exposed.
- **Transition out:** hard cut.

### SHOT 6 - 0:22-0:27 - MED.EYE.STATIC
- **Motion:** CHIEF struts to the gate (4-frame walk) and leans into the scanner (3-frame lean). The screen flashes **RED X** (2-frame pop with red burst). He startles (3-frame recoil). He wipes his face with one glove (4-frame wipe, smearing icing further). Leans in again - **RED X** (2-frame). More frantic wiping (6-frame frantic motion). Third lean - **RED X** (2-frame). His shoulders slump (4-frame deflation). PIP raises one eyebrow (2-frame).
- **Camera:** static two-shot (CHIEF at lock on left, PIP behind gate on right); 3-frame hold on each RED X.
- **Motion graphics/FX:** three flat red circle bursts (one per rejection); icing smear getting worse with each wipe (white shapes spreading). No sparkle - restraint carries the dread.
- **Transition out:** hard cut.

### SHOT 7 - 0:27-0:31 - MED.EYE.PUNCHIN -> SETTLE
- **Motion (beat 1, 0:27-0:29):** PIP reaches into his `POP_TEAL` scarf (3-frame reach) and pulls out the **tiny brass key** (2-frame reveal - key catches a metallic glint). He inserts it into a small manual keyhole on the lock's underside (4-frame insert). A simple mechanical **click** and the gate swings open (6-frame swing).
- **Motion (beat 2, 0:29-0:31):** PIP walks through calmly, hands behind his back (8-frame walk). CHIEF's jaw drops (3-frame snap down). Icing still covering his face. The lock's screen still shows RED X. PIP's expression shifts subtly from calm to gleeful (4-frame transition).
- **Camera:** quick punch-in on the key entering the lock (~6 frames), then settle back to wide; **0.5 s freeze on PIP walking through with CHIEF frozen in disbelief** (the screenshot-able punchline).
- **Motion graphics/FX:** metallic glint on the key (single-frame); a small `BRAND_YELLOW` circle burst on the manual keyhole as the gate opens; `FX_impact_star_v1` on the click. No sparkle on PIP.
- **AUDIO CUE:** music **SLAMS back** at 0:27 on the key reveal; the mechanical **click at 0:29 is crisp and satisfying** (file 03).
- **Transition out:** hard cut.

### SHOT 8 - 0:31-0:32 - WIDE.EYE.STATIC (== SHOT 1)
- **Motion:** PIP stands on the far side, holding the gate open politely (one arm extended, 4-frame settle). CHIEF shuffles through, hunched and mortified (6-frame shuffle), icing still all over his face. PIP turns and gives a small wave to camera (3-frame wave). One last icing drip falls off CHIEF's nose (4-frame fall).
- **Camera:** return to the **exact SHOT-1 framing** - same background plate, same gate, same table (now with cake missing). Only CHIEF's icing-covered state and the open gate differ.
- **Motion graphics/FX:** one white flat teardrop (icing drip) falling off his nose; no sparkle on PIP; no residual FX on the final frame (loop must be clean).
- **Transition out:** **hard cut** <=1 s after the wave, seaming back to SHOT 1.

---

## B) Transitions & cut map (quick reference)
| Between | Type | Notes |
|---|---|---|
| C1->C2->C3->C4 | hard cut | snappy 2-5 s clips |
| C4->C5 | hard cut | into the celebration bite |
| **C5 internal (0:16)** | **music cut only - no visual change** | pattern break by removing the score |
| C5->C6 | hard cut | to the rejection sequence |
| C6->C7 | hard cut into **punch-in** | the twist |
| **C7 internal (0:29)** | 0.5 s freeze | PIP walking through / CHIEF in disbelief |
| C7->C8 | hard cut | payoff |
| C8->(loop) | hard cut, seam to C1 | replay re-reads the key handoff and the cake |

**No** dissolves, fades, wipes, glitch, zoom-blur, or camera rotation anywhere. Effects are limited to:
flat sparks, flat circle bursts (green/red), flat icing shapes, metallic glints, motion lines, sparkle,
impact-star, and the listed holds/freezes.

---

## C) Optional single "master prompt" (for one-shot generators)
```
{style: flat-color 2D cartoon, thick uniform black outlines, no gradients, chunky 2.5-head proportions,
palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076, ALERT_RED
#E4322B, POP_TEAL #2FB6A3 - 9:16 VERTICAL}
A ~32s 9:16 flat-2D cartoon comedy short, 30fps, hard cuts only, no camera rotation, no blur or glow.
Recurring cast: CHIEF, a pompous rotund braggart in a teal jacket with an oversized peaked cap and a yellow
medal sash, white gloves; PIP, a tiny underdog with a teal scarf. Setting: a PAPER-coloured garden with a
simple ASPHALT gate, a small table with a round celebration cake with thick white icing.
Story in 8 beats:
(0-2s) WIDE static: a delivery driver hands CHIEF a shiny smart-lock box; in the same motion hands PIP a
TINY BRASS BACKUP KEY which PIP quickly pockets into his scarf. Cake visible on table.
(2-6s) MED slow push-in: CHIEF bolts the BRAND_YELLOW smart lock onto the gate, scans his face - GREEN
CHECKMARK - and wags his finger smugly at PIP through the bars.
(6-11s) CLOSE-MED static: CHIEF taps the lock screen 4 times, each adding a new security icon (fingerprint,
retinal, passcode, second face-scan). Lock glows brighter each time. He turns to PIP with bigger grins.
(11-16s) WIDE: CHIEF walks through the gate twice (green beep each time), doing a victory strut. The cake is
visible on its table each time he passes it.
(16-22s) MED low angle: CHIEF grabs the cake and takes an ENORMOUS BITE - thick white icing SMEARS across
his ENTIRE FACE (nose, cheeks, forehead, over one eye). He doesn't notice; holds a triumphant fist-raised
pose. MUSIC CUTS TO SILENCE.
(22-27s) MED static two-shot: CHIEF struts to gate, leans into scanner - RED X. Wipes face (smears icing
further) - tries again RED X. Frantic wiping - RED X. Locked out of his own gate. PIP raises an eyebrow.
(27-31s) MED punch-in: PIP reaches into his scarf, pulls out the TINY BRASS KEY, inserts it into a small
manual keyhole on the lock's underside - CLICK - gate swings open. PIP walks through calmly. CHIEF's jaw
drops, icing still on face. 0.5s freeze on the contrast.
(31-32s) WIDE, framing identical to opening: PIP holds gate open politely; CHIEF shuffles through,
mortified, icing on face. PIP waves to camera. One last icing drip off CHIEF's nose. Hard cut.
ZERO on-screen text anywhere. CHIEF never loses cap/sash/medals (icing-covered is fine). PIP never gloats.
The twist is CHIEF's own overreach (face-only lock + celebration cake icing). Advertiser-safe: CHIEF is
merely embarrassed with cake on his face - no injury or danger.
```

---

## D) Handoff / minimal-edit checklist
- [ ] **Rendered 9:16 / 1080x1920**, total ~32 s, on the locked 8-clip skeleton.
- [ ] Assemble C1->C8 with **hard cuts**; add no transitions.
- [ ] Insert the holds/freezes: C1 6-frame settle - C3 3-frame per icon - C5 ~1.5 s victory hold - C6 3-frame per RED X - C7 **0.5 s contrast freeze**.
- [ ] **Verify Seed A:** the tiny brass key is visible being handed to PIP in C1 and reappears from his scarf in C7.
- [ ] **Verify Seed B:** the celebration cake is visible in C1, C4, and consumed in C5.
- [ ] **Verify the trigger:** the lockout is caused by CHIEF's own icing-smeared face (his celebration) on his own over-engineered lock - no external sabotage.
- [ ] Verify PIP is **patient and kind** throughout - never locked out by force, never gloats, holds the gate open.
- [ ] Confirm the **music cuts at 0:16 with no visual cut**, and only ambient lock hum remains through 0:27.
- [ ] Confirm the **C7 mechanical click** is the most satisfying sound - crisp and simple vs. all the rejected digital beeps.
- [ ] Verify loop seam: overlay C8 on C1 - background plate, framing, gate position must match.
- [ ] Lay VO (if used) and BGM/SFX (file 03) onto the fixed timecodes - everything is pre-synced.
- [ ] Final QC: no baked text, no blur/glow, all icing is flat hard-edged white shapes, cast on-model, CHIEF has icing but is unharmed, advertiser-safe.
