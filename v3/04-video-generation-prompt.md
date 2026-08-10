# v3 — Video-Generation Script / Prompt ("One Block Too Many")

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or Anijam driving the stills from file 02). It specifies **motion, camera
> angles, transitions, cut timing, motion-graphics and on-screen FX per shot**, so the generated
> output needs **minimal editing** — ideally just top-and-tail + audio layup. Everything aligns to
> the master timeline in `01-video-script.md`, the visuals in `02`, VO in `03`, and audio in `05`.

**Global render spec:** 1080×1920 (9:16) · 30 fps · ~32 s (≈960 frames) · flat-2D cartoon house
style (see file 02 §0 style prefix) · snappy pose-to-pose with strong holds · **hard cuts only**
(no dissolves/fades) · **no camera rotation/orbit, no handheld** · **no blur/glow/gradients** ·
loop seam (C8 framing == C1 framing).

**Motion philosophy:** limited animation — hold poses on comedy beats, animate in short bursts.
v3 is a **vertical/gravity** story: the two motion languages are *deliberate placement* (PIP, slow and
precise) and *careless piling* (CHIEF, fast and sloppy). The collapse is the only large-scale motion in
the video — keep everything before it restrained so the crash feels enormous.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** — subject motion — camera — transitions/FX — cut.

### SHOT 1 — 0:00–0:02 · WIDE.EYE.STATIC
- **Motion:** CHIEF struts in from the left edge to his platform (bouncy 2-step strut). PIP looks up at the red band, then down at his blocks (small 2-key head move). Nothing else moves.
- **Camera:** locked wide. 6-frame settle hold on the full composition so the **seed registers** — the red target band and the yellow arrow pointing at it.
- **Motion graphics/FX:** none (clean establishing). Optional caption "watch the bottom block 👀" fades in 0:03 in the next shot, not here.
- **Transition out:** hard cut.

### SHOT 2 — 0:02–0:06 · MED.EYE.PUSHIN(slow)
- **Motion:** PIP places one block, taps it level (4-frame settle), reaches for the next — deliberate, unhurried. CHIEF sneers, then **slaps his first block down crooked** (fast 3-frame slam, block visibly off-square, small 2-frame wobble settle) and immediately drops a second block onto it, then a third.
- **Camera:** slow push-in (100%→110% over 4 s) that finishes centred on the **crooked block**.
- **FX:** a tiny flat stress line + 1-frame wobble on the crooked block as the second block lands (the audience must clock it). Optional caption "watch the bottom block 👀" 0:03.0–0:04.2 (edit, not baked).
- **Transition out:** hard cut.

### SHOT 3 — 0:06–0:11 · WIDE.EYE.STATIC
- **Motion:** both towers rise in staggered block pop-ins — PIP's one at a time and plumb, CHIEF's two at a time and leaning. PIP's final block settles **flush with the red band**; he steps back one pace and stops. CHIEF glances at the line, smirks (2-frame), and keeps stacking past it.
- **Camera:** locked wide; **4-frame hold** as PIP's top block meets the band exactly.
- **Motion graphics/FX:** a small clean sparkle "tick" at the moment PIP's block aligns with the band (confirms "target met" without text); `FX_wobble` begins faintly on CHIEF's tower.
- **Transition out:** hard cut.

### SHOT 4 — 0:11–0:16 · MED-WIDE.EYE.TILT-UP
- **Motion:** rapid block pop-ins build the spire far past the band and out of frame top; the whole tower develops a slow 2-second sway cycle. CHIEF scrambles up the side (short climb cycle) and plants his flag at the summit, arms wide.
- **Camera:** slight push-in, then a **tilt up** the spire that lands on the summit.
- **Motion graphics/FX:** `FX_wobble` arc lines strengthen; small dust flecks at the base on each new block; one sparkle glint off a medal at ~0:15.
- **Transition out:** hard cut.

### SHOT 5 — 0:16–0:22 · FULL.LOW.PUSHIN → HOLD
- **Motion:** CHIEF seizes the trophy, snaps into an enormous victory pose (trophy up, flag out), and **holds it** — a long, proud, convincing tableau (~1.5 s of true freeze inside the shot). Confetti drifts. The tower sways almost imperceptibly beneath him.
- **Camera:** low hero angle with a gentle rise/push-in that settles into the hold.
- **Motion graphics/FX:** `FX_confetti` drifting down, `FX_sparkle` around the trophy, subtle flat radial "hero" shape lines. **Sell the win completely.**
- **AUDIO CUE (critical):** music **cuts to silence** at ~0:16 at the top of the celebration, leaving only a faint wooden creak. See file 05.
- **Transition out:** hard cut.

### SHOT 6 — 0:22–0:27 · CU.LOW.STATIC → TILT-UP
- **Motion:** the **crooked block** shifts, grinds, and begins to buckle in small increments (3 discrete slips, ~1 s apart, each with a stress line and a dust trickle). The stack above leans a little further with each slip. PIP, at frame edge, looks up — eyes widening.
- **Camera:** hard cut to a **low static insert on the crooked block**, hold, then a slow tilt up the wobbling tower at ~0:26.
- **Motion graphics/FX:** flat stress lines, `FX_dustpuff` trickles, `FX_wobble` intensifying. Deliberately no sparkle, no impact FX — tension comes from restraint.
- **Transition out:** hard cut.

### SHOT 7 — 0:27–0:31 · WIDE.EYE.PUNCHIN → SETTLE
- **Motion (beat 1, 0:27–0:29):** the crooked block gives way completely; the spire **collapses** — blocks cascade outward in a flat tumble, CHIEF drops among them flailing, face running the **3-stage snap** triumphant→shocked→panicked. The trophy launches out of his grip in a clean arc.
- **Motion (beat 2, 0:29–0:31):** the trophy lands **neatly on top of PIP's tower**, which stands untouched and flush with the red band. PIP throws up a gleeful celebrate.
- **Camera:** **quick punch-in** on the buckling base (~6 frames), a **whip-tilt down** following the collapse, then settle wide on PIP's intact tower; ~0.5 s freeze on the trophy-on-PIP's-tower frame (the screenshot-able punchline).
- **Motion graphics/FX:** big flat `FX_impact_star` behind the collapse; `FX_dustpuff` bloom at ground level; `FX_motionlines` on the tumbling blocks; optional 1-frame white flash on the crash. **No block may touch or threaten PIP.**
- **AUDIO CUE:** music **SLAMS back** + wooden CRASH + block-clatter tail + a clean trophy "ting" + record-scratch, all across the ~0:29 hit.
- **Transition out:** hard cut.

### SHOT 8 — 0:31–0:32 · WIDE.EYE.STATIC (== SHOT 1)
- **Motion:** CHIEF sits buried to the neck in his own blocks, cap askew, giving one tiny sheepish shrug; his flag droops. PIP turns and gives a small friendly wave to camera. One last stray block topples off the pile with a small 3-frame tumble.
- **Camera:** return to the **exact SHOT-1 framing** — same background plate, same horizon line, same platform marks. Only the towers, the trophy and the cast states differ.
- **Motion graphics/FX:** a last thin dust wisp settling; a tiny sparkle on the trophy atop PIP's tower. Optional caption "he had it. briefly. 💀" 0:31.2–0:31.9 (edit, not baked). No residual FX on the final frame (loop must be clean).
- **Transition out:** **hard cut** ≤1 s after the wave, seaming back to SHOT 1.

---

## B) Transitions & cut map (quick reference)
| Between | Type | Notes |
|---|---|---|
| C1→C2→C3→C4 | hard cut | snappy 2–5 s clips |
| C4→C5 | hard cut | into the false victory |
| **C5 internal (0:16)** | freeze + audio drop | the pattern-break silence begins |
| C5→C6 | hard cut | **scale jump** wide summit → low base insert (the reveal of cause) |
| **C6 internal (0:22–0:27)** | 3 staged slips | tension built by increments, not motion |
| C6→C7 | hard cut into **punch-in** | the twist |
| **C7 internal (0:29)** | whip-tilt + 0.5 s freeze | collapse → trophy-on-PIP's-tower punchline |
| C7→C8 | hard cut | payoff |
| C8→(loop) | hard cut, seam to C1 | replay re-reads the crooked block |

**No** dissolves, fades, wipes, glitch, zoom-blur, or camera rotation anywhere. The only "effects" are
the listed pop-ins, stress lines, wobble arcs, dust puffs, motion lines, sparkle, confetti,
impact-star, one optional flash, and the holds/freezes.

> **The key edit in v3** is the C5→C6 cut: a hard jump from the widest, proudest, sky-heavy summit shot
> straight down to a tight, quiet insert on one failing block. That single cut is what converts a
> celebration into dread — do not soften it with a transition or an intermediate shot.

---

## C) Optional single "master prompt" (for one-shot generators)
If your tool takes one continuous prompt, use this (it references the same beats/timing):
```
{style prefix from file 02 §0}
A ~32s 9:16 flat-2D cartoon comedy short, 30fps, hard cuts only, no camera rotation, no blur or glow,
snappy pose-to-pose animation with strong holds. Two recurring characters: CHIEF, a smug rotund
braggart in a teal jacket with a peaked cap and a yellow medal sash; and PIP, a tiny careful underdog
with a teal scarf. Story in 8 beats:
(0-2s) WIDE static: a plain contest yard with two low platforms. Between them a post with a bright RED
target band and a YELLOW arrow pointing at it. A giant yellow trophy on a side table. PIP waits by a
neat pile of chunky blocks; CHIEF struts in.
(2-6s) MED slow push-in: PIP places a block carefully and levels it; CHIEF sneers and slaps his first
block down VISIBLY CROOKED, then piles more on top of it fast.
(6-11s) WIDE: PIP's neat plumb tower reaches EXACTLY flush with the red band and he stops, content;
CHIEF's leaning tower blasts straight past the band and he keeps stacking.
(11-16s) MED-WIDE tilt up: CHIEF's tower is an absurd swaying spire exiting the top of frame; he climbs
it and plants a little flag at the summit.
(16-22s) LOW hero angle, sky-heavy: at the summit CHIEF raises the giant yellow trophy in a huge
victory pose with confetti and sparkles — it completely reads as TOTAL VICTORY; MUSIC CUTS TO SILENCE.
(22-27s) LOW tight insert on the tower BASE, tense and quiet: the single CROOKED block grinds and
buckles in small slips with dust trickles; the stack leans further; PIP looks up hopefully; CHIEF still
posing far above, oblivious.
(27-31s) WIDE quick punch-in then whip-tilt down: the spire COLLAPSES, blocks cascading, CHIEF falling
and flailing, face snapping triumphant->shocked->panicked, the trophy flung from his hands; it lands
neatly on top of PIP's short tower which is STILL STANDING flush with the red band; 0.5s freeze on that.
(31-32s) WIDE, framing identical to the opening: CHIEF buried to his neck in his own blocks with his
cap askew and flag drooping; PIP beside his intact tower with the trophy on top, waving to camera.
Hard cut.
ZERO on-screen text anywhere. CHIEF never loses his cap/sash/medals; PIP never loses his teal scarf.
No crowd. Advertiser-safe: soft chunky blocks, comic landing, no injury and no blocks near PIP.
```

---

## D) Handoff / minimal-edit checklist
- [ ] Render each shot at the exact timecode length above (or trim to it) — total ≈32 s.
- [ ] Assemble in order C1→C8, **hard cuts**, no transitions added.
- [ ] Insert the holds/freezes: C1 6-frame settle · C3 4-frame line-match hold · C5 ~1.5 s victory hold · C6 three staged slips · C7 0.5 s trophy-on-tower freeze.
- [ ] Verify the seed: red band + yellow arrow legible in C1; band height **pixel-identical** in C1/C3/C6/C7/C8.
- [ ] Verify PIP's tower is **flush** with the band in C3, C7 and C8 (not near — flush).
- [ ] Verify the callback: crooked block legible in C2 → buckling in C6 → cause of collapse in C7 → visible in the C8 rubble.
- [ ] Verify the C5→C6 hard cut lands as a shock (wide summit → tight base insert, no transition).
- [ ] Verify loop seam: overlay C8 on C1 — background plate, framing and horizon must match.
- [ ] Confirm the music silence spans **0:16–0:27** and the CRASH lands at **~0:29**.
- [ ] Lay VO (file 03) and BGM/SFX (file 05) onto the fixed timecodes — everything is pre-synced.
- [ ] Final QC: no baked text, no blur/glow, cast on-model, no crowd, **no block touching PIP**, CHIEF unharmed.
