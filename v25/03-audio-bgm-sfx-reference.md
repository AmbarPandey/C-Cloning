# v25 — BGM, SFX & Audio Reference ("The Tie-Breaker") · **SHORTS**

> Prescriptive cue sheet. §2 gives the layer stack per time range; §4 lists every hit with timecode and
> level. Locks to `01-video-script.md`. **Mute-first.**

## 1. Assets

**Music**
| ID | Description | Used |
|---|---|---|
| `MUS_contest_bed_v1` | House cue, contest variant — plucky bass, marimba, light snare, ~120 BPM, major. **A marimba note per tile placed**, so the build is scored by the building | 0:01.5–0:16 |
| `MUS_contest_stinger_v1` | Bright hit deflating into a descending marimba run | 0:27 |
| `MUS_contest_resolve_v1` | Main melody once through, slow, warm | 0:29–0:32 |

**SFX**
| ID | Description |
|---|---|
| **`SFX_tile_set_v1`** | **Signature, stage 1** — one tile stood upright on a hard surface. Small, dry, precise |
| **`SFX_tile_topple_v1`** | **Signature, stage 2** — one tile falling and striking the next |
| **`SFX_tile_run_v1`** | **Signature, stage 3** — a chain running. A rolling clatter whose **rate is constant** and whose **pitch shifts with the tile token** (see below) |
| **`SFX_marker_fall_v1`** | **Signature, stage 4 (the payoff)** — the prize marker toppling. One clean wooden knock with a short tail |
| `SFX_ramp_place_v1` | The ramp section set down |
| `SFX_ting_v1` · `SFX_scratch_v1` · `SFX_button_v1` | Reused series set |
| `SFX_amb_hall_v1` | Very low interior hall ambience |

> **The pitch rule — the cleverest thing in this mix.** `SFX_tile_run_v1` needs **two variants a third
> apart**: a **lower** one for CHIEF's `PAPER` run and a **higher** one for PIP's `POP_TEAL` run. The
> two-token rule in the visuals is mirrored in the audio, so at 0:29 the listener hears the chain
> **change pitch** at the crossing point. That is the twist, delivered to the ear, with no words: his run
> becomes her run. A viewer with their eyes shut still gets the joke.

## 2. ⭐ Exact cue sheet

`BGM` · `SFX` · `VO` · `AMB` (`SFX_amb_hall_v1`, 0:02→0:32)

| # | Time | Layer stack | BGM | Notes |
|---|---|---|---|---|
| 1 | **0:00–0:01.5** | **SFX + VO only** | **none** | Cold payoff. **No music.** One suspended `SFX_tile_topple_v1` — held, contact not yet made |
| 2 | **0:01.5–0:02** | **BGM + SFX** | `MUS_contest_bed_v1` **enters on the cut** (~-16 dB) | The rule arrives with the music |
| 3 | **0:02–0:06** | **BGM + SFX + VO + AMB** | bed (full, ~-14 dB), marimba per tile | Rewind. **Protect the two crossing-point tiles at 0:04** — they are the seed |
| 4 | **0:06–0:11** | **BGM + SFX + VO + AMB** | bed + marimba layer 1 | Escalation 1 |
| 5 | **0:11–0:16** | **BGM + SFX + VO + AMB** | bed + marimba layer 2 — **densest point** | Escalation 2 |
| 6 | **0:16** | **SFX + AMB only** | **cut mid-phrase on the flick** | The music stops the instant he starts the chain |
| 7 | **0:16–0:27** | **SFX + AMB — SILENCE (11 s)** | **none** | Only 2 sounds permitted (§3). **The run does not stop.** AMB ducked to ~-28 dB |
| 8 | **0:27–0:29** | **BGM + SFX + VO + AMB** | `MUS_contest_stinger_v1` slams in | The crossing |
| 9 | **0:29–0:32** | **BGM + SFX + VO + AMB** | `MUS_contest_resolve_v1` | Payoff + loop out |

```
0:00 (silence) ─┐
0:01.5          └─ BED ── +mar1 ── +mar2 (peak) ─┐ FLICK
0:16                                ╌╌ SILENCE ╌╌┘  ← but the RUN keeps clattering
0:27                                                ┌ stinger ┐ resolve ► 0:32
```

> **Why the music cuts on the flick rather than after the win:** the moment he sets the chain off is the
> moment he stops having any control over it. Removing the score exactly there hands the next eleven
> seconds entirely to a mechanical process nobody can stop — which is precisely what the picture is doing.

## 3. The silence beat (0:16–0:27)

11 s of musical silence, cut mid-phrase on the flick. **A filled silence** — fourth in the series — because
the running chain is the payoff arming itself and must be heard doing it.

| Time | Sound | Level | Why |
|---|---|---|---|
| **0:16–0:27** | **`SFX_tile_run_v1`** (LOW variant — CHIEF's `PAPER` run) | **-12 — the loudest element in the window** | **The chain, unstoppable.** A constant-rate clatter. Because the rate never changes, the listener tracks *distance*, not urgency |
| 0:16–0:27 | `SFX_amb_hall_v1` | -28 | The hall stays alive without filling the space |
| ~0:19 | `SFX_marker_fall_v1` | -14 | The prize toppling for CHIEF — his win, heard inside the silence. **This is the false floor** |

No VO except an optional whispered *"…it kept going."* at ~0:25 (≤0.6 s). No music, no stings.

> **This silence contains the win.** The marker falls for CHIEF at 0:19, inside the quiet — so the audience
> hears him succeed and then hears the clatter *carry on afterwards.* That gap between "he won" and "why is
> it still going" is the whole eleven seconds, and it is the sparsest, most purely mechanical tension in the
> batch: two sounds and a room.

## 4. Complete SFX hit list

| Time | SFX | Level | Purpose |
|---|---|---|---|
| 0:00 | `SFX_tile_topple_v1` (suspended) | **-10** | C1 — first sound, over no music. Held, contact pending |
| 0:01.5 | `SFX_ting_v1` | -14 | C1b — the tick reads |
| 0:02–0:05 | `SFX_tile_set_v1` ×4 (even, HIGH pitch — PIP) | -15 | C2 — PIP's four tiles |
| 0:02–0:06 | `SFX_tile_set_v1` ×6 (fast, LOW pitch — CHIEF) | -14 | C2 — CHIEF's grand arc |
| **0:04** | **`SFX_tile_set_v1` ×2 (LOW)** | **-16 (unremarkable)** | **C2 — SEED B. The two tiles at the crossing point. Audible, not highlighted** |
| 0:05 | `SFX_button_v1` "pfft" | -16 | C2 — the sneer |
| 0:07–0:10 | `SFX_tile_set_v1` (rapid, LOW) | -13 | C3 — the spiral |
| 0:09 | `SFX_ramp_place_v1` | -14 | C3 — the ramp |
| 0:10 | `SFX_button_v1` chuckle | -15 | C3 — laughing at four tiles |
| 0:11.5 / 0:13 / 0:14.5 | `SFX_tile_set_v1` ×3 rising (LOW) | -12 | C4 — the fan and final sections |
| 0:15 | `SFX_button_v1` fanfare stab | -12 | C4 — vanity punctuation |
| **0:16** | **`SFX_tile_topple_v1`** (the flick) | **-10** | **C5 — he sets it off. Music cuts on this exact frame** |
| **0:16–0:27** | **`SFX_tile_run_v1` (LOW)** | **-12** | C5→C6 — inside the silence, constant rate |
| **0:19** | **`SFX_marker_fall_v1`** | **-14** | **C5 — the prize falls for CHIEF, inside the silence. The false floor** |
| **0:29** | **`SFX_tile_run_v1` switches LOW → HIGH** | **-6 — loudest in the video** | **C7 — the crossing. The chain audibly changes pitch: his run becomes PIP's** |
| 0:29 | `SFX_tile_topple_v1` | -9 | C7 — the crossing contact |
| 0:29 | `SFX_scratch_v1` | -11 | C7 — reversal punctuation |
| **0:30** | **`SFX_marker_fall_v1`** | **-8** | **C7 — the prize falls again, this time onto PIP's side. Same asset, second time, opposite outcome** |
| 0:31 | `SFX_tile_set_v1` (single, LOW) | -15 | C8 — PIP stands one of CHIEF's tiles back up |
| 0:32 | `SFX_button_v1` ding | -12 | C8 — series close |

## 5. Loudness / delivery
- Integrated **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- Duck BGM ~5 dB under VO1–VO5; release into the silence. **Never duck the run** — it is doing the storytelling from 0:16.
- **Protected sounds:** the **two 0:04 crossing tiles** (the seed) and the **0:29 pitch switch**, which must be unmistakable.
- **Loudest, in order:** 0:29 run pitch-switch (-6) → 0:30 second marker fall (-8) → 0:29 crossing topple (-9). ~3 dB headroom before the switch.
- **The two mix decisions that carry this episode:**
  1. **`SFX_marker_fall_v1` is used twice** — at 0:19 for CHIEF and at 0:30 for PIP. Same recording, same level relationship, opposite outcome. Do not substitute a different asset for the second one; the repetition *is* the irony.
  2. **The pitch switch at 0:29 must survive a phone speaker.** A third is a musical interval, not a volume change, so support it with a small timbre shift (CHIEF's run slightly duller, PIP's slightly brighter) in case the interval alone is lost on a small driver.
- Never compress the silence up.
- Shorts play muted by default: confirm the two tile tokens and the crossing point carry the story with audio off.

## 6. Sourcing & signature
- Original or royalty-free/licensed only. Light tiles on a table — **no breakage or impact-against-person sounds anywhere.**
- Reused: `SFX_ting_v1`, `SFX_scratch_v1`, `SFX_button_v1`, narrator voice.
- **Signature-sound principle:** v18 jug · v19 plank · v20 cart · v21 pressure · v22 water height · v23 powder · v24 bearing. **v25's signature is the tile** — four states, `set → topple → run → MARKER FALL`. The inversion is the most literal in the whole series: the signature **changes pitch mid-payoff**, from his token to PIP's, at the crossing point he built himself. The last sound before the button is one tile being **stood back up** — the signature returned to its first state, by the person who won.
