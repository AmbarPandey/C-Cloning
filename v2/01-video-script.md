# v2 — Video Script ("The Victory Lap")

> **Video ID:** v2 · **Format:** YouTube Short, 1080×1920 (9:16), 30 fps · **Runtime:** ~33 s
> **Idea source (locked):** **A2** — the next-ranked item in the Stage 4 deterministic queue.
> **Decision path:** Goal *Reach* → Behavior *Share* → **NP2 Underdog Reversal** → **SC3 Competition**
> → **CM-E1 Escalation** (dominant mechanic) → **TW1 Role Reversal** (single twist core) → **FM Plot-Twist**.
> **Confidence:** High · **FinalScore:** **9.0**
> **Cast:** CHIEF (self-declared champion) + PIP (underdog challenger) — recurring cast, per the locked constraint.
> **Premise:** A boastful champion straps on rocket after rocket to win a race by a humiliating
> margin — and goes so fast he flies clean *over* the low finish tape without ever breaking it.
> The tiny challenger rolls up and snaps it with his chest. The roles swap completely.

**This folder (v2) contains 5 synced files — all share the same master timeline below:**
1. `01-video-script.md` ← you are here (beats, timeline, script)
2. `02-image-generation-reference.md` (characters, reactions, surroundings, per-shot image prompts)
3. `03-voiceover-script.md` (narration synced to timecodes)
4. `04-video-generation-prompt.md` (full motion/camera/transition/FX prompt)
5. `05-audio-bgm-sfx-reference.md` (BGM, SFX, silence beat, sync map)

---

## Formula mapping (Library 1 — the locked 6-beat skeleton)
| Beat | Clip(s) |
|---|---|
| Recognizable Hook | C1 |
| False Comfort | C2 |
| Visual Escalation | C3–C4 |
| Pattern Break | C5–C6 |
| Twist | C7 |
| Hard Cut Ending | C8 |

## The two seeds (what makes the twist fair + rewatchable)
- **Seed A (primary, mechanical):** the checkered **finish tape is strung LOW** — chest-height for tiny
  PIP — clearly visible in C1. CHIEF's escalation lifts him into the air, so he passes *above* it and
  never breaks it. Unpredictable in foresight, inevitable in hindsight.
- **Seed B (callback, comedic):** the drab little **participation ribbon** pinned to the podium in C1,
  which CHIEF contemptuously flicks away in C2 — and receives himself in C8.

## Score reproduction (auditable, per the repo's locked formulas)
```
ViralityPotential = 0.30·Share + 0.25·Replay + 0.20·Evergreen + 0.15·AdSafe + 0.10·Ease
Share 10 · Replay 9 (seed present ⇒ ×1.0) · Evergreen 10 · AdSafe 10 · Ease 6
                  = 3.00 + 2.25 + 2.00 + 1.50 + 0.60 = 9.35
CompatibilityChain: NP2↔SC3 5/5 · SC3↔CM-E1 5/5 · CM-E1↔TW1 5/5 · TW1↔FM 5/5
                  = (1.00×1.00×1.00×1.00)^(1/4) = 1.00
Confidence (High)  = 1.0
DifficultyPenalty  = 0.0833 × 4 = 0.33   (Difficulty 4 — new track environment + rocket/flight animation)
FinalScore = 9.35 × 1.00 × 1.0 − 0.33 = 9.02  ⇒ 9.0 ✔ (matches the locked Stage 4 queue value)
Hard gate: AdSafe 10 ≥ 4, one pattern, one twist core, not a forbidden combo ⇒ valid.
```
> Sub-scores are **seed values tagged inferred `[I]`** per the Immutability Contract — only real
> published-video analytics may promote them.

---

## Master timeline (single source of truth — every file aligns to these 8 clips)

| Clip | Timecode | Beat | On-screen | Emotion (CHIEF / PIP) |
|---|---|---|---|---|
| C1 | 0:00–0:03 | **Hook + SEEDS** | Start line. CHIEF struts up with rocket scooter + giant trophy; PIP on tiny skates. Far end: **low checkered finish tape**; podium with the drab **participation ribbon** | smug / worried |
| C2 | 0:03–0:07 | **False comfort** | CHIEF plants his trophy on the podium ("saving it"), flicks the participation ribbon away toward PIP, points mockingly | gloating / worried |
| C3 | 0:07–0:12 | **Escalation 1** | Flag drops. Booster #1 ignites — CHIEF rockets ahead in a flat smear; PIP starts a slow roll | triumphant / determined |
| C4 | 0:12–0:18 | **Escalation 2** | Greedy for a bigger margin, CHIEF stacks boosters #2, #3, #4; wheels leave the ground | peak-gloat / determined |
| C5 | 0:18–0:23 | **Anticipation** | Absurd velocity; nose tips up; he's flying. **Music cuts to silence at 0:19** | triumphant (L3) / — |
| C6 | 0:23–0:27 | **Pattern break** | He sails clean **OVER** the low tape — untouched, still swaying — and shrinks over the horizon, gloating, oblivious | oblivious / hopeful |
| C7 | 0:27–0:31 | **TWIST** | PIP rolls up and **breaks the tape** with his chest. Confetti. PIP on the podium with the giant trophy + champion medal. CHIEF screeches back into frame | shocked→panicked / gleeful |
| C8 | 0:31–0:33 | **Payoff / loop** | Deflated CHIEF stands in PIP's old start spot; PIP leans down and pins the **participation ribbon** on him. PIP waves. C1 composition, roles swapped | sheepish / relieved |

---

## Scene-by-scene script

> Legend — **VIS** visual/staging · **ACT** action · **CAM** camera · **VO** narration (optional layer) · **SFX** sound · **EMO** emotion

### C1 — HOOK + SEEDS (0:00–0:03)
- **VIS:** Wide flat race track. `ASPHALT` lane, `SKY` backdrop, flat empty grandstand shapes + bunting in bg. Start line (checkered) foreground-left. Far end mid-frame: the **checkered finish tape strung LOW**, at PIP's chest height (**Seed A**). Beside it a small podium with a drab `ASPHALT`-grey **participation ribbon** pinned to it (**Seed B**).
- **ACT:** CHIEF struts in, cap/sash/medals, wheeling a rocket scooter, a giant `BRAND_YELLOW` trophy tucked under one arm. PIP waits at the line on tiny roller skates.
- **CAM:** Static wide establishing (this framing returns in C8).
- **VO:** *"The champion brought a rocket."*
- **SFX:** Upbeat race bed (low); strut boings; a small engine idle.
- **EMO:** CHIEF smug · PIP worried.

### C2 — FALSE COMFORT (0:03–0:07)
- **VIS:** Medium two-shot at the start line.
- **ACT:** CHIEF plants the giant trophy on the podium as if already won, **flicks the little participation ribbon off the podium** so it flutters toward PIP, then points at him mockingly.
- **CAM:** Slow push-in on the smug point.
- **VO:** *"The challenger brought… roller skates."*
- **SFX:** Trophy clunk; a dismissive "pfft" flick; comedic "aha" sting.
- **EMO:** CHIEF gloating · PIP worried (shrinks).

### C3 — ESCALATION 1 (0:07–0:12)
- **VIS:** Checkered start flag drops.
- **ACT:** Booster #1 ignites — CHIEF launches down the track in a flat smear of motion lines. PIP begins a slow, determined roll.
- **CAM:** Static wide; whip-follow of the launch, then settle.
- **VO:** *"It went about how you'd expect."*
- **SFX:** Flag whoosh; **booster ignition #1** (the signature sound); doppler pass-by; tiny skate squeaks.
- **EMO:** CHIEF triumphant · PIP determined.

### C4 — ESCALATION 2 (0:12–0:18)
- **VIS:** CHIEF mid-track, already far ahead — but not satisfied.
- **ACT:** He straps on boosters **#2, #3, #4** in comic pop-ins. Engine scream rises. His wheels lift off the ground.
- **CAM:** Slight push-in; a 3-frame hold on each booster pop-in.
- **VO:** *"But winning wasn't enough. He wanted a margin."*
- **SFX:** **Booster ignitions #2–#4, each a step higher in pitch**; rising engine scream; a proud fanfare stab.
- **EMO:** CHIEF peak-gloat · PIP determined (still rolling).

### C5 — ANTICIPATION / peak overconfidence (0:18–0:23)
- **VIS:** Absurd velocity. Flat ghost-smears trail him. The scooter's nose tips upward — he is now genuinely airborne, sparkles trailing, chest out, aimed dead at the finish.
- **ACT:** He rises. He does not level out.
- **CAM:** Low hero angle, push-in that settles into a held shot.
- **VO:** *"So he went faster."* → then stop.
- **SFX:** Bed swells… then **CUTS TO SILENCE at 0:19**. Only a thin, distant engine whine remains.
- **EMO:** CHIEF triumphant (L3).

### C6 — PATTERN BREAK (0:23–0:27)
- **VIS:** In near-silence, CHIEF sails **clean over the low tape** — it is not touched. The tape sways gently, intact. He shrinks away toward the horizon, still holding the victory pose, utterly oblivious. Far behind, PIP keeps rolling, and looks up with dawning hope.
- **ACT:** The tape's stillness is the joke. Hold on it.
- **CAM:** Static wide, deep flat focus; suspense hold on the untouched tape at ~0:25.
- **VO:** (silence — let it breathe) optional whisper *"…all of it."*
- **SFX:** Silence; a fading doppler whine; one suspense tick; a soft flutter of tape.
- **EMO:** CHIEF oblivious · PIP hopeful.

### C7 — TWIST / ROLE REVERSAL (0:27–0:31)
- **VIS:** PIP rolls up and **breaks the finish tape with his chest.** `FX_confetti` bursts, the checkered flag waves. Cut to PIP up on the podium, the giant `BRAND_YELLOW` trophy in his arms, the champion medal around his neck.
- **ACT:** In the distance CHIEF slams to a stop, whips around, and sees it — face snapping **smug → shocked → panicked**.
- **CAM:** Quick punch-in on the tape snap; hard cut to the podium; ~0:5 s freeze on PIP + trophy.
- **VO:** *"He forgot one thing. You have to cross the line."*
- **SFX:** Music **SLAMS back**; tape SNAP; confetti pop; champion-medal ding; long skid screech; record-scratch.
- **EMO:** CHIEF panicked · PIP gleeful (L3). **← the SHARE trigger.**

### C8 — PAYOFF / LOOP (0:31–0:33)
- **VIS:** Composition matches C1. But the roles are swapped: **PIP is on the podium** with the trophy; **CHIEF stands deflated in PIP's old start-line spot**, boosters spent and drooping.
- **ACT:** PIP leans down and gently pins the drab **participation ribbon** on CHIEF's chest (**Seed B payoff**), then gives a small wave to camera.
- **CAM:** Return to the C1 framing; hard cut ≤1 s after the wave.
- **VO:** *"Slow and steady. Every time."*
- **SFX:** Sad booster deflate "pffffft"; ribbon pin tap; warm resolve chord; button ding.
- **EMO:** CHIEF sheepish · PIP relieved.

---

## Loop-seam note (deliberate difference from v1)
v1 used an **identical-frame** seam (last frame == first frame). v2 uses a **composition-match seam
with the roles swapped**: C8 reuses C1's exact camera framing, staging positions, and background
plate, but CHIEF and PIP have exchanged positions and status props. This is intentional — on replay
the viewer immediately re-reads the opening with the reversal in mind, which rewards the rewatch and
exposes Seed A (the low tape) and Seed B (the ribbon). **Requirement:** the background plate, framing,
and horizon line must match C1 exactly; only the characters and their props differ.

## Character-lock note (important for the render)
CHIEF's **cap, sash, and medals are costume, not props** — they are part of his locked silhouette and
must **never** be removed or transferred to PIP. The role reversal is therefore carried entirely by
**position + transferable props** (podium, giant trophy, champion medal, participation ribbon).
The comedy is stronger for it: CHIEF ends up still *dressed* as a champion while holding a
participation ribbon.

---

## Compliance checklist (do not ship if any fails)
- [ ] Story 100% clear with sound OFF (mute-readable).
- [ ] Hook lands in 0–3 s; twist lands 27–31 s.
- [ ] **Seed A** (low finish tape) clearly visible in C1 and visibly **untouched** in C6.
- [ ] **Seed B** (participation ribbon) visible in C1, flicked away in C2, pinned on CHIEF in C8.
- [ ] Exactly one twist core (TW1 Role Reversal); one dominant mechanic (CM-E1 Escalation); one pattern (NP2).
- [ ] Only CHIEF + PIP appear; no incidental characters or crowds; cast on-model (see file 02).
- [ ] **Zero on-frame text** anywhere — the checkered pattern carries start/finish.
- [ ] CHIEF keeps cap + sash + medals in every shot; PIP keeps his teal scarf in every shot.
- [ ] C8 framing/background matches C1 exactly (roles swapped).
- [ ] Music silence spans 0:19–0:27; VO never covers the tape SNAP (~0:29).
- [ ] Advertiser-safe: no crash damage, no injury — CHIEF simply overshoots and returns unharmed.
