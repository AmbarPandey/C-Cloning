# v16 - Video-Generation Script / Prompt ("The Book Tower") - **SHORTS 9:16**

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or equivalent). It specifies **motion, camera angles, transitions, cut timing,
> motion-graphics and on-screen FX per shot**, so the generated output needs **minimal editing** -
> ideally just top-and-tail + audio layup. Everything aligns to the master timeline in
> `01-video-script.md` and audio in `03-audio-bgm-sfx-reference.md`.

**Global render spec:** **1080x1920 (9:16 vertical)** - 30 fps - ~32 s (~960 frames) - flat-2D cartoon
house style (thick uniform black outlines, no gradients, chunky 2.5-head proportions) - snappy pose-to-pose
with strong holds - **hard cuts only** (no dissolves/fades) - **no camera rotation/orbit, no handheld** -
**no blur/glow/gradients** - loop seam (C8 == C1).

**Motion philosophy:** limited animation - hold poses on comedy beats, animate in short bursts. v16's
structure builds through **vertical accumulation** (tower growing taller, table bowing deeper) then
delivers a three-wave gravitational collapse. The contrast is between CHIEF's excess (dozens of books,
an engineering project of pettiness) and PIP's minimalism (one cushion, one slim book, perfect peace).

Two contrasting motion languages:
- **CHIEF:** aggressive, possessive, then panicked. Early: slamming, stacking, admiring with chest-puff. After the crack: lunging, flailing, buried. All motion is forceful and escalating.
- **PIP:** appears in C1 (approaching), C2 (sits on cushion, opens book), C7 (turns page, looks up), and C8 (holds SHHH sign, waves). Minimal motion. His page-turn is the calmest action in the video. His stillness is the punchline.

> **The one rule that cannot break:** the **tower must only grow** from C3 to C5. No books fall off
> before the C5 crack. The wobble increases, the table bows further, but the tower holds until the
> tiny paperback triggers the collapse. The collapse itself must escalate across three distinct waves
> in C6 -- each wave involving more books than the previous one.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** - subject motion - camera - transitions/FX - cut.

### SHOT 1A - 0:00-0:015 - CU.EYE.STATIC  *(cold payoff - replaces the old wide establishing shot)*
- **Motion:** Close on a table leg **splitting** — the joint opening, the whole tabletop dropping a hand's width, and the base of a huge book stack shearing sideways above it. One thin paperback slides off the top and hangs in the air. Cut before the stack lands. The motion is **already at full speed on frame 1** - there is no entrance, no settle, no push-in from a wide, and no character walks into shot.
- **Camera:** locked tight CU. The subject fills the frame. **Zero settle time.** Frame 1 is mid-event.
- **Motion graphics/FX:** flat impact shapes only - no glow, no blur, no gradients. Palette tokens only.
- **Transition out:** hard cut on the beat, *before* the event resolves.

### SHOT 1B - 0:015-0:02 - MED.EYE.STATIC  *(goal diagram)*
- **Motion:** Hard cut to the reading room: a small **load-limit pictogram** stamped on the table leg — a stacked-books shape with a line across it and a `BRAND_YELLOW` arrow at the line — with the actual stack already well past it. A floor cushion sits free beside the shelves. PIP is in the same frame on the floor cushion with one slim picture book open on his knees — same library, one book.
- **Camera:** locked medium-wide, held. **This exact framing returns in SHOT 8 for the loop seam.**
- **On-frame text:** **none baked into the render.** The 3-7 word hook caption *"One paperback too many"* is an **edit-layer overlay**, placed clear of the bottom bar and the right-hand action rail.
- **Transition out:** hard cut.

### SHOT 2 - 0:02-0:06 - MED-WIDE.EYE.STATIC
- **Motion:** CHIEF turns to the nearest shelf and rapidly pulls books (2-frame grab, 2-frame place, repeated 8 times -- rhythmic). He builds a WALL of upright books across the table's near edge facing PIP: 8 books side by side, then a second row on top. The wall is solid -- no gaps. He steps back (2-frame), dusts gloves together (3-frame pff), crosses arms (2-frame), and nods once (2-frame). PIP observes from 4 steps away: he looks at the wall (2-frame look), looks right toward the cushion (3-frame head turn), does a small shrug (3-frame: shoulders up, hold, down). He walks to the cushion (4-frame walk), sits cross-legged on it (4-frame: bend, lower, settle, legs cross). He opens his picture book flat on his lap (3-frame: lift cover, lay flat, hands rest). The reading lamp on the low shelf beside him casts a warm `BRAND_YELLOW` circular glow on his page.
- **Camera:** medium-wide, static. Left half: CHIEF + table + wall. Right half: PIP + cushion + low shelf.
- **Motion graphics/FX:** Each book placement is a simple 2-frame position snap (book appears in wall). The shrug is shoulder Y-offset (up 3px, hold 4 frames, down 3px). Lamp glow is a flat `BRAND_YELLOW` oval on PIP's book page.
- **Transition out:** hard cut.

### SHOT 3 - 0:06-0:11 - MED.EYE.STATIC
- **Motion:** CHIEF grabs a thick green encyclopedia from the shelf (3-frame pull) and places it flat on the table center (2-frame place). Then a red dictionary on top (2-frame). A blue atlas (2-frame). A yellow reference book (2-frame). A purple tome (2-frame). A brown volume (2-frame). The stack is now 6 books high, each spine visible (different colors create a rainbow tower). The table emits a subtle creak (no visual deformation yet -- audio only). CHIEF grabs two thick grey books and wedges them at angles against the tower base as "buttresses" (2-frame each, angled 45 degrees). He steps back (2-frame), places one hand on hip (2-frame), and admires: chest puffs, medals glint (1-frame `BRAND_YELLOW` sparkle on medal).
- **Camera:** static medium. CHIEF left-of-center, tower growing center-frame. The tower height progression is the visual focus.
- **Motion graphics/FX:** Each book is a flat colored rectangle with `INK` outline and a thin spine detail line. The "buttresses" are angled rectangles leaning against the main stack. Medal glint is a 1-frame `BRAND_YELLOW` 4-point star.
- **Transition out:** hard cut.

### SHOT 4 - 0:11-0:16 - MED.EYE.PUSHIN(slow)
- **Motion:** Tower is 10 books high now (4 more added in a 4-frame montage at shot start). It is absurdly tall -- nearly as tall as CHIEF. The tower wobbles: a 2-pixel X-offset oscillation on a 4-frame cycle (continuous). Table legs are visibly bowing: the front-left leg has a hairline gap at the upper joint (a thin `INK` line appears where solid wood should be). CHIEF stretches on tiptoes (3-frame rise), reaches up (3-frame arm extend), places a thick atlas on top (2-frame place). The tower sways more: 4-pixel oscillation, 3-frame cycle. CHIEF touches it with one finger (2-frame -- tower stops). He grins (2-frame). He immediately reaches toward the shelf for another book (3-frame reach). The table emits a low groan -- a visible vibration line passes through the table surface (a single `ASPHALT`-grey wavy line, left-to-right, 4-frame travel). CHIEF pauses (2-frame hold), shrugs (2-frame), continues reaching.
- **Camera:** slow push-in from 100% to 108% across 5 seconds. Ending frame shows both the bowing leg (bottom) and wobbling tower peak (top) in the same tight vertical composition.
- **Motion graphics/FX:** The wobble is X-position oscillation on the entire tower group. The leg gap is a thin `INK` line opening. The vibration line is a flat `ASPHALT` sine-wave stroke traveling left-to-right. The sway increase (2px to 4px) is a parameter change mid-shot.
- **Transition out:** hard cut.

### SHOT 5 - 0:16-0:22 - MED.EYE.STATIC -> HOLD
- **Motion:** CHIEF holds up a tiny paperback (smallest possible book -- thin, `BRAND_YELLOW` cover, almost comically small). He raises it ceremonially (6-frame slow lift to peak height). He reaches up to the tower's summit (4-frame). His finger releases the paperback (2-frame). It settles on top (2-frame settle). 4-frame HOLD (nothing happens -- tension). Then: the front-left table leg SNAPS (2-frame: the gap becomes a full break, the leg angles outward 15 degrees). **Music cuts on the CRACK sound.** The table surface tilts 5 degrees forward (3-frame tilt). The tower leans with it (3-frame lean). CHIEF's expression: 4-frame morph (smug mouth to open-O, squinted eyes to wide circles). He lunges (3-frame lunge, both arms extended toward tower). His hands push on the tower -- it wobbles MORE (4-frame violent shake from the touch). He pulls hands back (2-frame retract). The lean increases to 10 degrees (3-frame). Top 2 books begin sliding off the far side (they exit frame-top, foreshadowing C6).
- **Camera:** medium shot, static. CHIEF and tower centered vertically. The crack/tilt and expression change are clear mid-frame.
- **Motion graphics/FX:** The paperback is a tiny flat `BRAND_YELLOW` rectangle. The leg snap is a 2-frame rotation of the leg shape (0 to 15 degrees outward). The table tilt is a rotation of the table surface group. Tower lean follows table tilt. CHIEF's face morph: eyes scale 150%, mouth shape swap (line to O).
- **AUDIO CUE (critical):** music **cuts on the CRACK (0:16)**, leaving only sliding paper sounds and creaking wood.
- **Transition out:** hard cut.

### SHOT 6 - 0:22-0:27 - MED-WIDE.EYE.STATIC
- **Motion:** Three-wave collapse:
  - **Wave 1 (0:22-0:23.5):** Top 4 books slide off the tilting tower and fall (arc trajectory, 4-frame each). They hit CHIEF on the head sequentially (2-frame intervals): bonk (cap pushed down 3px), bonk (cap over eyes), bonk (CHIEF's knees bend), bonk (CHIEF staggers back one step). Each book bounces off and lands on the floor.
  - **Wave 2 (0:23.5-0:25):** The middle section loses cohesion. 6 books cascade simultaneously (multiple arc paths diverging outward, 4-frame flights). Two hit CHIEF's shoulders (2-frame impacts, he drops 3px). Two hit his chest (he doubles forward). Two fly past him to the floor. His arms flail (4-frame flail: arms up-out-up-out).
  - **Wave 3 (0:25-0:27):** The table fully collapses (4 legs splay outward simultaneously, 3-frame, the surface drops to the floor). The base wall of books (8+ volumes) slides forward as a unit (4-frame slide along the now-tilted surface) and hits CHIEF at knee level (2-frame impact). He topples backward (4-frame fall: upright-lean-tilt-flat). Books pile on top of him (6-frame settling, 10+ rectangles accumulating into a mound shape). Final state: a mound of books, CHIEF's cap visible on top (askew, tilted 30 degrees), one white-gloved hand poking out from the left side (fingers slightly spread).
- **Camera:** static medium-wide (pulled back to show full collapse trajectory and floor).
- **Motion graphics/FX:** Each book is a simple colored rectangle following an arc path (gravity curve). Impact frames: 1-frame `BRAND_YELLOW` impact star at hit point. The mound is layered rectangles in various colors creating a heap shape. Cap on top is the final element placed (settles last, 2-frame wobble).
- **Transition out:** hard cut.

### SHOT 7 - 0:27-0:31 - MED.EYE.STATIC -> PAN RIGHT
- **Motion (beat 1, 0:27-0:29):** The aftermath. Left side of frame: the collapsed table (legs splayed, surface flat on floor). The book mound sits where CHIEF stood -- a heap of colored rectangles. His cap on top, tilted 30 degrees. One white-gloved hand sticking out from the left side, fingers twitching (2-frame twitch cycle: fingers curl slightly then extend, repeated). A single page floats down from above (8-frame flutter path: side-to-side descent) and lands on the cap.
- **Motion (beat 2, 0:29-0:31):** Camera pans right to PIP. He sits on his `POP_TEAL` cushion, legs crossed, picture book open on his lap, reading lamp glowing warmly beside him on the low shelf. He turns a page (4-frame: finger slides under page edge, page lifts, page settles on other side). The most peaceful motion in the video. He looks up from the book toward camera (3-frame head lift). Above him on the wall: the "SHHH" sign, perfectly intact and unbothered. PIP gives a small head-tilt (3-frame: head rotates 10 degrees, hold) and a gentle close-mouthed smile (2-frame mouth curve).
- **Camera:** medium on book-mound (beat 1), smooth pan right (12-frame pan, constant speed) to PIP on cushion (beat 2). 1.5 s hold on PIP's reading + look-up.
- **Motion graphics/FX:** The floating page is a flat white rectangle rotating slowly (6 degrees per frame) during descent. Finger twitch is small-scale (2px curl). Page turn: page shape rotates on spine axis. The SHHH sign is static (a beacon of calm that has not moved all video).
- **AUDIO CUE:** music **returns at 0:27** -- warm resolve (glockenspiel + pizzicato melody).
- **Transition out:** hard cut.

### SHOT 8 - 0:31-0:32 - WIDE.EYE.STATIC (== SHOT 1 composition)
- **Motion:** Composition matches C1 exactly. The library wide shot: tall bookshelves (left, some gaps where CHIEF pulled books), collapsed table center (legs splayed flat, surface on floor), book mound with cap on top and gloved hand out. PIP stands beside his cushion on the right: his picture book is closed and placed neatly on the low shelf (spine facing out). He holds the round "SHHH" sign in his left hand (he took it off the wall -- the nail is visible on the bare wall) and points at it with his right hand, angled toward CHIEF's mound (3-frame: arm extends, finger points). He smiles. PIP turns to camera and gives his signature **small wave** (3-frame: hand up, wiggle-wiggle, hand down). A final book slides off the mound's peak and thuds on the floor (4-frame slide + 2-frame land).
- **Camera:** return to C1 wide framing. Hard cut. Loop seam: the bookshelves, the table position, the cushion, the SHHH sign location all match their C1 positions (minus the sign now in PIP's hand).
- **Motion graphics/FX:** The SHHH sign in PIP's hand is the same round white circle with text -- now a prop. The final book slide is a single colored rectangle moving along the mound slope and stopping on the floor. PIP's wave: standard 3-frame cycle (hand shape up at wrist, two lateral wiggles, return to side).
- **Transition out:** hard cut, seam to C1 (viewer replays and notices the table's sturdiness in C1, the floor cushion, and the SHHH sign from the start).

---

## B) Transitions & cut map (quick reference)

| Between | Type | Notes |
|---|---|---|
| C1->C2 | hard cut | table claimed; PIP redirects |
| C2->C3 | hard cut | from setup to vertical escalation |
| C3->C4 | hard cut | tower grows; table bows |
| C4->C5 | hard cut | the final paperback; the CRACK |
| C5->C6 | hard cut | three-wave collapse |
| C6->C7 | hard cut | aftermath reveal + PIP contrast |
| C7->C8 | hard cut | payoff pose, SHHH sign, loop seam |

---

## C) Loop seam verification

| Element | C1 (first frame) | C8 (last frame) | Match? |
|---|---|---|---|
| Bookshelves | full, colorful | some gaps (books removed) | near-match (acceptable -- shows consequence) |
| Table | center, intact, reading lamp on | center, collapsed, lamp on floor beside it | contextual match (same position) |
| SHHH sign | on back wall | in PIP's hand (wall shows nail) | position callback (the sign moved INTO the story) |
| Floor cushion | right side, empty | right side, PIP standing beside it | match |
| PIP position | entering from right | standing at right (same zone) | match |
| CHIEF position | entering from left | under mound at center-left | contextual match |
| Overall composition | wide library, warm `PAPER` tone | wide library, warm `PAPER` tone | match |
