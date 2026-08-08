# v2 — BGM, SFX & Audio Reference ("The Victory Lap")

> The complete audio map for v2 — music, sound effects, and the all-important **silence beat** —
> synced to the master timeline in `01-video-script.md`. Built so that when the video (file 04) is
> generated and VO (file 03) is laid in, **everything locks to the same timecodes** and produces a
> clean, share-ready mix with minimal editing. **Mute-first principle:** audio *amplifies* the
> comedy; it never *carries* the story (the video reads with sound off).

---

## 1. Music (BGM)
| Cue | Asset | Time | Behavior |
|---|---|---|---|
| Race bed (rising) | `MUS_race_bed_v1` | 0:00–0:16 | Upbeat, driving, comedic; intensity ramps with each booster |
| **SILENCE** | — | 0:16–0:27 | Music **cuts out** as CHIEF leaves the ground → tension (the pattern break) |
| Slam-back + resolve | `MUS_race_bed_v1` (stinger + warm tail) | 0:27–0:32 | SLAMS back on the tape snap, resolves warm on the button |

**Style of bed:** playful cartoon race cue — light percussion, plucky bass, a cheeky brass/whistle
motif, ~140 BPM (faster than v1's ~120–130 to sell the speed), major key, no lyrics, loopable,
royalty-free/original. **Series continuity:** same instrumentation and sonic palette as v1's
`MUS_comedy_bed_v1` — this is the "race variant" of the same bed, not a different band. Keep it out of
the vocal midrange so the VO sits on top.

---

## 2. The silence beat (the single most important audio move)
- A deliberate **~11-second musical silence from 0:16 to 0:27**, starting exactly as CHIEF leaves the
  ground. It signals "something is about to happen" and holds viewers to the twist (serves L5:
  withhold resolution → completion).
- During the silence, allow **only**: a thin **fading doppler engine whine** as he shrinks away, **one**
  suspense "tick" (~0:25), and a soft **flutter of the untouched tape** (~0:26).
- That tape flutter is the most important sound in the video: it tells the ear *the tape was never
  broken* at the same moment the eye sees it. Keep it quiet but clearly audible.
- **No VO** in this window (see file 03) except an optional whispered "…all of it." ≤0.6 s at ~0:26.
- Getting this silence right is what makes the twist pop — do not fill it with music or heavy VO.

---

## 3. SFX map (priority-ordered; synced to shots)
| Pri | SFX | Asset | Time / Shot | Purpose |
|---|---|---|---|---|
| 1 (hero) | **Booster ignition** | `SFX_booster_v1` | 0:07 (#1, C3), 0:12 / 0:13.5 / 0:15 (#2–#4, C4) | **v2's signature sound** — each ignition a step higher in pitch to sell escalation |
| 1 (hero) | **Tape snap** | `SFX_tapesnap_v1` | **~0:29 (C7)** | The twist impact — the moment of reversal |
| 1 (hero) | Booster deflate | `SFX_booster_deflate_v1` | 0:31 (C8) | The signature sound inverted — a sad "pffffft" |
| 2 | Engine scream (rising) | `SFX_engine_v1` | 0:07–0:16 | Escalation bed; ramps in pitch with each booster |
| 2 | Doppler pass-by / fade | `SFX_doppler_v1` | 0:08, 0:16–0:25 | Sells speed, then thins into the silence |
| 2 | Tape flutter | `SFX_tapeflutter_v1` | ~0:26 (C6) | **Tells the ear the tape is intact** — critical |
| 2 | Skid screech | `SFX_skid_v1` | ~0:29–0:30 (C7) | CHIEF slamming to a halt in the distance |
| 3 | Start flag whoosh | `SFX_flag_v1` | 0:06 (C3) | The GO beat |
| 3 | Confetti pop | `SFX_confetti_v1` | ~0:29 (C7) | Celebration texture |
| 3 | Champion medal ding | `SFX_medal_v1` | ~0:30 (C7) | The award moment |
| 3 | Record-scratch | `SFX_scratch_v1` | ~0:29 (C7) | Reversal punctuation |
| 3 | Strut boings | `SFX_button_v1` set | 0:00–0:02 (C1) | CHIEF's vain walk |
| 3 | Trophy clunk + dismissive "pfft" | `SFX_button_v1` set | 0:03–0:04 (C2) | Plants the trophy, flicks the ribbon |
| 3 | Skate squeaks/rumble | `SFX_skates_v1` | 0:07–0:29 | PIP's humble steady progress — quiet, persistent |
| 3 | Suspense tick | `SFX_button_v1` set | ~0:25 (C6) | The one sound in the silence |
| 3 | Ribbon pin tap + button ding | `SFX_button_v1` | 0:32 (C8) | Likeable close |

**Deliberate absence:** there is **no crowd/cheer audio anywhere** — the grandstands are empty (a locked
environment rule), so crowd sound would contradict the visuals. Celebration is carried by the confetti
pop, medal ding and music slam instead.

---

## 4. Master sync map (all layers on one timeline)
```
Time   | Video (file 04)               | VO (file 03)          | Music            | SFX
-------+-------------------------------+-----------------------+------------------+--------------------------
0:00   | C1 strut in / seeds           | VO1                   | race bed (low)   | strut boings, engine idle
0:02   | C2 trophy planted, ribbon flick| VO2–VO3              | bed              | clunk, "pfft", aha sting
0:06   | C3 flag drop, booster #1      | VO4                   | bed (build)      | flag whoosh, BOOSTER #1, doppler
0:11   | C4 boosters #2–#4 stack       | VO5                   | bed (ramp)       | BOOSTER #2/#3/#4, engine scream
0:16   | C5 lift-off, hero hold        | VO6 → stop            | ** CUT TO SILENCE**| (music out)
0:18   | C5 rising, airborne           | (silence)             | silence          | thin engine whine only
0:22   | C6 sails OVER the tape        | (silence)             | silence          | doppler fading away
0:25   | C6 hold on untouched tape     | opt. whisper          | silence          | suspense tick
0:26   | C6 tape sways, intact         | (silence)             | silence          | TAPE FLUTTER (critical)
0:27   | C7 PIP reaches the tape       | VO7                   | (about to slam)  | skate rumble rising
0:29   | C7 TAPE SNAP + punch-in       | (VO7 mid)             | SLAM back        | TAPE SNAP+confetti+scratch+skid
0:30   | C7 podium freeze (0.5s)       | (VO7 tail)            | stinger          | medal ding, impact star hit
0:31   | C8 ribbon pinned, PIP waves   | VO8 "Every time."     | warm resolve     | booster DEFLATE, pin tap, ding
0:32   | hard cut → loop to C1         | —                     | tail out         | —
```

---

## 5. Loudness / delivery (platform-ready)
- Integrated target **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- **Duck** the BGM ~4–6 dB under VO1–VO5; release fully into the 0:16–0:27 silence.
- VO peaks ≈ -12 to -10 dBFS, ~3 dB above the ducked bed.
- The twist hit (TAPE SNAP + music slam, ~0:29) is the loudest moment — leave ~2 dB headroom before it
  so it feels like a genuine impact. The 11 s of silence before it does most of the work.
- The **tape flutter (~0:26)** must survive the quiet mix — check it on phone speakers, not headphones.
- Everything must remain legible **with audio off** (mute-first). If a viewer can't follow it muted, fix
  the video, not the audio.

---

## 6. Sourcing notes
- Use original or royalty-free/licensed audio only (advertiser-safe, monetization-safe).
- Clone/lock the SFX and bed once and reuse across the series for a consistent sonic identity. Reuse
  v1's `SFX_button_v1` set and narrator voice; new to v2 and worth locking for future race/vehicle
  episodes: `SFX_booster_v1` + `SFX_booster_deflate_v1` (an ignition/deflate pair) and `SFX_tapesnap_v1`.
- **Signature-sound principle (shared with v1):** v1 recontextualised the *stamp* — CHIEF's power sound
  turned against him. v2 does the same with the **booster**: it's the sound of his arrogance escalating
  (4 ignitions, rising pitch), and it returns at the very end as a limp deflate. Keep this pattern in
  every episode — one signature sound, escalated, then inverted at the payoff.
