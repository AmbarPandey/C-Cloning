# v18 — BGM, SFX & Audio Reference ("The Last Drop") · **SHORTS**

> Prescriptive cue sheet. §2 states which layers play in every time range; §4 lists every SFX hit with
> its exact timecode and mix level. Locks to the master timeline in `01-video-script.md`.
> **Mute-first:** audio amplifies, never carries.

## 1. Assets

**Music**
| ID | Description | Used |
|---|---|---|
| `MUS_kitchen_bed_v1` | House cue, domestic variant — plucky bass, light woodblock, marimba lead, ~118 BPM, major, cheerful. A woodblock tick per pour stage | 0:01.5–0:16 |
| `MUS_kitchen_stinger_v1` | Bright hit that deflates into a wet descending slide | 0:27 |
| `MUS_kitchen_resolve_v1` | Main melody once through, slow, warm, resolving | 0:29–0:32 |

Same instrumentation family as v1's `MUS_comedy_bed_v1` — a variant, not a different band.

**SFX**
| ID | Description |
|---|---|
| **`SFX_glug_v1`** | **Signature, stage 1** — one heavy hollow glug from a jug |
| **`SFX_pour_v1`** | **Signature, stage 2** — continuous pour, three intensities |
| **`SFX_spread_v1`** | **Signature, stage 3** — liquid creeping across a hard surface |
| **`SFX_splash_big_v1`** | **Signature, stage 4** — a full jug emptying onto a person |
| `SFX_drip_v1` | Single drop (reused from v5/v7) |
| `SFX_ceramic_shift_v1` | A stacked bowl sliding one increment |
| `SFX_ceramic_crash_v1` | A stack of light bowls going over — **dull and soft, never a sharp smash** |
| `SFX_bracket_clang_v1` | A metal shelf bracket taking a knock |
| `SFX_glass_slide_v1` | A full glass pushed across a counter |
| `SFX_ting_v1` | Small bright confirm (reused) |
| `SFX_scratch_v1` · `SFX_button_v1` | Reused series set |

## 2. ⭐ Exact cue sheet

`BGM` music · `SFX` effects · `VO` narration · `AMB` low room ambience (`SFX_amb_room_v1`, 0:02→0:32)

| # | Time | Layer stack | BGM | Notes |
|---|---|---|---|---|
| 1 | **0:00–0:01.5** | **SFX + VO only** | **none** | Cold payoff. **No music at all** — the silence is the hook. One glug, one pour start |
| 2 | **0:01.5–0:02** | **BGM + SFX** | `MUS_kitchen_bed_v1` **enters on the cut** (~-16 dB) | The diagram. Music arrives with the rule |
| 3 | **0:02–0:06** | **BGM + SFX + VO + AMB** | bed (full, ~-14 dB) | Rewind/setup. **Protect the 0:03 ceramic shift** — it is the seed |
| 4 | **0:06–0:11** | **BGM + SFX + VO + AMB** | bed + woodblock layer 1 | Escalation 1 |
| 5 | **0:11–0:16** | **BGM + SFX + VO + AMB** | bed + woodblock layer 2 — **brightest, densest point** | Escalation 2 |
| 6 | **0:16** | **SFX + AMB only** | **cut mid-phrase** | Lands on the frame the toast locks |
| 7 | **0:16–0:27** | **SFX + AMB — SILENCE (11 s)** | **none** | Only 4 sounds permitted (§3). AMB ducked to ~-28 dB |
| 8 | **0:27–0:29** | **BGM + SFX + VO + AMB** | `MUS_kitchen_stinger_v1` slams in | The chain fires |
| 9 | **0:29–0:32** | **BGM + SFX + VO + AMB** | `MUS_kitchen_resolve_v1` | Payoff + loop out |

```
0:00 (silence) ─┐
0:01.5          └─ BED ── +wb1 ── +wb2 (peak) ─┐
0:16                              ╌╌ SILENCE ╌╌┘   0:27 ┌ stinger ┐ resolve ► 0:32
```

## 3. The silence beat (0:16–0:27)

11 s of total musical silence, cut **mid-phrase** on the frame the toast locks.

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16–0:27 | `SFX_amb_room_v1` | -28 | Room stays alive without filling the space |
| 0:17–0:26 | `SFX_spread_v1` (continuous, very low) | -22 | **The creep.** The audience hears the puddle advancing |
| **0:22 / 0:24 / 0:26** | **`SFX_ceramic_shift_v1` ×3, rising** | **-16** | **The countdown.** Three slips, each higher — the audible progress bar |
| ~0:20 | `SFX_drip_v1` | -20 | One drop off the counter edge |

No VO except an optional whispered *"…and then the bowls."* at ~0:25 (≤0.7 s). No music, no stings.

> The three ceramic slips are the most important sounds in the episode: they tell the listener that a
> chain is arming while the picture shows a man toasting himself.

## 4. Complete SFX hit list

| Time | SFX | Level | Purpose |
|---|---|---|---|
| 0:00 | `SFX_glug_v1` | **-8** | C1 — first sound in the video, over no music |
| 0:00.5 | `SFX_pour_v1` (starts) | -12 | C1 — the column already falling |
| 0:01.5 | `SFX_ting_v1` | -14 | C1b — the arrow lands on the line |
| 0:03 | `SFX_pour_v1` (light) | -14 | C2 — PIP's careful pour |
| **0:03.5** | **`SFX_ceramic_shift_v1`** | **-18 (unremarkable)** | **C2 — SEED B. The stack knocked askew. Audible, not highlighted** |
| 0:04 | `SFX_button_v1` "pfft" | -16 | C2 — CHIEF gloating |
| 0:07 | `SFX_ting_v1` (soft) | -16 | C3 — PIP's glass meets its line |
| 0:08 | `SFX_pour_v1` (rising) | -12 | C3 — CHIEF pours past the line |
| 0:09 / 0:10 | `SFX_drip_v1` ×2 | -16 | C3 — first overflow reaching the counter |
| 0:12 / 0:13.5 / 0:15 | `SFX_spread_v1` ×3 | -14 | C4 — the three puddle stages |
| 0:15 | `SFX_button_v1` fanfare stab | -12 | C4 — vanity punctuation |
| 0:16 | *(music cuts — no new SFX; the spread becomes exposed)* | — | C5 — the turn is achieved by subtraction |
| 0:20 | `SFX_drip_v1` | -20 | C6 — inside the silence |
| **0:22 / 0:24 / 0:26** | **`SFX_ceramic_shift_v1` ×3** | **-16** | **C6 — inside the silence. The arming chain** |
| 0:25 | `SFX_button_v1` tick | -18 | C6 — one anticipation beat |
| 0:27 | `SFX_ceramic_crash_v1` | -10 | C7 — chain stage 1. **Dull and soft, never a sharp smash** |
| 0:28 | `SFX_bracket_clang_v1` | -10 | C7 — chain stage 2/3 |
| **0:29** | **`SFX_splash_big_v1`** | **-6 — loudest in the video** | **C7 — chain stage 4. The jug empties over him** |
| 0:29 | `SFX_scratch_v1` | -11 | C7 — reversal punctuation |
| 0:30.5 | `SFX_drip_v1` | -15 | C7 — one last drop off his cap brim |
| 0:31 | `SFX_glass_slide_v1` | -14 | C8 — PIP slides his glass over |
| 0:32 | `SFX_button_v1` ding | -12 | C8 — series close |

## 5. Loudness / delivery
- Integrated **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- Duck BGM ~5 dB under VO1–VO5; release into the silence.
- **Protected sounds:** the **0:03.5 seed shift** (if inaudible the fair-play contract breaks) and the **three 0:22–0:26 slips**. Nothing may mask them.
- **Loudest, in order:** 0:29 splash (-6) → 0:00 glug (-8) → 0:27 crash (-10). Leave ~3 dB headroom before the splash.
- Never compress the silence up — 0:16–0:27 must read quiet on a phone at low volume.
- Shorts are watched muted by default: confirm the puddle and the bowl lean tell the story with audio off.

## 6. Sourcing & signature
- Original or royalty-free/licensed only; advertiser-safe and monetization-safe.
- Reused: `SFX_drip_v1`, `SFX_ting_v1`, `SFX_scratch_v1`, `SFX_button_v1`, narrator voice.
- **Signature-sound principle:** v1 stamp · v2 booster · v3 block clack · v4 panel slam · v5 discovery sting · v6 sweet clatter · v7 water. **v18's signature is the jug** — four states, `glug → pour → spread → SPLASH`, mapping to the four acts. The inversion is **the ceramic slip**: a different, quieter object answers the pour, and it is what actually ends him. The final sound is one drip off his cap brim.
