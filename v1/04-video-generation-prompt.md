# v1 — Video-Generation Script / Prompt ("The Wrong Scooter")

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway
> Gen-3, Pika, Luma, or Anijam driving the stills from file 02). It specifies **motion, camera
> angles, transitions, cut timing, motion-graphics and on-screen FX per second**, so the generated
> output needs **minimal editing** — ideally just top-and-tail + audio layup. Everything aligns to
> the master timeline in `01-video-script.md`, the visuals in `02`, VO in `03`, and audio in `05`.

**Global render spec:** 1080×1920 (9:16) · 30 fps · ~32 s (≈960 frames) · flat-2D cartoon house
style (see file 02 §0 style prefix) · snappy pose-to-pose with strong holds · **hard cuts only**
(no dissolves/fades) · **no camera rotation/orbit, no handheld** · loop-seam (last frame == first frame).

**Motion philosophy:** limited animation — hold poses on comedy beats, animate in short bursts.
Every camera move and graphic below is intentional; do not add extras.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** — subject motion — camera — transitions/FX — cut.

### SHOT 1 — 0:00–0:02 · WIDE.EYE.STATIC
- **Motion:** CHIEF struts in from left edge to left-third (bouncy 2-step strut cycle); PIP loops a small coin-fumble at the meter. CHIEF's scooter sits still in the red zone (lower-right).
- **Camera:** locked wide. 6-frame settle hold on the full composition so the red-zone seed registers.
- **Motion graphics/FX:** none (clean establishing). Optional tiny caption "watch the red zone 👀" fades in 0:00.8–0:01.6 (bottom-center pill).
- **Transition out:** hard cut.

### SHOT 2 — 0:02–0:06 · MED.EYE.PUSHIN(slow)
- **Motion:** CHIEF spots the tire, grin spreads; in one flourish he draws the ticket pad + giant stamp (slide-out from jacket). PIP shrinks back.
- **Camera:** slow push-in (scale 100%→110% over 4 s) toward CHIEF's grin.
- **FX:** small comic "aha" spark glint on CHIEF's eye at ~0:03.
- **Transition out:** hard cut.

### SHOT 3 — 0:06–0:11 · MED.EYE.STATIC
- **Motion:** CHIEF stamps a ticket onto PIP's scooter (arm slam), then clamps the yellow boot (snap-on). Blows on the stamp. PIP's eyes well up.
- **Camera:** locked. **4-frame impact hold** on the boot-clamp at ~0:08.
- **Motion graphics/FX:** `FX_motionlines` streak on the stamp slam; tiny impact puff on boot snap.
- **Transition out:** hard cut.

### SHOT 4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight)
- **Motion:** three tickets **pop-in** onto a growing pile (staggered ~4 frames apart); CHIEF polishes his medals in a loop.
- **Camera:** very slight push-in (100%→104%).
- **Motion graphics/FX:** each ticket pop-in gets a tiny "poof"; one sparkle glint off a medal.
- **Transition out:** hard cut.

### SHOT 5 — 0:16–0:22 · FULL.LOW.PUSHIN → HOLD
- **Motion:** CHIEF hops onto the podium, plants the flag, snaps into the victory pose, stamp raised to the sky. Then **freeze** (long ~1.5 s proud hold).
- **Camera:** low hero-angle, gentle rise/push-in that settles into the hold.
- **Motion graphics/FX:** `FX_sparkle` twinkles around the raised stamp; subtle radial "hero" shape lines behind him (flat, `PAPER`/`BRAND_YELLOW`).
- **AUDIO CUE (critical):** music **cuts to silence** exactly at the pose freeze (~0:18). See file 05.
- **Transition out:** hard cut.

### SHOT 6 — 0:22–0:27 · WIDE.EYE.STATIC (deep flat focus)
- **Motion:** CHIEF stays frozen mid-pose (fg-center). Tow truck drives in from bg-right, hook arm swings toward the red no-parking zone. PIP's head turns, eyes widen (hopeful).
- **Camera:** locked wide; a slow suspense **hold** as the hook aligns over CHIEF's scooter at ~0:26.
- **Motion graphics/FX:** none loud — keep it tense. Optional single sweat-bead pop on PIP or a faint "!" over PIP at ~0:25 (`INK`, tiny).
- **Transition out:** hard cut.

### SHOT 7 — 0:27–0:31 · WIDE.EYE.PUNCHIN → SETTLE
- **Motion:** hook clamps CHIEF's own scooter; the truck-arm wields CHIEF's own giant stamp and **slams** the red "TOWED" mark. CHIEF's face runs the **3-stage snap** smug→shocked→panicked as he's yanked off the podium, arms flailing. PIP throws up a gleeful celebrate.
- **Camera:** **quick punch-in** (fast 100%→118% over ~6 frames) on the stamp slam, then settle back.
- **Motion graphics/FX:** big `FX_impact_star` burst behind the "TOWED" stamp; `FX_motionlines` on the yank; **0.5 s freeze** on the "TOWED" frame (screenshot-able punchline). Optional quick white 1-frame flash on impact.
- **AUDIO CUE:** music SLAMS back + PUNCH + record-scratch exactly on the stamp hit (~0:29).
- **Transition out:** hard cut.

### SHOT 8 — 0:31–0:32 · WIDE.EYE.STATIC (== SHOT 1)
- **Motion:** CHIEF shrinks into bg-right, hung off his towed scooter (medals jangle). PIP peels the popped-off boot (small "pop"), turns, gives a small friendly wave to camera.
- **Camera:** return to the **exact Shot-1 framing/composition** (loop seam).
- **Motion graphics/FX:** tiny "pop" puff on the boot release; optional caption "rules are rules 😌" 0:31.2–0:31.9. No residual FX on the final frame (loop must be clean).
- **Transition out:** **hard cut** ≤1 s after the wave. Final frame must equal Shot-1 frame 1.

---

## B) Transitions & cut map (quick reference)
| Between | Type | Notes |
|---|---|---|
| C1→C2→C3→C4 | hard cut | snappy 2–5 s clips |
| C4→C5 | hard cut | into the flex |
| **C5 internal** | freeze + audio drop | the pattern-break silence begins |
| C5→C6 | hard cut | truck appears |
| C6→C7 | hard cut into **punch-in** | the twist |
| **C7 internal** | 0.5 s freeze on "TOWED" | screenshot punchline |
| C7→C8 | hard cut | payoff |
| C8→(loop) | hard cut, seam to C1 | seamless replay |

**No** dissolves, fades, wipes, glitch, or zoom-blur anywhere. The only "effects" are the listed pop-ins, sparkle, impact-star, motion-lines, one optional impact flash, and the two freezes.

---

## C) Optional single "master prompt" (for one-shot generators)
If your tool takes one continuous prompt, use this (it references the same beats/timing):
```
{style prefix from file 02 §0}
A ~32s 9:16 flat-2D cartoon comedy short, 30fps, hard cuts only, no camera rotation, snappy
pose-to-pose animation with strong holds. Story in 8 beats:
(0-2s) WIDE static: smug rotund warden CHIEF (teal jacket, peaked cap, yellow medal sash) struts
into a parking lot; tiny PIP (teal scarf) fumbles coins at a meter; CHIEF's own scooter sits in a
red NO-PARKING zone bottom-right.
(2-6s) MED slow push-in: CHIEF grins, draws a giant stamp and ticket pad.
(6-11s) MED static: CHIEF stamps a ticket and clamps a yellow wheel-boot on PIP's tiny scooter;
PIP tears up; impact hold on the clamp.
(11-16s) MED-WIDE: a mountain of tickets pops onto PIP's scooter; CHIEF polishes his medals.
(16-22s) LOW hero angle: CHIEF mounts a podium, plants a flag, raises the stamp in a victory pose
with sparkles; MUSIC CUTS TO SILENCE on the freeze.
(22-27s) WIDE static, tense: behind the oblivious CHIEF a tow truck rolls in toward the red zone;
PIP notices, hopeful.
(27-31s) WIDE quick punch-in: the hook tows CHIEF'S OWN scooter and his own stamp slams a red
"TOWED" mark; CHIEF snaps smug→shocked→panicked, yanked off the podium; impact-star burst;
0.5s freeze on "TOWED".
(31-32s) WIDE, identical framing to the opening: CHIEF hauled away; PIP's boot pops off, PIP waves
to camera; hard cut. The final frame matches the first frame for a seamless loop.
Only on-screen text anywhere is the word "TOWED". Advertiser-safe, no gore.
```

---

## D) Handoff / minimal-edit checklist
- [ ] Render each shot at the exact timecode length above (or trim to it) — total ≈32 s.
- [ ] Assemble in order C1→C8, **hard cuts**, no transitions added.
- [ ] Insert the two freezes (C5 ~1.5 s hero hold; C7 0.5 s "TOWED").
- [ ] Lay VO (file 03) and BGM/SFX (file 05) onto the fixed timecodes — everything is pre-synced.
- [ ] Verify loop seam: overlay last frame on first frame; re-render C8 to the C1 plate if it drifts.
- [ ] Confirm the music silence spans 0:16–0:27 and the PUNCH lands on the C7 stamp (~0:29).
