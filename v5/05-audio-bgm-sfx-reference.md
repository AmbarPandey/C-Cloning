# v5 — BGM, SFX & Audio Reference ("The Case of the Missing Pie") · **LONG FORM**

> The complete audio map for v5, synced to the master timeline in `01-video-script.md`. This file is
> **prescriptive, not advisory**: §2 is an exact cue sheet stating which layers are playing during every
> time range, and §4 lists every single SFX hit at its exact timecode. Drop these onto the timeline as
> written and the mix is done.
> **Mute-first principle:** audio *amplifies*; it never *carries*. The video reads with sound off.

---

## 1. Asset list (build/licence these once, then reuse)

### Music
| ID | Description | Used |
|---|---|---|
| `MUS_sleuth_bed_A_v1` | **Main investigative bed.** Playful pizzicato strings + light woodblock + walking upright bass, ~110 BPM, major, curious and comic. The "detective at work" theme | 0:03–0:44 |
| `MUS_sleuth_bed_B_v1` | **Driving variant** of the same theme — same melody, add low brass + snare pulse + faster woodblock, ~124 BPM, minor-leaning. Escalation for the case against PIP | 0:44–1:08 |
| `MUS_sleuth_stinger_v1` | **Reveal stinger** — a bright comic "ta-da" brass hit that immediately sours into a deflating trombone fall | 1:18 |
| `MUS_sleuth_resolve_v1` | **Warm resolve tail** — the main theme's melody once through, slow, warm, major, resolving | 1:22–1:30 |

> **Series continuity:** `MUS_sleuth_bed_A/B` are new for v5 but must be built from the **same
> instrumentation family** as v1's `MUS_comedy_bed_v1` (light percussion, plucky bass, no lyrics) so the
> channel keeps one sonic identity across formats. A and B must share a melody so the shift at 0:44 reads
> as the *same* story getting more serious, not a different song.

### Stings & SFX
| ID | Description |
|---|---|
| `SFX_sting_gasp_v1` | Sharp orchestral stab for a discovery/gasp (3 sizes: S/M/L) |
| `SFX_lens_whoosh_v1` | Comic whoosh as the magnifier swings up |
| `SFX_lens_ting_v1` | Small bright glass *ting* on close inspection |
| `SFX_notebook_v1` | Pencil scratch / crossing-out |
| `SFX_deflate_v1` | Little descending "wah" of disappointment |
| `SFX_tape_v1` | Tape-measure zip + snap |
| `SFX_pin_thunk_v1` | Corkboard pin push |
| `SFX_string_twang_v1` | Taut string pluck / sag |
| `SFX_brass_pomp_v1` | Short pompous brass stab |
| `SFX_stamp_whoosh_v1` | Rising whoosh as the giant stamp lifts |
| **`SFX_stamp_v1`** | **The series stamp thud — reused from v1** |
| `SFX_creak_wood_v1` | Wooden table creak (the tilt) |
| `SFX_drip_v1` | Single small drip of filling |
| `SFX_scratch_v1` | Record-scratch (reused) |
| `SFX_plate_clink_v1` | Ceramic plate clink |
| `SFX_dog_snore_v1` · `SFX_dog_yawn_v1` · `SFX_dog_whine_v1` · `SFX_dog_munch_v1` | BUD (wordless) |
| `SFX_cat_meow_v1` · `SFX_cat_lick_v1` | MITTENS (wordless, one flat meow only) |
| `SFX_crowd_murmur_v1` · `SFX_crowd_inhale_v1` · `SFX_crowd_applaud_v1` | Market crowd, always low and diffuse |
| `SFX_crumb_crunch_v1` | PIP's biscuit |
| `SFX_button_v1` | The series button/ding set (reused) |

---

## 2. ⭐ EXACT CUE SHEET — what is playing, when

**Layer key:** `BGM` = music bed · `SFX` = effects · `VO` = narration · `AMB` = market ambience bed
(a very low, constant `SFX_crowd_murmur_v1` that runs 0:03→1:30 **except** where noted).

| # | Time range | Layer stack | BGM playing | Notes |
|---|---|---|---|---|
| 1 | **0:00–0:01** | **SFX only** | — *(no music)* | Dead-cold open. One second of near-silence on the empty plate. **Do not put music here** — the absence is the hook |
| 2 | **0:01–0:03** | **SFX + VO** | — | The gasp sting lands. Music has still not started |
| 3 | **0:03–0:12** | **BGM + SFX + VO + AMB** | `MUS_sleuth_bed_A_v1` (enters on the downbeat at 0:03, ~-18 dB, building) | Market ambience enters here and runs to the end |
| 4 | **0:12–0:23** | **BGM + SFX + VO + AMB** | `MUS_sleuth_bed_A_v1` (full, ~-14 dB) | Suspect 1 cycle |
| 5 | **0:23–0:28** | **BGM + SFX + AMB** *(no VO)* | `MUS_sleuth_bed_A_v1` | Micro-payoff 1 — visual comedy, deliberately unnarrated |
| 6 | **0:28–0:39** | **BGM + SFX + VO + AMB** | `MUS_sleuth_bed_A_v1` (swells ~+2 dB at 0:28 for the pattern interrupt) | Suspect 2 cycle |
| 7 | **0:39–0:44** | **BGM + SFX + AMB** *(no VO)* | `MUS_sleuth_bed_A_v1` | Micro-payoff 2 — unnarrated |
| 8 | **0:44–0:50** | **BGM + SFX + VO + AMB** | **CROSSFADE A→B over 1 s at 0:44.** `MUS_sleuth_bed_B_v1` (driving) | The tonal turn. Same melody, more menace |
| 9 | **0:50–0:56** | **BGM + SFX + VO + AMB** | `MUS_sleuth_bed_B_v1` (building) | The absurd case |
| 10 | **0:56–1:02** | **BGM + SFX + VO + AMB** | `MUS_sleuth_bed_B_v1` (**highest tension point of the video** — full brass + snare) | Peak injustice |
| 11 | **1:02–1:08** | **BGM (thinning) + SFX + AMB** *(no VO)* | `MUS_sleuth_bed_B_v1` — **instruments drop out one at a time** as each character turns to look: brass out ~1:03, snare out ~1:05, bass out ~1:06, woodblock out ~1:07 | The most important music cue in the video. The arrangement *un-builds* in sync with the on-screen turn |
| 12 | **1:08–1:18** | **SFX only — SILENCE** | **— NONE. TOTAL MUSICAL SILENCE (10 s)** | Only 3 sounds permitted (see §3). Even the ambience drops to a whisper (~-30 dB) |
| 13 | **1:18–1:22** | **BGM + SFX + VO + AMB** | `MUS_sleuth_stinger_v1` (SLAM in on the reveal frame) | The ta-da that sours |
| 14 | **1:22–1:30** | **BGM + SFX + VO + AMB** | `MUS_sleuth_resolve_v1` (warm, resolving) | Payoff + loop out |

**Visual summary of the music shape:**
```
0:00 ─┐                                                        ┌── stinger ──┐
      │ (silence)                                              │             │ resolve
0:03  └── BED A (curious) ──────┐                              │             └────────► 1:30
0:44                            └── BED B (driving) ──┐        │
1:02                                 (un-builds) ─────┘        │
1:08                                          ╌╌ SILENCE ╌╌╌╌╌╌┘
                                                   (10 s)     1:18
```

---

## 3. The silence beat (1:08–1:18) — the single most important audio move

A **10-second total musical silence**, beginning the instant CHIEF lowers the stamp and starts to follow
PIP's finger. It is the payoff for the entire 68 seconds before it.

**Only these three sounds are permitted inside it:**

| Time | Sound | Level | Why |
|---|---|---|---|
| 1:08–1:18 | `SFX_crowd_murmur_v1` | **~-30 dB** (barely there) | Keeps the scene alive without filling the space |
| ~1:12 | `SFX_creak_wood_v1` (single) | -18 dB | The tilted table announces itself — the *cause* speaking up |
| ~1:15 | `SFX_drip_v1` (single) | -20 dB | One drop of filling. The sound of the answer |

- **No VO** in this window except an optional whispered *"…oh no."* at ~1:16, ≤0.7 s.
- **No music, no stings, no animal sounds, no footsteps.** Resist the urge to score the reveal — the
  silence *is* the score.
- The creak and the drip are the two clues delivered in audio. Together they tell a listener with their
  eyes closed exactly what happened, which is the point: **the answer was always available.**

---

## 4. Complete SFX hit list (every effect, exact timecode)

| Time | SFX | Level | Shot / purpose |
|---|---|---|---|
| 0:01 | `SFX_sting_gasp_v1` (L) | -8 | S1 — CHIEF's gasp. The first sound in the video |
| 0:05 | `SFX_creak_wood_v1` | -16 | **S2 — SEED A. The ledger tips the table.** Mix it audible but unremarkable |
| 0:05 | wooden *clunk* (`SFX_creak_wood_v1` layer) | -14 | S2 — the ledger landing against the leg |
| 0:06 | soft *thud* (`SFX_creak_wood_v1` low layer) | -16 | **S2 — SEED B. The evidence box set on the ground** |
| 0:08 | `SFX_lens_whoosh_v1` | -12 | S3 — magnifier swings up |
| 0:09 | `SFX_notebook_v1` (flick) | -16 | S3 — notebook opened |
| 0:13 | `SFX_sting_gasp_v1` (M) | -10 | S4 — accusation 1 |
| 0:14 | `SFX_dog_snore_v1` | -18 | S4 — BUD asleep |
| 0:18 | `SFX_lens_ting_v1` | -14 | S5 — magnifier on the muzzle |
| 0:20 | `SFX_string_twang_v1` | -14 | S5 — the lead pulled taut |
| 0:22 | `SFX_deflate_v1` | -12 | S5 — CHIEF deflating |
| 0:24 | `SFX_notebook_v1` (scratch) | -12 | S6 — crossing off suspect 1 |
| 0:25 | `SFX_dog_yawn_v1` | -12 | S6 — BUD's deadpan yawn (**the laugh**) |
| 0:27 | `SFX_button_v1` (tiny boop) | -18 | S6 — button on the beat |
| 0:29 | `SFX_sting_gasp_v1` (L) | -8 | S7 — accusation 2, bigger |
| 0:31 | `SFX_cat_meow_v1` | -14 | S7 — one flat meow. **The only cat vocalisation in the video** |
| 0:34 | `SFX_tape_v1` (zip) | -12 | S8 — tape measure out |
| 0:37 | `SFX_tape_v1` (snap) | -10 | S8 — tape snaps back |
| 0:38 | `SFX_button_v1` ("nope" honk) | -14 | S8 — the size-mismatch gag |
| 0:40 | `SFX_notebook_v1` (scratch) | -12 | S9 — crossing off suspect 2 |
| **0:41** | **`SFX_drip_v1`** | **-24 (deliberately low)** | **S9 — seed glimpse. Should be almost missable** |
| 0:42 | `SFX_cat_lick_v1` | -18 | S9 — MITTENS indifferent |
| 0:46 | `SFX_crumb_crunch_v1` | -16 | S10 — PIP's biscuit |
| 0:47 | `SFX_sting_gasp_v1` (XL) | -6 | S10 — the biggest gasp. Loudest sting in the video |
| 0:51 / 0:52 / 0:53 | `SFX_pin_thunk_v1` ×3 | -12 | S11 — three pins into the corkboard |
| 0:54 | `SFX_string_twang_v1` | -14 | S11 — red string pulled |
| 0:55 | `SFX_brass_pomp_v1` | -10 | S11 — pompous punctuation |
| 0:57 | `SFX_stamp_whoosh_v1` | -10 | S12 — the giant stamp lifts |
| 0:59 | `SFX_dog_whine_v1` | -16 | S12 — BUD's tiny whine |
| 1:00 | `SFX_crowd_inhale_v1` | -18 | S12 — the crowd holds its breath |
| — | *(1:02–1:08: no new SFX — the music un-builds instead)* | | S13 |
| **1:12** | **`SFX_creak_wood_v1`** | **-18** | **S14 — inside the silence. The cause speaks** |
| **1:15** | **`SFX_drip_v1`** | **-20** | **S14 — inside the silence. The answer** |
| 1:19 | `SFX_scratch_v1` | -10 | S15 — record-scratch under the stinger |
| 1:20 | `SFX_stamp_v1` | -8 | **S15 — the series stamp thud, landing on his own boot. The v1 callback** |
| 1:21 | `SFX_string_twang_v1` (sag) | -16 | S15 — the corkboard strings go slack |
| 1:26 | `SFX_plate_clink_v1` | -14 | S16 — the pie returned to the plate |
| 1:27 | `SFX_dog_munch_v1` | -14 | S16 — BUD gets his slice |
| 1:28 | `SFX_crowd_applaud_v1` | -20 | S16 — the crowd applauds PIP, low and warm |
| 1:29 | `SFX_button_v1` (ding) | -12 | S16 — series close button |

---

## 5. Loudness / delivery (platform-ready)
- Integrated target **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- **Duck BGM ~5 dB under VO** for VO1–VO8; release fully in the unnarrated payoff windows (0:23–0:28, 0:39–0:44) so the visual gags own those beats.
- VO peaks ≈ -12 to -10 dBFS, ~3 dB above the ducked bed.
- **Never compress the silence up.** 1:08–1:18 must genuinely read as quiet on a phone. If your loudness normalisation is lifting it, cut the ambience further rather than adding anything.
- **The two protected sounds** are the **1:12 creak** and the **1:15 drip**. Nothing may mask them, and nothing else may occupy that window.
- **The loudest moments, in order:** the 0:47 XL gasp sting → the 1:18 reveal stinger → the 1:20 stamp thud. Leave ~2 dB headroom before each.
- The 0:41 drip is intentionally **the quietest deliberate sound in the video** (-24 dB). It should register subconsciously on first watch and obviously on rewatch. If test viewers consciously notice it first time, drop it another 3 dB.
- Long form is often watched with sound **on** and on speakers, unlike Shorts — so check the mix on laptop speakers as well as a phone.

---

## 6. Sourcing notes
- Use original or royalty-free/licensed audio only (advertiser-safe, monetization-safe).
- Reuse from earlier episodes: **`SFX_stamp_v1`** (v1 — the callback that makes the ending land),
  `SFX_scratch_v1`, `SFX_button_v1` set, `SFX_creak_wood_v1` (v3's creak family), `SFX_drip_v1`, and the
  **narrator voice**.
- New and worth locking for future mystery/long-form episodes: `MUS_sleuth_bed_A/B_v1`,
  `MUS_sleuth_stinger_v1`, `MUS_sleuth_resolve_v1`, `SFX_sting_gasp_v1` (S/M/L/XL), `SFX_lens_whoosh_v1`,
  `SFX_lens_ting_v1`, `SFX_tape_v1`, `SFX_pin_thunk_v1`, `SFX_stamp_whoosh_v1`.
- **Signature-sound principle (series-wide):** v1 = the stamp · v2 = the booster · v3 = the block clack ·
  v4 = the panel slam. **v5's signature sound is the `SFX_sting_gasp_v1` discovery sting** — it escalates
  four times (S/M/L/XL at 0:01, 0:13, 0:29, 0:47), each one a bigger, more confident accusation. Then it
  is **inverted by its own absence**: at the actual moment of discovery (1:18) there is no gasp sting at
  all, because the discovery isn't his. The escalation is answered by silence where the sound should be.
  That is the cleanest inversion in the series so far.
