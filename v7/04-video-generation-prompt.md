# v7 — Video-Generation Script / Prompt ("The Big One") · **SHORTS 9:16**

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or Anijam driving the stills from file 02). It specifies **motion, camera angles,
> transitions, cut timing, motion-graphics and on-screen FX per shot**, so the generated output needs
> **minimal editing** — ideally just top-and-tail + audio layup. Everything aligns to the master
> timeline in `01-video-script.md`, the visuals in `02`, VO in `03`, and audio in `05`.

**Global render spec:** **1080×1920 (9:16 vertical)** · 30 fps · ~32 s (≈960 frames) · flat-2D cartoon
house style (file 02 §0) · snappy pose-to-pose with strong holds · **hard cuts only** (no dissolves/fades)
· **no camera rotation/orbit, no handheld** · **no blur/glow/gradients** · loop seam (C8 == C1).

**Motion philosophy:** limited animation — hold poses on comedy beats, animate in short bursts. v7 has an
unusual structure: **almost nothing happens for twenty-one seconds.** CHIEF gloats and the canopy sags.
That stillness is the design — the tension comes entirely from a slow, continuous, one-directional load
that the audience watches accumulate. Resist the urge to add business.

Two contrasting motion languages:
- **CHIEF:** big, wide, theatrical gestures, all at chest height and above — and **he never once tilts his head up.**
- **PIP:** almost perfectly still. Three small movements in the whole video: he is shoved (C1), he raises a hand to warn (C6), he offers his umbrella (C8).

> **The one rule that cannot break:** from C3 to C7, **CHIEF stands inside the gutter's drip line.** Mark
> that spot on the ground plate and never let him drift off it. Everything else is decoration.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** — subject motion — camera — transitions/FX — cut.

### SHOT 1A — 0:00—0:015 — CU.EYE.STATIC  *(cold payoff — replaces the old wide establishing shot)*
- **Motion:** An enormous umbrella canopy, filling the frame, sagging like a full waterskin — the fabric bulging downward, one fat seam of water walking along the rib toward the low point. It tips a few degrees further. Cut before it empties. The motion is **already at full speed on frame 1** — there is no entrance, no settle, no push-in from a wide, and no character walks into shot.
- **Camera:** locked tight CU. The subject fills the frame. **Zero settle time.** Frame 1 is mid-event.
- **Motion graphics/FX:** flat impact shapes only — no glow, no blur, no gradients. Palette tokens only.
- **Transition out:** hard cut on the beat, *before* the event resolves.

### SHOT 1B — 0:015—0:02 — MED.EYE.STATIC  *(goal diagram)*
- **Motion:** Hard cut to the shop doorway: a chalk-pale **dry patch** outlined on the wet pavement under the awning — the one spot that stays dry — with the broken gutter mouth directly above it, dripping. Two umbrellas in the stand beside it: one a deep bowl, one small and flat. PIP is already in frame, in shot, holding the small flat umbrella over himself and standing just outside the dry patch — same task, smaller method, no complaint.
- **Camera:** locked medium-wide, held. **This exact framing returns in SHOT 8 for the loop seam.**
- **On-frame text:** **none baked into the render.** The 3—7 word hook caption *"This umbrella is full"* is an **edit-layer overlay**, placed clear of the bottom bar and the right-hand action rail.
- **Transition out:** hard cut.

### SHOT 2 — 0:02–0:06 · MED.EYE.PUSHIN(slow)
- **Motion:** CHIEF seizes the enormous umbrella and **snaps it open in one big 4-frame flourish**, the deep bowl-shaped canopy unfurling with a 2-frame overshoot bounce. He gloats down at PIP, chest out. PIP calmly takes the tiny flat umbrella and pops it open (small 3-frame action, no reaction to the shove).
- **Camera:** slow push-in (100%→110% over 4 s), **ending framed on the deep bowl of the open canopy** — the audience must clearly register that it is a bucket.
- **FX:** rain streaks increasing in density; a couple of drops bouncing off the taut new canopy.
- **Transition out:** hard cut.

> **This is the fair-play moment.** By 0:06 the audience has seen the water source and the bucket. Show the
> canopy's depth clearly and move on — *shown, not sold.*

### SHOT 3 — 0:06–0:11 · WIDE.EYE.STATIC
- **Motion:** rain thickens. CHIEF struts three steps and **plants himself directly beneath the broken gutter** (mark this position), then twirls the huge umbrella and gloats across at PIP. Above and behind his head, the gutter's drip **becomes a steady trickle running into the canopy.** He does not look up. PIP stands dry a few steps clear.
- **Camera:** locked wide; **4-frame hold at the moment the trickle first enters the canopy** — the only nudge the audience gets.
- **Motion graphics/FX:** the trickle as a thin continuous flat `SKY` ribbon (2-frame cycle, no blur); rain streaks denser; `FX_motionlines_v1` on the umbrella twirl.
- **Transition out:** hard cut.

### SHOT 4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight)
- **Motion:** rain at full intensity; the gutter is now **pouring**. The canopy **sags in three discrete visible stages** (~1.6 s apart): shallow bow → clear droop with a visible pool → deep distended bowl with the shaft starting to lean. CHIEF gestures grandly at his own umbrella, then dismissively at PIP's tiny one, chest out, chin high. **Still never looks up.** PIP blinks placidly, completely dry.
- **Camera:** slight push-in (100%→104%); **3-frame hold on each of the three sag stages**.
- **Motion graphics/FX:** the pour as a thicker flat ribbon; the water pool inside the canopy visible as a flat `SKY` shape that grows with each stage; the shaft's lean increasing; one sparkle glint off a medal at ~0:15.
- **Transition out:** hard cut.

### SHOT 5 — 0:16–0:22 · FULL.LOW.PUSHIN → HOLD
- **Motion:** CHIEF plants an enormous triumphant pose — chest out, chin high, one glove on his hip — and **holds it** (~1.5 s of true freeze). Above him the canopy is hugely distended, water visibly heavy inside, the shaft bowing. The pour continues into it, unchanged and indifferent.
- **Camera:** low hero angle, gentle push-in settling into the hold. **Frame it so the bulging canopy dominates the top third** — the audience should be looking at the bomb while CHIEF poses beneath it.
- **Motion graphics/FX:** `FX_sparkle_v1` self-satisfaction accents around CHIEF; the pool inside the canopy at maximum; a faint flat strain-line or two on the taut fabric.
- **AUDIO CUE (critical):** the **music cuts mid-phrase on the frame he plants the pose (0:16)**, leaving the pour exposed as the loudest sound. See file 05.
- **Transition out:** hard cut.

### SHOT 6 — 0:22–0:27 · MED.EYE.STATIC → TILT-UP
- **Motion:** the canopy reaches its limit — fabric taut, shaft clearly bending, one or two drops escaping over the rim. **PIP steps forward and raises a small hand to warn him**, mouth opening (4-frame move). **CHIEF, without looking, raises one glove in a "don't interrupt" gesture** and keeps posing (3-frame move). PIP lowers his hand, glances up at the canopy, and **quietly takes one step back** (4-frame move).
- **Camera:** static two-shot for the warning exchange, then a **slow tilt up** to the straining canopy at ~0:25 and hold there.
- **Motion graphics/FX:** flat strain lines on the fabric increasing; 2 drops slipping over the canopy's rim. Deliberately no sparkle — restraint carries the dread.
- **Transition out:** hard cut.

> **PIP's step back is the most important small action in the video.** It must be clearly visible and
> completely undramatic — the quiet competence of someone who looked up.

### SHOT 7 — 0:27–0:31 · MED.EYE.PUNCHIN → SETTLE
- **Motion (beat 1, 0:27–0:29):** CHIEF makes his big finishing move — he **sweeps the enormous umbrella down and forward to point mockingly at PIP** (fast 6-frame arc). The canopy tips past horizontal and the entire accumulated reservoir cascades out **straight down over his own head** (a single large flat `SKY` water mass, 8 frames of fall, then a flat ground splash burst).
- **Motion (beat 2, 0:29–0:31):** CHIEF is instantly and completely drenched — hair flattened, sash sodden, medals drooping, mustache limp, cap slumped over one eye. He blinks once, slowly. His face runs the **3-stage snap** triumphant → shocked → panicked. Two steps away, PIP is **bone dry** under his tiny umbrella.
- **Camera:** **quick punch-in** on the tipping canopy (~6 frames), then settle back to a wide; **0.5 s freeze on drenched CHIEF beside bone-dry PIP** (the screenshot-able punchline — the contrast *is* the joke).
- **Motion graphics/FX:** flat water mass and splash burst (hard-edged shapes, **no blur, no transparency gradients**); `FX_impact_star_v1` on the ground impact; `FX_motionlines_v1` on the umbrella sweep; optional 1-frame white flash. One last drop hanging off his nose.
- **AUDIO CUE:** music **SLAMS back** at 0:27 on the tipping canopy; the **SPLASH at 0:29 is the loudest sound in the video** (file 05).
- **Transition out:** hard cut.

### SHOT 8 — 0:31–0:32 · WIDE.EYE.STATIC (== SHOT 1)
- **Motion:** drenched CHIEF stands in a shallow puddle, the emptied giant umbrella hanging **limp and inverted** in his glove. Beside him, **PIP holds out his tiny teal umbrella** — offering it plainly, no gloating, no smirk (4-frame extend). CHIEF hunches under it, far too big for it, mortified. PIP turns and gives a small wave to camera. **One last drop falls from the gutter.**
- **Camera:** return to the **exact SHOT-1 framing** — same background plate, same gutter position, same splash mark on the ground. Only the rain state, the umbrellas and the cast's condition differ.
- **Motion graphics/FX:** rain easing slightly; the puddle at his feet with two small ripple rings. **No sparkle on PIP** — his kindness should read as ordinary, not saintly. No residual FX on the final frame (loop must be clean).
- **Transition out:** **hard cut** ≤1 s after the wave, seaming back to SHOT 1.

---

## B) Transitions & cut map (quick reference)
| Between | Type | Notes |
|---|---|---|
| C1→C2→C3→C4 | hard cut | snappy 2–5 s clips |
| C4→C5 | hard cut | into the victory pose |
| **C5 internal (0:16)** | **music cut only — no visual change** | the pattern break is achieved by *removing the score*, not by cutting |
| C5→C6 | hard cut | to the warning exchange |
| **C6 internal (~0:25)** | slow tilt-up + hold | the straining canopy |
| C6→C7 | hard cut into **punch-in** | the twist |
| **C7 internal (0:29)** | 0.5 s freeze | drenched CHIEF beside bone-dry PIP |
| C7→C8 | hard cut | payoff |
| C8→(loop) | hard cut, seam to C1 | replay re-reads the gutter and the canopy's shape |

**No** dissolves, fades, wipes, glitch, zoom-blur, or camera rotation anywhere. Effects are limited to:
flat rain streaks, flat splash pops, flat water ribbons and masses, dust-free ground splash bursts,
motion lines, strain lines, sparkle, impact-star, one optional flash, and the listed holds/freezes.

> **The key craft note for v7:** the water must be rendered as **hard-edged flat `SKY` shapes** at every
> stage — a ribbon for the trickle, a thicker ribbon for the pour, a flat pool shape inside the canopy, and
> one large flat mass for the dump. No transparency gradients, no soft edges, no particle spray, no motion
> blur. Cartoon water in this house style is a *shape*, not an effect.

---

## C) Optional single "master prompt" (for one-shot generators)
```
{style prefix from file 02 §0 — 9:16 VERTICAL}
A ~32s 9:16 flat-2D cartoon comedy short, 30fps, hard cuts only, no camera rotation, no blur or glow, all
water rendered as hard-edged flat SKY-blue shapes (never soft or transparent), snappy pose-to-pose
animation with strong holds. Recurring cast: CHIEF, a pompous rotund braggart in a teal jacket with an
oversized peaked cap and a yellow medal sash; PIP, a tiny underdog with a teal scarf. Setting: a rainy
PAPER-coloured shop front on grey pavement, with a BROKEN GUTTER above the doorway dripping water, and an
umbrella stand holding ONE ENORMOUS BOWL-SHAPED YELLOW UMBRELLA and ONE TINY FLAT TEAL UMBRELLA.
Story in 8 beats:
(0-2s) WIDE static: first raindrops; a single drop falls from the broken gutter onto the pavement below it;
CHIEF struts in and SHOVES tiny PIP aside, eyeing the big umbrella.
(2-6s) MED slow push-in: CHIEF snaps the enormous umbrella open with a flourish — its canopy is clearly a
DEEP BOWL — and gloats down at PIP, who calmly takes the tiny flat one.
(6-11s) WIDE: rain thickens; CHIEF struts over and plants himself DIRECTLY BENEATH THE BROKEN GUTTER to
gloat, and the gutter's drip becomes a steady TRICKLE RUNNING INTO HIS CANOPY. He never looks up.
(11-16s) MED-WIDE: rain at full intensity, the gutter POURING; the huge canopy VISIBLY SAGS in stages, a
pool of water deepening inside it, the shaft beginning to lean. CHIEF gloats harder, gesturing at his
umbrella then at PIP's tiny one. Still never looks up. PIP is perfectly dry.
(16-22s) LOW hero angle: CHIEF plants a huge triumphant pose, the hugely distended water-heavy canopy
straining above him and dominating the top of frame. MUSIC CUTS TO SILENCE — only the pouring continues.
(22-27s) Static then slow tilt up: the canopy at its limit, fabric taut, shaft bending, a couple of drops
escaping the rim. PIP raises a hand to warn him; CHIEF raises a glove without looking as if to say DON'T
INTERRUPT; PIP quietly takes one step back.
(27-31s) MED quick punch-in: CHIEF SWEEPS THE UMBRELLA DOWN to point mockingly at PIP — and the entire
reservoir cascades straight down over HIS OWN HEAD. He is instantly drenched: hair flat, sash sodden, medals
drooping, cap slumped over one eye, blinking. PIP two steps away is BONE DRY. 0.5s freeze on the contrast.
(31-32s) WIDE, framing identical to the opening: drenched CHIEF in a puddle holding the limp inverted
umbrella; PIP kindly HOLDS OUT his tiny teal umbrella and CHIEF hunches under it, mortified; PIP waves to
camera; one last drop falls from the gutter. Hard cut.
ZERO on-screen text anywhere. CHIEF never loses his cap/sash/medals (sodden and drooping is fine). PIP
never gloats. CHIEF stands under the gutter from beat 3 to beat 7 and NEVER looks up before the twist. The
canopy sag only ever INCREASES. Advertiser-safe: CHIEF is merely wet and embarrassed — no shivering,
coughing, illness, lightning, storm danger or slipping.
```

---

## D) Handoff / minimal-edit checklist
- [ ] **Rendered 9:16 / 1080×1920**, total ≈32 s, on the locked 8-clip skeleton.
- [ ] Assemble C1→C8 with **hard cuts**; add no transitions.
- [ ] Insert the holds/freezes: C1 6-frame settle · C3 4-frame first-trickle hold · C4 3-frame on each of three sag stages · C5 ~1.5 s victory hold · C6 tilt-up hold on the straining canopy · C7 **0.5 s wet/dry contrast freeze**.
- [ ] **Verify Seed A:** the broken gutter and its splash mark on the pavement are legible in C1 without emphasis, and the gutter is in the **same screen position** in C1, C3, C4, C5, C6, C8.
- [ ] **Verify Seed B:** the canopy's bowl depth is unmistakable in C2.
- [ ] **Verify the position invariant: CHIEF is inside the gutter's drip line in every frame of C3–C7.** Scrub for drift.
- [ ] **Verify CHIEF never looks up** before C7. Not one frame.
- [ ] **Verify the sag is monotonic:** three discrete stages in C4, maximum in C5–C6, never rebounding.
- [ ] Verify the water pool inside the canopy is always consistent in volume with the sag.
- [ ] **Verify the trigger:** the dump is caused by **his own pointing sweep** — no wind, no external agent, no accident.
- [ ] Verify PIP is **completely dry** in C7 and C8, and **never gloats** (no smirk, no pointing, no sparkle).
- [ ] Confirm the **music cuts at 0:16 with no visual cut**, and the pour runs exposed through to 0:27.
- [ ] Confirm the **0:01 drip** and **PIP's 0:25 step back** are audible and unmasked (file 05 §5).
- [ ] Confirm the **0:29 splash** is the loudest moment with ~3 dB headroom before it.
- [ ] Verify loop seam: overlay C8 on C1 — background plate, framing, gutter and splash mark must match.
- [ ] Lay VO (file 03) and BGM/SFX (file 05) onto the fixed timecodes — everything is pre-synced.
- [ ] Final QC: no baked text, no blur/glow, all water is flat hard-edged shapes, cast on-model, CHIEF wet but unharmed, no storm/lightning/slip hazard, PIP kind and dry.
