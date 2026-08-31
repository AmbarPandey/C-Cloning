# v27 — BGM, SFX & Audio Reference ("The Chock") · **SHORTS**

> Prescriptive cue sheet. §2 gives the layer stack per time range; §4 lists every hit with timecode and
> level. Locks to `01-video-script.md`. **Mute-first.**

## 1. Assets

**Music**
| ID | Description | Used |
|---|---|---|
| `MUS_market_bed_v1` | House cue, street-market variant — plucky bass, hand percussion, a bright accordion-flavoured lead, ~120 BPM, major. **A rising pitch step per fruit added to the stack** — the melody climbs as the crate does | 0:01.5–0:16 |
| `MUS_market_stinger_v1` | Bright hit that deflates into a **descending run**, mirroring the fruit going downhill | 0:27 |
| `MUS_market_resolve_v1` | Main melody once through, slow, warm, coming to rest | 0:29–0:32 |

**SFX**
| ID | Description |
|---|---|
| **`SFX_chock_slide_v1`** | **Signature, stage 1** — a wedge sliding into place under a crate. Short, dry, *reassuring* |
| **`SFX_crate_creak_v1`** | **Signature, stage 2** — a crate flexing on an inadequate prop. Pitch **rises** with load |
| **`SFX_chock_shift_v1`** | **Signature, stage 3** — the wedge losing grip a hair at a time. Tiny, gritty, almost missable |
| **`SFX_fruit_roll_v1`** | **Signature, stage 4 (the payoff)** — many round fruit rolling downhill on stone, **receding into the distance** |
| `SFX_chock_pull_v1` | The wedge yanked out from the downhill edge |
| `SFX_chock_give_v1` | The wedge finally sliding clear |
| `SFX_crate_tip_v1` | A crate dropping off its prop onto the slope |
| `SFX_fruit_set_v1` | One round fruit placed onto a stack |
| `SFX_fruit_shift_v1` | One fruit rolling a few inches on top of a mound |
| `SFX_tick_stamp_v1` | The stallholder's tick stamped on a docket |
| `SFX_ting_v1` · `SFX_scratch_v1` · `SFX_button_v1` | Reused series set |
| `SFX_amb_market_v1` | Very low market ambience |

> **`SFX_chock_slide_v1` and `SFX_chock_pull_v1` are the same object making opposite sounds** — one seating,
> one leaving. Record them as a matched pair. PIP's version is heard at 0:03 and CHIEF's at 0:04, back to
> back, so the audience is handed the right answer and the wrong answer inside one second.

## 2. ⭐ Exact cue sheet

`BGM` · `SFX` · `VO` · `AMB` (`SFX_amb_market_v1`, 0:02→0:32)

| # | Time | Layer stack | BGM | Notes |
|---|---|---|---|---|
| 1 | **0:00–0:01.5** | **SFX + VO only** | **none** | Cold payoff. **No music.** `SFX_fruit_roll_v1` — three rounds accelerating away |
| 2 | **0:01.5–0:02** | **BGM + SFX** | `MUS_market_bed_v1` **enters on the cut** (~-16 dB) | The rule arrives with the music |
| 3 | **0:02–0:06** | **BGM + SFX + VO + AMB** | bed (full, ~-14 dB) | Rewind. **Protect the 0:03/0:04 chock pair** — they are the seed |
| 4 | **0:06–0:11** | **BGM + SFX + VO + AMB** | bed, **melody steps up per fruit** | Escalation 1 |
| 5 | **0:11–0:16** | **BGM + SFX + VO + AMB** | bed, **highest pitch, densest point** | Escalation 2 |
| 6 | **0:16** | **SFX + AMB only** | **cut mid-phrase** | Lands on the frame the tick is stamped |
| 7 | **0:16–0:27** | **SFX + AMB — SILENCE (11 s)** | **none** | Only 3 sounds permitted (§3). AMB ducked to ~-28 dB |
| 8 | **0:27–0:29** | **BGM + SFX + VO + AMB** | `MUS_market_stinger_v1` slams in, **descending** | The chock gives |
| 9 | **0:29–0:32** | **BGM + SFX + VO + AMB** | `MUS_market_resolve_v1` | Payoff + loop out |

```
0:00 (silence, fruit already rolling) ─┐
0:01.5                                 └─ BED ── pitch+ ── pitch++ (peak) ─┐ TICK
0:16                                                        ╌╌ SILENCE ╌╌╌─┘  0:27 ┌ stinger↓ ┐ resolve ► 0:32
```

> **The music decision:** the melody **climbs a step with every fruit added**, and the stinger at 0:27 is a
> **descending run**. The arrangement goes up with the stack and comes down with the hill. It is the simplest
> possible mapping of pitch to altitude, and it means a listener who has muted the video and unmuted it at
> 0:27 still knows which direction things just went.

## 3. The silence beat (0:16–0:27)

11 s of total musical silence, cut mid-phrase on the tick stamp.

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16–0:27 | `SFX_amb_market_v1` | -28 | The market stays alive without filling the space |
| **0:22 / 0:24 / 0:26** | **`SFX_crate_creak_v1` ×3, pitch rising** | **-15** | **The countdown.** One creak per settle increment. Rising pitch = increasing strain |
| ~0:24 | `SFX_fruit_shift_v1` | -19 | One fruit moving a few inches on top of the mound |
| **~0:26** | **`SFX_chock_shift_v1`** | **-17** | **The tell.** The wedge losing grip. Tiny, gritty, and the last thing heard before the music returns |

No VO except an optional whispered *"…the chock."* at ~0:25 (≤0.5 s). No music, no stings.

> **The structure of this silence:** it is a **three-part rising creak with two small interruptions**, and
> the last of them is the wedge itself. The audience hears the fault announce itself in its own voice at
> 0:26, one second before it happens. That gap — knowing, and being one beat early — is the most
> reliable tension device in the whole series, and this is its cleanest use.

## 4. Complete SFX hit list

| Time | SFX | Level | Purpose |
|---|---|---|---|
| 0:00 | `SFX_fruit_roll_v1` (three rounds, accelerating away) | **-9** | C1 — first sound, over no music |
| 0:01.5 | `SFX_ting_v1` | -14 | C1b — the chock pictogram reads |
| **0:03** | **`SFX_chock_slide_v1`** | **-15** | **C2 — PIP seats his chock. The right answer, stated first** |
| **0:04** | **`SFX_chock_pull_v1`** | **-15 (matched level)** | **C2 — SEED B. CHIEF pulls his out. The wrong answer, one second later, at the same volume** |
| 0:04.5 | `SFX_fruit_set_v1` ×2 | -15 | C2 — PIP's two apples |
| 0:05 | `SFX_button_v1` "pfft" | -16 | C2 — the sneer |
| 0:07 / 0:08.5 / 0:10 | `SFX_fruit_set_v1` ×3 | -14 | C3 — the stack rising |
| 0:09 | `SFX_crate_creak_v1` (first, low pitch) | -19 | C3 — the prop taking load |
| **0:10.5** | **`SFX_chock_shift_v1`** | **-22 (very quiet)** | **C3 — the first hint. Should be almost missable on a first watch** |
| 0:11.5 / 0:13 / 0:14.5 | `SFX_fruit_set_v1` ×3 rising | -13 | C4 — the absurd mound |
| 0:13 / 0:15 | `SFX_crate_creak_v1` ×2 (rising pitch) | -17 | C4 — the lean worsening |
| 0:15 | `SFX_button_v1` fanfare stab | -12 | C4 — vanity punctuation |
| **0:16** | **`SFX_tick_stamp_v1`** | **-7** | **C5 — the tick stamped. Music cuts on this exact frame** |
| **0:22 / 0:24 / 0:26** | **`SFX_crate_creak_v1` ×3 (rising)** | **-15** | **C6 — inside the silence. The countdown** |
| 0:24 | `SFX_fruit_shift_v1` | -19 | C6 — inside the silence |
| **0:26** | **`SFX_chock_shift_v1`** | **-17** | **C6 — inside the silence. The fault in its own voice, one beat early** |
| 0:27 | `SFX_chock_give_v1` | -10 | C7 — the wedge slides clear |
| 0:27.5 | `SFX_crate_tip_v1` | -9 | C7 — the crate drops off its prop |
| **0:29** | **`SFX_fruit_roll_v1`** (mass, receding downhill) | **-6 — loudest in the video** | **C7 — the whole load going. Long, granular, and it must audibly travel AWAY** |
| 0:29 | `SFX_scratch_v1` | -11 | C7 — reversal punctuation |
| 0:31 | `SFX_fruit_set_v1` ×2 | -15 | C8 — PIP puts his two apples in CHIEF's crate |
| 0:31.5 | `SFX_chock_slide_v1` | -15 | C8 — the chock handed back and seated. **The signature returned to its first state** |
| 0:32 | `SFX_button_v1` ding | -12 | C8 — series close |

## 5. Loudness / delivery
- Integrated **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- Duck BGM ~5 dB under VO1–VO5; release into the silence.
- **Protected sounds:** the **0:03/0:04 chock pair** (they must be at *matched level* so the contrast is between the actions, not the mix) and the **0:26 chock shift**, the one clue in the silence.
- **Loudest, in order:** 0:29 fruit roll (-6) → 0:16 tick stamp (-7) → 0:27.5 crate tip (-9). ~3 dB headroom before the roll.
- **The mix judgement that carries the episode:** `SFX_fruit_roll_v1` at 0:29 must **audibly recede.** Pan it wide, roll off the highs progressively and let it run for a full two seconds — the joke is not that things fell over, it is that they are *still leaving*. If it lands as a single impact, the ending reads as a crash instead of a loss.
- **Keep the 0:10.5 chock shift near-inaudible.** It is the fair-play plant; if a first-time viewer consciously hears it, drop it another 3 dB. It only has to be findable on rewatch.
- Never compress the silence up.
- Shorts play muted by default: confirm the slope angle and the chock's position carry the story with audio off.

## 6. Sourcing & signature
- Original or royalty-free/licensed only. **No impact-against-person sounds, no trip, no breakage** — the fruit rolls away and nothing hits anyone.
- Reused: `SFX_ting_v1`, `SFX_scratch_v1`, `SFX_button_v1`, narrator voice.
- **Signature-sound principle:** v18 jug · v19 plank · v20 cart · v21 pressure · v22 water height · v23 powder · v24 bearing · v25 tile · v26 lap. **v27's signature is the chock** — four states, `slide → creak → shift → ROLL`. The inversion is the tidiest in the series: the episode's **first** signature sound is PIP seating his chock correctly (0:03) and its **last** is that same chock being seated again (0:31.5), this time by PIP on CHIEF's behalf. Everything in between is the sound of one small wedge being asked to do a job it was moved away from.
