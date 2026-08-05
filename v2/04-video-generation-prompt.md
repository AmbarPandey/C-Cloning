# v2 — Video-Generation Script / Prompt ("The Victory Lap")

> A complete, timeline-locked prompt set for a text/image-to-video generator (Sora, Kling, Runway,
> Pika, Luma, or Anijam driving the stills from file 02). It specifies **motion, camera angles,
> transitions, cut timing, freezes and motion-graphics/FX per shot**, so the generated output needs
> **minimal editing** — ideally just top-and-tail plus the audio layup. Everything aligns to the master
> timeline in `01-video-script.md`, visuals in `02`, VO in `03`, audio in `05`.

**Global render spec:** 1080×1920 (9:16) · 30 fps · ~33 s (≈990 frames) · flat-2D cartoon house style
(file 02 §0) · snappy pose-to-pose with strong holds · **hard cuts only** (no dissolves/fades) · **no
camera rotation/orbit, no handheld** · **no blur/glow/gradients** · composition-match loop seam.

**Motion philosophy:** limited animation — hold poses on comedy beats, animate in short bursts.
**Speed is rendered flat:** hard-edged motion lines + 2–3 offset flat ghost silhouettes + smear shapes.
Never gaussian/motion blur. Every move below is intentional; add nothing extra.

---

## A) Shot-by-shot generation script (paste each block into your video tool)

> Format per shot: **[timecode] FRAMING.ANGLE.MOVEMENT** — subject motion — camera — transitions/FX — cut.

### SHOT 1 — 0:00–0:03 · WIDE.EYE.STATIC
- **Motion:** CHIEF struts in from the left edge to left-third (bouncy 2-step strut, trophy bobbing under his arm, scooter wheeled alongside). PIP does a small nervous skate-shuffle in place at the line. The low finish tape sways almost imperceptibly at the far end.
- **Camera:** locked wide. **8-frame settle hold** on the full composition so both seeds register — the **low tape** and the **participation ribbon on the podium**.
- **Motion graphics/FX:** none (clean establishing). Optional caption "watch the tape 👀" fades in 0:01.0–0:02.0 (bottom-center pill, added in edit, not baked).
- **Transition out:** hard cut.

### SHOT 2 — 0:03–0:07 · MED.EYE.PUSHIN(slow)
- **Motion:** CHIEF plants the giant trophy onto the podium (small settle bounce), then **flicks the participation ribbon** off the podium with one glove — the ribbon flutters in a slow arc toward PIP and lands at his skates. CHIEF turns and points, gloating. PIP shrinks.
- **Camera:** slow push-in (100%→110% over 4 s) toward the smug point.
- **FX:** small "aha" eye glint on CHIEF at ~0:05; the ribbon's flutter arc is a clean flat tumble (3–4 rotation keys, no blur).
- **Transition out:** hard cut.

### SHOT 3 — 0:07–0:12 · WIDE.EYE.WHIP → STATIC
- **Motion:** the checkered start flag **drops** (fast 3-frame snap). Booster #1 ignites; CHIEF launches left→right down the track as a flat smear, exiting deep into mid-frame. PIP begins a slow, steady, determined roll (small looping skate cycle).
- **Camera:** a short **whip-follow** of the launch (~8 frames) that settles back to a locked wide.
- **Motion graphics/FX:** `FX_motionlines` + 3 offset flat ghost silhouettes on the launch; a small flat dust puff at the start line; `FX_impact_star` (small) on ignition.
- **Transition out:** hard cut.

### SHOT 4 — 0:12–0:18 · MED-WIDE.EYE.PUSHIN(slight)
- **Motion:** boosters **#2, #3, #4 pop on** in sequence (staggered ~5 frames apart, each with a small recoil shove). Engine intensity ramps; the scooter's wheels lift off the ASPHALT by the end of the shot. CHIEF's gloat grows with each booster. PIP visible far behind, still rolling.
- **Camera:** slight push-in (100%→104%), plus a **3-frame hold on each booster pop-in** (comic punctuation).
- **Motion graphics/FX:** flame shapes scale up per booster; `FX_motionlines` thicken; one sparkle glint off a medal at ~0:16.
- **Transition out:** hard cut.

### SHOT 5 — 0:18–0:23 · FULL.LOW.PUSHIN → HOLD
- **Motion:** CHIEF's nose tips upward and he **lifts off**, rising steadily across the frame in a held victory pose, flames trailing. He does **not** level out. Long proud hold (~1.5 s) at peak.
- **Camera:** low hero angle with a gentle rise/push-in that settles into the hold.
- **Motion graphics/FX:** `FX_sparkle` trail; flat ghost smears behind him; subtle flat radial "hero" shape lines. The low tape stays visible, small, **below** his flight path.
- **AUDIO CUE (critical):** music **cuts to silence at 0:19**, leaving only a thin distant engine whine. See file 05.
- **Transition out:** hard cut.

### SHOT 6 — 0:23–0:27 · WIDE.EYE.STATIC (deep flat focus)
- **Motion:** CHIEF sails **clean over the low tape** and continues shrinking toward the horizon (scale down to ~15% over the shot), still locked in his victory pose, oblivious. **The tape is not touched** — it sways gently, intact. PIP keeps rolling in from the left and looks up, eyes widening (hopeful).
- **Camera:** locked wide; a deliberate **suspense hold on the untouched tape** at ~0:25 (the tape is the visual subject of this shot, not CHIEF).
- **Motion graphics/FX:** keep it bare — tension comes from stillness. Optional tiny `INK` "!" pop over PIP at ~0:26. No sparkle, no impact FX.
- **Transition out:** hard cut.

### SHOT 7 — 0:27–0:31 · MED.EYE.PUNCHIN → hard cut to podium
- **Motion (beat 1, 0:27–0:29):** PIP rolls into the tape and **breaks it with his chest** — the tape snaps into two flat halves that whip outward; `FX_confetti` bursts; a checkered flag waves in.
- **Motion (beat 2, 0:29–0:31):** hard cut to PIP up on the podium, giant trophy in his arms, champion medal on, gleeful (L3). In the far distance CHIEF skids to a halt and whips around — face running the **3-stage snap** smug→shocked→panicked, arms recoiling.
- **Camera:** **quick punch-in** (fast 100%→118% over ~6 frames) on the tape snap; then a hard cut to a locked medium on the podium.
- **Motion graphics/FX:** big flat `FX_impact_star` behind the snap; `FX_confetti` (flat shapes, falling with a slight stagger); **0.5 s freeze** on PIP-with-trophy (the screenshot-able punchline). Optional 1-frame white flash on the snap.
- **AUDIO CUE:** music **SLAMS back** + tape SNAP + confetti pop + medal ding + long skid screech + record-scratch, all on the ~0:29 hit.
- **Transition out:** hard cut.

### SHOT 8 — 0:31–0:33 · WIDE.EYE.STATIC (framing == SHOT 1)
- **Motion:** PIP, on the podium with the trophy, leans down and **pins the participation ribbon** onto slumped CHIEF's chest (small 4-frame tap), then turns and gives a small friendly wave to camera. CHIEF's four boosters sag/deflate. CHIEF gives one tiny sheepish shrug.
- **Camera:** return to the **exact SHOT-1 framing** — same background plate, same horizon line, same staging marks. Only the characters and their props are swapped.
- **Motion graphics/FX:** small flat "pfft" puff from each deflating booster; a tiny sparkle on the pinned ribbon. Optional caption "he never crossed it 💀" 0:31.4–0:32.4 (edit, not baked). No residual FX on the final frame.
- **Transition out:** **hard cut** ≤1 s after the wave, seaming back to SHOT 1.

---

## B) Transitions & cut map (quick reference)
| Between | Type | Notes |
|---|---|---|
| C1→C2→C3→C4 | hard cut | snappy 3–6 s clips |
| C4→C5 | hard cut | into the lift-off |
| **C5 internal (0:19)** | audio drop | the pattern-break silence begins |
| C5→C6 | hard cut | to the untouched tape |
| **C6 internal (~0:25)** | suspense hold | the tape is the subject |
| C6→C7 | hard cut into **punch-in** | the twist |
| **C7 internal (0:29)** | hard cut + 0.5 s freeze | tape snap → podium punchline |
| C7→C8 | hard cut | payoff |
| C8→(loop) | hard cut, composition seam to C1 | swapped-role replay |

**No** dissolves, fades, wipes, glitch, zoom-blur, or camera rotation anywhere. The only effects are the
listed pop-ins, motion lines, ghost smears, sparkle, impact-star, confetti, one optional flash, and the
two holds/freezes.

---

## C) Optional single "master prompt" (for one-shot generators)
```
{style prefix from file 02 §0}
A ~33s 9:16 flat-2D cartoon comedy short, 30fps, hard cuts only, no camera rotation, no blur or glow,
speed shown with flat motion lines and offset ghost silhouettes, snappy pose-to-pose animation with
strong holds. Two recurring characters: CHIEF, a smug rotund champion in a teal jacket with a peaked
cap and a yellow medal sash; and PIP, a tiny underdog with a teal scarf. Story in 8 beats:
(0-3s) WIDE static: a plain race track with empty grandstands. CHIEF struts to the start line wheeling
a rocket scooter with a giant yellow trophy under his arm; tiny PIP waits on roller skates. At the far
end a checkered finish tape is strung LOW, at PIP's chest height, beside a podium with a small drab
grey participation ribbon pinned to it.
(3-7s) MED slow push-in: CHIEF plants his trophy on the podium as if already won, flicks the drab
ribbon away toward PIP, and points at him mockingly.
(7-12s) WIDE: the start flag drops; one rocket booster fires and CHIEF blasts down the track as a flat
smear; PIP starts a slow determined roll.
(12-18s) MED-WIDE push-in: greedy for a bigger margin, CHIEF stacks three more boosters; his wheels
lift off the ground.
(18-23s) LOW hero angle: CHIEF is fully AIRBORNE, nose tipped up, rising in a proud victory pose with
sparkles; MUSIC CUTS TO SILENCE.
(23-27s) WIDE static, tense and quiet: he sails clean OVER the low tape without touching it and shrinks
toward the horizon, oblivious; the tape sways, INTACT; PIP rolls on, looking up hopefully.
(27-31s) MED quick punch-in: PIP breaks the low tape with his chest; confetti bursts; hard cut to PIP on
the podium holding the giant yellow trophy with a champion medal, beaming; in the distance CHIEF skids
to a stop and snaps smug->shocked->panicked; 0.5s freeze on PIP with the trophy.
(31-33s) WIDE, framing identical to the opening but with the roles SWAPPED: PIP on the podium with the
trophy waving to camera; CHIEF slumped in PIP's old start spot, boosters deflating, still wearing his
cap and sash, now with the drab participation ribbon pinned to his chest. Hard cut.
ZERO on-screen text anywhere. CHIEF never loses his cap/sash/medals; PIP never loses his teal scarf.
Grandstands stay empty. Advertiser-safe: no crash, damage, or injury.
```

---

## D) Handoff / minimal-edit checklist
- [ ] Render each shot at the exact timecode length above (or trim to it) — total ≈33 s.
- [ ] Assemble C1→C8 with **hard cuts**; add no transitions.
- [ ] Insert the holds/freezes: C1 8-frame settle · C4 3-frame per booster · C5 ~1.5 s hero hold · C6 tape hold · C7 0.5 s podium freeze.
- [ ] Verify **Seed A**: the tape reads clearly *low* in C1 and clearly *intact* in C6.
- [ ] Verify **Seed B**: ribbon on podium (C1) → flicked away (C2) → pinned on CHIEF (C8).
- [ ] Verify the **loop seam**: overlay C8 on C1 — background plate, framing and horizon must match; only cast/props differ.
- [ ] Confirm the music silence spans **0:19–0:27** and the tape SNAP lands at **~0:29**.
- [ ] Lay VO (file 03) and BGM/SFX (file 05) onto the fixed timecodes — everything is pre-synced.
- [ ] Final QC: no baked text, no blur/glow, cast on-model, grandstands empty, CHIEF unharmed.
