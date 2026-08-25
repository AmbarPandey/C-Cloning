# v12 - Video-Generation Script / Prompt ("The Express Elevator") - **SHORTS 9:16**

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or equivalent). It specifies **motion, camera angles, transitions, cut timing,
> motion-graphics and on-screen FX per shot**, so the generated output needs **minimal editing** -
> ideally just top-and-tail + audio layup. Everything aligns to the master timeline in
> `01-video-script.md` and audio in `03-audio-bgm-sfx-reference.md`.

**Global render spec:** **1080x1920 (9:16 vertical)** - 30 fps - ~32 s (~960 frames) - flat-2D cartoon
house style (thick uniform black outlines, no gradients, chunky 2.5-head proportions) - snappy pose-to-pose
with strong holds - **hard cuts only** (no dissolves/fades) - **no camera rotation/orbit, no handheld** -
**no blur/glow/gradients** - loop seam (C8 == C1).

**Motion philosophy:** limited animation - hold poses on comedy beats, animate in short bursts. v12's
structure builds tension through **obsessive repetition** (the same button press, escalating in force)
then delivers the collapse through a single inevitable failure point (electrical short-circuit from abuse).
The contrast is between CHIEF's frantic energy and PIP's calm absence.

Two contrasting motion languages:
- **CHIEF:** obsessive rhythmic jabbing that escalates in force and speed -- one finger, two fingers, palm, fist. Never stops moving in the elevator. After the failure: frantic, desperate multi-action panic.
- **PIP:** appears only in C1 (shoved), C2 (walks to stairs), C7 (standing relaxed with cup), and C8 (offers cup, waves). Total stillness when he appears in C7 -- the calm is the punchline.

> **The one rule that cannot break:** the **button damage must escalate monotonically** from C3 to C5.
> The scorch mark only grows, the smoke only thickens, and the button only sinks deeper. Never let
> any damage element reverse or disappear between frames.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** - subject motion - camera - transitions/FX - cut.

### SHOT 1A - 0:00-0:015 - CU.EYE.STATIC  *(cold payoff - replaces the old wide establishing shot)*
- **Motion:** Close on a lift button panel with a gloved thumb jabbing it, fast and repeatedly — and on the fourth jab the panel **sparks**, a flat `BRAND_YELLOW` flash, and every light on it dies at once. The car lurches. Cut on the lurch. The motion is **already at full speed on frame 1** - there is no entrance, no settle, no push-in from a wide, and no character walks into shot.
- **Camera:** locked tight CU. The subject fills the frame. **Zero settle time.** Frame 1 is mid-event.
- **Motion graphics/FX:** flat impact shapes only - no glow, no blur, no gradients. Palette tokens only.
- **Transition out:** hard cut on the beat, *before* the event resolves.

### SHOT 1B - 0:015-0:02 - MED.EYE.STATIC  *(goal diagram)*
- **Motion:** Hard cut to the lobby: the floor indicator above the doors showing the target floor, and immediately beside the lift, a **staircase** drawn with a simple riser-and-arrow pictogram going up to the same number. Two routes, one destination, both in frame. PIP is in the same frame at the foot of the stairs, one foot already on the first riser — same destination, the slower route.
- **Camera:** locked medium-wide, held. **This exact framing returns in SHOT 8 for the loop seam.**
- **On-frame text:** **none baked into the render.** The 3-7 word hook caption *"He mashed the close button"* is an **edit-layer overlay**, placed clear of the bottom bar and the right-hand action rail.
- **Transition out:** hard cut.

### SHOT 2 - 0:02-0:06 - SPLIT: LOBBY.EYE.STATIC / INTERIOR.EYE.PUSHIN
- **Motion (lobby beat, 0:02-0:03.5):** PIP faces the closed elevator doors, blinks once (2-frame), turns his head toward the stairwell door (3-frame turn), walks over (4-frame walk cycle), and pushes the stairwell door open (3-frame push). He disappears inside.
- **Motion (elevator beat, 0:03.5-0:06):** CHIEF inside, presses floor "5" button (2-frame). Leans against back mirror wall (4-frame lean). Adjusts cap in mirror (3-frame adjust). Does a little triumphant shimmy (6-frame shimmy cycle). One finger rests on the "CLOSE" button -- still pressing idly.
- **Camera:** hard cut between the two locations. Lobby shot static. Elevator interior: slow push-in (100% to 105%) ending on CHIEF's smug face in the mirror.
- **Motion graphics/FX:** stairwell door opens showing concrete stairs beyond (flat `ASPHALT` grey). Inside elevator: mirror reflection of CHIEF (simplified flat reflection). Floor indicator above doors shows "1."
- **Transition out:** hard cut.

### SHOT 3 - 0:06-0:11 - MED.EYE.STATIC
- **Motion:** Inside elevator, medium shot framing CHIEF and the button panel. CHIEF jabs the "CLOSE" button with his **right index finger** in a steady rhythm (3-frame jab, 0.5 s interval -- 10 jabs across the shot). He looks at his reflection, adjusts his sash with his free hand, jabs again. He is humming (indicated by a small head-bob cycle). The floor indicator above: "1" ticks to "2" (at 0:08). Around the button, a faint **dark ring** appears (the scorch mark Stage 1) -- 4-frame fade-in at 0:09.
- **Camera:** static medium; 4-frame hold at 0:09 when the scorch mark first appears (subtle -- audience may miss it first viewing).
- **Motion graphics/FX:** flat dark `INK` ring around button (Stage 1 damage -- very thin, just a discoloration). The button itself looks normal. Floor indicator digit flip is a simple 2-frame swap.
- **Transition out:** hard cut.

### SHOT 4 - 0:11-0:16 - MED-CLOSE.EYE.PUSHIN(slow)
- **Motion:** CHIEF's pressing **escalates in three visible stages** (~1.6 s apart):
  - **Stage A (0:11):** switches to **two fingers** pressing together (3-frame transition from one finger).
  - **Stage B (0:13):** switches to his **whole palm** slamming flat against the button (4-frame slam cycle, faster rhythm now -- 0.3 s interval).
  - **Stage C (0:15):** the button is **visibly depressed deeper** than its housing -- pushed inward beyond its normal travel. The dark scorch mark is now wide and clearly visible. Thin grey smoke wisps (2 flat wavy lines) curl from the panel edges (4-frame oscillation cycle).
  CHIEF does not look at the panel -- he is turned toward the mirror, flexing his medals with his free hand. Floor indicator: "2" ticks to "3" (at 0:14).
- **Camera:** slow push-in (100% to 106%) ending tight on the panel showing the full escalation of damage.
- **Motion graphics/FX:** scorch mark grows wider/darker at each stage (3-frame fade transitions). Smoke wisps are flat `ASPHALT` grey wavy lines (no blur, no transparency gradient). The inward-pushed button is shown by a darker shadow gap around it. One flat `BRAND_YELLOW` sparkle glint off a medal at 0:15.
- **Transition out:** hard cut.

### SHOT 5 - 0:16-0:22 - MED.LOW.STATIC -> HOLD
- **Motion:** CHIEF rears back (4-frame wind-up) and delivers one final enormous **FIST SLAM** on the button (2-frame impact). A bright `BRAND_YELLOW` **SPARK** shoots outward from the panel (4-frame burst). The overhead lights **flicker twice** (2-frame on, 2-frame off, 2-frame on, then off permanently at 0:17.5). A single `ALERT_RED` emergency light activates in the ceiling (2-frame pop-on). The floor indicator display **dies** showing a frozen position between "3" and "4" (display artifacts/half-lit segments). The elevator **shudders** (3-frame position shake -- left, right, center) and **stops**. CHIEF's expression crashes: triumphant fist-pump pose freezes, then 4-frame snap to wide-eyed horror.
- **Camera:** medium shot, slight low angle. CHIEF and the sparking panel share the frame. Static hold once the red light activates.
- **Motion graphics/FX:** `BRAND_YELLOW` spark burst (flat star shape, 4 frames); flat flicker (simple on/off, no glow); `ALERT_RED` circle in ceiling corner; the frozen indicator shows garbled segments (flat rectangles, some lit, some dark). Position shake is simple X-offset, no blur.
- **AUDIO CUE (critical):** music **cuts mid-phrase on the SPARK frame (0:16)**, leaving only the mechanical groan and emergency hum.
- **Transition out:** hard cut.

### SHOT 6 - 0:22-0:27 - MED.EYE.STATIC
- **Motion:** Red emergency light blinks (2-frame on, 8-frame off cycle throughout). CHIEF's three panic attempts:
  - **Attempt 1 (0:22-0:23.5):** Jabs every other button on the panel rapidly (8 jabs in 1.5 s, 3-frame each) -- none light up, all dead.
  - **Attempt 2 (0:23.5-0:25):** Wedges his gloved fingers into the door seam (4-frame wedge). Doors open a tiny crack -- grey concrete shaft visible (4-frame hold on the gap). Doors snap shut (2-frame snap). CHIEF yanks fingers back.
  - **Attempt 3 (0:25-0:27):** CHIEF crouches (3-frame) and JUMPS (4-frame up, 4-frame down). The elevator sways left-right on its cable (6-frame sway cycle, dampening). It stays stuck. The red light blinks on unconcerned.
- **Camera:** static medium; the red blink provides visual rhythm. The ceiling cable attachment point visible in top of frame during the jump.
- **Motion graphics/FX:** dead button panel (all dark, no response to presses). Door gap shows flat grey with vertical lines (shaft texture). The elevator sway is a simple X-position oscillation (no blur). The red blink is a flat circle toggling on/off.
- **Transition out:** hard cut.

### SHOT 7 - 0:27-0:31 - MED.EYE.STATIC -> SETTLE WIDE
- **Motion (beat 1, 0:27-0:29):** The elevator emits a low groan (no visual -- just the feeling of something lurching). It crawls upward (indicated by the floor indicator flickering back to life: "4... 5"). The doors begin to **creak open** -- painfully slowly (the full door-open takes 2 seconds, the slowest motion in the video). As the gap widens, warm `PAPER` hallway light floods in from outside, replacing the red emergency glow.
- **Motion (beat 2, 0:29-0:31):** Doors fully open to reveal: **PIP** standing in a bright, calm hallway. He is leaning slightly against the wall next to a **water cooler** (visible, mundane, ordinary). He holds a paper cup. He takes one calm **sip** (3-frame lift, 4-frame sip, 3-frame lower). His expression is neutral-pleasant. He has clearly been here a while. CHIEF is frozen in the elevator, mouth open, one glove still raised from the jump.
- **Camera:** starts medium (inside elevator looking out through widening door gap). As doors open fully, settles to wide framing showing both characters: CHIEF in red-lit elevator on left, PIP in bright hallway on right. **0.5 s hold on this contrast.**
- **Motion graphics/FX:** door-gap light is a warm `PAPER` rectangle that widens as doors open (flat shape, no glow/gradient). The hallway beyond is bright and flat -- water cooler is a simple flat blue-grey rectangle with a small cup dispenser. PIP's cup is white with a flat `SKY` water fill. No sparkle on PIP.
- **AUDIO CUE:** music **SLAMS back** at 0:27 on the lurch; the **door CREAK is the signature sound of the twist** -- longest single SFX in the video.
- **Transition out:** hard cut.

### SHOT 8 - 0:31-0:32 - WIDE.EYE.STATIC (== SHOT 1 composition, reversed angle)
- **Motion:** The elevator doors are fully open, framing the scene (doors as a proscenium arch). CHIEF stands inside: cap askew, medals tarnished with grey smoke residue, one glove blackened from the spark, sweating (flat drop on forehead). The scorched panel behind him, still faintly smoking. PIP stands in the hallway, **holding out the paper cup of water** toward CHIEF (4-frame extend). CHIEF takes it with a trembling glove (3-frame reach). PIP turns to camera and gives a **small wave** (3-frame wave). One last **spark** pops from the dead panel behind CHIEF (2-frame flat star).
- **Camera:** return to the C1 wide framing (from outside looking in at the elevator, mirrored with C1's perspective). Hard cut out within 1 s after the wave.
- **Motion graphics/FX:** flat sweat drop on CHIEF's forehead; the cup hand-off is simple and un-emphasized; the final spark is a small flat `BRAND_YELLOW` star, same as C5 but tiny. No residual FX on the final frame except the scorched panel (loop must be readable).
- **Transition out:** hard cut, seam to C1 (the viewer replays and notices the stairwell door and the "5" sign).

---

## B) Transitions & cut map (quick reference)
| Between | Type | Notes |
|---|---|---|
| C1->C2 | hard cut | lobby to split interior/exterior |
| C2->C3 | hard cut | to elevator interior only |
| C3->C4 | hard cut | escalation of force |
| C4->C5 | hard cut | into the fist-slam and failure |
| **C5 internal (0:16)** | **music cut only -- no visual cut at the spark** | the pattern break starts aurally |
| C5->C6 | hard cut | to the panic attempts |
| C6->C7 | hard cut | the lurch and slow reveal |
| **C7 internal (0:29)** | 0.5 s hold | CHIEF in red-lit box vs. PIP in bright hallway -- the contrast freeze |
| C7->C8 | hard cut | payoff |
| C8->(loop) | hard cut, seam to C1 | replay re-reads the stairwell door and the close button |

**No** dissolves, fades, wipes, glitch, zoom-blur, or camera rotation anywhere. Effects are limited to:
flat spark bursts, flat smoke wisps (wavy lines), flat red blink circle, flat light rectangles (door gap),
flat sweat drop, motion lines, and the listed holds/freezes.

---

## C) Optional single "master prompt" (for one-shot generators)
```
{style prefix -- 9:16 VERTICAL, flat-2D cartoon, thick black outlines, no gradients}
A ~32s 9:16 flat-2D cartoon comedy short, 30fps, hard cuts only, no camera rotation, no blur or glow,
snappy pose-to-pose animation with strong holds. Recurring cast: CHIEF, a pompous rotund braggart in a
teal jacket with an oversized peaked cap and a yellow medal sash; PIP, a tiny underdog with a teal scarf.
Setting: a building lobby with polished grey elevator doors (center) and a STAIRWELL DOOR with a "5" sign
beside it (right side). A DOOR CLOSE BUTTON on the elevator's interior panel.
Story in 8 beats:
(0-2s) WIDE static: elevator doors open; CHIEF shoves PIP aside, enters elevator, hammers the DOOR CLOSE
button. Doors close on PIP. The stairwell door and "5" sign visible beside the elevator.
(2-6s) SPLIT: PIP calmly walks to the stairwell door and enters. Inside the elevator, CHIEF presses floor
5, leans against the mirror wall, and does a smug shimmy. Still idly pressing CLOSE.
(6-11s) MED static: inside the elevator, CHIEF jabbing CLOSE rhythmically with one finger even though doors
are shut. Floor indicator crawls "1...2." A faint dark SCORCH MARK appears around the button edges.
(11-16s) MED-CLOSE push-in: the pressing ESCALATES -- two fingers, then PALM, then the button pushed
deeper than its housing. Scorch mark grows. Smoke wisps curl from panel edges. CHIEF doesn't notice --
admiring medals in mirror. Floor indicator "2...3."
(16-22s) MED low angle: CHIEF delivers a final FIST SLAM. A bright SPARK shoots from the panel. Lights
flicker and die. Red emergency light. Floor indicator freezes between 3 and 4. Elevator SHUDDERS and STOPS.
MUSIC CUTS TO SILENCE. CHIEF's face falls.
(22-27s) MED static: in red-blinking silence, CHIEF tries: jabs all buttons (dead), pries doors (sees
shaft, doors snap shut), JUMPS (elevator sways but stays stuck). All fail.
(27-31s) MED to WIDE: elevator groans, crawls to floor 5. Doors CREAK OPEN slowly. Standing in the bright
hallway is PIP, relaxed, holding a cup of water from the hallway cooler. He takes a sip. CHIEF frozen,
mouth open. 0.5s hold on the contrast.
(31-32s) WIDE, framing identical to opening: CHIEF inside elevator (cap askew, medals smoky, scorched panel
behind him). PIP offers the cup of water. CHIEF takes it with trembling glove. PIP waves. One last spark
pops from the panel. Hard cut.
ZERO on-screen text anywhere (the "5" sign and floor indicator are diegetic set elements). CHIEF never loses
cap/sash/medals (disheveled and smoky is fine). PIP never gloats. Button damage only INCREASES. CHIEF
never notices the damage until the spark. Advertiser-safe: CHIEF is stuck and embarrassed -- no real danger,
no falling elevator, no injury, no claustrophobia distress.
```

---

## D) Handoff / minimal-edit checklist
- [ ] **Rendered 9:16 / 1080x1920**, total ~32 s, on the locked 8-clip skeleton.
- [ ] Assemble C1->C8 with **hard cuts**; add no transitions.
- [ ] Insert the holds/freezes: C1 6-frame settle - C3 4-frame scorch mark hold - C4 3-frame on each escalation stage - C5 static hold on dead elevator - C6 red-blink rhythm - C7 **0.5 s contrast freeze** (CHIEF in red box vs PIP in bright hallway).
- [ ] **Verify Seed A:** stairwell door with "5" sign visible in C1, used by PIP in C2.
- [ ] **Verify Seed B:** the CLOSE button is pressed in C1 and escalates through C3-C5.
- [ ] **Verify damage monotonic:** scorch mark only grows (C3 faint -> C4 dark+smoke -> C5 spark+death). Never shrinks or disappears.
- [ ] **Verify CHIEF never notices damage** before C5. He is always looking at mirror/medals, not the panel.
- [ ] Verify the failure is caused by **his own obsessive pressing** -- no power cut, no external event.
- [ ] Verify PIP is **completely relaxed** in C7 and C8 (leaning, sipping water, no sweat, no panting).
- [ ] Confirm music cuts at 0:16 (the spark frame) with no visual transition.
- [ ] Confirm the **door creak (0:27-0:29)** is the longest uninterrupted SFX -- the slow reveal.
- [ ] Confirm PIP **never gloats** (no smirk, no pointing, neutral-pleasant expression only).
- [ ] Verify loop seam: C8 and C1 share the elevator-doors-as-frame composition; background matches.
- [ ] Lay VO and BGM/SFX onto fixed timecodes -- everything pre-synced.
- [ ] Final QC: no baked text, no blur/glow, cast on-model, CHIEF stuck but unharmed, no falling/claustrophobia/danger, PIP kind and calm.
