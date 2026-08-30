# v21 — BGM, SFX & Audio Reference ("The Upgrade") · **SHORTS**

> Prescriptive cue sheet. §2 gives the layer stack per time range; §4 lists every hit with timecode and
> level. Locks to `01-video-script.md`. **Mute-first.**

## 1. Assets

**Music**
| ID | Description | Used |
|---|---|---|
| `MUS_fairground_bed_v1` | **Reused from v6** — bright fairground cue, plucky bass, glockenspiel lead, ~126 BPM, major. Here a glockenspiel note is locked to **each pump stroke**, so the tune is played by his greed | 0:01.5–0:16 |
| `MUS_fairground_stinger_v1` | **Reused from v6** — bright hit deflating into a descending slide | 0:27 |
| `MUS_fairground_resolve_v1` | **Reused from v6** — main melody once through, warm | 0:29–0:32 |

Deliberate reuse: v6 and v21 share the fairground arena, so they share the bed. The *sound design* is what distinguishes them.

**SFX**
| ID | Description |
|---|---|
| **`SFX_pump_v1`** | **Signature, stage 1** — one hand-pump stroke. Three speeds: slow / rhythmic / fast |
| **`SFX_needle_tick_v1`** | **Signature, stage 2** — the gauge needle stepping up one increment. Pitched, and the pitch rises as it climbs |
| **`SFX_rubber_creak_v1`** | **Signature, stage 3** — latex under tension, pitch rising with strain |
| **`SFX_rubber_stretch_v1`** | **Signature, stage 4 (the payoff)** — one long, slow, low stretching groan as the last feature smooths away. **Not a pop** |
| `SFX_blob_wobble_v1` | A large soft mass wobbling — dull, rounded, faintly comic |
| `SFX_valve_click_v1` · `SFX_valve_release_v1` | The valve jammed shut; then sighing open at the end |
| `SFX_ting_v1` · `SFX_scratch_v1` · `SFX_button_v1` | Reused series set |
| `SFX_amb_fair_v1` | Very low fairground ambience (reused from v6) |

> **There is no burst or pop asset in this episode, by design.** If one appears in the mix, the twist has
> been rendered wrong.

## 2. ⭐ Exact cue sheet

`BGM` · `SFX` · `VO` · `AMB` (`SFX_amb_fair_v1`, 0:02→0:32)

| # | Time | Layer stack | BGM | Notes |
|---|---|---|---|---|
| 1 | **0:00–0:01.5** | **SFX + VO only** | **none** | Cold payoff. **No music.** One rising `SFX_rubber_creak_v1` |
| 2 | **0:01.5–0:02** | **BGM + SFX** | `MUS_fairground_bed_v1` **enters on the cut** (~-16 dB) | The rule arrives with the music |
| 3 | **0:02–0:06** | **BGM + SFX + VO + AMB** | bed (full, ~-14 dB) | Rewind. **Protect the 0:04 valve click** — it is the seed |
| 4 | **0:06–0:11** | **BGM + SFX + VO + AMB** | bed + glockenspiel per pump stroke | Escalation 1. The music climbs with the needle |
| 5 | **0:11–0:16** | **BGM + SFX + VO + AMB** | bed, **fastest and brightest** — glock notes now above the melody's normal range | Escalation 2. The arrangement itself sounds over-inflated |
| 6 | **0:16** | **SFX + AMB only** | **cut mid-phrase** | Lands on the frame he hoists the lion |
| 7 | **0:16–0:27** | **SFX + AMB — SILENCE (11 s)** | **none** | Only 3 sounds permitted (§3). **The pump does not stop.** AMB ducked to ~-28 dB |
| 8 | **0:27–0:29** | **BGM + SFX + VO + AMB** | `MUS_fairground_stinger_v1` slams in | The blob |
| 9 | **0:29–0:32** | **BGM + SFX + VO + AMB** | `MUS_fairground_resolve_v1` | Payoff + loop out |

```
0:00 (silence) ─┐
0:01.5          └─ BED ── +glock ── fastest/brightest ─┐
0:16                                    ╌╌ SILENCE ╌╌╌┘  ← but the PUMP keeps running
0:27                                                     ┌ stinger ┐ resolve ► 0:32
```

## 3. The silence beat (0:16–0:27)

11 s of musical silence, cut mid-phrase on the hoist. **This is a *filled* silence** — the second in the
series after v7 — because the pump is the thing loading the payoff and it must be heard doing it.

| Time | Sound | Level | Why |
|---|---|---|---|
| **0:16–0:27** | **`SFX_pump_v1`** (relentless, unchanged) | **-12 — the loudest element in the window** | **The valve is jammed, so nothing stops.** A mechanical, indifferent sound loading a payoff the character can't see |
| 0:16–0:27 | `SFX_amb_fair_v1` | -28 | The fair stays alive without filling the space |
| **0:22 / 0:24 / 0:26** | **`SFX_rubber_creak_v1` ×3, pitch rising** | **-15** | **The countdown.** One creak per morph stage — the audible progress bar of the deformation |

No VO except an optional whispered *"…the valve."* at ~0:25 (≤0.5 s). No music, no stings.

> The relentless pump is the whole beat: the picture shows a man holding a magnificent sculpture aloft
> while the sound tells you it is still being over-filled and nobody is going to stop it.

## 4. Complete SFX hit list

| Time | SFX | Level | Purpose |
|---|---|---|---|
| 0:00 | `SFX_rubber_creak_v1` | **-9** | C1 — first sound, over no music, already under tension |
| 0:01.5 | `SFX_ting_v1` | -14 | C1b — the max line reads |
| 0:03 | `SFX_pump_v1` (slow) ×2 | -14 | C2 — the first strokes |
| **0:04** | **`SFX_valve_click_v1`** | **-17 (unremarkable)** | **C2 — SEED B. The valve jammed shut. Audible, not highlighted** |
| 0:05 | `SFX_button_v1` "pfft" | -16 | C2 — the sneer |
| 0:07–0:10 | `SFX_pump_v1` (rhythmic) | -13 | C3 — steady inflation |
| 0:07 / 0:08.5 / 0:10 | `SFX_needle_tick_v1` ×3, rising pitch | -15 | C3 — the needle climbing |
| 0:11–0:15 | `SFX_pump_v1` (fast) | -11 | C4 — two-handed pumping |
| **0:13** | **`SFX_needle_tick_v1`** (highest pitch) | **-13** | **C4 — the needle crosses the `ALERT_RED` max line** |
| 0:14 | `SFX_rubber_creak_v1` (enters, low) | -19 | C4 — strain begins |
| 0:15 | `SFX_button_v1` fanfare stab | -12 | C4 — vanity punctuation |
| 0:16 | *(music cuts — no new SFX; the pump becomes exposed)* | — | C5 — the turn by subtraction |
| **0:16–0:27** | **`SFX_pump_v1`** (continuous) | **-12** | C5→C6 — inside the silence, relentless |
| **0:22 / 0:24 / 0:26** | **`SFX_rubber_creak_v1` ×3** | **-15** | **C6 — inside the silence. One per morph stage** |
| **0:29** | **`SFX_rubber_stretch_v1`** | **-7 — loudest in the video** | **C7 — one long slow low groan as the last feature goes. NOT a pop** |
| 0:29 | `SFX_scratch_v1` | -11 | C7 — reversal punctuation |
| 0:30 | `SFX_blob_wobble_v1` | -14 | C7 — the featureless mass settling |
| 0:31 | `SFX_valve_release_v1` | -16 | C8 — the valve sighs open at last |
| 0:32 | `SFX_button_v1` ding | -12 | C8 — series close |

## 5. Loudness / delivery
- Integrated **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- Duck BGM ~5 dB under VO1–VO5; release into the silence. **Never duck the pump** — it is doing the storytelling from 0:16.
- **Protected sounds:** the **0:04 valve click** (the seed) and the **three 0:22–0:26 creaks**.
- **Loudest, in order:** 0:29 stretch (-7) → 0:00 creak (-9) → 0:11–0:15 pump (-11). ~3 dB headroom before the stretch.
- **The single most important mix judgement in this episode:** the payoff is a **long low groan, not a transient.** Every other episode in the series peaks on an impact (splash, crash, snap, gloop). v21 peaks on a *duration*. Do not shorten it, do not add a transient to it, and do not let a limiter clamp its sustain — the joke is that the loudest moment in the video has no bang in it at all.
- Never compress the silence up.
- Shorts play muted by default: confirm the gauge needle and the six morph states carry the story with audio off.

## 6. Sourcing & signature
- Original or royalty-free/licensed only. **No burst/pop asset may exist in this project folder.**
- Reused: the whole v6 fairground music family, `SFX_ting_v1`, `SFX_scratch_v1`, `SFX_button_v1`, `SFX_amb_fair_v1`, narrator voice.
- **Signature-sound principle:** v18 jug · v19 plank · v20 cart. **v21's signature is pressure** — four states, `pump → needle tick → creak → STRETCH`. The inversion is the quietest in the series and the most on-thesis: after four escalating stages of *forcing air in*, the final sound is the valve **sighing open** — the release he jammed shut, finally arriving one beat too late to save him.
