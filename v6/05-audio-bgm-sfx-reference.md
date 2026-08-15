# v6 — BGM, SFX & Audio Reference ("One Sweet, One Coin") · **SHORTS**

> The complete audio map for v6, synced to the master timeline in `01-video-script.md`. This file is
> **prescriptive, not advisory**: §2 is an exact cue sheet stating which layers are playing during every
> time range, and §4 lists every SFX hit at its exact timecode and mix level. Drop these onto the timeline
> as written and the mix is done.
> **Mute-first principle:** audio *amplifies*; it never *carries*. The video reads with sound off.

---

## 1. Asset list

### Music
| ID | Description | Used |
|---|---|---|
| `MUS_fairground_bed_v1` | **Main bed.** A bright fairground/carousel variant of the house cue — plucky bass, light glockenspiel or calliope-flavoured lead, hand percussion, ~126 BPM, major, cheerful and a little greedy. Accelerates subtly with the scooping | 0:00–0:16 |
| `MUS_fairground_stinger_v1` | **Reveal stinger** — a bright hit that immediately deflates into a descending comic slide | 0:27 |
| `MUS_fairground_resolve_v1` | **Warm resolve tail** — the main melody once through, slow and warm, resolving | 0:29–0:32 |

> **Series continuity:** built from the same instrumentation family as v1's `MUS_comedy_bed_v1` (light
> percussion, plucky bass, no lyrics) so the channel keeps one sonic identity. The fairground colour is a
> *variant*, not a different band. Lock a **glockenspiel note to each scoop** so the music is literally
> played by his greed — the tempo and pitch climb together across 0:06–0:16.

### SFX
| ID | Description |
|---|---|
| **`SFX_sweetclatter_v1`** | **The signature sound** — a handful of hard sweets clattering into a cup. Needs 4 sizes: S (one scoop) / M / L / XL (two-handed shovel) |
| **`SFX_coin_tink_v1`** | A single small coin landing on a metal pan. Delicate, lonely, precise |
| `SFX_purse_thud_v1` | The heavy ostentatious purse slamming onto the counter |
| `SFX_purse_rattle_v1` | Coins shifting inside — deliberately **thin and sparse** |
| `SFX_purse_flap_v1` | An empty leather purse being shaken and turned inside out |
| `SFX_scale_groan_v1` | Brass balance scale beams settling — slow metallic creak |
| `SFX_scale_crash_v1` | A loaded pan hitting the bottom of its travel |
| `SFX_scale_balance_ting_v1` | The clean, satisfying *ting* of two pans coming perfectly level |
| `SFX_cup_clack_v1` | A stacked paper/tin cup being pulled off the pile |
| `SFX_sweet_patter_v1` | Loose sweets tumbling and settling on a counter |
| `SFX_reverse_clatter_v1` | Sweets being scooped rapidly *back* — the clatter, reversed in feel |
| `SFX_scratch_v1` | Record-scratch (reused) |
| `SFX_dog_munch_v1` · `SFX_dog_tailwag_v1` | BUD (wordless) |
| `SFX_fair_amb_v1` | Very low fairground ambience — distant crowd, a far-off organ |
| `SFX_button_v1` | The series button/ding set (reused) |

---

## 2. ⭐ EXACT CUE SHEET — what is playing, when

**Layer key:** `BGM` = music bed · `SFX` = effects · `VO` = narration · `AMB` = fairground ambience bed
(a very low, constant `SFX_fair_amb_v1` running 0:00→0:32 **except** where noted).

| # | Time range | Layer stack | BGM playing | Notes |
|---|---|---|---|---|
| 1 | **0:00–0:02** | **BGM + SFX + VO + AMB** | `MUS_fairground_bed_v1` (enters on frame 1, ~-16 dB) | Unlike v5's cold open, v6 starts **with** music — the cheerful bed makes his greed feel fun before it turns |
| 2 | **0:02–0:06** | **BGM + SFX + VO + AMB** | `MUS_fairground_bed_v1` (full, ~-14 dB) | Setup. **Protect the 0:04 purse rattle** — it is the seed |
| 3 | **0:06–0:11** | **BGM + SFX + VO + AMB** | `MUS_fairground_bed_v1` — **tempo and pitch begin climbing**; a glockenspiel note per scoop | Escalation 1. The music is played by his scooping |
| 4 | **0:11–0:16** | **BGM + SFX + AMB** *(VO ends 0:15)* | `MUS_fairground_bed_v1` — **highest, fastest, brightest point of the whole cue** | Escalation 2. Let the clatter and the music run wild together |
| 5 | **0:16–0:17** | **SFX only** — *music cuts mid-phrase on the SLAM* | **— NONE from 0:16** | The slam and the cut land on the same frame |
| 6 | **0:17–0:27** | **SFX only — SILENCE** | **— NONE. TOTAL MUSICAL SILENCE (11 s total from 0:16)** | Only 4 sounds permitted (see §3). Ambience drops to ~-30 dB |
| 7 | **0:27–0:29** | **BGM + SFX + VO + AMB** | `MUS_fairground_stinger_v1` (SLAM in on the first returned handful) | The bright hit that deflates |
| 8 | **0:29–0:32** | **BGM + SFX + VO + AMB** | `MUS_fairground_resolve_v1` (warm, resolving) | Payoff + loop out |

**Visual summary of the music shape:**
```
0:00 ── BED (cheerful) ──── climbing ──── FASTEST/BRIGHTEST ─┐
0:16                                                         │ (cut mid-phrase on the SLAM)
0:16                                          ╌╌╌ SILENCE ╌╌╌┘
                                                  (11 s)
0:27                                                         ┌── stinger ──┐
0:29                                                         │             └── resolve ──► 0:32
```

---

## 3. The silence beat (0:16–0:27) — the single most important audio move

An **11-second total musical silence**, cut **mid-phrase** on the exact frame the cup slams onto the pan.
It is the payoff for the escalation and the space in which the arithmetic lands.

**Only these four sounds are permitted inside it:**

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16–0:27 | `SFX_fair_amb_v1` | **~-30 dB** (barely there) | Keeps the fairground alive without filling the space |
| 0:17–0:22 | `SFX_scale_groan_v1` (slow, continuous) | -20 dB | The scale doing its arithmetic. Dread as a mechanical noise |
| **~0:23** | **`SFX_coin_tink_v1`** (single) | **-14 dB** | **The most important sound in the video.** One coin. After ten seconds of clattering abundance, a single tiny note |
| ~0:24 | `SFX_scale_crash_v1` | -12 dB | The sweets pan hitting the bottom — the verdict |
| ~0:26 | `SFX_purse_flap_v1` | -20 dB | He shakes an empty purse. The sound of nothing |

- **No VO** in this window except an optional whispered *"…one."* at ~0:25, ≤0.5 s.
- **No music, no stings.** The coin *tink* must arrive into total musical silence or the joke is lost.

> **The whole sound design of this episode is a volume joke:** ten seconds of loud, greedy, escalating
> clatter, answered by one small *tink*. Build the mix so that contrast is unmissable.

---

## 4. Complete SFX hit list (every effect, exact timecode)

| Time | SFX | Level | Clip / purpose |
|---|---|---|---|
| 0:00 | `SFX_button_v1` (strut boings ×2) | -18 | C1 — CHIEF's vain walk |
| 0:01 | `SFX_purse_thud_v1` | **-8** | C1 — the purse slams down. Heavy, confident, the sound of a man who thinks he's rich |
| 0:02 | `SFX_cup_clack_v1` | -14 | C1 — he seizes the largest cup |
| 0:03 | `SFX_sweetclatter_v1` (S) | -12 | C2 — first scoop |
| **0:04** | **`SFX_purse_rattle_v1`** | **-20 (deliberately thin)** | **C2 — SEED B. The purse falls open. Sparse, unremarkable, but there.** Should register subconsciously |
| 0:05 | `SFX_button_v1` (dismissive "pfft") | -16 | C2 — waving PIP off |
| 0:05 | `SFX_sweetclatter_v1` (S) | -12 | C2 — second scoop |
| 0:07 / 0:08.5 / 0:10 | `SFX_sweetclatter_v1` (M) ×3 | -11 | C3 — escalating scoops, each ~1 dB louder and a semitone higher |
| 0:09 | `SFX_sweet_patter_v1` | -16 | C3 — sweets settling on the pile |
| 0:11.5 / 0:13 / 0:14.5 | `SFX_sweetclatter_v1` (L→XL) ×3 | -9 | C4 — two-handed shovelling, the loudest clatters in the video |
| 0:13 | `SFX_sweet_patter_v1` | -14 | C4 — sweets spilling onto the counter |
| 0:15 | `SFX_button_v1` (proud fanfare stab) | -12 | C4 — vanity punctuation |
| **0:16** | **`SFX_scale_crash_v1` (impact of the slam)** | **-7** | **C5 — the cup slams onto the pan. Music cuts on this exact frame** |
| 0:17–0:22 | `SFX_scale_groan_v1` | -20 | C5→C6 — inside the silence. The scale settling |
| **0:23** | **`SFX_coin_tink_v1`** | **-14** | **C6 — inside the silence. ONE coin. The pivot of the whole episode** |
| 0:24 | `SFX_scale_crash_v1` | -12 | C6 — the sweets pan bottoms out |
| 0:26 | `SFX_purse_flap_v1` | -20 | C6 — the empty purse shaken out |
| 0:27 | `SFX_reverse_clatter_v1` (building) | -10 | C7 — sweets going frantically back |
| 0:28 | `SFX_scratch_v1` | -10 | C7 — reversal punctuation under the stinger |
| **0:30** | **`SFX_scale_balance_ting_v1`** | **-11** | **C7 — the pans come level. One sweet, one coin. Must read perfectly clean** |
| 0:31 | `SFX_sweetclatter_v1` (XL) | -12 | C8 — the whole mountain poured into BUD's cup |
| 0:31.5 | `SFX_dog_munch_v1` | -14 | C8 — BUD's reward |
| 0:32 | `SFX_button_v1` (ding) | -12 | C8 — series close button |

---

## 5. Loudness / delivery (platform-ready)
- Integrated target **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- **Duck BGM ~4–6 dB under VO** for VO1–VO6; release fully into the silence.
- VO peaks ≈ -12 to -10 dBFS, ~3 dB above the ducked bed.
- **The two protected sounds** are the **0:23 coin tink** and the **0:30 balance ting**. Nothing may mask either. Duck the stinger ~3 dB for ~200 ms around 0:30 so the ting sits in its own pocket.
- **The loudest moments, in order:** the 0:16 slam → the 0:01 purse thud → the 0:11–0:15 XL clatters. Leave ~2 dB headroom before the slam.
- The **0:04 purse rattle is intentionally the quietest deliberate sound** (-20 dB, thin and sparse). If test viewers consciously notice it first time, drop it another 3 dB — it should only be obvious on rewatch.
- **Never compress the silence up.** 0:16–0:27 must genuinely read as quiet on a phone at low volume.
- Shorts are watched **muted by default** — so verify one final time that the balance scale tells the whole story with the audio off.

---

## 6. Sourcing notes
- Use original or royalty-free/licensed audio only (advertiser-safe, monetization-safe).
- Reuse from earlier episodes: `SFX_scratch_v1`, `SFX_button_v1` set, `SFX_dog_munch_v1` (v5), and the **narrator voice**.
- New and worth locking for future stall/market/economy episodes: `MUS_fairground_bed_v1` (+ stinger and resolve), `SFX_sweetclatter_v1` (S/M/L/XL), `SFX_coin_tink_v1`, `SFX_purse_thud_v1`, `SFX_purse_rattle_v1`, `SFX_purse_flap_v1`, `SFX_scale_groan_v1`, `SFX_scale_crash_v1`, `SFX_scale_balance_ting_v1`, `SFX_reverse_clatter_v1`.
- **Signature-sound principle (series-wide):** v1 = the stamp · v2 = the booster · v3 = the block clack ·
  v4 = the panel slam · v5 = the discovery sting. **v6's signature sound is the sweet clatter** — it
  escalates four sizes (S→M→L→XL) across 0:03–0:15 as his greed grows, and is then **inverted by scale**:
  answered by a single `SFX_coin_tink_v1` at 0:23 and resolved by one delicate `ting` at 0:30. Loud
  abundance, defeated by one small precise note. Same principle as v4's slam→click, but here the
  inversion is *arithmetic* rather than *mechanical* — it's the sound of a number being smaller than he
  thought.
