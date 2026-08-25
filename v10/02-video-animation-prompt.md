# v10 - Video-Generation Script / Prompt ("The Printer") - **SHORTS 9:16**

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or equivalent). It specifies **motion, camera angles, transitions, cut timing,
> motion-graphics and on-screen FX per shot**, so the generated output needs **minimal editing** -
> ideally just top-and-tail + audio layup. Everything aligns to the master timeline in
> `01-video-script.md` and audio in `03-audio-bgm-sfx-reference.md`.

**Global render spec:** **1080x1920 (9:16 vertical)** - 30 fps - ~32 s (~960 frames) - flat-2D cartoon
house style (thick uniform black outlines, no gradients, chunky 2.5-head proportions) - snappy pose-to-pose
with strong holds - **hard cuts only** (no dissolves/fades) - **no camera rotation/orbit, no handheld** -
**no blur/glow/gradients** - loop seam (C8 == C1).

**Motion philosophy:** limited animation - hold poses on comedy beats, animate in short bursts. v10's
structure builds tension through **accumulation** (each printed page adds to the overload) then delivers
the collapse through a mechanical inevitability (overheat, jam, reset). Resist over-animating PIP - his
stillness is the contrast.

Two contrasting motion languages:
- **CHIEF:** big theatrical gestures, aggressive paper-loading, triumphant posing with pages, frantic pulling and slapping at jammed printer.
- **PIP:** nearly motionless throughout. Four actions total: slips sheet into bypass tray (C1), waits patiently (C2-C5), raises an eyebrow (C6), picks up his page and walks away (C7-C8), waves (C8).

> **The one rule that cannot break:** the **bypass tray** must be visible in C1 (PIP slips his sheet in)
> and must be the source of PIP's printed page in C7. The audience must be able to verify the fair-play
> contract on replay.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** - subject motion - camera - transitions/FX - cut.

### SHOT 1 - 0:00-0:02 - WIDE.EYE.STATIC
- **Motion:** CHIEF shoves PIP aside (3-frame shove, PIP stumbles 2-frame) and slams an enormous tower of blank paper into the printer's main tray (4-frame slam). While CHIEF gloats at his stack, PIP quietly reaches to the printer's side and slips **a single sheet into the small bypass tray** in a quick 3-frame motion (easy to miss). The printer's screen glows `BRAND_YELLOW`.
- **Camera:** locked wide. 6-frame settle hold so both seeds register - the bypass tray sheet and the printer's eager screen.
- **Motion graphics/FX:** a small `BRAND_YELLOW` glow on the printer screen; a tiny paper edge visible in the bypass tray. The paper tower dominates the frame (no emphasis on the bypass tray).
- **Transition out:** hard cut.

### SHOT 2 - 0:02-0:06 - MED.EYE.PUSHIN(slow)
- **Motion:** CHIEF jabs the copy-count button rapidly (6-frame jabbing cycle). The screen counter climbs: "001" -> "050" -> "100" -> "500" -> **"999"** (each number pops for 3 frames). He slams the green PRINT button (2-frame slam). The printer whirs to life (screen shows spinning icon). He turns 180 degrees (4-frame spin) and wags his finger at PIP (3-frame wag cycle x2).
- **Camera:** slow push-in (100% to 108% over 4 s), ending framed on the "999" counter and CHIEF's smug face together.
- **FX:** counter numbers pop in with small flat bursts; green button press has a small `BRAND_YELLOW` circle burst; printer screen shows a spinning progress icon.
- **Transition out:** hard cut.

### SHOT 3 - 0:06-0:11 - CLOSE-MED.EYE.STATIC
- **Motion:** Pages fly out of the printer's output slot rapidly (5 bursts, 3 frames each). Each page shows CHIEF's face with decorative frame. CHIEF catches them with both hands (4-frame catch), fans them out (3-frame fan), holds one next to his real face for comparison (4-frame pose), then tucks them under his arm for more.
- **Camera:** static close-medium on the printer output; 3-frame hold between each burst of pages.
- **Motion graphics/FX:** pages have flat motion lines as they shoot out; small `FX_motionlines_v1` on the rapid printing. No sparkle on PIP.
- **Transition out:** hard cut.

### SHOT 4 - 0:11-0:16 - WIDE.EYE.STATIC -> PUSHIN(slight)
- **Motion:** Wide shot reveals CHIEF knee-deep in printed pages covering the floor. He stands triumphant, arms spread (6-frame pose). Behind him, the printer's glow shifts from `BRAND_YELLOW` to `ALERT_RED` at edges (4-frame color transition). A flat wavy heat-shimmer appears above the machine (2 flat wavy lines oscillating, 4-frame cycle). PIP tilts his head (2-frame tilt).
- **Camera:** static wide for the first half; slight push-in (100% to 103%) framing CHIEF on his paper mountain with the overheating printer behind.
- **Motion graphics/FX:** flat `ALERT_RED` glow edge on printer; two flat wavy heat lines above it (no gradient/blur); paper pile is static once placed.
- **Transition out:** hard cut.

### SHOT 5 - 0:16-0:22 - MED.LOW.STATIC -> HOLD
- **Motion:** The printer screen flashes a **red thermometer icon** (2-frame pop). The machine shudders (3-frame shake cycle x3, intensity increasing). A loud **CLUNK** at 0:17 - total stoppage. The printer goes dark (2-frame fade to dark). Then a single `ALERT_RED` light begins blinking (2-frame on, 8-frame off cycle). Pages are frozen mid-feed, crumpled in the rollers. CHIEF's expression crashes from triumph to horror (4-frame transition). His paper tower around his feet collapses slightly.
- **Camera:** medium shot, slight low angle. The dead printer and CHIEF's fallen expression share the frame. Static hold on the blinking red light.
- **Motion graphics/FX:** flat red thermometer icon pop; shake uses simple position offset (no blur); the blinking red light is a flat circle toggling on/off. One or two flat paper sheets slide off the pile (gravity fall, 6-frame).
- **AUDIO CUE (critical):** music **CUTS TO SILENCE on the frame of the CLUNK (0:17)**, leaving the mechanical death exposed.
- **Transition out:** hard cut.

### SHOT 6 - 0:22-0:27 - MED.EYE.STATIC
- **Motion:** CHIEF yanks at jammed paper (4-frame pull) - it **rips** (2-frame snap, paper tears). He opens three access panels on the printer (each 3-frame flip). He pulls out crumpled wads (4-frame pulls x3). He slaps the printer with an open palm (3-frame slap) - the red light keeps blinking. The **bypass tray** on the printer's side remains untouched and visible but unemphasized throughout. PIP raises one eyebrow (2-frame).
- **Camera:** static two-shot (CHIEF at printer on left, PIP standing back on right); 3-frame hold on each failed fix attempt.
- **Motion graphics/FX:** torn paper has flat white confetti bits; panels flip open with small hinge motion. No sparkle - restraint carries the dread. The bypass tray has no highlight (it is just there, waiting).
- **Transition out:** hard cut.

### SHOT 7 - 0:27-0:31 - MED.EYE.PUNCHIN -> SETTLE
- **Motion (beat 1, 0:27-0:29):** The printer suddenly **reboots** - screen flashes white (2-frame), then `BRAND_YELLOW` (2-frame), startup animation plays. The main tray is visibly empty. The **bypass tray** whirs (3-frame vibration) and feeds PIP's single sheet through the rollers (6-frame feed). One perfect page slides into the output tray (4-frame slide). The screen shows "QUEUE: 0".
- **Motion (beat 2, 0:29-0:31):** PIP steps forward (4-frame walk), picks up his single page (3-frame reach and lift), holds it neatly. CHIEF's jaw drops (3-frame snap down). He looks at the screen ("QUEUE: 0"), then at PIP's page, then at his mountain of crumpled paper. PIP's expression shifts subtly from calm to gleeful (4-frame transition).
- **Camera:** quick punch-in on the bypass tray feeding the sheet (~6 frames), then settle back to wide; **0.5 s freeze on PIP holding his page with CHIEF surrounded by paper carnage** (the screenshot-able punchline).
- **Motion graphics/FX:** `BRAND_YELLOW` startup glow on screen; a clean single-page motion with no confetti; `FX_impact_star_v1` on the output *ding*. No sparkle on PIP.
- **AUDIO CUE:** music **SLAMS back** at 0:27 on the reboot chime; the clean page *shk* at 0:28 is crisp and satisfying (file 03).
- **Transition out:** hard cut.

### SHOT 8 - 0:31-0:32 - WIDE.EYE.STATIC (== SHOT 1)
- **Motion:** PIP walks away with his single page, neat and tidy (4-frame walk). CHIEF sits slumped, surrounded by crumpled paper mountain, holding a torn shred (static pose). One last crumpled page falls off the pile onto CHIEF's head (6-frame fall). PIP turns and waves to camera (3-frame wave). The printer screen shows a happy idle smiley icon.
- **Camera:** return to the **exact SHOT-1 framing** - same background plate, same desk, same printer. Only the paper carnage and CHIEF's defeated posture differ.
- **Motion graphics/FX:** one flat paper shape falling onto CHIEF's head; printer screen shows flat smiley; no residual FX on the final frame (loop must be clean).
- **Transition out:** **hard cut** <=1 s after the wave, seaming back to SHOT 1.

---

## B) Transitions & cut map (quick reference)
| Between | Type | Notes |
|---|---|---|
| C1->C2->C3->C4 | hard cut | snappy 2-5 s clips |
| C4->C5 | hard cut | into the overheat/jam |
| **C5 internal (0:17)** | **music cut only - no visual change** | pattern break by removing the score on the CLUNK |
| C5->C6 | hard cut | to the desperate fix attempts |
| C6->C7 | hard cut into **punch-in** | the twist |
| **C7 internal (0:29)** | 0.5 s freeze | PIP holding his page / CHIEF in paper carnage |
| C7->C8 | hard cut | payoff |
| C8->(loop) | hard cut, seam to C1 | replay re-reads the bypass tray sheet |

**No** dissolves, fades, wipes, glitch, zoom-blur, or camera rotation anywhere. Effects are limited to:
flat motion lines, flat circle bursts, flat color glow (BRAND_YELLOW/ALERT_RED), heat-shimmer (flat wavy
lines), blinking light, impact-star, paper confetti, and the listed holds/freezes.

---

## C) Optional single "master prompt" (for one-shot generators)
```
{style: flat-color 2D cartoon, thick uniform black outlines, no gradients, chunky 2.5-head proportions,
palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076, ALERT_RED
#E4322B, POP_TEAL #2FB6A3 - 9:16 VERTICAL}
A ~32s 9:16 flat-2D cartoon comedy short, 30fps, hard cuts only, no camera rotation, no blur or glow.
Recurring cast: CHIEF, a pompous rotund braggart in a teal jacket with an oversized peaked cap and a yellow
medal sash, white gloves; PIP, a tiny underdog with a teal scarf. Setting: a tiny PAPER-coloured office
with one printer on a desk.
Story in 8 beats:
(0-2s) WIDE static: CHIEF shoves PIP aside and slams a comically tall tower of blank paper into the
printer's main tray. While CHIEF gloats, PIP quietly slips A SINGLE SHEET into the small BYPASS TRAY
on the printer's side (easy to miss).
(2-6s) MED slow push-in: CHIEF jabs the copy-count button - counter climbs to 999. He slams PRINT.
Printer whirs. He wags his finger smugly at PIP.
(6-11s) CLOSE-MED static: Pages fly out rapidly - all showing CHIEF's face "EMPLOYEE OF THE MONTH". He
catches and fans them, posing with his own printed face. PIP waits.
(11-16s) WIDE: CHIEF knee-deep in printed pages. Printer glow shifts from BRAND_YELLOW to ALERT_RED at
edges. Heat shimmer above machine. PIP tilts head.
(16-22s) MED low angle: Printer screen flashes RED THERMOMETER. Machine shudders. LOUD CLUNK - total
paper jam. Printer goes dark, single ALERT_RED blinking light. CHIEF's triumph collapses to horror.
MUSIC CUTS TO SILENCE.
(22-27s) MED static two-shot: CHIEF yanks jammed paper (rips it), opens panels, pulls crumpled wads,
slaps printer in desperation. Red light keeps blinking. Bypass tray sits untouched on side. PIP raises
eyebrow.
(27-31s) MED punch-in: Printer REBOOTS (screen flashes, hums alive). Main tray empty. Bypass tray whirs -
PIP's SINGLE SHEET feeds through cleanly. Screen shows "QUEUE: 0". PIP picks up his page, smiles.
CHIEF jaw drops, surrounded by paper carnage. 0.5s freeze on the contrast.
(31-32s) WIDE, framing identical to opening: PIP walks away with his neat page. CHIEF slumps in paper
mountain, holding torn shred. One last page falls on his head. PIP waves. Printer screen shows smiley.
Hard cut.
ZERO overlaid on-screen text. CHIEF never loses cap/sash/medals. PIP never gloats. The twist is CHIEF's
own overreach (999 copies overheat the printer, reset clears his queue, PIP's pre-loaded bypass tray job
prints). Advertiser-safe: CHIEF is merely surrounded by paper and embarrassed - no injury or danger.
```

---

## D) Handoff / minimal-edit checklist
- [ ] **Rendered 9:16 / 1080x1920**, total ~32 s, on the locked 8-clip skeleton.
- [ ] Assemble C1->C8 with **hard cuts**; add no transitions.
- [ ] Insert the holds/freezes: C1 6-frame settle - C3 3-frame between bursts - C5 blinking red hold - C6 3-frame per attempt - C7 **0.5 s contrast freeze**.
- [ ] **Verify Seed A:** the bypass tray with PIP's single sheet is visible in C1 and is the source of his printed page in C7.
- [ ] **Verify Seed B:** the "999" counter is visible in C2 and makes the overheat inevitable.
- [ ] **Verify the trigger:** the jam/reset is caused by CHIEF's own absurd 999-copy job overheating the printer - no external sabotage.
- [ ] Verify PIP is **patient and kind** throughout - never aggressive, never gloats, simply picks up his page.
- [ ] Confirm the **music cuts at ~0:17 with no visual cut**, and only the blinking light and mechanical sounds remain through 0:27.
- [ ] Confirm the **C7 reboot chime and clean page sound** are the most satisfying sounds - warm startup vs. all the harsh jams and rips.
- [ ] Verify loop seam: overlay C8 on C1 - background plate, framing, desk and printer position must match.
- [ ] Lay VO (if used) and BGM/SFX (file 03) onto the fixed timecodes - everything is pre-synced.
- [ ] Final QC: no overlaid text, no blur/glow, all paper is flat shapes, cast on-model, CHIEF merely embarrassed and paper-covered, advertiser-safe.
