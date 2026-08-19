# v7 — BGM, SFX & Audio Reference ("The Big One") · **SHORTS**

> The complete audio map for v7, synced to the master timeline in `01-video-script.md`. This file is
> **prescriptive, not advisory**: §2 is an exact cue sheet stating which layers are playing during every
> time range, and §4 lists every SFX hit at its exact timecode and mix level. Drop these onto the timeline
> as written and the mix is done.
> **Mute-first principle:** audio *amplifies*; it never *carries*. The video reads with sound off.

---

## 1. Asset list

### Music
| ID | Description | Used |
|---|---|---|
| `MUS_rainy_bed_v1` | **Main bed.** A light, jaunty "walking in the rain" variant of the house cue — plucky bass, soft brushed percussion, a cheerful clarinet or whistle lead, ~118 BPM, major. Builds in density as the rain intensifies | 0:00–0:16 |
| `MUS_rainy_stinger_v1` | **Reveal stinger** — a bright cymbal-led splash hit that immediately deflates into a soggy descending trombone slide | 0:27 |
| `MUS_rainy_resolve_v1` | **Warm resolve tail** — the main melody once through, slow, warm, major, with a gentle final cadence | 0:29–0:32 |

> **Series continuity:** built from the same instrumentation family as v1's `MUS_comedy_bed_v1` (light
> percussion, plucky bass, no lyrics). The rainy colour is a *variant*, not a different band.
> **Do this:** as the rain intensifies across 0:06–0:16, add percussion layers so the **weather and the
> arrangement thicken together** — the music should feel like it is getting wetter.

### SFX
| ID | Description |
|---|---|
| **`SFX_drip_v1`** | **The signature sound, stage 1** — a single clear water drop. Discrete, pitched, lonely |
| **`SFX_trickle_v1`** | **Signature stage 2** — a thin continuous run of water |
| **`SFX_pour_v1`** | **Signature stage 3** — a steady, heavy pour into a body of water. The dread engine |
| **`SFX_splash_big_v1`** | **Signature stage 4 (the payoff)** — one enormous volume of water dumping onto a person and pavement |
| `SFX_rain_light_v1` · `SFX_rain_med_v1` · `SFX_rain_heavy_v1` | Three rain ambience intensities, crossfaded in sequence |
| `SFX_umbrella_fwoomp_v1` | A large umbrella snapping open |
| `SFX_umbrella_pop_v1` | A small umbrella popping open |
| `SFX_fabric_strain_v1` | Taut canvas creaking under load — rising in pitch as it stretches |
| `SFX_umbrella_limp_v1` | A sodden, inverted umbrella flopping |
| `SFX_shove_oof_v1` | A small character being shoved aside (soft, comic, non-violent) |
| `SFX_step_back_v1` | One quiet footstep on wet pavement |
| `SFX_puddle_v1` | Feet settling into a shallow puddle |
| `SFX_scratch_v1` | Record-scratch (reused) |
| `SFX_button_v1` | The series button/ding set — includes the "pfft" and the fanfare stab (reused) |

---

## 2. ⭐ EXACT CUE SHEET — what is playing, when

**Layer key:** `BGM` = music bed · `SFX` = effects · `VO` = narration · `RAIN` = rain ambience bed
(crossfading through three intensities; runs 0:00→0:32 and **never fully stops**, including during the
musical silence — the rain is the world, not the score).

| # | Time range | Layer stack | BGM playing | RAIN intensity | Notes |
|---|---|---|---|---|---|
| 1 | **0:00–0:02** | **BGM + SFX + VO + RAIN** | `MUS_rainy_bed_v1` (enters frame 1, ~-17 dB) | `SFX_rain_light_v1` | First drops. **The single gutter drip must be audible here** — it is the seed |
| 2 | **0:02–0:06** | **BGM + SFX + VO + RAIN** | `MUS_rainy_bed_v1` (full, ~-14 dB) | `light` → `med` crossfade | Umbrella selection. Drip continues underneath |
| 3 | **0:06–0:11** | **BGM + SFX + VO + RAIN** | `MUS_rainy_bed_v1` — **percussion layer 1 added** | `SFX_rain_med_v1` | **The drip becomes a `trickle`** — signature stage 2. This is the sound of the trap loading |
| 4 | **0:11–0:16** | **BGM + SFX + RAIN** *(VO ends 0:15)* | `MUS_rainy_bed_v1` — **percussion layer 2 added; brightest, densest point of the cue** | `SFX_rain_heavy_v1` | **The trickle becomes a `pour`** — signature stage 3. Fabric strain enters underneath |
| 5 | **0:16** | **SFX + RAIN only** — *music cuts mid-phrase on the victory pose* | **— NONE from 0:16** | `heavy` | The cut lands on the frame he plants his pose |
| 6 | **0:16–0:27** | **SFX + RAIN only — MUSICAL SILENCE (11 s)** | **— NONE** | `heavy`, ducked to ~-24 dB | Only 4 sounds permitted (see §3). **The pour is now the loudest thing in the video** |
| 7 | **0:27–0:29** | **BGM + SFX + VO + RAIN** | `MUS_rainy_stinger_v1` (SLAM in on the tipping canopy) | `heavy` | Cymbal splash hit → soggy trombone fall |
| 8 | **0:29–0:32** | **BGM + SFX + VO + RAIN** | `MUS_rainy_resolve_v1` (warm, resolving) | `heavy` → `med` (easing off) | Payoff + loop out |

**Visual summary of the music shape:**
```
0:00 ── BED (jaunty) ── +perc1 ── +perc2 (densest) ─┐
0:16                                                │ (cut mid-phrase on the pose)
0:16                                 ╌╌╌ SILENCE ╌╌╌┘   ← but the POUR keeps running
                                        (11 s)
0:27                                                ┌── stinger ──┐
0:29                                                │             └── resolve ──► 0:32
```

> **The defining audio decision of this episode:** the rain and the pour **do not stop** during the musical
> silence. In v1–v6 the silence was near-total. Here it is filled with one relentless, mechanical sound —
> water pouring into a bucket the character can't see. That is far more unbearable than quiet, because the
> audience can *hear the payoff being loaded* in real time.

---

## 3. The silence beat (0:16–0:27) — the single most important audio move

An **11-second musical silence**, cut **mid-phrase** on the frame CHIEF plants his victory pose.

**Only these four sounds are permitted inside it:**

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16–0:27 | `SFX_rain_heavy_v1` | **~-24 dB** (ducked, present but pushed back) | The world keeps raining. Removing it entirely would feel artificial |
| **0:16–0:27** | **`SFX_pour_v1`** (continuous) | **-12 dB — the loudest element in the window** | **The trap loading.** A steady, indifferent pour into the canopy. This is the sound of the joke being built |
| 0:22–0:26 | `SFX_fabric_strain_v1` (rising in pitch) | -16 dB | The canopy at its limit. Pitch climbs as the fabric stretches — an audible countdown |
| ~0:25 | `SFX_step_back_v1` (single) | -20 dB | PIP quietly taking one step back. A tiny sound that tells you exactly what's coming |
| ~0:26 | `SFX_button_v1` (suspense tick) | -18 dB | One final beat of anticipation |

- **No VO** in this window except an optional whispered *"…he tried to say something."* at ~0:24, ≤0.8 s.
- **No music, no stings.** The pour and the fabric strain must own the space.

> **PIP's single step back (0:25) is the best sound in the video.** It is barely audible, it is the only
> thing PIP does, and it tells the listener that the person who was shoved aside now knows better than the
> person who shoved him. Mix it so an attentive viewer catches it.

---

## 4. Complete SFX hit list (every effect, exact timecode)

| Time | SFX | Level | Clip / purpose |
|---|---|---|---|
| 0:00 | `SFX_rain_light_v1` (enters) | -20 | C1 — first rain |
| **0:01** | **`SFX_drip_v1`** (single, clear) | **-14** | **C1 — SEED A. The gutter drip. Signature stage 1. Must be clearly audible** |
| 0:01 | `SFX_button_v1` (strut boings ×2) | -18 | C1 — CHIEF's vain walk |
| 0:02 | `SFX_shove_oof_v1` | -14 | C1 — PIP shoved aside (soft and comic, never harsh) |
| 0:03 | `SFX_umbrella_fwoomp_v1` | **-9** | C2 — the enormous umbrella snapping open. Big, satisfying, confident |
| 0:04 | `SFX_button_v1` (dismissive "pfft") | -16 | C2 — gloating down at PIP |
| 0:05 | `SFX_umbrella_pop_v1` | -15 | C2 — PIP's tiny umbrella. Deliberately modest next to the fwoomp |
| 0:05 | `SFX_drip_v1` ×2 | -15 | C2 — the gutter, still just dripping |
| **0:07** | **`SFX_trickle_v1`** (enters, continuous) | **-14** | **C3 — signature stage 2. The drip becomes a trickle as he steps into position** |
| 0:09 | `SFX_button_v1` (proud fanfare stab) | -13 | C3 — vanity punctuation |
| **0:12** | **`SFX_pour_v1`** (crossfades in over `trickle`) | **-13** | **C4 — signature stage 3. Now a steady pour into the canopy** |
| 0:13 | `SFX_fabric_strain_v1` (enters low) | -20 | C4 — the canopy beginning to take the load |
| 0:15 | `SFX_button_v1` (fanfare stab) | -12 | C4 — peak gloating |
| **0:16** | *(music cuts — no new SFX; the pour simply becomes exposed)* | — | **C5 — the most effective transition in the episode: nothing is added, the score is removed** |
| 0:16–0:27 | `SFX_pour_v1` (continuous) | **-12** | C5→C6 — inside the silence. The loudest element |
| 0:22–0:26 | `SFX_fabric_strain_v1` (rising pitch) | -16 | C6 — inside the silence. The audible countdown |
| **0:25** | **`SFX_step_back_v1`** | **-20** | **C6 — inside the silence. PIP steps back. The tell** |
| 0:26 | `SFX_button_v1` (suspense tick) | -18 | C6 — final anticipation beat |
| **0:29** | **`SFX_splash_big_v1`** | **-6 — loudest sound in the video** | **C7 — signature stage 4. The entire reservoir lands on him** |
| 0:29 | `SFX_scratch_v1` | -11 | C7 — reversal punctuation under the stinger |
| 0:30 | `SFX_umbrella_limp_v1` | -14 | C7 — the emptied canopy flopping inverted |
| **0:30.5** | **`SFX_drip_v1`** (single) | **-15** | **C7 — one last drop off his nose. The signature sound, returned to stage 1** |
| 0:31 | `SFX_puddle_v1` | -16 | C8 — his feet settling in the puddle |
| 0:31.5 | `SFX_umbrella_pop_v1` | -15 | C8 — PIP offering the tiny umbrella |
| **0:32** | **`SFX_drip_v1`** (single) + `SFX_button_v1` (ding) | -15 / -12 | C8 — the gutter drips once more, seaming into the loop |

---

## 5. Loudness / delivery (platform-ready)
- Integrated target **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- **Duck BGM ~4–6 dB under VO** for VO1–VO6; release fully into the silence.
- VO peaks ≈ -12 to -10 dBFS, ~3 dB above the ducked bed.
- **The water is the story, so give it the dynamic range.** The four signature stages must be clearly
  *different in kind*, not just in volume: `drip` = discrete and pitched · `trickle` = thin and continuous ·
  `pour` = heavy and steady · `splash` = one enormous transient. A listener with their eyes closed should be
  able to describe what happened.
- **The protected sounds** are the **0:01 drip** (the seed — if it's inaudible, the fair-play contract breaks)
  and **PIP's 0:25 step back**. Neither may be masked.
- **The loudest moments, in order:** the **0:29 splash** (-6, by a clear margin) → the 0:03 umbrella fwoomp
  → the 0:12–0:27 pour. Leave ~3 dB headroom before the splash so it genuinely lands as a deluge.
- **Never compress the silence up.** 0:16–0:27 has no music; the pour should feel exposed and close, not
  loud. Push the rain ambience back to ~-24 dB so the pour sits forward of it.
- Shorts are watched **muted by default** — verify one final time that the sagging canopy tells the whole
  story with the audio off.

---

## 6. Sourcing notes
- Use original or royalty-free/licensed audio only (advertiser-safe, monetization-safe).
- Reuse from earlier episodes: `SFX_scratch_v1`, `SFX_button_v1` set, `SFX_drip_v1` (introduced in v5's
  reveal, promoted to signature status here), and the **narrator voice**.
- New and worth locking for future weather/outdoor episodes: `MUS_rainy_bed_v1` (+ stinger and resolve),
  `SFX_trickle_v1`, `SFX_pour_v1`, `SFX_splash_big_v1`, `SFX_rain_light/med/heavy_v1`,
  `SFX_umbrella_fwoomp_v1`, `SFX_umbrella_pop_v1`, `SFX_fabric_strain_v1`, `SFX_umbrella_limp_v1`.
- **Signature-sound principle (series-wide):** v1 = the stamp · v2 = the booster · v3 = the block clack ·
  v4 = the panel slam · v5 = the discovery sting · v6 = the sweet clatter. **v7's signature sound is
  water**, and it is the most literal escalation in the series — it moves through **four distinct physical
  states** (`drip → trickle → pour → SPLASH`) that map exactly onto the story's four acts. The inversion is
  the cleanest yet: after the enormous splash, the very last sound of the episode is **one single drip off
  his nose** — the signature sound returned to its smallest possible form, right where it started.
