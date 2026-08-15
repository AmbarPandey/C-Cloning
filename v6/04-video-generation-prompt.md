# v6 — Video-Generation Script / Prompt ("One Sweet, One Coin") · **SHORTS 9:16**

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or Anijam driving the stills from file 02). It specifies **motion, camera angles,
> transitions, cut timing, motion-graphics and on-screen FX per shot**, so the generated output needs
> **minimal editing** — ideally just top-and-tail + audio layup. Everything aligns to the master
> timeline in `01-video-script.md`, the visuals in `02`, VO in `03`, and audio in `05`.

**Global render spec:** **1080×1920 (9:16 vertical)** · 30 fps · ~32 s (≈960 frames) · flat-2D cartoon
house style (file 02 §0) · snappy pose-to-pose with strong holds · **hard cuts only** (no dissolves/fades)
· **no camera rotation/orbit, no handheld** · **no blur/glow/gradients** · loop seam (C8 == C1).

**Motion philosophy:** limited animation — hold poses on comedy beats, animate in short bursts. v6's engine
is **accumulation then subtraction**: the pile grows in discrete pop-in bursts for ten seconds, then
un-builds in four seconds. Two contrasting motion languages:
- **CHIEF:** fast, careless, wide-armed, always in motion.
- **PIP:** almost completely still. One small polite point (C2) and one small wave (C8). His stillness is
  what makes the scale — not him — deliver the verdict.

> **The vertical frame is an asset here.** 9:16 is the ideal shape for a *tall pile* and a *balance scale*.
> Stack the composition: sweets mountain in the upper third, scale in the middle, purse and counter in the
> lower third. The viewer's eye travels up and down the price, not across it.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** — subject motion — camera — transitions/FX — cut.

### SHOT 1 — 0:00–0:02 · WIDE.EYE.STATIC
- **Motion:** CHIEF struts in from frame left (bouncy 2-step strut), **slams the huge red purse onto the counter** (fast 4-frame slam + 2-frame settle bounce), and **seizes the largest cup** off the stack (3-frame grab). PIP does one small worried blink. Nothing else moves.
- **Camera:** locked wide. 6-frame settle hold so the **rate pictogram** (1 sweet = 1 coin) and the **balance scale** both register clearly.
- **Motion graphics/FX:** small flat dust puff on the purse slam. **No highlight or sparkle on the rate sign** — it must read as ordinary stall signage. Optional caption "watch the purse 👀" fades in 0:00.8–0:01.8 (edit, not baked).
- **Transition out:** hard cut.

### SHOT 2 — 0:02–0:06 · MED.EYE.PUSHIN(slow)
- **Motion:** CHIEF scoops twice into the cup. PIP raises one small hand and **politely points at the rate pictogram** (single 4-frame move, then still). CHIEF waves him off without looking (2-frame flick). **His elbow knocks the purse and it tips open for ~3 frames — showing it is nearly empty — then flops shut.**
- **Camera:** slow push-in (100%→110% over 4 s) ending framed on the purse at the moment it falls open.
- **FX:** none on the purse — **do not** sparkle, highlight, zoom or slow down for the seed. It must look accidental. The push-in is the only nudge the audience gets.
- **Transition out:** hard cut.

> **This is the fair-play moment.** Everything needed to predict the ending is visible by 0:06: the rate,
> and the contents of the purse. Show it clearly and move on — *shown, not sold.*

### SHOT 3 — 0:06–0:11 · MED.EYE.STATIC
- **Motion:** three scoops land in the cup as staggered pop-ins (~1.5 s apart), the pile mounding above the rim. Each scoop is visibly more careless — wider arm arc, more spillage. PIP's eyes flick between the pile and the scale (2 discrete looks), widening.
- **Camera:** locked medium; **3-frame impact hold on every second scoop**.
- **Motion graphics/FX:** `FX_motionlines_v1` on each arm swing; a few loose sweets bounce and settle on the counter (flat 3-key tumbles).
- **Transition out:** hard cut.

### SHOT 4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight)
- **Motion:** he drops the scoop and **shovels with both hands** — three big two-handed loads (staggered ~1.5 s), the pile becoming an absurd overflowing `BRAND_YELLOW` mountain, sweets cascading onto the counter. He then gloats at PIP over the top of it, chest out, chin high (held 8 frames).
- **Camera:** slight push-in (100%→104%); **3-frame hold as the final handful lands**.
- **Motion graphics/FX:** `FX_motionlines_v1` thickening on each shovel; sweets spilling in flat tumbles; one sparkle glint off a medal at ~0:15.
- **Transition out:** hard cut.

### SHOT 5 — 0:16–0:22 · FULL.LOW.PUSHIN → HOLD
- **Motion:** he **SLAMS** the overflowing cup down onto the scale's left pan (fast 3-frame slam) and thrusts his other hand out palm-up, waiting for the total — then **holds** the pose (~1.5 s of true freeze). Beneath him the pans begin to move, slowly.
- **Camera:** low hero angle, gentle push-in settling into the hold; the mountain towers in the upper frame.
- **Motion graphics/FX:** flat dust puff on the slam; `FX_sparkle_v1` self-satisfaction accents. The pan movement is slow and mechanical — 3 discrete increments, not a smooth glide.
- **AUDIO CUE (critical):** the slam impact and the **music cut land on the same frame at 0:16**. See file 05.
- **Transition out:** hard cut.

### SHOT 6 — 0:22–0:27 · MED.EYE.STATIC → TILT-UP
- **Motion:** PIP calmly lifts the huge red purse, turns it over above the right pan — and **one single coin drops out** (a clean 8-frame fall, landing with a small bounce). Beat. Then the **sweets pan crashes to the bottom** of its travel and the coin pan flies up. CHIEF's grin dies in three discrete stages (~1 s apart): flatten → look at purse → shake it out. One sweat bead pops.
- **Camera:** static two-shot on the scale for the coin drop and the crash, then a slow **tilt up** to CHIEF's face as it drains.
- **Motion graphics/FX:** `FX_motionlines_v1` on the pan crash; a tiny flat puff as the empty purse is shaken. Deliberately no sparkle — restraint carries the dread.
- **Transition out:** hard cut.

### SHOT 7 — 0:27–0:31 · MED.EYE.PUNCHIN → SETTLE
- **Motion (beat 1, 0:27–0:29):** CHIEF frantically scoops sweets **back out** — four rapid handfuls (staggered ~0.4 s, accelerating), the pile visibly shrinking, the two pans creeping toward level. His face runs the **3-stage snap** triumphant → shocked → panicked.
- **Motion (beat 2, 0:29–0:31):** the pile is down to almost nothing. He removes one last handful and the pans settle **perfectly level** — **one single sweet** on the left, one coin on the right. PIP beams.
- **Camera:** **quick punch-in** on the balancing pans (~6 frames), then settle; **0.5 s freeze on the level scale** — one sweet, one coin, in perfect balance (the screenshot-able punchline).
- **Motion graphics/FX:** `FX_motionlines_v1` on the fast returning handfuls; small flat `FX_impact_star_v1` at the moment the pans level; optional 1-frame white flash on the balance.
- **AUDIO CUE:** music **SLAMS back** at 0:27 on the first returned handful; the balance *ting* at ~0:30 must read clean.
- **Transition out:** hard cut.

### SHOT 8 — 0:31–0:32 · WIDE.EYE.STATIC (== SHOT 1)
- **Motion:** CHIEF stands holding **one tiny sweet** pinched between two oversized white gloves, staring at it, cap drooping slightly. Beside him PIP tips the entire returned mountain into a big cup and sets it down for **BUD**, who dives in happily (tail wagging). The flat empty red purse lies on the counter.
- **Camera:** return to the **exact SHOT-1 framing** — same background plate, same counter line, same scale position. Only the scale state, the purse and what each character is holding differ.
- **Motion graphics/FX:** a small sparkle on BUD's overflowing cup. Optional caption "one. sweet. 💀" 0:31.2–0:31.9 (edit, not baked). No residual FX on the final frame (loop must be clean).
- **Transition out:** **hard cut** ≤1 s after the wave, seaming back to SHOT 1.

---

## B) Transitions & cut map (quick reference)
| Between | Type | Notes |
|---|---|---|
| C1→C2→C3→C4 | hard cut | snappy 2–5 s clips |
| C4→C5 | hard cut | into the slam |
| **C5 internal (0:16)** | slam + audio drop on the same frame | the pattern-break silence begins |
| C5→C6 | hard cut | to the coin drop |
| **C6 internal** | 3 staged faltering beats + pan crash | tension by increments |
| C6→C7 | hard cut into **punch-in** | the twist |
| **C7 internal (0:30)** | 0.5 s freeze | the level scale — one sweet, one coin |
| C7→C8 | hard cut | payoff |
| C8→(loop) | hard cut, seam to C1 | replay re-reads the rate sign and the purse |

**No** dissolves, fades, wipes, glitch, zoom-blur, or camera rotation anywhere. Effects are limited to:
pop-ins, dust puffs, motion lines, flat sweet tumbles, sparkle, impact-star, one optional flash, and the
listed holds/freezes.

> **The key craft note for v6:** the scale must move **mechanically, in discrete increments**, never as a
> smooth animated glide. Three steps down as the pile grows, three steps up as it shrinks. Mechanical
> motion reads as *arithmetic being performed*, and that is the whole joke — the machine is doing sums
> while CHIEF is doing vanity.

---

## C) Optional single "master prompt" (for one-shot generators)
```
{style prefix from file 02 §0 — 9:16 VERTICAL}
A ~32s 9:16 flat-2D cartoon comedy short, 30fps, hard cuts only, no camera rotation, no blur or glow,
snappy pose-to-pose animation with strong holds. Recurring cast: CHIEF, a pompous rotund braggart in a
teal jacket with an oversized peaked cap and a yellow medal sash; PIP, a tiny underdog stall keeper with
a teal scarf; BUD, a tiny scruffy dog with a teal collar. Setting: a bright fairground sweet stall with a
teal striped awning, jars of yellow sweets, and a two-pan brass BALANCE SCALE on the counter. Propped on
the stall front is a wordless PICTOGRAM SIGN showing one sweet, an equals sign, and one coin.
Story in 8 beats:
(0-2s) WIDE static: CHIEF struts up, SLAMS a huge ostentatious RED coin purse on the counter and grabs
the LARGEST cup. Tiny PIP watches, worried. The pictogram sign and the balance scale are clearly visible.
(2-6s) MED slow push-in: CHIEF scoops sweets in; PIP politely points at the pictogram sign; CHIEF waves
him off; his elbow knocks the purse and IT FALLS OPEN FOR A MOMENT, showing it is NEARLY EMPTY.
(6-11s) MED: three more careless scoops, the pile mounding over the cup's rim; PIP's eyes widen.
(11-16s) MED-WIDE: CHIEF shovels with BOTH HANDS, building an absurd overflowing YELLOW mountain of
sweets, and gloats at PIP over the top of it.
(16-22s) LOW hero angle: he SLAMS the overflowing cup onto the scale's left pan and holds out his palm for
the total, chest out, triumphant; the pans begin to move; MUSIC CUTS TO SILENCE on the slam.
(22-27s) Static on the scale, then tilt up: PIP calmly turns the huge purse over above the right pan and
EXACTLY ONE COIN drops out; the sweets pan CRASHES to the bottom; CHIEF's grin dies, he shakes the empty
purse, a sweat bead pops.
(27-31s) MED quick punch-in: CHIEF frantically scoops handful after handful of sweets BACK OUT, the pans
creeping level, until they BALANCE PERFECTLY with ONE SINGLE SWEET against one coin; 0.5s freeze on the
level scale; CHIEF snaps triumphant->shocked->panicked; PIP beams.
(31-32s) WIDE, framing identical to the opening: CHIEF holding one tiny sweet between two huge gloves,
mortified, the flat empty red purse on the counter; PIP tipping the whole returned mountain into a big cup
for BUD, who dives in happily; PIP waves to camera. Hard cut.
ZERO on-screen text anywhere; the rate is a pictogram and the scale has no numbers. CHIEF never loses his
cap/sash/medals; PIP never loses his teal scarf. The pile only ever GROWS before 0:16 and only ever
SHRINKS after 0:27. The scale moves in discrete mechanical increments, never a smooth glide.
Advertiser-safe: CHIEF is embarrassed by his own greed, never harmed; no mockery of poverty — he is a
show-off with an empty flashy purse; no animal harmed.
```

---

## D) Handoff / minimal-edit checklist
- [ ] **Rendered 9:16 / 1080×1920**, total ≈32 s, on the locked 8-clip skeleton.
- [ ] Assemble C1→C8 with **hard cuts**; add no transitions.
- [ ] Insert the holds/freezes: C1 6-frame settle · C3 3-frame per second scoop · C4 3-frame final handful · C5 ~1.5 s victory hold · C6 three faltering beats · C7 **0.5 s level-scale freeze**.
- [ ] **Verify Seed A:** the rate pictogram (1 sweet = 1 coin) is legible in C1 without being emphasised.
- [ ] **Verify Seed B:** the purse falls open at ~0:04 for ~3 frames, nearly empty, with no FX drawing attention to it. Test on a cold viewer — unease, not information.
- [ ] **Verify the pile is monotonic:** grows every beat C2→C5, shrinks every beat in C7. Scrub for any frame that contradicts.
- [ ] **Verify pan physics:** the pan positions must always be consistent with the pile size. Viewers *will* check this on replay — it is the video's logic.
- [ ] The scale moves in **discrete increments**, not smooth glides.
- [ ] Confirm the **music cut and the slam impact land on the same frame (0:16)**, and the silence runs to 0:27.
- [ ] Confirm the **0:23 coin tink** and the **0:30 balance ting** are unmasked (file 05 §5).
- [ ] Verify loop seam: overlay C8 on C1 — background plate, framing and counter line must match.
- [ ] Lay VO (file 03) and BGM/SFX (file 05) onto the fixed timecodes — everything is pre-synced.
- [ ] Final QC: no baked text, no blur/glow, cast on-model, BUD wordless and happy, CHIEF embarrassed but unharmed, and **nothing that reads as mocking poverty** — the target is vanity.
