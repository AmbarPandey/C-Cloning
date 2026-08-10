# v4 — Video-Generation Script / Prompt ("The Wrong Side of the Fence")

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or Anijam driving the stills from file 02). It specifies **motion, camera
> angles, transitions, cut timing, motion-graphics and on-screen FX per shot**, so the generated
> output needs **minimal editing** — ideally just top-and-tail + audio layup. Everything aligns to
> the master timeline in `01-video-script.md`, the visuals in `02`, VO in `03`, and audio in `05`.

**Global render spec:** 1080×1920 (9:16) · 30 fps · ~32 s (≈960 frames) · flat-2D cartoon house
style (see file 02 §0 style prefix) · snappy pose-to-pose with strong holds · **hard cuts only**
(no dissolves/fades) · **no camera rotation/orbit, no handheld** · **no blur/glow/gradients** ·
loop seam (C8 framing == C1 framing).

**Motion philosophy:** limited animation — hold poses on comedy beats, animate in short bursts. v4's
whole engine is **framing, not motion**: the twist is true on screen from frame 1, and the only thing
that changes is how much of the frame the audience is allowed to see. C5 hides the geometry; C6's
pull-back reveals it. Treat the camera as the storyteller.

> **v4's signature camera move is the `PULLOUT` reveal in C6** — v1 used PUNCHIN, v2 WHIP, v3 TILT-UP.
> Do not add extra moves; the restraint is what makes the pull-back land.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** — subject motion — camera — transitions/FX — cut.

### SHOT 1 — 0:00–0:02 · WIDE.EYE.STATIC
- **Motion:** CHIEF struts in from the right edge and stops, staring left at the shade (bouncy 2-step strut, then a hold). In the garden: PIP gives a small contented blink; BUD's tail wags twice; two lounging animals shift very slightly (2-key idles). Fountain water loops. Nothing else moves.
- **Camera:** locked wide. 6-frame settle hold on the full composition so the **seeds register** — the fence-panel stack, the padlock on the post, and the crisp shade/sun edge on the ground.
- **Motion graphics/FX:** faint flat heat-shimmer chevrons rising off the sunny ground (flat shapes, **not** a blur filter). Optional caption "watch where he's standing 👀" fades in 0:00.8–0:01.8 (bottom-center pill, edit, not baked).
- **Transition out:** hard cut.

### SHOT 2 — 0:02–0:06 · MED.EYE.PUSHIN(slow)
- **Motion:** CHIEF looks at the shade, then at PIP, and his smug half-smile widens into a sneer (3-key). He hauls the first fence panel across (short drag cycle) and **slams it into the ground** (fast 4-frame slam + 2-frame recoil settle). PIP straightens up, worried; BUD tilts his head.
- **Camera:** slow push-in (100%→110% over 4 s), finishing on the first panel landing.
- **FX:** flat dust puff at the panel base; small flat impact chevrons on the slam.
- **Transition out:** hard cut.

### SHOT 3 — 0:06–0:11 · WIDE.EYE.STATIC
- **Motion:** panels go in along the shade boundary in a steady rhythm — 5–6 panels, each a slam + settle, staggered ~0.8 s apart. CHIEF works with gleeful efficiency (loop the haul-and-slam cycle). PIP and BUD edge backward into the shade; two lounging animals lift their heads to watch.
- **Camera:** locked wide; **3-frame impact hold on every second panel** (comic punctuation).
- **Motion graphics/FX:** dust puff per panel; `FX_motionlines` on the swing; BUD gives one worried ear-droop.
- **Transition out:** hard cut.

### SHOT 4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight)
- **Motion:** a second row of panels pops on top of the first (staggered ~5 frames apart) — the wall doubles in height, absurdly overbuilt. CHIEF then hangs the `ALERT_RED` **padlock** on the final gate (4-frame hold as it settles and swings) and dusts his gloves with two crisp claps.
- **Camera:** slight push-in (100%→104%).
- **Motion graphics/FX:** a small metallic sparkle glint on the padlock as it settles; one sparkle off a medal at ~0:15.
- **Transition out:** hard cut.

### SHOT 5 — 0:16–0:22 · MCU.LOW.PUSHIN → HOLD
- **Motion:** CHIEF plants his fists on his hips, steps back, and locks into a proud admiring pose — chest out, chin high — and **holds it** (~1.5 s of true freeze inside the shot). Self-satisfied sparkles.
- **Camera:** low hero angle, gentle push-in settling into the hold. **CRITICAL: keep the framing TIGHT on CHIEF and the wall face.** The audience must not be able to see which side of the fence he is on, or where the shade is. The fence fills the frame behind him.
- **Motion graphics/FX:** `FX_sparkle` self-satisfaction accents; subtle flat radial "hero" shape lines. Heat chevrons are present but kept low in frame so they don't tip the reveal.
- **AUDIO CUE (critical):** music **cuts to silence** at ~0:16 at the peak of the pose, leaving only a cicada buzz that begins to rise. See file 05.
- **Transition out:** **no cut** — SHOT 6 continues the same camera in one continuous pull-back.

### SHOT 6 — 0:22–0:27 · WIDE.EYE.PULLOUT (the reveal)
- **Motion:** CHIEF holds his proud pose for the first second, then it falters: his grin flattens, he glances left, glances right, and a single sweat bead pops (3 discrete beats, ~1.3 s apart). In the garden PIP looks up, eyes widening with hope; BUD's ears prick.
- **Camera:** a slow, continuous **PULLOUT** from SHOT 5's tight framing to a full wide — revealing that the fence rings the **shade**, and CHIEF is standing **outside it on the bare sunny side**, alone. The shade/sun edge on the ground runs right along his boots. **The reveal is the camera move, not a cut** — do not cut into this.
- **Motion graphics/FX:** heat chevrons intensify on his side as more of the sunny ground enters frame; the cool flat shadow and the animals become visible on the other side. No sparkle, no impact FX — restraint carries the dread.
- **Transition out:** hard cut.

### SHOT 7 — 0:27–0:31 · MED.EYE.PUNCHIN → SETTLE
- **Motion (beat 1, 0:27–0:29):** BUD trots to the gate and **nudges it swinging shut with his nose** (small, matter-of-fact, unhurried). PIP steps up on tiptoes and **clicks the padlock closed from the inside** (single decisive 3-frame action).
- **Motion (beat 2, 0:29–0:31):** CHIEF's face runs the **3-stage snap** triumphant→shocked→panicked; he grabs the fence and rattles it twice. Heat lines rise off his cap. Inside, PIP beams and the lounging animals settle back down, completely unbothered.
- **Camera:** **quick punch-in** on the padlock click (~6 frames), then settle back to a wide; ~0.5 s freeze on CHIEF gripping the fence with the cool green garden and PIP behind it (the screenshot-able punchline).
- **Motion graphics/FX:** small flat `FX_impact_star` on the click; `FX_motionlines` on the fence rattle; heat chevrons at maximum on CHIEF's side. Optional 1-frame white flash on the click.
- **AUDIO CUE:** music **SLAMS back** + a small decisive **padlock CLICK** + fence rattle + record-scratch across the ~0:29 hit. The CLICK must read clean and quiet against the slam.
- **Transition out:** hard cut.

### SHOT 8 — 0:31–0:32 · WIDE.EYE.STATIC (== SHOT 1)
- **Motion:** CHIEF wilts in the sun outside his wall — shoulders sagging, cap drooping over his eyes, gloves still hooked on the fence (slow 2-key droop). Inside, PIP settles back on the bench with BUD, turns, and gives a small friendly wave to camera. BUD's tail gives one wag. The fountain trickles; the animals lounge.
- **Camera:** return to the **exact SHOT-1 framing** — same background plate, same horizon line, same shade/sun edge position. Only the fence, the padlock state and the cast positions differ.
- **Motion graphics/FX:** heat chevrons still rising on CHIEF's side; cool stillness on PIP's. Optional caption "he locked himself out 💀" 0:31.2–0:31.9 (edit, not baked). No residual FX on the final frame (loop must be clean).
- **Transition out:** **hard cut** ≤1 s after the wave, seaming back to SHOT 1.

---

## B) Transitions & cut map (quick reference)
| Between | Type | Notes |
|---|---|---|
| C1→C2→C3→C4 | hard cut | snappy 2–5 s clips |
| C4→C5 | hard cut | into the proud admiring pose |
| **C5 internal (0:16)** | freeze + audio drop | the pattern-break silence begins |
| **C5→C6** | **NO CUT — continuous PULLOUT** | the single most important move in the video |
| **C6 internal** | 3 staged faltering beats | grin flattens → glances → sweat bead |
| C6→C7 | hard cut into **punch-in** | the twist |
| **C7 internal (0:29)** | 0.5 s freeze | CHIEF gripping the fence, garden behind PIP |
| C7→C8 | hard cut | payoff |
| C8→(loop) | hard cut, seam to C1 | replay re-reads which side he was always on |

**No** dissolves, fades, wipes, glitch, zoom-blur, or camera rotation anywhere. The only "effects" are
the listed pop-ins, dust puffs, flat heat chevrons, motion lines, sparkle, impact-star, one optional
flash, and the holds/freezes.

> **The key edit in v4** is that C5→C6 is *not a cut*. Every other episode reveals its twist with a hard
> cut or a punch-in; v4 reveals it by widening the frame on a man who hasn't moved. If you cut there
> instead, the joke still works but loses its best quality — the sense that the answer was on screen the
> whole time and you simply weren't shown it.

---

## C) Optional single "master prompt" (for one-shot generators)
If your tool takes one continuous prompt, use this (it references the same beats/timing):
```
{style prefix from file 02 §0}
A ~32s 9:16 flat-2D cartoon comedy short, 30fps, hard cuts only (except one continuous pull-back), no
camera rotation, no blur or glow, snappy pose-to-pose animation with strong holds. Recurring cast:
CHIEF, a smug rotund braggart in a teal jacket with a peaked cap and a yellow medal sash; PIP, a tiny
underdog with a teal scarf; and BUD, PIP's tiny scruffy dog. Story in 8 beats:
(0-2s) WIDE static: a hot park. On the left a lush shady garden with POP_TEAL foliage, a small fountain
and several park animals lounging around exactly like people (reclining, sipping, reading) as quiet
desaturated shapes; PIP and BUD sit on a little bench there. On the right, bare blazing PAPER ground
under a big flat BRAND_YELLOW sun, with flat heat-shimmer chevrons. On the boundary: a leaning stack of
fence panels and a red padlock hanging on a post, and a crisp shade/sun edge drawn on the ground. CHIEF
struts in from the sunny right and stares at the shade.
(2-6s) MED slow push-in: CHIEF sneers at PIP, hauls the first fence panel over and SLAMS it into the
ground along the boundary.
(6-11s) WIDE: panel after panel slams into place, sealing the shady garden off; PIP and BUD edge back
into the shade; lounging animals lift their heads.
(11-16s) MED-WIDE: a second row of panels doubles the wall's height, absurdly overbuilt; CHIEF hangs the
red padlock on the final gate and dusts off his gloves.
(16-22s) TIGHT low hero angle on CHIEF and the wall face only — he plants his fists on his hips and
holds a proud admiring pose, sparkles of self-satisfaction. The framing deliberately HIDES which side of
the fence he is on. MUSIC CUTS TO SILENCE.
(22-27s) One continuous slow PULL-BACK to a full wide, no cut: it reveals the fence rings the SHADE and
CHIEF is standing OUTSIDE it, alone on the blazing sunny side, the shade edge right at his boots, while
PIP, BUD and all the animals are inside the cool green. His grin falters; a sweat bead pops.
(27-31s) MED quick punch-in: BUD nudges the gate shut with his nose and PIP clicks the red padlock closed
FROM THE INSIDE; CHIEF snaps triumphant->shocked->panicked and rattles the fence, heat lines off his cap;
the animals settle back, unbothered; 0.5s freeze on CHIEF gripping the fence with the garden behind PIP.
(31-32s) WIDE, framing identical to the opening: CHIEF wilting in the sun outside his own magnificent
wall, cap drooping; PIP back on the bench with BUD in the cool shade, waving to camera. Hard cut.
ZERO on-screen text anywhere. CHIEF never loses his cap/sash/medals; PIP never loses his teal scarf.
CHIEF is on the SUNNY side in every single shot. Advertiser-safe: CHIEF is hot and embarrassed, never
harmed or distressed; no animal is harmed, caged or upset.
```

---

## D) Handoff / minimal-edit checklist
- [ ] Render each shot at the exact timecode length above (or trim to it) — total ≈32 s.
- [ ] Assemble in order C1→C8 with **hard cuts**, except **C5→C6 which must be one continuous pull-back**.
- [ ] Insert the holds/freezes: C1 6-frame settle · C3 3-frame per second panel · C4 4-frame padlock hold · C5 ~1.5 s proud hold · C6 three faltering beats · C7 0.5 s fence-grip freeze.
- [ ] **Verify the twist invariant: CHIEF is on the sunny side of the shade edge in every single frame of every shot.** Scrub the whole video for this one thing.
- [ ] Verify C5 genuinely **hides** the geometry — show it to someone cold and confirm they can't predict the reveal.
- [ ] Verify the shade/sun ground edge is in the **same screen position** in C1 and C8.
- [ ] Verify the padlock is the same `ALERT_RED` object in C1 (on the post), C4 (hung), C7 (clicked).
- [ ] Verify loop seam: overlay C8 on C1 — background plate, framing and horizon must match.
- [ ] Confirm the music silence spans **0:16–0:27** and the padlock CLICK lands at **~0:29** and is not masked.
- [ ] Lay VO (file 03) and BGM/SFX (file 05) onto the fixed timecodes — everything is pre-synced.
- [ ] Final QC: no baked text, no blur/glow, cast on-model, animals silhouette-level and unharmed, BUD silent, CHIEF unharmed.
