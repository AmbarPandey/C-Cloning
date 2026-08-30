# v20 — BGM, SFX & Audio Reference ("The Inspection") · **SHORTS**

> Prescriptive cue sheet. §2 gives the layer stack per time range; §4 lists every hit with timecode and
> level. Locks to `01-video-script.md`. **Mute-first.**

## 1. Assets

**Music**
| ID | Description | Used |
|---|---|---|
| `MUS_depot_bed_v1` | House cue, bureaucratic variant — plucky bass, clipped woodblock, a marching pizzicato lead, ~122 BPM, major. A woodblock tick per item added to the cart | 0:01.5–0:16 |
| `MUS_depot_stinger_v1` | Bright official hit that deflates into a hollow descending slide | 0:27 |
| `MUS_depot_resolve_v1` | Main melody once through, slow, warm | 0:29–0:32 |

**SFX**
| ID | Description |
|---|---|
| **`SFX_cart_rattle_v1`** | **Signature, stage 1** — a loaded cart rolling. Three weights: light / medium / heavy |
| **`SFX_crate_thud_v1`** | **Signature, stage 2** — a crate landing on a stack |
| **`SFX_crate_wedge_v1`** | **Signature, stage 3** — a crate compressing into a tight opening; strain rises |
| **`SFX_cart_hollow_v1`** | **Signature, stage 4 (the inversion)** — the same cart, now **empty**, rattling light and tinny |
| `SFX_cart_roll_v1` | A clean unobstructed roll (PIP's) |
| `SFX_cart_strain_v1` | Forcing a cart through a tight gap |
| `SFX_stamp_thump_v1` | The tick stamp coming down — heavy, official, satisfying |
| `SFX_stamp_settle_v1` | The stamp arm settling back on its post |
| `SFX_crate_creak_v1` · `SFX_crate_free_v1` | The wedged crate creaking; then lifted free |
| `SFX_ting_v1` · `SFX_scratch_v1` · `SFX_button_v1` | Reused series set |
| `SFX_amb_depot_v1` | Very low depot ambience |

## 2. ⭐ Exact cue sheet

`BGM` · `SFX` · `VO` · `AMB` (`SFX_amb_depot_v1`, 0:02→0:32)

| # | Time | Layer stack | BGM | Notes |
|---|---|---|---|---|
| 1 | **0:00–0:01.5** | **SFX + VO only** | **none** | Cold payoff. **No music.** One straining `SFX_crate_wedge_v1` |
| 2 | **0:01.5–0:02** | **BGM + SFX** | `MUS_depot_bed_v1` **enters on the cut** (~-16 dB) | The rule arrives with the music |
| 3 | **0:02–0:06** | **BGM + SFX + VO + AMB** | bed (full, ~-14 dB) | Rewind. **Protect the 0:04 crate thud** — it is the seed |
| 4 | **0:06–0:11** | **BGM + SFX + VO + AMB** | bed + woodblock layer 1 | Escalation 1 |
| 5 | **0:11–0:16** | **BGM + SFX + VO + AMB** | bed + woodblock layer 2 — **densest point** | Escalation 2 |
| 6 | **0:16** | **SFX + AMB only** | **cut mid-phrase** | Lands on the **stamp thump** — the loudest official sound and the last musical beat together |
| 7 | **0:16–0:27** | **SFX + AMB — SILENCE (11 s)** | **none** | Only 3 sounds permitted (§3). AMB ducked to ~-28 dB |
| 8 | **0:27–0:29** | **BGM + SFX + VO + AMB** | `MUS_depot_stinger_v1` slams in | The reveal |
| 9 | **0:29–0:32** | **BGM + SFX + VO + AMB** | `MUS_depot_resolve_v1` | Payoff + loop out |

```
0:00 (silence) ─┐
0:01.5          └─ BED ── +wb1 ── +wb2 (peak) ─┐ STAMP
0:16                              ╌╌ SILENCE ╌╌┘  0:27 ┌ stinger ┐ resolve ► 0:32
```

> **The best audio move in this episode:** the music cut and the **stamp thump** land on the same frame at
> 0:16. The most authoritative, most final sound in the video is also the moment the score abandons him.

## 3. The silence beat (0:16–0:27)

11 s of total musical silence, cut mid-phrase on the stamp thump.

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16–0:27 | `SFX_amb_depot_v1` | -28 | The depot stays alive without filling the space |
| 0:17 | `SFX_stamp_settle_v1` | -18 | The stamp arm settling. Officialdom, finished |
| **~0:24** | **`SFX_crate_creak_v1`** (single) | **-15** | **The tell.** One creak from behind him — the only information in the window, and it comes from the direction the camera is pulling toward |
| ~0:26 | `SFX_button_v1` tick | -18 | One anticipation beat |

No VO except an optional whispered *"…the crate."* at ~0:25 (≤0.5 s). No music, no stings.

> Deliberately the sparsest silence in the batch — three sounds. v20's tension is **visual** (the frame
> widening), so the audio's job is to stay out of the way and place exactly one clue behind his shoulder.

## 4. Complete SFX hit list

| Time | SFX | Level | Purpose |
|---|---|---|---|
| 0:00 | `SFX_crate_wedge_v1` | **-8** | C1 — first sound, over no music, already straining |
| 0:01.5 | `SFX_ting_v1` | -14 | C1b — the tick reads |
| 0:03 | `SFX_cart_rattle_v1` (light) | -15 | C2 — PIP's modest cart |
| **0:04** | **`SFX_crate_thud_v1`** | **-16 (unremarkable)** | **C2 — SEED B. The crate goes on top. Audible, not highlighted** |
| 0:05 | `SFX_button_v1` "pfft" | -16 | C2 — CHIEF's sneer |
| 0:07 | `SFX_cart_roll_v1` (clean) | -14 | C3 — PIP's cart passing through |
| 0:08 | `SFX_ting_v1` (soft) | -16 | C3 — PIP clears the slot |
| 0:09 | `SFX_crate_thud_v1` | -14 | C3 — CHIEF adds another |
| 0:12 | `SFX_cart_strain_v1` | -11 | C4 — forcing the cart |
| 0:13.5 | `SFX_cart_rattle_v1` (heavy) | -12 | C4 — overloaded roll |
| 0:14.5 | `SFX_crate_wedge_v1` (first, low) | -17 | C4 — the crate catching. Quiet on purpose |
| 0:15 | `SFX_button_v1` fanfare stab | -12 | C4 — vanity punctuation |
| **0:16** | **`SFX_stamp_thump_v1`** | **-7** | **C5 — the tick stamped. Music cuts on this exact frame** |
| 0:17 | `SFX_stamp_settle_v1` | -18 | C5 — inside the silence |
| **0:24** | **`SFX_crate_creak_v1`** | **-15** | **C6 — inside the silence. The single clue** |
| 0:26 | `SFX_button_v1` tick | -18 | C6 — anticipation |
| 0:27 | `SFX_crate_creak_v1` (longer) | -12 | C7 — the reveal |
| **0:29** | **`SFX_cart_hollow_v1`** | **-6 — loudest in the video** | **C7 — the empty cart. Light, tinny, humiliating. The signature inverted** |
| 0:29 | `SFX_scratch_v1` | -11 | C7 — reversal punctuation |
| 0:31 | `SFX_crate_free_v1` | -14 | C8 — PIP lifts the crate out |
| 0:32 | `SFX_button_v1` ding | -12 | C8 — series close |

## 5. Loudness / delivery
- Integrated **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- Duck BGM ~5 dB under VO1–VO5; release into the silence.
- **Protected sounds:** the **0:04 crate thud** (the seed) and the **0:24 creak** (the only clue in the silence). Neither may be masked.
- **Loudest, in order:** 0:29 hollow rattle (-6) → 0:16 stamp (-7) → 0:00 wedge (-8). ~3 dB headroom before each.
- **The critical mix judgement:** the loudest sound in the episode is an *absence* — a cart with nothing in it. Do not let it read as a small sound just because it is a light one. Give the hollow rattle presence and length so the ear registers **empty** as an event.
- Never compress the silence up.
- Shorts play muted by default: confirm the fit/no-fit diagram and the empty cart carry the story with audio off.

## 6. Sourcing & signature
- Original or royalty-free/licensed only.
- Reused: `SFX_ting_v1`, `SFX_scratch_v1`, `SFX_button_v1`, `SFX_crate_thud_v1` (from v19), narrator voice.
- **Signature-sound principle:** v18 the jug, v19 the plank. **v20's signature is the cart** — four states, `rattle → thud → wedge → HOLLOW`. The inversion is the most conceptual in the series so far: the first three states are the sound of *accumulation*, and the payoff is the same object sounding **empty**. He earns the loudest, most official sound in the video at 0:16 and is answered by the emptiest one at 0:29.
