# v19 — BGM, SFX & Audio Reference ("The Deep End") · **SHORTS**

> Prescriptive cue sheet. §2 gives the layer stack for every time range; §4 lists every SFX hit with
> timecode and level. Locks to the master timeline in `01-video-script.md`. **Mute-first.**

## 1. Assets

**Music**
| ID | Description | Used |
|---|---|---|
| `MUS_outdoor_bed_v1` | House cue, outdoor variant — plucky bass, brushed percussion, a jaunty whistle lead, ~116 BPM, major. A wood-tap accent per contraption part | 0:01.5–0:16 |
| `MUS_outdoor_stinger_v1` | Bright hit deflating into a low sucking descent | 0:27 |
| `MUS_outdoor_resolve_v1` | Main melody once through, slow, warm | 0:29–0:32 |

Same instrumentation family as v1's `MUS_comedy_bed_v1`.

**SFX**
| ID | Description |
|---|---|
| **`SFX_plank_clack_v1`** | **Signature, stage 1** — one plank set down on stone. Dry, woody, pitched |
| **`SFX_rig_creak_v1`** | **Signature, stage 2** — the contraption taking load; pitch rises with strain |
| **`SFX_rig_collapse_v1`** | **Signature, stage 3** — the rig pivoting and giving way |
| **`SFX_mud_gloop_v1`** | **Signature, stage 4** — one deep, slow, satisfying mud swallow |
| `SFX_mud_part_v1` | Mud surface parting under weight |
| `SFX_mud_bubble_v1` | A single bubble surfacing |
| `SFX_plank_drag_v1` | A plank hauled out and shouldered |
| `SFX_stone_scrape_v1` | Plank pivoting on stone |
| `SFX_crate_thud_v1` | The counterweight crate landing |
| `SFX_ting_v1` · `SFX_scratch_v1` · `SFX_button_v1` | Reused series set |
| `SFX_amb_field_v1` | Very low outdoor ambience — distant birds, faint wind |

## 2. ⭐ Exact cue sheet

`BGM` · `SFX` · `VO` · `AMB` (`SFX_amb_field_v1`, 0:02→0:32)

| # | Time | Layer stack | BGM | Notes |
|---|---|---|---|---|
| 1 | **0:00–0:01.5** | **SFX + VO only** | **none** | Cold payoff. **No music.** One rising `SFX_mud_part_v1` |
| 2 | **0:01.5–0:02** | **BGM + SFX** | `MUS_outdoor_bed_v1` **enters on the cut** (~-16 dB) | The diagram arrives with the music |
| 3 | **0:02–0:06** | **BGM + SFX + VO + AMB** | bed (full, ~-14 dB) | Rewind. **Protect the 0:04 plank drag** — it is the seed |
| 4 | **0:06–0:11** | **BGM + SFX + VO + AMB** | bed + wood-tap layer 1 | Escalation 1 |
| 5 | **0:11–0:16** | **BGM + SFX + VO + AMB** | bed + wood-tap layer 2 — **brightest, densest** | Escalation 2 |
| 6 | **0:16** | **SFX + AMB only** | **cut mid-phrase** | Lands on the frame the pose locks |
| 7 | **0:16–0:27** | **SFX + AMB — SILENCE (11 s)** | **none** | Only 4 sounds permitted (§3). AMB ducked to ~-28 dB |
| 8 | **0:27–0:29** | **BGM + SFX + VO + AMB** | `MUS_outdoor_stinger_v1` slams in | The pivot |
| 9 | **0:29–0:32** | **BGM + SFX + VO + AMB** | `MUS_outdoor_resolve_v1` | Payoff + loop out |

```
0:00 (silence) ─┐
0:01.5          └─ BED ── +tap1 ── +tap2 (peak) ─┐
0:16                                ╌╌ SILENCE ╌╌┘  0:27 ┌ stinger ┐ resolve ► 0:32
```

## 3. The silence beat (0:16–0:27)

11 s of total musical silence, cut **mid-phrase** on the frame CHIEF's pose locks.

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16–0:27 | `SFX_amb_field_v1` | -28 | The field stays alive without filling the space |
| **0:22 / 0:24 / 0:26** | **`SFX_rig_creak_v1` ×3, pitch rising** | **-15** | **The countdown.** Three settle increments, each higher-pitched — an audible progress bar toward the gap |
| ~0:25 | `SFX_mud_bubble_v1` | -20 | One bubble from the X. The mud, waiting |
| ~0:26 | `SFX_button_v1` tick | -18 | One anticipation beat |

No VO except an optional whispered *"…he took that one."* at ~0:24 (≤0.7 s). No music, no stings.

> The rising creak is the whole beat: the picture shows a man standing triumphantly above the mud while
> the sound tells you the thing holding him up is losing.

## 4. Complete SFX hit list

| Time | SFX | Level | Purpose |
|---|---|---|---|
| 0:00 | `SFX_mud_part_v1` | **-9** | C1 — first sound, over no music |
| 0:01.5 | `SFX_ting_v1` | -14 | C1b — the X reads |
| 0:03 | `SFX_plank_clack_v1` | -13 | C2 — PIP steps onto plank one |
| **0:04** | **`SFX_plank_drag_v1`** | **-16 (unremarkable)** | **C2 — SEED B. The plank hauled out. Audible, not highlighted** |
| 0:05 | `SFX_button_v1` "pfft" | -16 | C2 — CHIEF's contempt |
| 0:07 | `SFX_stone_scrape_v1` | -14 | C3 — the see-saw balancing |
| 0:08 / 0:10 | `SFX_plank_clack_v1` ×2 | -13 | C3 — PIP crossing |
| 0:11.5 / 0:13 / 0:14.5 | `SFX_plank_clack_v1` ×3 rising | -11 | C4 — parts added, each louder and higher |
| 0:13 | `SFX_crate_thud_v1` | -12 | C4 — the counterweight |
| 0:14 | `SFX_rig_creak_v1` (enters, low) | -20 | C4 — the rig begins to take load |
| 0:15 | `SFX_button_v1` fanfare stab | -12 | C4 — vanity punctuation |
| 0:16 | *(music cuts — no new SFX; the creak becomes exposed)* | — | C5 — the turn by subtraction |
| **0:22 / 0:24 / 0:26** | **`SFX_rig_creak_v1` ×3** | **-15** | **C6 — inside the silence. The settle countdown** |
| 0:25 | `SFX_mud_bubble_v1` | -20 | C6 — inside the silence |
| 0:27 | `SFX_rig_collapse_v1` | -10 | C7 — the pivot |
| **0:29** | **`SFX_mud_gloop_v1`** | **-6 — loudest in the video** | **C7 — one deep, slow swallow. Satisfying, not violent** |
| 0:29 | `SFX_scratch_v1` | -11 | C7 — reversal punctuation |
| 0:30.5 | `SFX_mud_bubble_v1` | -16 | C7 — one bubble beside him |
| 0:31 | `SFX_plank_clack_v1` | -13 | C8 — PIP lays the plank back |
| 0:32 | `SFX_button_v1` ding | -12 | C8 — series close |

## 5. Loudness / delivery
- Integrated **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- Duck BGM ~5 dB under VO1–VO5; release into the silence.
- **Protected sounds:** the **0:04 plank drag** (the seed) and the **three 0:22–0:26 creaks**.
- **Loudest, in order:** 0:29 gloop (-6) → 0:00 mud part (-9) → 0:27 collapse (-10). ~3 dB headroom before the gloop.
- **The gloop must read as satisfying, not violent** — long, low and slow, not a sharp impact. This is the audio half of the ad-safety guardrail: the sound sells *indignity*, not *peril*.
- Never compress the silence up.
- Shorts play muted by default: confirm the depth stick and the gap tell the story with audio off.

## 6. Sourcing & signature
- Original or royalty-free/licensed only.
- Reused: `SFX_ting_v1`, `SFX_scratch_v1`, `SFX_button_v1`, narrator voice.
- **Signature-sound principle:** v18's jug, v19's is the **plank** — four states, `clack → creak → collapse → GLOOP`, mapping to the four acts. The inversion is the cleanest available here: the episode's **first** sound is one dry plank clack as PIP steps on, and its **last** sound is the same dry clack as PIP lays the plank back. The signature opens and closes on the underdog doing the simple thing correctly, with all of CHIEF's engineering noise in between.
