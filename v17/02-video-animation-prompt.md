# v17 - Video-Generation Script / Prompt ("The Biggest Kite") - **SHORTS 9:16**

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or equivalent). It specifies **motion, camera angles, transitions, cut timing,
> motion-graphics and on-screen FX per shot**, so the generated output needs **minimal editing** -
> ideally just top-and-tail + audio layup. Everything aligns to the master timeline in
> `01-video-script.md` and audio in `03-audio-bgm-sfx-reference.md`.

**Global render spec:** **1080x1920 (9:16 vertical)** - 30 fps - ~32 s (~960 frames) - flat-2D cartoon
house style (thick uniform black outlines, no gradients, chunky 2.5-head proportions) - snappy pose-to-pose
with strong holds - **hard cuts only** (no dissolves/fades) - **no camera rotation/orbit, no handheld** -
**no blur/glow/gradients** - loop seam (C8 == C1).

**Motion philosophy:** limited animation - hold poses on comedy beats, animate in short bursts. v17's
structure builds through **escalating pull force** (feet sliding, body lifting, full tow) then delivers
a ballistic arc ending in a mud-splash impact. The contrast is between CHIEF's excess (massive kite,
ego-printed, thin string) and PIP's simplicity (tiny handmade kite, relaxed grip, perfect flight).

Two contrasting motion languages:
- **CHIEF:** forceful, then strained, then ragdolled. Early: stomping, slamming, flexing. Middle: sliding, digging in, wrapping wrist (desperation masked as confidence). After snap: pinwheeling, tumbling, splatting. All motion fights against or surrenders to external force.
- **PIP:** appears in C1 (flying kite, startled by shove), C2 (background, relaxed), C4 (background, sitting), C7 (standing with kite, look-and-tilt), and C8 (catches kite, waves). His motion is minimal and gravity-neutral -- his kite flies effortlessly, his body is always at rest.

> **The one rule that cannot break:** the **string tension must only increase** from C3 to C5. The string
> never slackens, the kite never dips, CHIEF's lean angle never decreases. Each gust is stronger than
> the last. The snap happens at absolute maximum tension -- the thinnest, tautest, most vibrating state.
> After the snap, CHIEF's trajectory must be a clean parabolic arc from hilltop to puddle with no
> mid-air recovery attempts.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** - subject motion - camera - transitions/FX - cut.

### SHOT 1 - 0:00-0:02 - WIDE.EYE.STATIC
- **Motion:** An open grassy hilltop. The vertical frame is divided: top 40% is `SKY`-blue with 3 puffy white cumulus clouds drifting left-to-right (1 pixel/frame drift). Middle 45%: green grass hill sloping from upper-right to lower-left. All grass blades lean right (wind indicator, 2-frame sway cycle). Bottom 15%: the hill's base with flat brown `ASPHALT`-tinted oval MUD PUDDLE (SEED B -- reflective surface, flat oval shape with slight `SKY` reflection). PIP stands mid-hill (small figure, center-right), holding a thin white string attached to a small diamond-shaped `POP_TEAL` kite with a 3-ribbon tail (each ribbon a different length, fluttering in the wind with offset phase). CHIEF enters frame-left: stomping walk (4-frame cycle, heavy), carrying a rolled canvas bundle under right arm and a massive `ASPHALT`-grey metal spool under left arm (the spool is as big as his torso). He elbows PIP's string (2-frame: elbow out, string deflects). PIP stumbles right 2 steps (3-frame stumble). Kite dips (4-frame dip then recover). CHIEF drops spool with a THUD (2-frame drop, dust puff on impact) and begins unrolling canvas (3-frame).
- **Camera:** locked wide. Full hill visible: sky (top), hilltop with characters (center), slope with puddle (bottom). This exact framing returns in C8.
- **Motion graphics/FX:** Wind indicators: grass blades lean right (2-frame sway), cloud drift (1px/frame), PIP's kite ribbons flutter (3 ribbons, offset 2-frame phase each). Spool drop creates a flat `PAPER` dust ring (3-frame expand + fade). Mud puddle is a flat brown oval with a thin `SKY`-blue highlight line (reflection).
- **Transition out:** hard cut.

### SHOT 2 - 0:02-0:06 - MED-WIDE.EYE.STATIC
- **Motion:** CHIEF unfurls the kite canvas (4-frame unroll: the fabric snaps open revealing full size). The kite is a delta-wing shape, twice CHIEF's height in wingspan, bright `ALERT_RED` fabric. Center of the kite: CHIEF's own face printed large (medals, cap, smug expression -- a flat graphic reproduction). He attaches the kite to the spool with string: the string is visibly THIN (1-pixel-wide `PAPER`-white line vs. PIP's 2-pixel string visible in background). He hammers a metal stake through the spool base (3-frame: stake position, hammer up, hammer CLANG -- stake sinks into ground). He launches: holds kite up (3-frame), releases (2-frame). The wind CATCHES it: the kite snaps from vertical to 60 degrees in 2 frames (a violent pull). The string goes instantly taut (straight diagonal line from spool to sky). The massive kite fills the upper 30% of frame. CHIEF crosses arms (2-frame) and grins (2-frame). Background: PIP's tiny `POP_TEAL` kite floats in the upper-right corner, string loose (a gentle curve vs. CHIEF's rigid straight line).
- **Camera:** medium-wide, static. CHIEF and his kite operation dominate left-center. PIP small in background-right.
- **Motion graphics/FX:** The kite unfurl is a scale animation (0% to 100% width in 4 frames). The thin string is a 1-pixel `PAPER` line (contrast with PIP's 2-pixel). The wind catch is a 2-frame snap (kite position jumps from CHIEF's hands to sky). CHIEF's face on the kite is a simplified flat graphic (same design as his actual face but printed-looking: `ALERT_RED` background, `INK` outlines, `BRAND_YELLOW` medals).
- **Transition out:** hard cut.

### SHOT 3 - 0:06-0:11 - MED.EYE.STATIC
- **Motion:** A gust hits (all grass bends further right -- from 15-degree lean to 30-degree). CHIEF's kite surges upward and forward in the sky (4-frame movement to higher position). The string angle steepens. The string starts HUMMING: a visible vibration (the 1-pixel line becomes a 3-pixel blur zone, oscillating 1px left-right on a 1-frame cycle). CHIEF's feet SLIDE forward on the grass (6-frame slide: both feet move 20px right, leaving two brown dirt-streak marks on the green surface). He leans backward to compensate (body angle from 90 degrees to 60 degrees, 4-frame lean). His gloved hands grip the string (visible squeeze -- fingers tighten). The spool bolt shows a tiny bend (the stake angles 5 degrees in CHIEF's pull direction -- barely visible). CHIEF opens mouth in a laugh (3-frame: open-hold-close). He reaches one hand to the spool and feeds out more string (4-frame: hand to spool, unreel motion, hand back to string). The kite moves HIGHER and the pull increases (string blur zone widens from 3px to 5px). His feet slide again (another 15px).
- **Camera:** static medium. CHIEF centered. Grass and sky fill the vertical frame around him. The string angle and foot-position changes are the primary motion story.
- **Motion graphics/FX:** String vibration: the line renders as a blurred zone (achieved by showing 3 instances of the 1px line at -1, 0, +1 pixel offset alternating per frame). Foot slides leave brown marks on green (simple color swap in the grass texture behind feet). The spool feed is a rotation animation on the spool cylinder (4-frame CCW rotation).
- **Transition out:** hard cut.

### SHOT 4 - 0:11-0:16 - MED.EYE.PUSHIN(slow)
- **Motion:** Stronger gust (grass at 45 degrees, clouds accelerate to 2px/frame). CHIEF's kite at maximum height (touching top of frame). The pull is enormous: CHIEF's heels dig TRENCHES (his feet drag backward through the grass, leaving two parallel brown grooves 40px long across the 5 seconds). His body leans at 45 degrees (nearly diagonal). Then: a 4-frame LIFTOFF -- both feet leave the ground by 3cm (a visible gap between shoe soles and grass). His eyes POP wide (eye shapes scale to 150% in 2 frames). He lands (2-frame drop back to ground). Immediately he wraps the string around his right wrist (4-frame wrap: string loops around wrist 2 times, locking him to it). The string vibration is now maximum: 7-pixel blur zone. The spool bolt bends to 15 degrees (visible metal deformation, the stake nearly horizontal). Background right: PIP sits cross-legged on the grass (appeared since C3), one hand loosely holding his string at shoulder height, kite bobbing gently above. PIP is perfectly relaxed.
- **Camera:** slow push-in from 100% to 106%. Ending frame is tight on CHIEF's wrapped wrist and the vibrating string blur, with the bending bolt visible below.
- **Motion graphics/FX:** Trenches: brown color fills behind foot positions as they move. Liftoff gap: a thin green line appears between shoe bottoms and grass surface for 4 frames. Eye pop: eye shape scales 150% + white sclera expands. Wrist wrap: string path changes from straight-to-sky to loop-around-wrist-then-to-sky. Bolt bend: the stake shape rotates from near-vertical to near-horizontal. PIP in background is a small static figure (only his kite bobs: 2-frame Y-oscillation, 4px).
- **Transition out:** hard cut.

### SHOT 5 - 0:16-0:22 - MED.EYE.STATIC -> HOLD
- **Motion:** The biggest gust (grass horizontal, a stray leaf flies across frame). CHIEF's kite LUNGES forward in the sky. The pull yanks CHIEF off the ground entirely: his feet leave the earth by 10cm and he is now being TOWED HORIZONTALLY (body at 30-degree incline, hanging from his wrist-wrapped string, moving rightward at speed). He covers visible distance (his body translates 60px rightward over 2 seconds of tow). His free left hand pinwheels (4-frame flail cycle). Then: **SNAP**. The thin string breaks at its midpoint (2-frame: the taut line becomes two severed whipping ends -- one flies toward the kite, one toward CHIEF's wrist. A `BRAND_YELLOW` snap-flash at the break point, 1 frame). **Music cuts on the SNAP.** CHIEF now has forward momentum but no upward support. His arc begins: body starts descending (the parabolic trajectory begins). His cap lifts off his head (1-frame separation, cap begins own upward trajectory). Two medals detach from sash (they fly outward like confetti). The broken kite above folds inward (the delta-wing crumples, 4-frame fold) and begins tumbling.
- **Camera:** medium shot, static. CHIEF's horizontal tow and the snap happen center-frame.
- **Motion graphics/FX:** The tow is a horizontal translation of CHIEF's body (30px/second rightward). The SNAP is a 1-frame `BRAND_YELLOW` 6-point star burst at the break point + the line splitting into two curling ends (each end recoils with a spring animation: 4-frame settle). Cap separation: cap Y-velocity becomes positive (rising) while body Y-velocity becomes negative (falling). Medal detach: 2 flat `BRAND_YELLOW` circles fly outward on diverging arcs.
- **AUDIO CUE (critical):** music **cuts on the SNAP (0:16)**, leaving only wind rushing past CHIEF's body.
- **Transition out:** hard cut.

### SHOT 6 - 0:22-0:27 - WIDE.EYE.STATIC
- **Motion:** Three-phase ballistic flight (camera pulls back to WIDE to show full hill -- CHIEF's arc goes from hilltop to puddle at base):
  - **Phase 1 (0:22-0:23.5):** CHIEF's body translates rightward and begins descending. Arms pinwheel (4-frame flail cycle, repeated 2x). Cap rises above him (separate arc, upward then settling on hillside mid-slope). Two medals trace diverging arcs outward (landing on grass -- small glints where they land). His expression: wide eyes, open mouth (frozen panic face -- no animation needed, held static).
  - **Phase 2 (0:23.5-0:25):** CHIEF reaches the APEX of his parabola (highest point of arc, horizontally past the hilltop but only 1 meter high now). He hangs frozen for 2 frames (zero-velocity peak -- the comedy timing beat). His eyes look DOWN (2-frame eye-direction change -- he sees the puddle below). The brown oval is directly beneath him.
  - **Phase 3 (0:25-0:27):** Accelerating descent. CHIEF's body rotates from 30-degree lean to 60-degree nose-dive (4-frame rotation). He gets larger (approaching camera plane as he descends the hill). He hits the mud puddle: SPLAT. The impact frame (2-frame): (a) CHIEF's body enters the brown oval from top, (b) 8 brown mud droplets spray radially outward in a starburst pattern (each droplet is a flat brown circle on an arc trajectory, 4-frame flight + 2-frame settle on grass), (c) a mud-wave ring expands from the impact point (flat brown ring, 4-frame expand + fade). Post-splash state (0:26.5-0:27): CHIEF is face-down in the puddle -- only his legs stick up at 45 degrees (from the waist down visible above the brown surface). His broken `ALERT_RED` kite drifts down slowly (6-frame flutter -- fabric wobbles left-right during descent) and drapes over his back/legs (2-frame settle). The printed face on the kite now faces the sky, mud-speckled (brown dots added to the printed face).
- **Camera:** static wide (same as C1 framing). The full parabolic arc is visible from hilltop to puddle.
- **Motion graphics/FX:** CHIEF's trajectory is a smooth parabolic curve (position calculated per frame). The pinwheel arms are a 4-frame rotation animation. The apex freeze is a literal 2-frame hold of all positions. The nose-dive rotation is a simple body-angle increment. The mud splash is 8 radial flat circles + 1 expanding ring. The kite drift is a Y-descent with X-wobble (sine wave on X, linear on Y). Mud specks on kite-face: 5-6 small brown dots randomly placed over the printed face graphic.
- **Transition out:** hard cut.

### SHOT 7 - 0:27-0:31 - LOW.EYE.STATIC -> PAN UP
- **Motion (beat 1, 0:27-0:29):** Camera starts LOW, at puddle level. CHIEF face-down in the mud: his upper body submerged (brown surface), legs sticking up at 45 degrees (boots visible, one slightly twitching -- 2-frame twitch: 3-degree rotation then back). The broken kite draped over his back (the `ALERT_RED` fabric with his own mud-speckled face looking up -- visual irony). One `BRAND_YELLOW` medal sits on the mud surface beside the puddle, slowly sinking (1px/2frames Y-descent into the brown). Three mud bubbles rise from where CHIEF's face is submerged (flat brown circles: 2-frame appear, 2-frame grow slightly, 2-frame pop -- staggered timing so one is always visible).
- **Motion (beat 2, 0:29-0:31):** Camera pans UP the hill (12-frame smooth vertical pan). The hillside passes: green grass with the two trench marks, the cap (sitting on the slope where it landed), the bent spool bolt (string dangling limp). Camera arrives at hilltop: PIP stands relaxed, legs slightly apart, one hand at hip height holding his string. His tiny `POP_TEAL` kite dances directly above him -- exactly where it has been the entire video, undisturbed by any of the chaos below. The kite's 3 tail-ribbons flutter gently (2-frame phase offset each). PIP looks down the hill (3-frame head angle down), then looks up at his kite (3-frame head angle up), then faces camera with a gentle head-tilt (3-frame, 10-degree rotation) and a close-mouthed smile (2-frame mouth curve up).
- **Camera:** starts at LOW angle (puddle level, looking across mud), smooth PAN UP (12-frame vertical travel) to hilltop level showing PIP and sky.
- **Motion graphics/FX:** Mud bubbles: flat brown circles with a 2-frame animation cycle (appear small, grow, pop into nothing). Medal sinking: simple Y-translation downward (brown covers more of the gold circle each frame). Kite ribbon flutter: each ribbon is a wavy line with a traveling wave animation (offset phase per ribbon creates organic flutter). PIP's head movements are simple rotation on neck pivot.
- **AUDIO CUE:** music **returns at 0:27** -- warm resolve (acoustic guitar fingerpick + whistling melody, matching the C1 bed's cheerful tone but softer, warmer).
- **Transition out:** hard cut.

### SHOT 8 - 0:31-0:32 - WIDE.EYE.STATIC (== SHOT 1 composition)
- **Motion:** Composition matches C1 exactly. The wide hilltop shot: `SKY`-blue sky with calmer clouds (slower drift: 0.5px/frame). Green grass blowing gently (15-degree lean -- the wind has calmed). PIP stands on hilltop center-right. His kite is still in the air above. At the base: CHIEF in the puddle (legs up, kite-cape on back). Mid-slope: the spool (still bolted, string dangling limp from the severed end) and CHIEF's cap (sitting on grass). PIP reels in his kite (3-frame pull: hand-over-hand on string, kite descends smoothly into his arms). He tucks it under one arm (2-frame fold + tuck). He turns to camera and gives his signature **small wave** (3-frame: hand up, wiggle-wiggle, hand down). A final gust picks up CHIEF's cap from the hillside (2-frame lift -- the cap rises and tumbles out of frame-left, rotating (4-frame rotation cycle)).
- **Camera:** return to C1 wide framing. Hard cut. Loop seam: hill, sky, puddle, spool positions all match C1.
- **Motion graphics/FX:** Kite reel-in: the kite's Y-position decreases linearly over 3 frames until it reaches PIP's hands (the string shortens correspondingly). Tuck: kite shape compresses to fit under arm (scale 100% to 40%). Wave: PIP's standard 3-frame hand cycle. Cap tumble: the cap shape rotates (full 360 over 4 frames) while translating leftward and upward (exit frame-left-top).
- **Transition out:** hard cut, seam to C1 (viewer replays and notices the thin string, the mud puddle, and the spool from the start).

---

## B) Transitions & cut map (quick reference)

| Between | Type | Notes |
|---|---|---|
| C1->C2 | hard cut | kite launched; the flaw is planted |
| C2->C3 | hard cut | first wind escalation; sliding begins |
| C3->C4 | hard cut | liftoff tease; wrist wrap |
| C4->C5 | hard cut | full tow; the SNAP |
| C5->C6 | hard cut | ballistic arc; the mud splash |
| C6->C7 | hard cut | aftermath reveal; PIP contrast |
| C7->C8 | hard cut | payoff pose, kite catch, loop seam |

---

## C) Loop seam verification

| Element | C1 (first frame) | C8 (last frame) | Match? |
|---|---|---|---|
| Sky | `SKY`-blue, 3 clouds drifting | `SKY`-blue, 3 clouds (calmer drift) | match |
| Hill/grass | green, blowing right | green, blowing right (gentler) | match |
| Mud puddle | brown oval at base, empty | brown oval at base, CHIEF inside | contextual match (same position) |
| Spool | CHIEF carrying it in (entering) | bolted mid-slope, string limp | contextual match (same zone) |
| PIP position | mid-hill, holding kite string | hilltop, kite in arms | near-match (same character zone, kite present) |
| PIP's kite | flying upper-right | being tucked under arm | callback (kite present in both) |
| CHIEF position | entering frame-left | in puddle at base | contextual match |
| Overall composition | wide hill, sky above, puddle below | wide hill, sky above, puddle below | match |
