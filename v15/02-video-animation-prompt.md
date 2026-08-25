# v15 - Video-Generation Script / Prompt ("The Last Dryer") - **SHORTS 9:16**

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or equivalent). It specifies **motion, camera angles, transitions, cut timing,
> motion-graphics and on-screen FX per shot**, so the generated output needs **minimal editing** -
> ideally just top-and-tail + audio layup. Everything aligns to the master timeline in
> `01-video-script.md` and audio in `03-audio-bgm-sfx-reference.md`.

**Global render spec:** **1080x1920 (9:16 vertical)** - 30 fps - ~32 s (~960 frames) - flat-2D cartoon
house style (thick uniform black outlines, no gradients, chunky 2.5-head proportions) - snappy pose-to-pose
with strong holds - **hard cuts only** (no dissolves/fades) - **no camera rotation/orbit, no handheld** -
**no blur/glow/gradients** - loop seam (C8 == C1).

**Motion philosophy:** limited animation - hold poses on comedy beats, animate in short bursts. v15's
structure builds through **mechanical overload** (dryers shaking progressively harder, gauges climbing,
machines walking) then delivers a chain-reaction eruption. The contrast is between CHIEF's excess
(five machines, all overstuffed) and PIP's minimalism (one shirt, one warm pipe).

Two contrasting motion languages:
- **CHIEF:** confident, possessive, then frantic. Early: arm-cross, chest-puff, medal-polish. After the first pop: flailing, grabbing, clawing at static-stuck fabric. All motion is exaggerated and effortful.
- **PIP:** appears in C1 (shoved), C2 (hangs shirt, sits), C7 (removes shirt, folds), and C8 (offers dryer sheet, waves). Minimal motion. Folding is precise and meditative. His calm in C7 is the punchline.

> **The one rule that cannot break:** the **dryer overload must escalate monotonically** from C3 to C6.
> Vibration only increases, gauges only climb, and machines only get worse. No dryer calms down or
> resets before its eruption. Each eruption must be visually bigger than the previous one.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** - subject motion - camera - transitions/FX - cut.

### SHOT 1A - 0:00-0:015 - CU.EYE.STATIC  *(cold payoff - replaces the old wide establishing shot)*
- **Motion:** Close on a row of dryer doors **bursting open in sequence**, one-two-three-four-five, each one flinging a tangled knot of laundry out into the room — a sock arriving flat against the lens. Machines still rocking. Cut on the fifth door. The motion is **already at full speed on frame 1** - there is no entrance, no settle, no push-in from a wide, and no character walks into shot.
- **Camera:** locked tight CU. The subject fills the frame. **Zero settle time.** Frame 1 is mid-event.
- **Motion graphics/FX:** flat impact shapes only - no glow, no blur, no gradients. Palette tokens only.
- **Transition out:** hard cut on the beat, *before* the event resolves.

### SHOT 1B - 0:015-0:02 - MED.EYE.STATIC  *(goal diagram)*
- **Motion:** Hard cut to the laundromat: a **fill line** printed inside an open drum with a `BRAND_YELLOW` arrow at it, and the drum stuffed far past it. On the wall behind, a single warm radiator pipe with one small shirt hanging on it. PIP is in frame at the radiator pipe, smoothing his one small shirt flat on it — same laundry problem, no machine.
- **Camera:** locked medium-wide, held. **This exact framing returns in SHOT 8 for the loop seam.**
- **On-frame text:** **none baked into the render.** The 3-7 word hook caption *"All five, past the line"* is an **edit-layer overlay**, placed clear of the bottom bar and the right-hand action rail.
- **Transition out:** hard cut.

### SHOT 2 - 0:02-0:06 - MED-WIDE.EYE.STATIC
- **Motion:** All five dryers tumbling (round windows show fabric masses rotating -- 8-frame rotation cycle per window). CHIEF walks along the row left-to-right, patting each door with his glove (2-frame pat per door, 5 pats total). He dusts his gloves together (3-frame clap). PIP, holding his single wet shirt (dripping 2 flat drops), looks at the row of taken dryers (2-frame look left, hold, look right), then turns to see the radiator pipe (3-frame head turn). He walks to the pipe (4-frame walk), reaches up and drapes the shirt over it carefully (4-frame drape, smoothing flat). A tiny `PAPER`-white steam wisp rises (3-frame fade-in, 6-frame oscillation loop). PIP sits in the chair (3-frame sit), crosses legs (2-frame), and relaxes (settle hold).
- **Camera:** medium-wide, static. Left half: dryer row and CHIEF. Right half: PIP, pipe, chair.
- **Motion graphics/FX:** Dryer windows show rotating mass (simplified: a flat colored circle rotating inside each window). The steam wisp is a single flat wavy white line rising from the shirt-pipe junction. Water drops from shirt are 2 flat `SKY`-blue dots that fall and disappear.
- **Transition out:** hard cut.

### SHOT 3 - 0:06-0:11 - MED.EYE.STATIC
- **Motion:** CHIEF center-frame, arms crossed, chest puffed. The five dryers behind him are tumbling. Dryer #1 (leftmost) starts a visible **side-to-side wobble** (2-pixel X-offset oscillation, 4-frame cycle -- faster than the others). Its temperature gauge (a small semicircular dial above the coin slot) shows the needle moving: center (green) toward 2 o'clock (yellow). The dial is small but the movement is clear (3-frame needle tick). Through dryer #1's round window: the clothes inside are so packed they form ONE SOLID MASS rotating slowly -- a single blob that barely moves (4-frame rotation vs. the normal 8-frame in other dryers). CHIEF polishes a medal with his glove finger (6-frame polish cycle), oblivious.
- **Camera:** static medium. CHIEF in foreground, dryer row behind. The wobble on #1 and the gauge are visible background details (dramatic irony for attentive viewers).
- **Motion graphics/FX:** The wobble is a simple X-position oscillation on dryer #1's body (2-pixel, 4-frame). The gauge needle is a thin `INK` line rotating on the dial arc. The solid clothing mass is a single flat colored shape rotating slowly inside the round window. Medal polish: 1-frame `BRAND_YELLOW` glint.
- **Transition out:** hard cut.

### SHOT 4 - 0:11-0:16 - MED.EYE.PUSHIN(slow)
- **Motion:** ALL five dryers now wobble (4-frame oscillation, each slightly out of phase -- a ripple effect). Gauges on #1 and #2: needles in yellow/orange zone. Gauges on #3-#5: needles creeping from green to yellow. **Dryer #3** starts **walking forward** -- its vibration is so intense it inches away from the wall (1 pixel per 4 frames, total 4 pixels across the shot). A dark gap appears behind it. Faint wavy `ASPHALT`-grey heat/smell lines (2 flat wavy lines, 6-frame oscillation) rise from the top vents of #1 and #2. CHIEF notices #3 out of line (2-frame head-turn, 2-frame frown). He walks over (3-frame), pushes it back with one palm (3-frame push, the machine resists -- it slides back but keeps shaking). He returns to pose (4-frame walk back, arms cross). **The instant his arms cross:** #3 inches forward again AND #4 begins walking too (simultaneous, 1 frame after arms-cross).
- **Camera:** slow push-in (100% to 106%) ending tight on the gauges in the climax frame.
- **Motion graphics/FX:** The walking motion is X/Y position shift toward camera. The heat lines are flat `ASPHALT` wavy strokes. Gauge needles are animated thin `INK` lines on semicircle dials. The gap behind #3 is a flat dark `INK` rectangle.
- **Transition out:** hard cut.

### SHOT 5 - 0:16-0:22 - MED.EYE.STATIC -> HOLD
- **Motion:** Dryer #1's gauge needle hits the `ALERT_RED` zone (2-frame snap to far right). The machine shakes violently (4-pixel oscillation, 2-frame cycle -- twice as fast and big as before). A high-pitched whine is implied (no visual indicator needed -- audio carries it). CHIEF turns to look (3-frame head turn). The dryer door **pops open** (2-frame: latch snaps, door swings 90 degrees outward). A single sock launches in a flat arc trajectory (6-frame flight path) and sticks to CHIEF's face (2-frame stick -- the sock conforms to his face shape and stays). Static crackle lines (3 small zigzag `BRAND_YELLOW` lines) appear around the sock-face contact.
  CHIEF stands frozen (8-frame hold). He reaches up (3-frame) and slowly peels the sock off (6-frame peel -- the sock stretches/resists before releasing with a static snap). He holds the sock at arm's length and looks at it (2-frame hold). Then he turns his head to look at dryers #2-#5 (3-frame pan) -- all shaking violently, all gauges climbing. His expression crashes: confident to horrified (4-frame face transition: eyes widen, mouth drops).
- **Camera:** medium shot, static. CHIEF centered. Dryer #1 (door popping) on his left side of frame.
- **Motion graphics/FX:** The door pop is a 2-frame rotation. Sock trajectory is an arc path (the sock is a flat C-shape). Static lines are flat `BRAND_YELLOW` zigzags (3 small, 2-frame flash). The peel uses 2-frame stretch frames showing sock elongating before snapping free.
- **AUDIO CUE (critical):** music **cuts mid-phrase on the door BANG (0:16)**, leaving only the other dryers' rattle and static crackle.
- **Transition out:** hard cut.

### SHOT 6 - 0:22-0:27 - MED-WIDE.EYE.STATIC
- **Motion:** Sequential eruptions (each bigger than the last):
  - **Eruption 2 (0:22-0:23.5):** Dryer #2 door pops (2-frame). Three tangled shirts launch out (4-frame arc paths, diverging). Two drape over CHIEF's head and shoulders (2-frame drape). One sticks to his back (static lines flash). CHIEF stumbles backward blind (he can't see through the shirt over his face, 4-frame stumble, arms outstretched).
  - **Eruption 3 (0:23.5-0:25):** Dryer #3 pops (2-frame). Two pants and underwear launch (4-frame arcs, wider trajectories). One pair of pants sticks to the side wall (static cling -- 2-frame stick). Underwear arcs high and lands on CHIEF's cap (2-frame land). CHIEF claws the shirt off his face (4-frame claw) only for the #3 pants to wrap around his legs (3-frame wrap-around).
  - **Eruption 4+5 (0:25-0:27):** Dryers #4 and #5 pop simultaneously (2-frame, both). A BLIZZARD: 10+ fabric items launch in all directions (various arc paths filling the frame, 6-frame flight each). Items stick to: ceiling (2 socks), chair (a towel), floor (scattered), and CHIEF (4-5 items accumulate on him). CHIEF flails arms (4-frame flail cycle, repeated 2x) but items stick to his gloves faster than he removes them.
- **Camera:** static medium-wide (pulled back to show full room for the blizzard). The fabric fills the frame progressively.
- **Motion graphics/FX:** Each fabric item is a simple flat colored shape with `INK` outline. Arc paths are smooth curves. Static cling is indicated by `BRAND_YELLOW` zigzag lines at each contact point (2-frame flash per stick). Items on surfaces stay put once stuck (no falling off).
- **Transition out:** hard cut.

### SHOT 7 - 0:27-0:31 - MED.EYE.STATIC -> PAN RIGHT
- **Motion (beat 1, 0:27-0:29):** CHIEF stands center-frame, completely covered. Specific items: socks stuck to his cap (3, various colors), two shirts layered over his jacket, pants wrapped around his lower legs, underwear draped on his medal sash, a towel over one shoulder. His hair (visible under his lopsided cap) stands on end (spiky, static-charged). One arm is raised with 3 items hanging from the glove. His expression: frozen wide-eyes, mouth slightly open. Small static `BRAND_YELLOW` zigzag lines pulse around him (2-frame cycle). A single sock falls from the ceiling in the background (6-frame fall).
- **Motion (beat 2, 0:29-0:31):** Camera pans right to PIP. He sits in his chair beside the radiator pipe. He stands (3-frame), reaches up to the pipe (3-frame arm extend), and lifts his single `POP_TEAL` shirt off with both hands (4-frame peel -- a tiny last steam wisp rises as the shirt leaves the pipe). The shirt is perfect: flat, dry, warm, no wrinkles. PIP holds it up (2-frame admire), then folds it: fold 1 (3-frame, sides to center), fold 2 (3-frame, top to bottom), fold 3 (2-frame, final square). He places the folded square on top of his basket (2-frame set-down). He turns to look at CHIEF and tilts his head (3-frame tilt).
- **Camera:** medium on CHIEF (beat 1), then smooth pan right (12-frame pan) to PIP at the pipe. 0.5 s hold on PIP's fold sequence.
- **Motion graphics/FX:** Static lines on CHIEF are `BRAND_YELLOW` zigzags (multiple, pulsing 2-frame). The steam wisp on shirt removal is a final `PAPER`-white wavy line dissolving (3-frame fade out). The folded shirt is a clean `POP_TEAL` rectangle. No static lines near PIP -- he is static-free.
- **AUDIO CUE:** music **SLAMS back** at 0:27; the static crackling on CHIEF is the signature sound layered with the stinger.
- **Transition out:** hard cut.

### SHOT 8 - 0:31-0:32 - WIDE.EYE.STATIC (== SHOT 1 composition)
- **Motion:** Composition matches C1 exactly. All five dryer doors hanging open (interiors empty, dark). CHIEF center-frame: a walking pile of static-clinging laundry. PIP right-of-center by the radiator pipe, basket in hand with folded shirt on top. PIP extends a small flat white square toward CHIEF (a dryer sheet -- 3-frame arm extend). PIP turns to camera and gives a **small wave** (3-frame wave: hand up, wiggle, down). One final sock unsticks from the ceiling and falls onto CHIEF's head (6-frame fall, 2-frame land -- the button gag).
- **Camera:** return to C1 wide framing. Hard cut out within 1 s. Loop seam: the dryers, the pipe, the chair all match their C1 positions.
- **Motion graphics/FX:** The dryer sheet is a small flat white square with a tiny sparkle `BRAND_YELLOW` line. The falling sock is the same arc physics as the launch socks but slower (gravity only, no static velocity). PIP's wave is his series-standard 3-frame cycle.
- **Transition out:** hard cut, seam to C1 (viewer replays and notices the overstuffed machines and the warm radiator pipe from the start).

---

## B) Transitions & cut map (quick reference)

| Between | Type | Notes |
|---|---|---|
| C1->C2 | hard cut | both strategies established |
| C2->C3 | hard cut | to CHIEF-only escalation + machine overload |
| C3->C4 | hard cut | overload intensifies, machines walk |
| C4->C5 | hard cut | first eruption |
| C5->C6 | hard cut | chain-reaction eruptions |
| C6->C7 | hard cut | aftermath reveal + PIP contrast |
| C7->C8 | hard cut | payoff pose, loop seam |
| C8->C1 | **loop seam** | last frame matches first frame composition |

---

## C) Character costume locks (must persist every frame)

| Character | Required elements | Notes |
|---|---|---|
| CHIEF | peaked cap, `POP_TEAL` jacket, `BRAND_YELLOW` sash with medals, white gloves | Visible underneath accumulated laundry in C6-C8. Cap goes lopsided but never disappears. Items layer ON TOP of his costume, never replacing it |
| PIP | `POP_TEAL` scarf | Always visible. The shirt he is drying is a SEPARATE `POP_TEAL` item (matching but distinct -- no scarf removal) |

---

## D) Loop-seam frame check

| Element | Frame 1 (C1 start) | Frame 960 (C8 end) |
|---|---|---|
| Background | laundromat, 5 dryers (doors closed), radiator pipe | laundromat, 5 dryers (doors open), radiator pipe |
| PIP position | entering from right with basket | standing right with basket + folded shirt |
| CHIEF position | entering from left with overfull basket | standing center, covered in clothes |
| Dryer state | doors shut, one being stuffed | doors open, all empty |
| Camera | wide, static | wide, static, same framing |

> The narrative loop: the viewer sees C1's overstuffed dryer and the warm pipe shimmer and thinks
> "it was obvious from the start" -- they rewatch to count how many warning signs CHIEF ignored.
