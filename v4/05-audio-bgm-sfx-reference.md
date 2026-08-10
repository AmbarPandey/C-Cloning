# v4 — BGM, SFX & Audio Reference ("The Wrong Side of the Fence")

> The complete audio map for v4 — music, sound effects, and the all-important **silence beat** —
> synced to the master timeline in `01-video-script.md`. Built so that when the video (file 04) is
> generated and VO (file 03) is laid in, **everything locks to the same timecodes** and produces a
> clean, share-ready mix with minimal editing. **Mute-first principle:** audio *amplifies* the
> comedy; it never *carries* the story (the video reads with sound off).

---

## 1. Music (BGM)
| Cue | Asset | Time | Behavior |
|---|---|---|---|
| Comedy bed (building) | `MUS_comedy_bed_v1` | 0:00–0:16 | Light, jaunty, mischievous; a busy "working" rhythm that ramps with the panel slams |
| **SILENCE** | — | 0:16–0:27 | Music **cuts out** at the peak of his proud pose → dread (the pattern break) |
| Slam-back + resolve | `MUS_comedy_bed_v1` (stinger + warm tail) | 0:27–0:32 | SLAMS back on the padlock click, resolves warm and cool on the button |

**Style of bed:** the same playful cartoon cue family as v1 and v3 — light percussion, plucky bass,
~120–130 BPM, major key, no lyrics, loopable, royalty-free/original. **Series continuity:** v4 reuses
v1's `MUS_comedy_bed_v1` directly. Let the percussion lock to the **panel slams** so the music sounds
like it is being built along with the fence. Keep it out of the vocal midrange so the VO sits on top.

**Cut it mid-phrase at 0:16**, at the brightest, most self-congratulatory point. An unresolved phrase is
what makes the silence feel wrong.

---

## 2. The silence beat (the single most important audio move)
- A deliberate **~11-second musical silence from 0:16 to 0:27**, starting at the peak of CHIEF's proud
  pose and running through the entire pull-back reveal. It converts triumph into dread and holds viewers
  to the twist (serves L5: withhold resolution → completion).
- During the silence, allow **only**: a **rising cicada buzz** (the sound of the sun), one hollow **gust**,
  a single **suspense tick** (~0:25), and — crucially — the **cool water trickle of the fountain, now
  clearly positioned on the other side of the fence**.
- **That trickle is v4's cleverest sound.** As the camera pulls back, the cool, pleasant sound is
  *audibly out of reach* while the dry buzz closes in around CHIEF. The audio performs the irony at the
  same moment the framing reveals it. Pan the trickle toward the garden side and the buzz toward CHIEF's.
- **No VO** in this window (see file 03) except an optional whispered "…oh." ≤0.6 s at ~0:26.
- Getting this silence right is what makes the twist pop — do not fill it with music or heavy VO.

---

## 3. SFX map (priority-ordered; synced to shots)
| Pri | SFX | Asset | Time / Shot | Purpose |
|---|---|---|---|---|
| 1 (hero) | **Fence panel SLAM** | `SFX_panelslam_v1` | 0:04 (C2), 0:06–0:11 ×6 (C3), 0:11–0:14 ×4 (C4) | **v4's signature sound** — heavy, loud, rising in pitch as the wall grows |
| 1 (hero) | **Padlock CLICK** | `SFX_padlockclick_v1` | **~0:29 (C7)** | The twist. Tiny, quiet, decisive — the small sound that defeats every loud one |
| 1 (hero) | Cicada buzz (rising) | `SFX_cicada_v1` | 0:00 (faint), **0:16–0:31 (rising)** | The sound of the sunny side; becomes CHIEF's punishment |
| 2 | Water trickle | `SFX_fountain_v1` | 0:00–0:32 (panned to the shade side) | The cool side; audibly *out of reach* after 0:22 |
| 2 | Padlock clink (hung) | `SFX_padlockclink_v1` | ~0:14 (C4) | Plants the hero prop in the ear before it matters |
| 2 | Fence rattle | `SFX_fencerattle_v1` | ~0:30 (C7) | His futile response |
| 2 | Dust puff | `SFX_dust_v1` | per panel (C2–C4) | Weight and texture under the slams |
| 3 | Strut boings | `SFX_button_v1` set | 0:00–0:02 (C1) | CHIEF's vain walk |
| 3 | Dismissive "pfft" | `SFX_button_v1` set | ~0:03 (C2) | CHIEF sneering at PIP |
| 3 | Glove claps ×2 | `SFX_button_v1` set | ~0:15 (C4) | "Job done" punctuation |
| 3 | Proud fanfare stab | `SFX_button_v1` set | ~0:15 (C4) | Vanity texture |
| 3 | Hollow gust | `SFX_gust_v1` | ~0:24 (C6) | Emptiness on his side |
| 3 | Suspense tick | `SFX_button_v1` set | ~0:25 (C6) | One of only four sounds in the silence |
| 3 | Record-scratch | `SFX_scratch_v1` | ~0:29 (C7) | Reversal punctuation |
| 3 | BUD whine / gate creak | `SFX_gatecreak_v1` | 0:09 (C3), 0:28 (C7) | A tiny worried whine, then the gate swinging shut |
| 3 | Button ding | `SFX_button_v1` | 0:32 (C8) | Likeable close |

**Deliberate absence:** no crowd/cheer audio and **no animal vocalisations beyond one small BUD whine**.
The park animals are visual set dressing; giving them voices would pull focus from the leads and break
the mute-first discipline. Silence from the animals also makes their calm indifference at the twist funnier.

---

## 4. Master sync map (all layers on one timeline)
```
Time   | Video (file 04)                 | VO (file 03)        | Music              | SFX
-------+---------------------------------+---------------------+--------------------+---------------------------
0:00   | C1 strut in / seeds + shade edge| VO1                 | comedy bed (low)   | strut boings, trickle, faint cicada
0:02   | C2 sneer, first panel SLAM      | VO2–VO3             | bed                | pfft, PANEL SLAM, dust
0:06   | C3 panels seal the boundary     | VO4                 | bed (build)        | SLAM x6 rising, dust, BUD whine
0:11   | C4 wall doubles, padlock hung   | VO5                 | bed (ramp)         | SLAM x4, padlock CLINK, claps, fanfare
0:16   | C5 tight proud pose (geometry hidden) | VO6 "He thought
       |                                 | of everything." stop| ** CUT TO SILENCE**| cicada begins to rise
0:18   | C5 held pose                    | (silence)           | silence            | cicada rising only
0:22   | C6 PULL-BACK begins             | (silence)           | silence            | trickle now clearly on the far side
0:24   | C6 grin falters                 | (silence)           | silence            | hollow gust
0:25   | C6 glances, sweat bead          | opt. whisper "…oh." | silence            | suspense tick
0:27   | C7 BUD nudges the gate          | VO7 "He'd built it— | (about to slam)    | gate creak
0:29   | C7 PADLOCK CLICK + punch-in     | —from the outside." | SLAM back          | PADLOCK CLICK (clean) + scratch
0:30   | C7 fence rattle, freeze         | (VO7 tail)          | stinger            | fence rattle, impact star, cicada max
0:31   | C8 CHIEF wilting, PIP waves     | VO8 "Every time."   | warm resolve       | cicada, trickle, button ding
0:32   | hard cut → loop to C1           | —                   | tail out           | —
```

---

## 5. Loudness / delivery (platform-ready)
- Integrated target **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- **Duck** the BGM ~4–6 dB under VO1–VO5; release fully into the 0:16–0:27 silence. **Never duck the cicada buzz** — it is doing the storytelling.
- VO peaks ≈ -12 to -10 dBFS, ~3 dB above the ducked bed.
- **The critical mix decision in v4:** the **padlock CLICK must be quiet and still be the clearest sound in the video.** Do not compress it up to match the panel slams. Duck the music stinger ~3 dB for ~200 ms around ~0:29 so the click lands in a small pocket of space. The joke is that a tiny sound beats twelve loud ones — the mix has to sell that.
- The panel SLAMS should be the loudest *sustained* element (they establish the scale of his effort), while the CLICK is the most *legible*.
- **Pan the two worlds:** trickle and BUD toward the garden side, cicada buzz and slams toward CHIEF's side. On phone speakers this collapses to mono, so also separate them by frequency — trickle bright and thin, cicada dry and mid.
- Everything must remain legible **with audio off** (mute-first). If a viewer can't follow it muted, fix the video, not the audio.

---

## 6. Sourcing notes
- Use original or royalty-free/licensed audio only (advertiser-safe, monetization-safe).
- Clone/lock the SFX and bed once and reuse across the series for a consistent sonic identity. Reuse
  v1's `MUS_comedy_bed_v1`, `SFX_button_v1` set, `SFX_scratch_v1`, `SFX_dust_v1` and the narrator voice.
  New to v4 and worth locking for future outdoor/build episodes: `SFX_panelslam_v1`,
  `SFX_padlockclick_v1`, `SFX_padlockclink_v1`, `SFX_cicada_v1`, `SFX_fountain_v1`, `SFX_fencerattle_v1`,
  `SFX_gust_v1`, `SFX_gatecreak_v1`.
- **Signature-sound principle (shared across the series):** v1 recontextualised the *stamp*, v2 the
  *booster*, v3 the *block clack*. v4 uses the **panel slam** — twelve escalating slams of brute effort,
  inverted at the payoff by a single tiny **padlock click** that undoes all of them. One signature sound,
  escalated, then inverted at the payoff. v4 is the purest expression of that principle so far, because
  the inversion is a *different, smaller* sound rather than a weakened version of the same one.
