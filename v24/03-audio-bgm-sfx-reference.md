# v24 — BGM, SFX & Audio Reference ("The Fast Lane") · **SHORTS**

> Prescriptive cue sheet. §2 gives the layer stack per time range; §4 lists every hit with timecode and
> level. Locks to `01-video-script.md`. **Mute-first.**

## 1. Assets

**Music**
| ID | Description | Used |
|---|---|---|
| `MUS_street_bed_v1` | House cue, urban variant — plucky bass, clipped hand percussion, a bustling pizzicato lead, ~124 BPM, major. **The tempo rises with the door's rotation speed** — the arrangement accelerates with him | 0:01.5–0:16 |
| `MUS_street_stinger_v1` | Bright hit deflating into a flat descending slide | 0:27 |
| `MUS_street_resolve_v1` | Main melody once through, slow, warm, coming to rest | 0:29–0:32 |

**SFX**
| ID | Description |
|---|---|
| **`SFX_door_bearing_v1`** | **Signature, all four stages** — the door's bearing. **One recording at four speeds**: slow / medium / fast / relentless. A rising rotational hum with a soft per-wing thump |
| **`SFX_door_thunk_v1`** | **Signature, stage 4 (the payoff)** — the compartment arriving at the pavement stop. One firm, final, deflating thunk |
| `SFX_door_still_v1` | The door held stationary — bearing silence, one settle tick |
| `SFX_shove_v1` | A body-weight shove against a door wing. Three sizes |
| `SFX_crate_wedge_v1` | A crate compressing corner-to-corner (reused from v20) |
| `SFX_crate_creak_v1` | The wedged crate under rotational load |
| `SFX_glass_tap_v1` | A glove tapping glass |
| `SFX_footstep_v1` | Driving footfalls (reused from v22) |
| `SFX_ting_v1` · `SFX_scratch_v1` · `SFX_button_v1` | Reused series set |
| `SFX_amb_street_v1` | Very low street ambience |

## 2. ⭐ Exact cue sheet

`BGM` · `SFX` · `VO` · `AMB` (`SFX_amb_street_v1`, 0:02→0:32)

| # | Time | Layer stack | BGM | Notes |
|---|---|---|---|---|
| 1 | **0:00–0:01.5** | **SFX + VO only** | **none** | Cold payoff. **No music.** `SFX_door_bearing_v1` already at *fast* — the ear starts mid-crisis too |
| 2 | **0:01.5–0:02** | **BGM + SFX** | `MUS_street_bed_v1` **enters on the cut** (~-16 dB) | The rule arrives with the music |
| 3 | **0:02–0:06** | **BGM + SFX + VO + AMB** | bed (full, ~-14 dB) | Rewind. **Protect the 0:04 crate wedge** — it is the seed |
| 4 | **0:06–0:11** | **BGM + SFX + VO + AMB** | bed, **tempo +4%** | Escalation 1. Bearing at *medium* |
| 5 | **0:11–0:16** | **BGM + SFX + VO + AMB** | bed, **tempo +10%, brightest** | Escalation 2. Bearing at *fast* |
| 6 | **0:16** | **SFX + AMB only** | **cut mid-phrase** | Lands on the frame he plants the pose |
| 7 | **0:16–0:27** | **SFX + AMB — SILENCE (11 s)** | **none** | Only 3 sounds permitted (§3). **The bearing does not stop.** AMB ducked to ~-28 dB |
| 8 | **0:27–0:29** | **BGM + SFX + VO + AMB** | `MUS_street_stinger_v1` slams in | The pavement delivery |
| 9 | **0:29–0:32** | **BGM + SFX + VO + AMB** | `MUS_street_resolve_v1` | Payoff + loop out |

```
0:00 (silence, bearing fast) ─┐
0:01.5                        └─ BED ── +4% ── +10% (peak) ─┐
0:16                                          ╌╌ SILENCE ╌╌╌┘  ← the BEARING keeps turning
0:27                                                          ┌ stinger ┐ resolve ► 0:32
```

> **The best music decision in this episode:** the bed's **tempo is tied to the door's rotation.** He isn't
> just spinning faster, he's dragging the score along with him — and when the music cuts at 0:16 the
> bearing carries on at the tempo the music was holding. The rhythm survives its own soundtrack.

## 3. The silence beat (0:16–0:27)

11 s of musical silence, cut mid-phrase on the pose. **A filled silence** — third in the series after v7
and v21 — because the bearing is the thing carrying him past his own exit and must be heard doing it.

| Time | Sound | Level | Why |
|---|---|---|---|
| **0:16–0:27** | **`SFX_door_bearing_v1`** at *relentless* | **-12 — the loudest element in the window** | **The machine, indifferent.** A rotational hum with a per-wing thump. Because the wing thumps are periodic, the listener can *count the revolutions he is failing to get off at* |
| 0:16–0:27 | `SFX_amb_street_v1` | -28 | The street stays alive without filling the space |
| **0:22 / 0:24 / 0:26** | **`SFX_crate_creak_v1` ×3, rising** | **-15** | **The countdown.** One creak per pass-by of the inside opening — the crate audibly doing the blocking |

No VO except an optional whispered *"…the crate."* at ~0:25 (≤0.5 s). No music, no stings.

> **The rhythmic tell:** the per-wing thump inside the bearing loop gives the silence a *pulse*. Line each
> of the three crate creaks up with a thump so the ear registers "past it again… past it again… past it
> again." It is a countdown with no numbers.

## 4. Complete SFX hit list

| Time | SFX | Level | Purpose |
|---|---|---|---|
| 0:00 | `SFX_door_bearing_v1` (*fast*) | **-9** | C1 — first sound, over no music, already spinning |
| 0:01.5 | `SFX_ting_v1` | -14 | C1b — the arrow reads |
| 0:03 | `SFX_door_bearing_v1` (*slow*) | -16 | C2 — the door at rest, nudged |
| **0:04** | **`SFX_crate_wedge_v1`** | **-17 (unremarkable)** | **C2 — SEED B. The crate wedged across the compartment. Audible, not highlighted** |
| 0:05 | `SFX_button_v1` "pfft" | -16 | C2 — the sneer |
| 0:06–0:11 | `SFX_door_bearing_v1` (*medium*) | -14 | C3 — steady rotation |
| 0:07 | `SFX_footstep_v1` (driving) ×2 | -15 | C3 — his push |
| **0:09** | **`SFX_door_bearing_v1`** wing thump | **-13** | **C3 — the first pass of the inside opening. Mark it clearly; the ear needs the reference** |
| 0:10 | `SFX_glass_tap_v1` | -16 | C3 — gesturing at PIP through the glass |
| 0:11.5 / 0:13 / 0:14.5 | `SFX_shove_v1` ×3 rising | -11 | C4 — three progressively bigger shoves |
| 0:11–0:15 | `SFX_door_bearing_v1` (*fast*) | -12 | C4 — accelerating |
| 0:15 | `SFX_button_v1` fanfare stab | -12 | C4 — vanity punctuation |
| 0:16 | *(music cuts — no new SFX; the bearing becomes exposed)* | — | C5 — the turn by subtraction |
| **0:16–0:27** | **`SFX_door_bearing_v1`** (*relentless*) | **-12** | C5→C6 — inside the silence, with periodic wing thumps |
| **0:22 / 0:24 / 0:26** | **`SFX_crate_creak_v1` ×3** | **-15** | **C6 — inside the silence, aligned to wing thumps. The pass-by countdown** |
| **0:29** | **`SFX_door_thunk_v1`** | **-6 — loudest in the video** | **C7 — the compartment arrives at the pavement. One firm, final, deflating thunk** |
| 0:29 | `SFX_scratch_v1` | -11 | C7 — reversal punctuation |
| 0:30 | `SFX_crate_wedge_v1` | -14 | C7 — the crate, still wedged, arriving with him |
| 0:31 | `SFX_door_still_v1` | -16 | C8 — PIP holds the door stationary. **The bearing stops for the first time in the episode** |
| 0:32 | `SFX_button_v1` ding | -12 | C8 — series close |

## 5. Loudness / delivery
- Integrated **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- Duck BGM ~5 dB under VO1–VO5; release into the silence. **Never duck the bearing** — it is doing the storytelling from 0:16.
- **Protected sounds:** the **0:04 crate wedge** (the seed) and the **three 0:22–0:26 creaks**, which must sit clear of the wing thumps rather than on top of them.
- **Loudest, in order:** 0:29 door thunk (-6) → 0:00 bearing (-9) → 0:11–0:15 shoves (-11). ~3 dB headroom before the thunk.
- **The mix decision that carries the episode:** the bearing must have a **periodic wing thump** inside its loop. Without that pulse the silence is just a hum; with it, the listener can count the revolutions and feel him missing the exit three times. Set the thump interval to match the rendered rotation speed exactly, or the audio and the picture will drift apart in the most noticeable eleven seconds of the video.
- Never compress the silence up.
- Shorts play muted by default: confirm the wedged crate and the three pass-bys carry the story with audio off.

## 6. Sourcing & signature
- Original or royalty-free/licensed only. **No sounds of impact against a person, no pinch, no alarm.**
- Reused: `SFX_crate_wedge_v1` (v20), `SFX_footstep_v1` (v22), `SFX_ting_v1`, `SFX_scratch_v1`, `SFX_button_v1`, narrator voice.
- **Signature-sound principle:** v18 jug · v19 plank · v20 cart · v21 pressure · v22 water height · v23 powder. **v24's signature is the bearing**, and it is the most economical in the series: **one recording at four speeds** — `slow → medium → fast → relentless` — with the payoff being a single `SFX_door_thunk_v1`. The inversion is the last sound before the button: `SFX_door_still_v1`, the bearing **stopping**, which happens only when PIP puts a hand on it. The machine he spent the whole episode driving is quieted instantly by the person who never pushed it.
