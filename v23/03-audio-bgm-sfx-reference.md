# v23 — BGM, SFX & Audio Reference ("The Evidence") · **SHORTS**

> Prescriptive cue sheet. §2 gives the layer stack per time range; §4 lists every hit with timecode and
> level. Locks to `01-video-script.md`. **Mute-first.**

## 1. Assets

**Music**
| ID | Description | Used |
|---|---|---|
| `MUS_sleuth_bed_A_v1` | **Reused from v5** — investigative cue: pizzicato strings, light woodblock, walking upright bass, ~110 BPM, major, curious and comic | 0:01.5–0:16 |
| `MUS_sleuth_stinger_v1` | **Reused from v5** — bright comic hit souring into a deflating trombone fall | 0:27 |
| `MUS_sleuth_resolve_v1` | **Reused from v5** — main melody once through, slow, warm | 0:29–0:32 |

Deliberate reuse: v5 and v23 are both `SC6` investigations, so they share the detective bed. This is a
**series cue for a premise type**, and it means a returning viewer recognises the genre in one bar.

**SFX**
| ID | Description |
|---|---|
| **`SFX_powder_tap_v1`** | **Signature, stage 1** — a pinch of powder tapped out. Small, dry, precise |
| **`SFX_powder_puff_v1`** | **Signature, stage 2** — a brush-load of powder released. Three sizes |
| **`SFX_powder_press_v1`** | **Signature, stage 3** — a glove pressing into powder and lifting |
| **`SFX_powder_settle_v1`** | **Signature, stage 4 (the payoff)** — a whole room's powder settling. Long, soft, almost nothing |
| `SFX_glove_creak_v1` | Latex glove flexing — the sound of the culprit, heard throughout |
| `SFX_card_flick_v1` | The comparison card raised and turned |
| `SFX_jar_scrape_v1` · `SFX_jar_set_v1` | The jar dragged from under the shelf; then set back in its ring |
| `SFX_ting_v1` · `SFX_scratch_v1` · `SFX_button_v1` | Reused series set |
| `SFX_amb_room_v1` | Very low interior ambience (reused from v5) |

> **`SFX_glove_creak_v1` is the tell, and it is in the mix from 0:03.** The answer is audible for
> twenty-four seconds before it is visible. That is the audio half of `TM3`.

## 2. ⭐ Exact cue sheet

`BGM` · `SFX` · `VO` · `AMB` (`SFX_amb_room_v1`, 0:02→0:32)

| # | Time | Layer stack | BGM | Notes |
|---|---|---|---|---|
| 1 | **0:00–0:01.5** | **SFX + VO only** | **none** | Cold payoff. **No music.** One `SFX_powder_press_v1` |
| 2 | **0:01.5–0:02** | **BGM + SFX** | `MUS_sleuth_bed_A_v1` **enters on the cut** (~-16 dB) | The card arrives with the music |
| 3 | **0:02–0:06** | **BGM + SFX + VO + AMB** | bed (full, ~-14 dB) | Rewind. **Protect the 0:03 glove creak** — it is the seed |
| 4 | **0:06–0:11** | **BGM + SFX + VO + AMB** | bed + woodblock layer 1 | Escalation 1 |
| 5 | **0:11–0:16** | **BGM + SFX + VO + AMB** | bed + woodblock layer 2 — **densest point** | Escalation 2 |
| 6 | **0:16** | **SFX + AMB only** | **cut mid-phrase** | Lands on the frame the card and print go overhead |
| 7 | **0:16–0:27** | **SFX + AMB — SILENCE (11 s)** | **none** | Only 3 sounds permitted (§3). AMB ducked to ~-28 dB |
| 8 | **0:27–0:29** | **BGM + SFX + VO + AMB** | `MUS_sleuth_stinger_v1` slams in | The match |
| 9 | **0:29–0:32** | **BGM + SFX + VO + AMB** | `MUS_sleuth_resolve_v1` | Payoff + loop out |

```
0:00 (silence) ─┐
0:01.5          └─ BED ── +wb1 ── +wb2 (peak) ─┐
0:16                              ╌╌ SILENCE ╌╌┘  0:27 ┌ stinger ┐ resolve ► 0:32
```

## 3. The silence beat (0:16–0:27)

11 s of musical silence, cut mid-phrase on the overhead hold. **The quietest silence in the batch** — the
episode's payoff sound is powder settling, so the window has to be genuinely still to make room for it.

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16–0:27 | `SFX_amb_room_v1` | -28 | The room stays alive without filling the space |
| **0:18 / 0:21 / 0:24** | **`SFX_powder_settle_v1` ×3, each softer** | **-18 → -22 → -26** | **A countdown that fades.** The only descending escalation in the series — the room going quiet is what finally lets him hear his own glove |
| **~0:26** | **`SFX_glove_creak_v1`** (single, close) | **-15** | **The tell, now unmasked.** It has been in the mix since 0:03; here it is the loudest thing in the room |

No VO except an optional whispered *"…his own."* at ~0:25 (≤0.5 s). No music, no stings.

> **The inversion is structural:** in every other episode the silence gets *louder* as the payoff arms. In
> v23 it gets *quieter*, and the clue is revealed by subtraction — the powder stops falling, so the glove
> becomes audible. He is undone by the room going still.

## 4. Complete SFX hit list

| Time | SFX | Level | Purpose |
|---|---|---|---|
| 0:00 | `SFX_powder_press_v1` | **-9** | C1 — first sound, over no music |
| 0:01.5 | `SFX_ting_v1` | -14 | C1b — the card reads |
| 0:03 | `SFX_powder_tap_v1` | -14 | C2 — the first pinch |
| **0:03.5** | **`SFX_glove_creak_v1`** | **-19 (unremarkable)** | **C2 — SEED B. The tell enters the mix and never leaves** |
| 0:05 | `SFX_button_v1` "pfft" | -16 | C2 — the sneer |
| 0:07 | `SFX_powder_puff_v1` (S) | -14 | C3 — dusting |
| 0:08 | `SFX_card_flick_v1` | -15 | C3 — the card raised to compare |
| 0:10 | `SFX_powder_puff_v1` (M) | -13 | C3 — more powder |
| 0:11.5 / 0:13 / 0:14.5 | `SFX_powder_puff_v1` (L) ×3 rising | -11 | C4 — the whiteout |
| 0:12 / 0:14 | `SFX_glove_creak_v1` ×2 | -17 | C4 — every surface he touches |
| 0:15 | `SFX_button_v1` fanfare stab | -12 | C4 — vanity punctuation |
| 0:16 | *(music cuts — no new SFX)* | — | C5 — the turn by subtraction |
| **0:18 / 0:21 / 0:24** | **`SFX_powder_settle_v1` ×3, descending** | **-18 / -22 / -26** | **C6 — inside the silence. The fading countdown** |
| **0:26** | **`SFX_glove_creak_v1`** | **-15** | **C6 — inside the silence. The tell, unmasked** |
| **0:29** | **`SFX_glove_creak_v1`** (long, loud) | **-7 — loudest in the video** | **C7 — the glove turned over. The signature's own sound convicting him** |
| 0:29 | `SFX_scratch_v1` | -11 | C7 — reversal punctuation |
| 0:30 | `SFX_jar_scrape_v1` | -14 | C7 — PIP drags the jar out from under the shelf |
| 0:31 | `SFX_jar_set_v1` | -14 | C8 — the jar back in its ring |
| 0:32 | `SFX_button_v1` ding | -12 | C8 — series close |

## 5. Loudness / delivery
- Integrated **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- Duck BGM ~5 dB under VO1–VO5; release into the silence.
- **Protected sounds:** the **0:03.5 glove creak** (the seed — it must be *present but unremarkable*, and if it is inaudible the fair-play contract breaks) and the **0:26 creak** where the same sound becomes the loudest thing in a quiet room.
- **Loudest, in order:** 0:29 glove creak (-7) → 0:00 powder press (-9) → 0:11–0:15 puffs (-11).
- **The unusual mix judgement here:** the loudest sound in the video is the **same asset** as one of the quietest. `SFX_glove_creak_v1` appears at -19 (seed), -17 (escalation), -15 (unmasked) and -7 (payoff). Use one recording at four levels rather than four variants — the recognition is the point, and a listener should feel they have heard it before without being able to say when.
- **Do not fill the 0:16–0:27 window.** It is the quietest passage in the series by design.
- Shorts play muted by default: confirm the three matching treads in C6 carry the story with audio off.

## 6. Sourcing & signature
- Original or royalty-free/licensed only. **Bloodless `SC6`:** no violence, menace, weapon, alarm, siren or restraint sounds anywhere.
- Reused: the whole v5 sleuth music family, `SFX_ting_v1`, `SFX_scratch_v1`, `SFX_button_v1`, `SFX_amb_room_v1`, narrator voice.
- **Signature-sound principle:** v18 jug · v19 plank · v20 cart · v21 pressure · v22 water height.
  **v23's signature is powder** — four states, `tap → puff → press → SETTLE`. But the real trick is a
  **second, hidden signature running underneath it**: the glove creak, planted at -19 dB in the third
  second and escalated only by *unmasking*, never by performance. The powder escalates and then fades to
  nothing; what's left is the sound that was always there.
