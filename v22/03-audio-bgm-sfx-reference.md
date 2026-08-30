# v22 — BGM, SFX & Audio Reference ("The Shortcut") · **SHORTS**

> Prescriptive cue sheet. §2 gives the layer stack per time range; §4 lists every hit with timecode and
> level. Locks to `01-video-script.md`. **Mute-first.**

## 1. Assets

**Music**
| ID | Description | Used |
|---|---|---|
| `MUS_park_bed_v1` | House cue, strolling variant — plucky bass, soft brushed percussion, a light pizzicato walking lead, ~112 BPM, major. A pizzicato note per footstep pair, so the tempo tracks his hurry | 0:01.5–0:16 |
| `MUS_park_stinger_v1` | Bright hit deflating into a low descending slide | 0:27 |
| `MUS_park_resolve_v1` | Main melody once through, slow, warm | 0:29–0:32 |

**SFX**
| ID | Description |
|---|---|
| **`SFX_footstep_v1`** | **Signature, stage 1** — one footfall on stone. Three speeds: steady / brisk / fast |
| **`SFX_duck_shuffle_v1`** | **Signature, stage 2** — a small webbed shuffle. Gets *closer*, not louder |
| **`SFX_trough_lap_v1`** | **Signature, stage 3** — shallow water at ground level. Low, flat, small |
| **`SFX_fountain_arc_v1`** | **Signature, stage 4 (the payoff)** — a proper fountain arcing into a basin. Bright, tall, generous |
| `SFX_glove_tap_v1` | A glove tapping a signpost |
| `SFX_cup_set_v1` | A cup set down on stone |
| `SFX_ting_v1` · `SFX_scratch_v1` · `SFX_button_v1` | Reused series set |
| `SFX_amb_park_v1` | Very low park ambience — distant birds |

> **The two water assets are the twist.** `SFX_trough_lap_v1` and `SFX_fountain_arc_v1` must be
> unmistakably different in **height and generosity**, not merely in volume: one is a puddle, the other is
> a jet. A listener with their eyes shut should know which one is the good fountain.

## 2. ⭐ Exact cue sheet

`BGM` · `SFX` · `VO` · `AMB` (`SFX_amb_park_v1`, 0:02→0:32)

| # | Time | Layer stack | BGM | Notes |
|---|---|---|---|---|
| 1 | **0:00–0:01.5** | **SFX + VO only** | **none** | Cold payoff. **No music.** One `SFX_trough_lap_v1` — the small, wrong water, heard before it is understood |
| 2 | **0:01.5–0:02** | **BGM + SFX** | `MUS_park_bed_v1` **enters on the cut** (~-16 dB) | The sign arrives with the music |
| 3 | **0:02–0:06** | **BGM + SFX + VO + AMB** | bed (full, ~-14 dB) | Rewind. Glove taps on the signpost |
| 4 | **0:06–0:11** | **BGM + SFX + VO + AMB** | bed + pizzicato per footstep pair | Escalation 1, intercut |
| 5 | **0:11–0:16** | **BGM + SFX + VO + AMB** | bed, **fastest** — tempo tracks his hurry | Escalation 2 |
| 6 | **0:16** | **SFX + AMB only** | **cut mid-phrase** | Lands on the frame he plants the pose |
| 7 | **0:16–0:27** | **SFX + AMB — SILENCE (11 s)** | **none** | Only 3 sounds permitted (§3). AMB ducked to ~-28 dB |
| 8 | **0:27–0:29** | **BGM + SFX + VO + AMB** | `MUS_park_stinger_v1` slams in | The reveal |
| 9 | **0:29–0:32** | **BGM + SFX + VO + AMB** | `MUS_park_resolve_v1` | Payoff + loop out |

```
0:00 (silence) ─┐
0:01.5          └─ BED ── +pizz ── fastest ─┐
0:16                          ╌╌ SILENCE ╌╌╌┘  0:27 ┌ stinger ┐ resolve ► 0:32
```

## 3. The silence beat (0:16–0:27)

11 s of musical silence, cut mid-phrase on the pose.

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16–0:27 | `SFX_amb_park_v1` | -28 | The park stays alive without filling the space |
| 0:16–0:27 | `SFX_trough_lap_v1` (continuous, small) | -18 | The wrong water, close and shallow |
| **0:22 / 0:24 / 0:26** | **`SFX_duck_shuffle_v1` ×3, each PANNED CLOSER** | **-16** | **The countdown.** Not louder — *nearer*. Three shuffles closing in on a kneeling man |

No VO except an optional whispered *"…the paw."* at ~0:25 (≤0.5 s). No music, no stings.

> **The craft point:** the escalation inside the silence is **spatial, not dynamic.** The ducks do not get
> louder, they get closer. That is a genuinely different tension device from every prior episode, all of
> which escalated by volume or pitch. On phone speakers, support the pan with a small rise in presence so
> the effect survives a mono fold-down.

## 4. Complete SFX hit list

| Time | SFX | Level | Purpose |
|---|---|---|---|
| 0:00 | `SFX_trough_lap_v1` | **-10** | C1 — first sound, over no music. Small, shallow, wrong |
| 0:01 | `SFX_duck_shuffle_v1` | -16 | C1 — one shuffle at the frame edge |
| 0:01.5 | `SFX_ting_v1` | -14 | C1b — the arrows read |
| 0:03 / 0:04 | `SFX_glove_tap_v1` ×2 | -14 | C2 — CHIEF taps the short arrow |
| 0:04 | `SFX_footstep_v1` (steady) | -16 | C2 — PIP sets off |
| 0:05 | `SFX_button_v1` "pfft" | -16 | C2 — the sneer |
| 0:06–0:11 | `SFX_footstep_v1` (brisk / steady, alternating per intercut) | -14 | C3 — the scoreboard, audible |
| 0:11–0:15 | `SFX_footstep_v1` (fast) | -12 | C4 — the hurry |
| 0:13 | `SFX_duck_shuffle_v1` (low, off-frame) | -20 | C4 — the queue forming just out of shot |
| 0:15 | `SFX_button_v1` fanfare stab | -12 | C4 — vanity punctuation |
| 0:16 | *(music cuts — no new SFX; the trough lap becomes exposed)* | — | C5 — the turn by subtraction |
| 0:16–0:27 | `SFX_trough_lap_v1` (continuous) | -18 | C5→C6 — inside the silence |
| **0:22 / 0:24 / 0:26** | **`SFX_duck_shuffle_v1` ×3, panning closer** | **-16** | **C6 — inside the silence. The spatial countdown** |
| **0:29** | **`SFX_fountain_arc_v1`** | **-7 — loudest in the video** | **C7 — the tall fountain, from PIP's side. Bright, generous, tall** |
| 0:29 | `SFX_scratch_v1` | -11 | C7 — reversal punctuation |
| 0:30.5 | `SFX_trough_lap_v1` | -18 | C7 — his own water, still there, still small |
| 0:31 | `SFX_cup_set_v1` | -15 | C8 — PIP sets the cup down |
| 0:32 | `SFX_button_v1` ding | -12 | C8 — series close |

## 5. Loudness / delivery
- Integrated **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- Duck BGM ~5 dB under VO1–VO5; release into the silence.
- **Protected sounds:** the **0:00 trough lap** (planted before it is understood — the audio half of `TM3`) and the **three panned duck shuffles**.
- **Loudest, in order:** 0:29 fountain arc (-7) → 0:00 trough lap (-10) → 0:15 fanfare (-12).
- **The defining mix decision:** the payoff sound belongs to **PIP's side of frame**, not CHIEF's. Every other episode's loudest moment happens *to* CHIEF. Here the loudest moment is simply the correct fountain working properly, somewhere else. Pan it toward PIP and let CHIEF's small trough lap continue underneath it — the two heard together *is* the joke.
- Never compress the silence up.
- Shorts play muted by default: confirm the two fountain heights and the kneeling posture carry the story with audio off.

## 6. Sourcing & signature
- Original or royalty-free/licensed only. **No animal distress vocalisations of any kind** — the ducks shuffle, nothing more.
- Reused: `SFX_ting_v1`, `SFX_scratch_v1`, `SFX_button_v1`, narrator voice.
- **Signature-sound principle:** v18 jug · v19 plank · v20 cart · v21 pressure. **v22's signature is water height** — four states, `footstep → duck shuffle → trough lap → FOUNTAIN ARC`. The inversion is unique in the series: the signature's final, best state is **never heard by the antagonist at all** — it plays from the far side of frame, at the destination he didn't walk to. The first sound of the episode is the small wrong water, and it is still running underneath the big right one at the end.
