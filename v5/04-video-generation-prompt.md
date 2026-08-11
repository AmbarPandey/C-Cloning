# v5 — Video-Generation Script / Prompt ("The Case of the Missing Pie") · **LONG FORM 16:9**

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or Anijam driving the stills from file 02). It specifies **motion, camera angles,
> transitions, cut timing, motion-graphics and on-screen FX per shot**, so the generated output needs
> **minimal editing** — ideally just assembly plus the audio layup. Everything aligns to the master
> timeline in `01-video-script.md`, the visuals in `02`, VO in `03`, and audio in `05`.

**Global render spec:** **1920×1080 (16:9 horizontal)** · 30 fps · **1:30 (90 s / 2700 frames)** ·
flat-2D cartoon house style (file 02 §0) · snappy pose-to-pose with strong holds · **hard cuts only**
(except the three specified continuous moves) · **no camera rotation/orbit, no handheld** ·
**no blur/glow/gradients** · loop seam (S16 final frame == S1 first frame).

**Motion philosophy:** limited animation — hold poses on comedy beats, animate in short bursts. v5 is a
**four-cycle escalation**: three investigation cycles (accuse → examine → cross off), each performed
bigger than the last, then a collapse. CHIEF is always in motion and always wrong; PIP barely moves at
all and is always right. That contrast is the comedy, so **keep PIP still** — his single deliberate action
(the point at S13) lands hard precisely because he has done nothing for 62 seconds.

> **Three continuous moves only** (everything else is a hard cut):
> **1)** S1's pull-back from plate to CHIEF · **2)** S14's 10-second eyeline track · **3)** S15's pull-back
> to the full geometry. Each is a reveal; nothing else should move the camera.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** — subject motion — camera — transitions/FX — cut.

### ACT 1 — THE CRIME (0:00–0:12)

#### SHOT 1 — 0:00–0:03 · ECU→MED.EYE.PULLOUT
- **Motion:** frames 0–30: **nothing moves.** A dead-still extreme close-up of the empty plate. Then a fast pull-back as CHIEF's head snaps into frame right, mouth opening into a huge gasp (3-key snap), glove flying up.
- **Camera:** locked ECU for a full second, then a **fast continuous PULLOUT** to a medium.
- **FX:** flat `FX_shocklines_v1` burst behind CHIEF's head on the gasp.
- **Audio note:** the first second has **no music** — see file 05 cue 1. The stillness plus silence is the hook.
- **Transition out:** hard cut.

#### SHOT 2 — 0:03–0:07 · WIDE.EYE.STATIC · **SEED SHOT**
- **Motion:** CHIEF plants a boot on a crate, then performs **two casual, incidental actions in one continuous move**: he leans the heavy ledger against the stall table leg (the table visibly tips a few degrees, 4-frame settle) and sets his open evidence box on the ground behind the stall (2-frame settle). Neither action is emphasised — he isn't even looking. Meanwhile PIP nibbles a biscuit; BUD's chest rises with a snore; MITTENS blinks once.
- **Camera:** locked wide. **Hold the full 4 seconds** — this is the longest static shot in Act 1 and both seeds must read clearly without being pointed at.
- **FX:** small flat dust puff as the ledger lands. **No sparkle, no emphasis, no highlight on either seed** — they must look like set dressing.
- **Transition out:** hard cut.

> **This is the most important shot in the video.** Everything the audience needs to solve the mystery is
> here. Render it clean, well-lit and unhurried — but never draw attention to the ledger or the box. The
> fair-play contract is: *shown, not sold.*

#### SHOT 3 — 0:07–0:12 · MED.EYE.PUSHIN(slow)
- **Motion:** CHIEF whips the magnifier up (fast 3-frame arc), his eye ballooning comically through the lens (hold 6 frames), flicks open the notebook, and sweeps the lens across the square in a slow 2-second arc. Crowd silhouettes lean in as he passes.
- **Camera:** slow push-in (100%→108%).
- **FX:** a flat lens-glint chevron as the magnifier catches the light; his eye scales ~1.6× behind the glass.
- **Transition out:** hard cut.

### ACT 2 — SUSPECT 1: BUD (0:12–0:28)

#### SHOT 4 — 0:12–0:17 · MED.EYE.WHIP-PAN → STATIC
- **Motion:** the lens stops. CHIEF gasps (M size) and spins to point his whole arm at BUD — medals jangling on the swing (3-frame overshoot then settle). BUD does not stir; his tail twitches once.
- **Camera:** short **whip-pan** to BUD (~7 frames) settling into a locked medium two-shot.
- **FX:** `FX_motionlines_v1` on the arm swing; small `FX_shocklines_v1` on the gasp.
- **Transition out:** hard cut.

#### SHOT 5 — 0:17–0:23 · ECU→MED.EYE.PULLOUT
- **Motion:** magnifier descends onto BUD's muzzle — **spotless** (hold 10 frames on the clean muzzle). Pull back: CHIEF tugs BUD's lead taut (2-frame snap), then measures the gap between dog and table with two gloved fingers, walking them through the air. His grin sags across 8 frames.
- **Camera:** ECU on the muzzle → **PULLOUT** revealing the taut lead and the gap.
- **FX:** flat lens-glint on the inspection; `FX_motionlines_v1` on the lead snap.
- **Transition out:** hard cut.

#### SHOT 6 — 0:23–0:28 · MED.EYE.STATIC · **micro-payoff + seed glimpse**
- **Motion:** CHIEF drags a huge crossing-out through the notebook (one big 6-frame diagonal stroke). BUD wakes, delivers an **enormous 12-frame yawn**, and flops back to sleep. Hold on the flop.
- **Camera:** locked medium. **At 0:26, for ~3 frames only:** as CHIEF's elbow swings past, a thin golden filling smear on the table's back edge is briefly un-occluded, then hidden again.
- **FX:** none beyond the seed glimpse. Keep the frame clean so the yawn owns it.
- **Transition out:** hard cut.

### ACT 3 — SUSPECT 2: MITTENS (0:28–0:44)

#### SHOT 7 — 0:28–0:33 · LOW.MED.STATIC → cut to FLAT MED
- **Motion:** CHIEF spins 180°, steps **up onto a crate** (2-step climb), and delivers a bigger, more operatic point — both glove and magnifier extended, chest thrown out, held for 10 frames. Hard cut to MITTENS: perfectly still, one slow blink.
- **Camera:** low hero angle on CHIEF for maximum pomposity; then a deliberately **flat, unimpressed eye-level medium** on the cat — the framing itself is the joke.
- **FX:** `FX_shocklines_v1` (larger) behind CHIEF; nothing at all on the cat.
- **Transition out:** hard cut.
- **RET:** this is **pattern interrupt #1** — new suspect, new staging side, bigger performance, landing at the ~0:30 drop-off point.

#### SHOT 8 — 0:33–0:39 · MED-WIDE.EYE.STATIC
- **Motion:** CHIEF stretches a tape measure between MITTENS and the plate (zip out, 4-frame snap-taut). He looks tape → cat → tape (3 discrete head turns, 8 frames each). Then he **mimes** carrying a huge round pie with tiny paws — arms curling into an impossible shape, held 6 frames.
- **Camera:** locked medium-wide; **4-frame hold on the mime**.
- **FX:** flat measurement chevrons along the tape; `FX_motionlines_v1` on the snap.
- **Transition out:** hard cut.

#### SHOT 9 — 0:39–0:44 · MED.EYE.STATIC · **micro-payoff + seed glimpse**
- **Motion:** a second crossing-out (6-frame stroke); the notebook now shows two scribbled-out lines. MITTENS licks a paw (2 cycles) and turns away. CHIEF's mustache twitches twice.
- **Camera:** locked medium. **At 0:41, in the background, ~50% occluded by a crate:** the table's tilt is now clearly greater and **a single drop of filling forms and falls** off the back edge. Roughly 8 frames, deliberately unemphasised.
- **FX:** none beyond the seed glimpse.
- **Transition out:** hard cut.

### ACT 4 — THE CASE AGAINST PIP (0:44–1:08)

#### SHOT 10 — 0:44–0:50 · PUSHIN → MED
- **Motion:** slow push onto PIP mid-bite; a few crumbs on his teal scarf come into clear view. PIP freezes, eyes widening (3-key). CHIEF advances from frame right, magnifier thrust forward, and delivers the **largest gasp of the video** (XL, 5-key snap, held 8 frames).
- **Camera:** slow **PUSHIN** onto the crumbs (100%→118%), then settle to a medium two-shot.
- **FX:** large flat `FX_shocklines_v1` in `ALERT_RED` behind CHIEF; a lens-glint on the magnifier.
- **Transition out:** hard cut.
- **RET:** the stakes turn personal and unjust here — the strongest retention driver in the episode.

#### SHOT 11 — 0:50–0:56 · MED-WIDE.EYE.PUSHIN(slight)
- **Motion:** CHIEF slams up the corkboard (3-frame impact), then **pins three photos in sequence** (pin thunks at 0:51 / 0:52 / 0:53, each a 3-frame hold), pulls a red string taut between them, and taps the board three times like a professor. PIP shrinks further with each tap.
- **Camera:** slight push-in (100%→106%); **3-frame hold on each tap**.
- **FX:** `FX_motionlines_v1` on the string pull; small dust puff on each pin.
- **Transition out:** hard cut.

#### SHOT 12 — 0:56–1:02 · LOW.MED.STATIC · **PEAK INJUSTICE**
- **Motion:** CHIEF hoists the giant stamp above his head in a slow 20-frame rise and **holds it at the top of the arc** for a full second. PIP curls into a tiny ball at the bottom of frame (8-frame compress), eyes welling. BUD whines. Crowd silhouettes freeze mid-inhale.
- **Camera:** dramatic **low angle**, stamp huge at the top of frame, PIP tiny at the bottom — maximum status gap in one composition.
- **FX:** `FX_motionlines_v1` on the stamp lift. **At 0:58, for ~4 frames:** in the stamp's polished metal, a reflection of the filling smear and the corner of the evidence box is faintly visible.
- **Transition out:** hard cut.
- **RET:** **pattern interrupt #2** at the ~1:00 drop-off point. Maximum jeopardy.

#### SHOT 13 — 1:02–1:08 · MED.EYE.STATIC · **the turn**
- **Motion:** PIP raises one small arm and **points** past CHIEF (single deliberate 4-frame move, then absolutely still). CHIEF, not looking, lifts the stamp *higher*. Then, one at a time and roughly 1.2 s apart: **BUD's head turns** → **MITTENS turns** → **two crowd silhouettes turn** — all following PIP's finger. CHIEF alone keeps gloating.
- **Camera:** locked medium two-shot. No move — the turning heads carry the beat.
- **FX:** none. Deliberately bare.
- **Audio note:** the music **un-builds** across this shot, one instrument dropping out per turn (file 05 cue 11). Sync each dropout to a head turn.
- **Transition out:** hard cut.

### ACT 5 — SILENCE & REVEAL (1:08–1:30)

#### SHOT 14 — 1:08–1:18 · MED→WIDE.EYE.TRACK · **THE 10-SECOND SILENCE**
- **Motion:** CHIEF lowers the stamp (slow 15-frame descent) and finally turns his head to follow PIP's finger. His expression drains across the full 10 seconds — smug → puzzled → uneasy → horrified, in four discrete 2.5-second stages. PIP stays perfectly still, arm still raised.
- **Camera:** **one continuous slow TRACK along his eyeline, 10 seconds, no cuts:** the tipped table → the filling smear on its back edge → the run down the table leg → the drip point → across the cobbles → settling on his own open evidence box. Move at a steady, unhurried pace; let each element register.
- **FX:** none. No shocklines, no sparkle, nothing. The absence of effects is doing the work.
- **Audio note:** **total musical silence.** Only the 1:12 creak and the 1:15 drip (file 05 §3).
- **Transition out:** hard cut on the last frame of the box.

> **Do not shorten this shot.** Ten seconds of near-silence feels enormous while editing and reads as
> perfectly judged in playback. It is the single highest-tension stretch in the episode and the entire
> reason the format was extended to long form.

#### SHOT 15 — 1:18–1:25 · ECU→WIDE.EYE.PULLOUT · **THE REVEAL**
- **Motion:** ECU inside the box: **the pie**, intact, one slice-shaped dent. Hold 12 frames. Then a continuous pull-back to the full geometry. CHIEF's face runs the **3-stage snap** (triumphant→shocked→panicked, 4 frames each). The giant stamp slips from his glove, falls, and thuds onto his own boot, leaving an `ALERT_RED` mark. The corkboard's strings visibly sag.
- **Camera:** ECU → continuous **PULLOUT** to a full wide holding, in one frame: the ledger against the leg, the tipped table, the trail, and the box. **0.7 s freeze** on that full-geometry wide.
- **FX:** big flat `FX_impact_star_v1` on the reveal; `FX_motionlines_v1` on the falling stamp; one optional 1-frame white flash.
- **Transition out:** hard cut.

#### SHOT 16 — 1:25–1:30 · WIDE → ECU (== SHOT 1) · **payoff + loop**
- **Motion:** PIP calmly lifts the pie out, sets it back on its plate (plate clink), and hands CHIEF the empty box. CHIEF takes it, mortified, cap drooping, stamp mark on his boot. BUD receives a slice and munches. MITTENS licks a crumb. Crowd silhouettes applaud. PIP turns and gives a small wave to camera; BUD's tail wags once.
- **Camera:** wide, then a slow settle into the **exact SHOT-1 ECU framing on the pie plate** as the final frame.
- **FX:** a tiny sparkle on the restored pie. No residual FX on the final frame (the loop must be clean).
- **Transition out:** **hard cut** on the final frame, seaming back to SHOT 1.

---

## B) Transitions & cut map (quick reference)
| Between | Type | Notes |
|---|---|---|
| **S1 internal** | **continuous PULLOUT** | plate → CHIEF's gasp |
| S1→S2 | hard cut | into the seed shot |
| S2→S3→S4 | hard cut | 4–5 s clips |
| **S5 internal** | continuous PULLOUT | muzzle → the taut lead |
| S5→S6→S7 | hard cut | |
| **S7 internal** | hard cut | CHIEF (low, pompous) → cat (flat, unimpressed) |
| S7→S8→S9→S10 | hard cut | |
| **S10 internal** | PUSHIN | onto PIP's crumbs |
| S10→S11→S12→S13 | hard cut | |
| **S13→S14** | hard cut | into the silence |
| **S14 internal** | **continuous 10 s TRACK** | the eyeline. No cuts, no exceptions |
| **S15 internal** | **continuous PULLOUT** + 0.7 s freeze | pie in box → full geometry |
| S15→S16 | hard cut | payoff |
| S16→(loop) | hard cut, seam to S1 | final frame == first frame |

**No** dissolves, fades, wipes, glitch, zoom-blur, or camera rotation anywhere. Effects are limited to:
pop-ins, dust puffs, motion lines, lens glints, flat `ALERT_RED` shock lines, sparkle, impact-star, one
optional flash, and the specified holds/freezes.

---

## C) Optional single "master prompt" (for one-shot generators)
```
{style prefix from file 02 §0 — 16:9 HORIZONTAL}
A 90-second 16:9 flat-2D cartoon comedy detective short, 30fps, hard cuts only except three continuous
camera moves, no camera rotation, no blur or glow, snappy pose-to-pose animation with strong holds.
Recurring cast: CHIEF, a pompous rotund cartoon detective in a teal jacket with an oversized peaked cap
and a yellow medal sash, carrying a huge magnifying glass; PIP, a tiny underdog with a teal scarf; BUD, a
tiny scruffy dog with a teal collar on a short lead; MITTENS, a very small grey cat. Setting: a flat
cartoon market square with a pie stall. Story in 16 beats:
(0-3s) Dead-still EXTREME CLOSE-UP of an EMPTY pie plate, then a fast pull-back to CHIEF gasping.
(3-7s) WIDE static, held: CHIEF casually LEANS A HEAVY LEDGER AGAINST THE STALL TABLE'S LEG, tipping the
table a few degrees, and SETS AN OPEN WOODEN EVIDENCE BOX ON THE GROUND BEHIND THE STALL. Neither action
is emphasised. PIP eats a biscuit; BUD dozes on a short lead; MITTENS sits on crates.
(7-12s) MED push-in: CHIEF strikes a detective pose, eye huge through the magnifying glass.
(12-17s) He points dramatically at the sleeping BUD.
(17-23s) Close on BUD's SPOTLESS muzzle, then pull back to show his SHORT TAUT LEAD ending far from the
table. CHIEF deflates.
(23-28s) He crosses BUD off his notebook; BUD delivers an enormous deadpan yawn. Briefly, behind CHIEF's
elbow, a thin smear of filling on the table's back edge flickers into view.
(28-33s) LOW pompous angle: CHIEF steps onto a crate and points operatically at MITTENS; flat unimpressed
cut to the tiny cat.
(33-39s) He measures the cat against the plate with a tape — the cat is far smaller than the pie — and
mimes trying to carry it.
(39-44s) He crosses off suspect two, frustrated; the cat licks a paw. In the background, half hidden by a
crate, the table is more tilted and a drop of filling falls.
(44-50s) Push-in: PIP frozen mid-bite with crumbs on his scarf; CHIEF delivers his biggest gasp yet.
(50-56s) He pins up a corkboard of PHOTOS ONLY joined by red string, every thread pointing at PIP.
(56-62s) LOW angle: CHIEF raises a giant comic stamp high over tiny cowering teary PIP. Reflected faintly
in the stamp's metal: filling and the corner of the evidence box.
(62-68s) PIP calmly POINTS past CHIEF; one by one BUD, then the cat, then the crowd turn to look; CHIEF
alone keeps gloating and raises the stamp higher.
(68-78s) MUSIC CUTS TO TOTAL SILENCE. One continuous 10-second slow TRACKING shot along CHIEF's eyeline:
the tipped table, a trail of filling down its back edge and leg, across the cobbles, settling on HIS OWN
OPEN EVIDENCE BOX. His face drains from smug to horrified.
(78-85s) CLOSE-UP: the whole pie sitting inside his own evidence box. Continuous PULL-BACK to reveal the
full geometry — his ledger propping the table askew, the filling trail leading into the box. CHIEF snaps
shocked then panicked; the stamp drops onto his own boot leaving a red mark.
(85-90s) PIP sets the pie back on the plate and hands CHIEF his empty box; BUD gets a slice; the crowd
applauds PIP; PIP waves to camera. Framing settles into an EXTREME CLOSE-UP of the plate IDENTICAL to the
opening frame.
ZERO on-screen text anywhere; the corkboard uses photos, pins and string only. CHIEF never loses his
cap/sash/medals; PIP never loses his teal scarf. The table's tilt only ever INCREASES. Advertiser-safe:
the entire crime is a missing pie — no violence or menace; CHIEF is humiliated but unharmed; no animal is
harmed or distressed.
```

---

## D) Handoff / minimal-edit checklist
- [ ] **Rendered 16:9 / 1920×1080** — not vertical, or YouTube will classify it as a Short.
- [ ] Total runtime **1:30**; each shot trimmed to its exact timecode.
- [ ] Assemble S1→S16 with **hard cuts**, preserving the **three continuous moves** (S1 pull-back, S14 10-second track, S15 pull-back).
- [ ] **S2 held the full 4 seconds** with both seeds legible and neither emphasised.
- [ ] **Table tilt charted and monotonically increasing** across S2 → S14. Scrub for any frame where it un-tilts.
- [ ] **Ledger and box never move** between S2 and S15.
- [ ] **Filling trail grows:** smear (S6) → forming drip (S9) → run down the leg (S12) → complete trail (S14–S15).
- [ ] Seed glimpses present and *subtle* at **0:26** (~3 frames, elbow-occluded), **0:41** (~8 frames, crate-occluded), **0:58** (~4 frames, in the stamp's reflection). Test on a cold viewer: they should feel uneasy, not informed.
- [ ] Holds/freezes in place: S2 4 s hold · S5 10-frame muzzle · S6 12-frame yawn · S8 4-frame mime · S11 3-frame per tap · S12 1 s stamp-top hold · S15 0.7 s geometry freeze.
- [ ] **S14 is a full 10 seconds** and contains no cuts.
- [ ] Music silence spans **1:08–1:18**; only the 1:12 creak and 1:15 drip inside it.
- [ ] Loop seam: overlay S16's final frame on S1's first frame — the plate framing must match.
- [ ] Lay VO (file 03) and BGM/SFX (file 05) onto the fixed timecodes — everything is pre-synced.
- [ ] Generate the thumbnail per file 06 and pair it with a title from that file's table.
- [ ] Final QC: no baked text, no blur/glow, cast on-model, crowd silhouette-level, animals wordless and unharmed, CHIEF humiliated but unharmed, PIP vindicated.
