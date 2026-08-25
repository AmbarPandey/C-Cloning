# v14 - Video-Generation Script / Prompt ("The Sand Castle") - **SHORTS 9:16**

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or equivalent). It specifies **motion, camera angles, transitions, cut timing,
> motion-graphics and on-screen FX per shot**, so the generated output needs **minimal editing** -
> ideally just top-and-tail + audio layup. Everything aligns to the master timeline in
> `01-video-script.md` and audio in `03-audio-bgm-sfx-reference.md`.

**Global render spec:** **1080x1920 (9:16 vertical)** - 30 fps - ~32 s (~960 frames) - flat-2D cartoon
house style (thick uniform black outlines, no gradients, chunky 2.5-head proportions) - snappy pose-to-pose
with strong holds - **hard cuts only** (no dissolves/fades) - **no camera rotation/orbit, no handheld** -
**no blur/glow/gradients** - loop seam (C8 == C1).

**Motion philosophy:** limited animation - hold poses on comedy beats, animate in short bursts. v14's
structure builds through **escalating construction** (the fortress grows, the moat deepens, the channels
extend) then delivers the collapse through CHIEF's own engineering funneling the tide directly into his
creation. The contrast is between CHIEF's frantic over-engineering and PIP's single tiny patient sculpture.

Two contrasting motion languages:
- **CHIEF:** increasingly manic building energy -- digging, sculpting, climbing, posing. After the flood begins: desperate plugging, blocking, scooping. All motion is large, sweeping, effortful.
- **PIP:** gentle, patient, small motions -- pat-pat-pat on tiny turtle. Almost static. Appears in C1, C2, C7, and C8 only. His stillness in C7 is the punchline.

> **The one rule that cannot break:** the **water/tide must advance monotonically** from C2 to C6.
> The waterline only creeps closer, the channels only fill more, and the fortress only gets wetter.
> Never let the water level reverse or recede until C8 (the final payoff recede).

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** - subject motion - camera - transitions/FX - cut.

### SHOT 1A - 0:00-0:015 - CU.EYE.STATIC  *(cold payoff - replaces the old wide establishing shot)*
- **Motion:** Close, low on the sand: a **moat channel running inward**, and seawater sprinting along it toward the fortress core — the channel doing its job perfectly and in the wrong direction. The first wall base darkens and slumps. Cut as it gives. The motion is **already at full speed on frame 1** - there is no entrance, no settle, no push-in from a wide, and no character walks into shot.
- **Camera:** locked tight CU. The subject fills the frame. **Zero settle time.** Frame 1 is mid-event.
- **Motion graphics/FX:** flat impact shapes only - no glow, no blur, no gradients. Palette tokens only.
- **Transition out:** hard cut on the beat, *before* the event resolves.

### SHOT 1B - 0:015-0:02 - MED.EYE.STATIC  *(goal diagram)*
- **Motion:** Hard cut to the beach: a **tide line** drawn as a dark wet arc across the sand with a `BRAND_YELLOW` arrow showing which way it is moving, the fortress wall built inside the arc, and a small sand turtle patted down safely outside it. PIP is in the same frame just outside the tide line, patting the last shell onto his little sand turtle — same beach, same sand, smaller ambition.
- **Camera:** locked medium-wide, held. **This exact framing returns in SHOT 8 for the loop seam.**
- **On-frame text:** **none baked into the render.** The 3-7 word hook caption *"His moat is pointing inward"* is an **edit-layer overlay**, placed clear of the bottom bar and the right-hand action rail.
- **Transition out:** hard cut.

### SHOT 2 - 0:02-0:06 - MED-WIDE.EYE.STATIC
- **Motion:** CHIEF grabs a flat shovel from the sand (2-frame grab) and starts building: scoop sand (3-frame), pile on wall (3-frame), pat down (2-frame) -- repeating cycle. He also digs a trench on the ocean side (3-frame scoop down, 3-frame toss aside). The trench slopes visibly downhill toward the waterline (the grade is clear in the cross-section). Behind the wall, PIP wipes sand grains off his `POP_TEAL` scarf (3-frame brush), blinks (2-frame), then returns to his mound: gentle pat-pat-pat on his sand lump (now slightly more turtle-shaped -- a dome with four tiny bumps emerging).
- **Camera:** medium-wide, static. The wall divides the frame: CHIEF and ocean on one side, PIP on the other. Both visible.
- **Motion graphics/FX:** Shovel is a flat `ASPHALT`-grey shape. Sand arcs are flat dot clusters. The trench/moat beginning is a darker stripe in the sand. A single gentle wave laps in the far background (flat white foam shape, 8-frame cycle).
- **Transition out:** hard cut.

### SHOT 3 - 0:06-0:11 - MED.EYE.STATIC
- **Motion:** CHIEF's wall is now at his shoulder height. He digs the moat deeper and wider. Three **channel arms** extend outward from the moat ring toward the ocean -- like fingers reaching for the waterline. CHIEF packs the channel walls smooth with his shovel (3-frame pat per wall section). He adds decorative turrets to the fortress top (3-frame sculpt per turret, 3 turrets total). Each gets a tiny `BRAND_YELLOW` flag (2-frame plant each). The waterline has crept ~2 feet closer (the foam line is now further up the beach than in C1/C2). PIP is NOT in frame.
- **Camera:** static medium, centered on CHIEF and his fortress. The bottom of frame clearly shows the channel slopes running toward the waterline. The water's closer position is visible but not emphasized.
- **Motion graphics/FX:** Three channel trenches are darker tan stripes extending from the moat ring toward the bottom of frame (toward ocean). Turrets are simple dome shapes with flag triangles. Foam line is closer to channel tips than before. Medal jingle indicated by 1-frame flash on medals.
- **Transition out:** hard cut.

### SHOT 4 - 0:11-0:16 - MED.EYE.PUSHIN(slow)
- **Motion:** The fortress is now massive -- shoulder-height walls, 3 turrets with flags, deep moat ring, three channel arms extending 4-5 feet seaward. CHIEF climbs ON TOP of the tallest turret (6-frame climb: hand-hand-foot-foot-stand-pose). The turret flexes slightly under his weight (2-frame wobble). He stands with arms spread wide, triumphant pose, medals forward. He looks inland (toward where PIP would be, gloating). In the bottom of frame: the waterline foam is now **inches** from the outermost channel tip. A thin glisten of water (flat `SKY`-blue line) connects the foam to the channel end. CHIEF does not see this.
- **Camera:** slow push-in (100% to 106%) ending on a split composition: CHIEF posing triumphantly in the top half, the water-meets-channel contact visible in the bottom third.
- **Motion graphics/FX:** Medals get a 1-frame `BRAND_YELLOW` glint at the peak of the pose. The turret wobble is a 2-pixel lateral shift. The thin water contact line is a subtle flat `SKY`-blue stroke connecting foam to channel entrance. Sand texture under CHIEF's feet shows slight compression cracks.
- **Transition out:** hard cut.

### SHOT 5 - 0:16-0:22 - MED.LOW-ANGLE.STATIC -> HOLD
- **Motion:** A wave rolls in (6-frame approach: flat white foam shape advancing). The leading edge flows directly into the first channel entrance (3-frame pour-in). Water runs smoothly down the channel slope toward the moat -- it accelerates as the grade helps it (indicated by the water front moving faster). CHIEF, still atop the turret, looks down (3-frame head-drop). His pose freezes. Expression crashes: triumph to horror (4-frame face transition). He scrambles down the turret side (8-frame scramble -- sand crumbles under his feet in 2-frame chunks falling). At the base, he shoves his gloved hands into the channel entrance (3-frame shove). Water flows between his fingers (flat blue-white lines parting around his hands).
- **Camera:** medium shot, slightly low angle showing CHIEF on the turret from below initially, then following his scramble down to ground level. Static hold once he's at the channel.
- **Motion graphics/FX:** Wave foam is flat white. Channel water is flat `SKY`-blue filling the darker trench shape progressively (like a loading bar, frame by frame). Sand crumbles are small `PAPER`-tan squares falling. Water between fingers is 3 flat lines diverging around hand shapes.
- **AUDIO CUE (critical):** music **cuts mid-phrase on the frame water enters the channel (0:16)**, leaving only ocean ambience and water flow sounds.
- **Transition out:** hard cut.

### SHOT 6 - 0:22-0:27 - MED.EYE.STATIC
- **Motion:** All three channels flowing simultaneously (flat `SKY`-blue fills advancing from three directions into the moat). Three panic attempts:
  - **Attempt 1 (0:22-0:23.5):** CHIEF scoops armfuls of dry sand (4-frame scoop) and dumps them into a channel entrance (3-frame dump). The sand dissolves instantly as water saturates it (3-frame: sand pile becomes flat wet patch). Water keeps flowing.
  - **Attempt 2 (0:23.5-0:25):** CHIEF sits bodily on the second channel entrance (4-frame sit-down, heavy). Water visibly diverts -- it backs up 1 frame, then accelerates through the third channel (4-frame acceleration). The moat water level is now visibly rising (flat `SKY`-blue level line moves up the moat walls).
  - **Attempt 3 (0:25-0:27):** CHIEF yanks off his cap (2-frame grab) and uses it to scoop water OUT of the moat (4-frame scoop, 3-frame toss -- water arc goes behind him). But the main tower walls are saturated -- they darken in color (2-frame color shift to darker tan) and lean inward (2-pixel lean per frame over 4 frames). A crack appears on the tallest turret (2-frame line appears).
- **Camera:** static medium. The moat water level rising is the key visual progression across this shot.
- **Motion graphics/FX:** Water fills are flat `SKY`-blue shapes. Dissolving sand is a 3-frame transition from `PAPER`-tan pile to flat wet `ASPHALT`-tan. Cap scoop water arc is a flat blue curve shape (3 frames). Wall darkening is a simple color shift. Cracks are `INK` lines appearing.
- **Transition out:** hard cut.

### SHOT 7 - 0:27-0:31 - MED.EYE.STATIC -> PULLBACK TO WIDE
- **Motion (beat 1, 0:27-0:29):** The tallest turret leans (4-frame lean), cracks propagate down the walls (2-frame per crack line), and the entire fortress **collapses inward** (8-frame crumble: shapes break into chunks, chunks settle into a mound). Wet sand piles around CHIEF, burying him to the waist (his upper body sticks out, arms splayed, expression frozen in shock). His `BRAND_YELLOW` flags topple and lie flat in the wet sand. His shovel sticks up from the debris at an angle.
- **Motion (beat 2, 0:29-0:31):** Camera pulls back to wide. REVEAL: On the raised mound (untouched by any water -- it is clearly above the flood line), PIP's tiny sand **turtle** is perfectly intact. It has a cute dome shell with hexagon pattern, four small flippers, and two dot eyes. PIP sits cross-legged beside it, pats one last grain into place (2-frame pat), then looks over at CHIEF and tilts his head (3-frame tilt).
- **Camera:** starts medium (on CHIEF and the collapse), then steady pull-back to wide (106% to 100%) revealing the full scene with PIP's mound on the right. 0.5 s (15-frame) hold on the final wide composition showing the contrast.
- **Motion graphics/FX:** Collapse is chunky flat shapes breaking apart and settling (no dust clouds, no blur). Wet sand is darker `PAPER`-tan. The turtle is a small detailed flat shape with `POP_TEAL` accents on its shell edges. The mound is clearly dry and elevated. A flat water stain line on the beach shows exactly where the flood reached -- below the mound.
- **AUDIO CUE:** music **SLAMS back** at 0:27 on the first lean frame; the wet collapse sound is the signature.
- **Transition out:** hard cut.

### SHOT 8 - 0:31-0:32 - WIDE.EYE.STATIC (== SHOT 1 composition)
- **Motion:** Composition matches C1 exactly. The wide beach framing: CHIEF half-buried in wet collapsed sand (where his fortress was), flags scattered flat, cap soggy and misshapen atop debris. PIP on his raised mound with the intact turtle beside him. PIP extends a hand toward CHIEF (4-frame arm extend -- offering to help). PIP turns to camera and gives a **small wave** (3-frame wave: hand up, wiggle, down). The tide gently recedes in the background (flat white foam line moving back 2 pixels over the hold).
- **Camera:** return to C1 wide framing. Hard cut out within 1 s after the wave -- loops seamlessly to C1 (the beach, the mound, the waterline position match C1's opening).
- **Motion graphics/FX:** PIP's wave is his signature -- same 3-frame cycle as all prior episodes. The receding tide is a subtle foam line retreat. No new FX on the final frame to keep loop clean.
- **Transition out:** hard cut, seam to C1 (viewer replays and notices the moat channels sloping toward the water, and PIP's higher-ground position).

---

## B) Transitions & cut map (quick reference)

| Between | Type | Notes |
|---|---|---|
| C1->C2 | hard cut | establishes both characters' strategies |
| C2->C3 | hard cut | to CHIEF-only escalation |
| C3->C4 | hard cut | fortress reaches peak, water contact |
| C4->C5 | hard cut | into the flood beginning |
| C5->C6 | hard cut | into panic attempts |
| C6->C7 | hard cut | into collapse and reveal |
| C7->C8 | hard cut | payoff pose, loop seam |
| C8->C1 | **loop seam** | last frame matches first frame composition |

---

## C) Character costume locks (must persist every frame)

| Character | Required elements | Notes |
|---|---|---|
| CHIEF | peaked cap, `POP_TEAL` jacket, `BRAND_YELLOW` sash with medals, white gloves | Cap gets soggy/misshapen in C7-C8 (but never disappears). Gloves get sandy. Sash stays on |
| PIP | `POP_TEAL` scarf | Gets sand grains in C1 (brushed off in C2). Otherwise clean throughout |

---

## D) Loop-seam frame check

| Element | Frame 1 (C1 start) | Frame 960 (C8 end) |
|---|---|---|
| Background | sunny beach, ocean, sky | identical |
| PIP position | on mound, kneeling | on mound, kneeling (offering hand variant) |
| CHIEF position | entering from left | half-buried (visual gag of contrast) |
| Waterline | background, gentle foam | background, gentle foam (receded to match) |
| Camera | wide, static | wide, static, same framing |

> The narrative loop: the viewer sees C1's beach and thinks "wait, the mound was higher all along"
> and "the moat channels were pointing at the ocean the whole time" -- rewatch trigger.
