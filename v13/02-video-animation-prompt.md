# v13 - Video-Generation Script / Prompt ("The Big Catch") - **SHORTS 9:16**

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or equivalent). It specifies **motion, camera angles, transitions, cut timing,
> motion-graphics and on-screen FX per shot**, so the generated output needs **minimal editing** -
> ideally just top-and-tail + audio layup. Everything aligns to the master timeline in
> `01-video-script.md` and audio in `03-audio-bgm-sfx-reference.md`.

**Global render spec:** **1080x1920 (9:16 vertical)** - 30 fps - ~32 s (~960 frames) - flat-2D cartoon
house style (thick uniform black outlines, no gradients, chunky 2.5-head proportions) - snappy pose-to-pose
with strong holds - **hard cuts only** (no dissolves/fades) - **no camera rotation/orbit, no handheld** -
**no blur/glow/gradients** - loop seam (C8 == C1).

**Motion philosophy:** limited animation - hold poses on comedy beats, animate in short bursts. v13's
structure builds tension through **accumulation** (each new attachment adds visible weight to the line)
then delivers the collapse through a single physics event (the snap). The key motion contrast is between
CHIEF's theatrical overloading and PIP's complete stillness.

Two contrasting motion languages:
- **CHIEF:** theatrical, showy gestures -- admiring each lure, polishing his reel, flexing his medals, winding up for a massive cast. Every action adds complexity.
- **PIP:** almost motionless. Three significant actions in the whole video: picks up the stick (C1), ties string (C2), lifts the fish (C7). In between he simply sits and waits. His stillness is the counterpoint.

> **The one rule that cannot break:** the **line sag must escalate monotonically** from C3 to C5.
> Each new attachment makes it droop lower. The catenary curve only deepens. Never let the sag
> reduce or the rod tip spring back up between additions.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** - subject motion - camera - transitions/FX - cut.

### SHOT 1 - 0:00-0:02 - WIDE.EYE.STATIC
- **Motion:** Peaceful pond scene. A shared tackle box (wooden, open lid) sits center-frame on the bank, visibly full of colorful gear. CHIEF storms in from frame-left and grabs items rapidly (4-frame grab cycle x4): the big rod, a fistful of lures, the reel, weights. He slams the empty box lid shut (2-frame slam). PIP approaches from frame-right, opens the box (3-frame), looks inside (empty - 2-frame blink), then spots the **stick** on the ground beside the box (3-frame look-down) and picks it up (3-frame pickup). The stick has a string already attached with a bent pin at the end.
- **Camera:** locked wide. The full pond, bank, box, and both characters visible. 6-frame settle hold to register both seeds (PIP's stick and the now-loaded rod).
- **Motion graphics/FX:** flat water with gentle 8-frame ripple cycle on the pond surface. Lures in the tackle box are flat colored shapes (chrome, green, red). The bent pin on PIP's string catches a small `BRAND_YELLOW` glint. No emphasis on either seed.
- **Transition out:** hard cut.

### SHOT 2 - 0:02-0:06 - MED.EYE.PUSHIN(slow)
- **Motion:** Medium two-shot on the bank. CHIEF holds up his loaded rod (already has reel attached, one large chrome lure dangling). He waves it back and forth mockingly (4-frame wave cycle x3), then points at PIP's bare stick (3-frame point). PIP calmly wraps his string around the stick tip -- three distinct wraps (2-frame each), ties a knot (2-frame pull), and the bent pin drops to dangle at the end of the string (2-frame swing). CHIEF sees this, looks at PIP's "rod," looks at his own magnificent rod, and laughs -- mouth wide, chest bouncing (6-frame laugh cycle).
- **Camera:** slow push-in (100% to 108%) ending on the two setups side by side in the frame: elaborate rod (left) vs. bare stick (right). The visual contrast is the joke being planted.
- **Motion graphics/FX:** one `BRAND_YELLOW` sparkle glint off CHIEF's reel (the vanity); PIP's knot-tying is precise and unhurried. No motion lines on PIP's movements -- keep them small and grounded.
- **Transition out:** hard cut.

### SHOT 3 - 0:06-0:11 - CLOSE-MED.EYE.STATIC
- **Motion:** Close-medium on CHIEF's rod and line. He clips on the second lure (a shiny chrome oval, 3-frame clip action + 2-frame admire). Then the third (a feathered lure, green and yellow, 3-frame clip + 2-frame admire). Then a lead weight (grey, heavy-looking, 3-frame clip -- the line visibly drops 8px lower). After each addition, the **line sags more**: a clear step-down in the catenary curve. CHIEF admires each one by holding it up to the light (4-frame hold) before clipping. In the right edge of frame: PIP's stick is propped on a small rock, the taut string running into the water, the bent pin invisible below the surface. The string is perfectly still.
- **Camera:** static close-medium; **4-frame hold after each new attachment** to let the audience register the additional sag. Three distinct sag levels in this shot.
- **Motion graphics/FX:** each lure/weight is a distinct flat colored shape. The line's sag is drawn as a simple curve that deepens in discrete steps (not animated continuously -- pose-to-pose). The water where PIP's pin sits has one gentle bobbing circle (4-frame cycle). Chrome lure has a 2-frame flat glint.
- **Transition out:** hard cut.

### SHOT 4 - 0:11-0:16 - MED.EYE.PUSHIN(slow)
- **Motion:** The overloading becomes absurd. CHIEF clips on: the **massive red bobber** (a `ALERT_RED` sphere the size of his fist -- 4-frame clip, the line DROPS visibly on attachment), then **two more lead weights** (grey, clipped in rapid succession, 2-frame each), then the **fourth lure** (a fancy multi-jointed metallic fish shape, 4-frame admire + clip). The line now forms a **deep catenary sag almost touching the ground** -- the gear cluster hangs heavy and low, swaying slightly (2-frame pendulum cycle). The rod tip bends downward under the static weight (visible bend, tip pointing at ~30 degrees). CHIEF does NOT look at the line -- he is polishing his reel housing with one glove and checking his medals' reflection in the chrome. PIP's string in the far right gives a small **2-frame twitch** (a nibble) then goes still.
- **Camera:** slow push-in (100% to 105%) framing the full depth of the line's sag prominently in the center of the vertical frame. The gear cluster dominates the lower third. 3-frame hold on each major addition (bobber, weights, final lure).
- **Motion graphics/FX:** the bobber is a large flat `ALERT_RED` circle that bounces once on attachment. The catenary line is drawn as a simple curve. The rod-tip bend is a clear angular change. The medal reflection is a 2-frame flat `BRAND_YELLOW` glint. PIP's string twitch is a simple 2-frame displacement then return. No sparkle on PIP.
- **Transition out:** hard cut.

### SHOT 5 - 0:16-0:22 - LOW.WIDE.STATIC -> HOLD
- **Motion:** CHIEF plants his feet wide on the bank (4-frame power-stance spread). Grips the rod with both hands (2-frame grip adjustment). He winds up for a MASSIVE CAST -- rearing back with full theatrical force (8-frame wind-up arc, the rod sweeping from front to far back). As the rod swings backward, the overloaded line and gear cluster follow in a heavy arc behind his head -- the four lures, three weights, and massive bobber all swinging in a weighty cluster, pulling the line taut at maximum extension. **The line stretches diagonally behind him against the sky**, vibrating visibly (1-frame oscillation cycle). Everything at breaking point. **HOLD** for 6 frames on this maximum-tension tableau: CHIEF mid-backswing, rod behind, line stretched, gear cluster hanging in the air behind his head.
- **Camera:** low angle looking up -- CHIEF's silhouette and the stretched line against the `SKY`-blue sky. Static hold once maximum tension is reached. The gear cluster is visible as dark shapes against the bright sky.
- **Motion graphics/FX:** flat motion lines on the initial wind-up sweep. The taut line is drawn as a single stressed line with small 1-frame lateral vibration. The gear cluster is a clump of distinct colored shapes. No blur on any motion.
- **AUDIO CUE (critical):** music **cuts mid-phrase on the frame the line reaches maximum tension (0:16)**, leaving only the thin vibration hum.
- **Transition out:** hard cut.

### SHOT 6 - 0:22-0:27 - WIDE.EYE.STATIC
- **Motion (beat 1, 0:22-0:23.5):** The line **SNAPS** at the rod tip (a clean 1-frame break -- the line separates into two pieces). The freed gear cluster -- still travelling in the backswing arc -- launches **backward over CHIEF's head** and flies toward the pond BEHIND him (6-frame flight arc, the cluster of shapes arcing over). It enters the water with a large flat **SPLASH** (4-frame splash burst using `SKY` shapes for water).
- **Motion (beat 2, 0:23.5-0:25):** Simultaneously, the rod (now bare) whips forward from the released energy (4-frame whip). The single empty hook on the remaining bit of line travels in a sad little arc and lands in the water in front of CHIEF with the tiniest, most pathetic *ploop* (a single 2-frame ripple ring, nothing more).
- **Motion (beat 3, 0:25-0:27):** CHIEF holds his follow-through pose (rod extended forward, one glove behind for balance) for 6 frames. Then **slow realization**: his head turns to look down at the bare line in front of him (4-frame turn). Then turns further to look behind him (4-frame turn) at the spreading ripple rings where his gear sank. The big red bobber surfaces for 8 frames (a flat red circle), then sinks below the surface (4-frame descent).
- **Camera:** wide shot covering the full scene: pond behind (splash zone), CHIEF in center, water in front (ploop zone). Static throughout -- let the physics and the realization play in real time.
- **Motion graphics/FX:** the snap is a 1-frame break (line becomes two segments). The flying cluster uses flat motion lines. The back-splash is large (flat `SKY` shapes, 4-frame burst). The front-ploop is tiny (one circle, 2 frames). The bobber surfaces as a flat red circle, then sinks. Ripple rings spread concentrically (3-frame expansion cycle). No blur on anything.
- **Transition out:** hard cut.

### SHOT 7 - 0:27-0:31 - MED-WIDE.EYE.STATIC -> SETTLE
- **Motion (beat 1, 0:27-0:29):** PIP's stick **twitches** (2-frame displacement). His string goes taut (1-frame snap to straight). PIP lifts the stick with one hand (6-frame lift, smooth and unhurried). A small **fish** emerges from the water on the bent pin -- it dangles, wriggles happily (4-frame wiggle cycle, repeating). It is small, modest, but real. PIP smiles (3-frame smile transition).
- **Motion (beat 2, 0:29-0:31):** PIP holds the fish up. The camera shows both characters: PIP (right) with fish on a stick, calm and smiling; CHIEF (left) still holding his bare rod over empty water, staring at his single naked hook dangling limply in the water. CHIEF's expression: shocked -> dejected (4-frame snap). **0.5 s freeze on this contrast.**
- **Camera:** medium-wide, static. Quick 4-frame punch-in on the wriggling fish, then settle back to the two-shot contrast. The 0.5 s hold is on the wide contrast framing.
- **Motion graphics/FX:** the fish is a small flat `POP_TEAL`/`SKY` shape with flat fins and a happy eye-dot. Its wiggle is a simple 4-frame lateral oscillation. Water drops fall off it (2 flat drops, 3-frame fall). No sparkle on PIP or the fish. `FX_impact_star_v1` optional on the initial twitch.
- **AUDIO CUE:** music **SLAMS back** at 0:27 on the stick twitch; the fish's *splish* emerges is the bright punctuation.
- **Transition out:** hard cut.

### SHOT 8 - 0:31-0:32 - WIDE.EYE.STATIC (== SHOT 1)
- **Motion:** Composition matches C1. The same pond, same bank. CHIEF slumped on the bank, bare rod drooping across his lap, the empty tackle box open beside him (mirrors C1's setup but inverted -- in C1 it was full, now it is empty like his rod). PIP stands beside him, **holding out the small fish** toward CHIEF (4-frame extend -- offering to share, expression kind, no smirk). CHIEF gingerly takes the fish with one trembling glove (3-frame reach). PIP turns to camera and gives a **small wave** (3-frame wave). In the background pond, a single **bubble** rises from where the gear sank (4-frame rise and pop).
- **Camera:** return to the exact C1 wide framing. Same bank, same tackle box position, same pond. Hard cut out within 1 s after the wave.
- **Motion graphics/FX:** the bubble is a single flat circle that rises and pops (a flat ring burst). The fish in hand is still (no wiggle needed at this scale). No residual FX on the final frame. The empty tackle box and bare rod tell the visual story of inversion.
- **Transition out:** hard cut, seam to C1 (the viewer replays and notices the stick-and-string and the original sag).

---

## B) Transitions & cut map (quick reference)
| Between | Type | Notes |
|---|---|---|
| C1->C2 | hard cut | establishing to two-shot |
| C2->C3 | hard cut | to close-medium on the loading |
| C3->C4 | hard cut | continued escalation (wider to show full sag) |
| C4->C5 | hard cut | into the cast wind-up |
| **C5 internal (0:16)** | **music cut only -- no visual cut** | the tension is achieved by removing the score |
| C5->C6 | hard cut | to the wide snap/splash shot |
| **C6 internal (~0:25)** | 0.5 s hold on follow-through pose | CHIEF frozen before the realization turn |
| C6->C7 | hard cut | to the fish reveal |
| **C7 internal (0:29)** | 0.5 s hold | PIP with fish vs. CHIEF with nothing -- the contrast freeze |
| C7->C8 | hard cut | payoff |
| C8->(loop) | hard cut, seam to C1 | replay re-reads the stick, the line sag, and the gear cluster |

**No** dissolves, fades, wipes, glitch, zoom-blur, or camera rotation anywhere. Effects are limited to:
flat splash shapes, flat ripple circles, flat motion lines, the bobber circle, the fish shape, water
drops, and the listed holds/freezes.

---

## C) Optional single "master prompt" (for one-shot generators)
```
{style prefix -- 9:16 VERTICAL, flat-2D cartoon, thick black outlines, no gradients}
A ~32s 9:16 flat-2D cartoon comedy short, 30fps, hard cuts only, no camera rotation, no blur or glow,
snappy pose-to-pose animation with strong holds. Recurring cast: CHIEF, a pompous rotund braggart in a
teal jacket with an oversized peaked cap and a yellow medal sash; PIP, a tiny underdog with a teal scarf.
Setting: a peaceful pond with a flat bank. A shared TACKLE BOX sits between two fishing spots. A bare
STICK with a string and bent pin lies on the ground beside the box.
Story in 8 beats:
(0-2s) WIDE static: CHIEF storms over and grabs EVERYTHING from the shared tackle box (rod, reel, all
lures, weights, bobber). Slams empty box shut. PIP picks up a BARE STICK with string and bent pin from
the ground beside the box.
(2-6s) MED push-in: CHIEF holds up his enormous loaded rod mockingly. PIP calmly ties his string to the
stick, bent pin dangling. CHIEF laughs, pointing at PIP's pathetic setup. Contrast clear: elaborate vs bare.
(6-11s) CLOSE-MED static: CHIEF clips on a SECOND lure, a THIRD lure, and a LEAD WEIGHT. Line visibly SAGS
lower with each addition. He admires each before clipping. PIP has already cast -- pin bobbing in water.
(11-16s) MED push-in: CHIEF adds a MASSIVE RED BOBBER (fist-sized), TWO MORE WEIGHTS, a FOURTH LURE. Line
now sags almost to GROUND -- a heavy catenary. Rod tip bends. CHIEF polishes reel, oblivious. PIP's string
twitches once (a nibble).
(16-22s) LOW WIDE: CHIEF winds up for a MASSIVE CAST. Rears back -- the overloaded gear swings behind him in
a heavy arc. Line STRETCHES TAUT at maximum tension against the sky, vibrating. MUSIC CUTS TO SILENCE. Hold.
(22-27s) WIDE static: in silence, the line SNAPS at the rod tip. All gear launches BACKWARD over his head
into the pond BEHIND him (large splash). Rod whips forward bare -- empty hook plops into water in front
(tiny pathetic ploop). CHIEF frozen in follow-through, turns slowly to see ripples where gear sank. Red
bobber surfaces, then sinks.
(27-31s) MED-WIDE: PIP's stick twitches. He lifts it -- a small FISH dangles from the bent pin, wriggling
happily. Beside him, CHIEF holds a bare rod over empty water. 0.5s hold on the contrast.
(31-32s) WIDE, framing identical to opening: CHIEF slumped, bare rod in lap, empty box beside him. PIP
offers the fish, kindly sharing. PIP waves. A bubble rises from where gear sank. Hard cut.
ZERO on-screen text anywhere. CHIEF never loses cap/sash/medals. PIP never gloats. Line sag only
INCREASES. CHIEF never looks at the line before the snap. Advertiser-safe: the fish is happy and unharmed,
CHIEF is merely empty-handed and embarrassed, no hook injuries, no one falls in.
```

---

## D) Handoff / minimal-edit checklist
- [ ] **Rendered 9:16 / 1080x1920**, total ~32 s, on the locked 8-clip skeleton.
- [ ] Assemble C1->C8 with **hard cuts**; add no transitions.
- [ ] Insert the holds/freezes: C1 6-frame settle - C3 4-frame after each attachment - C4 3-frame on each addition - C5 6-frame maximum-tension hold - C6 0.5 s follow-through freeze, 8-frame bobber surface - C7 **0.5 s contrast freeze** (fish vs. nothing).
- [ ] **Verify Seed A:** stick-and-string visible in C1 when PIP picks it up, and catches fish in C7.
- [ ] **Verify Seed B:** line sag visible from C3 and escalating through C5 -- four distinct sag levels.
- [ ] **Verify sag monotonic:** catenary curve only deepens, rod tip only bends further. Never rebounds.
- [ ] **Verify CHIEF never looks at the line** before C6. Always looking at lures, reel, or medals.
- [ ] Verify the snap is caused by **weight alone** -- no wind, no external pull, no fish tugging.
- [ ] Verify the gear flies **backward** (following backswing momentum) and the rod whips **forward** bare.
- [ ] Verify PIP catches a **modest, happy** fish and **never gloats** (calm smile, offers to share).
- [ ] Confirm music cuts at 0:16 (maximum tension frame) with no visual cut.
- [ ] Confirm the **SNAP at 0:22** is the loudest sound in the silence beat.
- [ ] Confirm PIP's **stick twitch (0:27)** syncs with the music slam-back.
- [ ] Verify loop seam: C8 and C1 share the same pond-and-bank composition; background matches.
- [ ] Lay VO and BGM/SFX onto fixed timecodes -- everything pre-synced.
- [ ] Final QC: no baked text, no blur/glow, cast on-model, fish happy and unharmed, no hook injuries, no falling in water, PIP kind and calm.
