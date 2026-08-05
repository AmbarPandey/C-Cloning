# v2 — BGM, SFX & Audio Reference ("The Victory Lap")

> The complete audio map for v2 — music, sound effects and the **silence beat** — synced to the master
> timeline in `01-video-script.md`. Built so that when the video (file 04) is generated and the VO
> (file 03) is laid in, **everything locks to the same timecodes**, producing a clean, share-ready mix
> with minimal editing. **Mute-first principle:** audio *amplifies* the comedy; it never *carries* the
> story (the video reads with sound off).

---

## 1. Music (BGM)
| Cue | Asset | Time | Behavior |
|---|---|---|---|
| Race bed (rising) | `MUS_race_bed_v1` | 0:00–0:19 | Upbeat, driving, comedic; intensity ramps with each booster |
| **SILENCE** | — | 0:19–0:27 | Music **cuts out** as CHIEF lifts off → tension (the pattern break) |
| Slam-back + resolve | `MUS_race_bed_v1` (stinger + warm tail) | 0:27–0:33 | SLAMS back on the tape snap, resolves warm on the button |

**Style of bed:** playful cartoon race cue — light percussion, plucky bass, a cheeky brass/whistle
motif, ~140 BPM (faster than v1's ~120–130 to sell the speed), major key, no lyrics, loopable,
royalty-free/original. **Series continuity:** same instrumentation and sonic palette as v1's
`MUS_comedy_bed_v1` so the channel keeps one recognisable musical identity — this is the "race variant"
of the same bed, not a different band. Keep it out of the vocal midrange so the VO sits on top.

---

## 2. The silence beat (the single most important audio move)
- A deliberate **~8-second musical silence from 0:19 to 0:27**, starting exactly as CHIEF leaves the
  ground. It signals "something is about to happen" and holds viewers through the drop-off zone.
- During the silence, allow **only**: a thin **fading doppler engine whine** as he shrinks away, one
  **suspense tick** (~0:25), and a soft **flutter of the untouched tape** (~0:26).
- That tape flutter is the most important sound in the video: it tells the ear *the tape was never
  broken* at the same moment the eye sees it. Keep it quiet but clearly audible.
- **No VO** in this window (see file 03), except an optional whispered *"…all of it."* ≤0.6 s at ~0:26.

---

## 3. SFX map (priority-ordered; synced to shots)
| Pri | SFX | Asset | Time / Shot | Purpose |
|---|---|---|---|---|
| 1 (hero) | **Booster ignition** | `SFX_booster_v1` | 0:08 (#1), 0:13 / 0:15 / 0:17 (#2–#4) | **v2's signature sound** — each ignition a step higher in pitch to sell escalation |
| 1 (hero) | **Tape snap** | `SFX_tapesnap_v1` | **~0:29 (C7)** | The twist impact — the moment of reversal |
| 1 (hero) | Booster deflate | `SFX_booster_deflate_v1` | 0:31 (C8) | The signature sound inverted — a sad "pffffft". Pays off the escalation |
| 2 | Engine scream (rising) | `SFX_engine_v1` | 0:08–0:19 | Escalation bed; ramps in pitch with each booster |
| 2 | Doppler pass-by / fade | `SFX_doppler_v1` | 0:09, 0:19–0:26 | Sells speed, then thins into the silence |
| 2 | Tape flutter | `SFX_tapeflutter_v1` | ~0:26 (C6) | **Tells the ear the tape is intact** — critical |
| 2 | Skid screech | `SFX_skid_v1` | ~0:29–0:30 (C7) | CHIEF slamming to a halt in the distance |
| 3 | Start flag whoosh | `SFX_flag_v1` | 0:07 (C3) | The GO beat |
| 3 | Confetti pop | `SFX_confetti_v1` | ~0:29 (C7) | Celebration texture |
| 3 | Champion medal ding | `SFX_medal_v1` | ~0:30 (C7) | The award moment |
| 3 | Record-scratch | `SFX_scratch_v1` | ~0:29 (C7) | Reversal punctuation |
| 3 | Strut boings | `SFX_button_v1` set | 0:00–0:03 (C1) | CHIEF's vain walk |
| 3 | Trophy clunk + dismissive "pfft" | `SFX_button_v1` set | 0:04–0:05 (C2) | Plants the trophy, flicks the ribbon (Seed B) |
| 3 | Skate squeaks/rumble | `SFX_skates_v1` | 0:08–0:29 | PIP's humble steady progress — quiet, persistent |
| 3 | Suspense tick | `SFX_button_v1` set | ~0:25 (C6) | One of only three sounds in the silence |
| 3 | Ribbon pin tap + button ding | `SFX_button_v1` | 0:32 (C8) | Likeable close |

**Deliberate absence:** there is **no crowd/cheer audio anywhere** — the grandstands are empty (a locked
environment rule), so crowd sound would contradict the visuals. Celebration is carried by confetti pop,
medal ding and the music slam instead.

---

## 4. Master sync map (all layers on one timeline)
```
Time   | Video (file 04)               | VO (file 03)        | Music              | SFX
-------+-------------------------------+---------------------+--------------------+------------------------------
0:00   | C1 strut in / both seeds      | VO1                 | race bed (low)     | strut boings, engine idle
0:03   | C2 trophy planted, ribbon flick| VO2                | bed                | clunk, "pfft", aha sting
0:07   | C3 flag drop, booster #1      | VO3                 | bed (build)        | flag whoosh, BOOSTER #1, doppler
0:12   | C4 boosters #2-#4 stack       | VO4                 | bed (ramp)         | BOOSTER #2/#3/#4, engine scream
0:18   | C5 lift-off, hero hold        | VO5 -> stop (0:19)  | ** CUT TO SILENCE**| (music out)
0:19   | C5 rising, airborne           | (silence)           | silence            | thin engine whine only
0:23   | C6 sails OVER the tape        | (silence)           | silence            | doppler fading away
0:25   | C6 hold on untouched tape     | opt. whisper        | silence            | suspense tick
0:26   | C6 tape sways, intact         | (silence)           | silence            | TAPE FLUTTER (critical)
0:27   | C7 PIP reaches the tape       | VO6                 | (about to slam)    | skate rumble rising
0:29   | C7 TAPE SNAP + punch-in       | (VO6 mid)           | SLAM back          | TAPE SNAP + confetti + scratch + skid
0:30   | C7 podium freeze (0.5s)       | (VO6 tail)          | stinger            | medal ding, impact star hit
0:31   | C8 ribbon pinned, PIP waves   | VO7 "Every time."   | warm resolve       | booster DEFLATE, pin tap, button ding
0:33   | hard cut -> loop to C1        | -                   | tail out           | -
```

---

## 5. Loudness / delivery (platform-ready)
- Integrated target **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- **Duck** the BGM ~4–6 dB under VO1–VO5; release fully into the 0:19–0:27 silence.
- VO peaks ≈ -12 to -10 dBFS, ~3 dB above the ducked bed.
- The twist hit (TAPE SNAP + music slam, ~0:29) is the loudest moment — leave ~2 dB headroom before it
  so it lands as a genuine impact. The 8 s of silence immediately before it does most of the work.
- The **tape flutter (~0:26)** must survive the quiet mix — check it on phone speakers, not just headphones.
- Everything must remain legible **with audio off** (mute-first). If a viewer can't follow it muted, fix
  the video, not the audio.

---

## 6. Sourcing & series notes
- Use original or royalty-free/licensed audio only (advertiser-safe, monetization-safe).
- **Series sonic identity:** reuse v1's `SFX_button_v1` set, the narrator voice, and the same
  instrumentation family. New to v2 and worth locking for future race/vehicle episodes:
  `SFX_booster_v1` + `SFX_booster_deflate_v1` (an ignition/deflate pair) and `SFX_tapesnap_v1`.
- **Signature-sound design principle (shared with v1):** v1 recontextualised the *stamp* — CHIEF's power
  sound turned against him. v2 does the same with the **booster**: it's the sound of his arrogance
  escalating (4 ignitions, rising pitch), and it returns at the very end as a limp deflate. Keep this
  pattern in every episode — one signature sound, escalated, then inverted at the payoff.
