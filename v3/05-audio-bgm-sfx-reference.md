# v3 — BGM, SFX & Audio Reference ("One Block Too Many")

> The complete audio map for v3 — music, sound effects, and the all-important **silence beat** —
> synced to the master timeline in `01-video-script.md`. Built so that when the video (file 04) is
> generated and VO (file 03) is laid in, **everything locks to the same timecodes** and produces a
> clean, share-ready mix with minimal editing. **Mute-first principle:** audio *amplifies* the
> comedy; it never *carries* the story (the video reads with sound off).

---

## 1. Music (BGM)
| Cue | Asset | Time | Behavior |
|---|---|---|---|
| Comedy bed (building) | `MUS_comedy_bed_v1` | 0:00–0:16 | Light, jaunty, gently accelerating; a plucky "construction" feel that ramps with the stacking |
| **SILENCE** | — | 0:16–0:27 | Music **cuts out** at the top of the false victory → dread (the pattern break) |
| Slam-back + resolve | `MUS_comedy_bed_v1` (stinger + warm tail) | 0:27–0:32 | SLAMS back on the collapse, resolves warm on the button |

**Style of bed:** the same playful cartoon cue family as v1 — light percussion, plucky bass, ~120–130 BPM,
major key, no lyrics, loopable, royalty-free/original. **Series continuity:** v3 reuses v1's
`MUS_comedy_bed_v1` directly (v2 used the faster "race variant"). Add a light woodblock/marimba layer
that ticks up with each stacked block, so the music itself performs the escalation. Keep it out of the
vocal midrange so the VO sits on top.

**Cruel detail worth doing:** let the music reach its brightest, most triumphant point *right* at 0:16
— and cut it mid-phrase. An unresolved musical phrase is what makes the silence feel wrong.

---

## 2. The silence beat (the single most important audio move)
- A deliberate **~11-second musical silence from 0:16 to 0:27**, starting at the peak of CHIEF's
  celebration. It converts triumph into dread and holds viewers to the twist (serves L5: withhold
  resolution → completion).
- During the silence, allow **only**: escalating **wooden creaks** from the crooked block (three
  discrete grinding slips, matching the three visual slips in C6), one **dust trickle**, and one
  **suspense tick** (~0:25).
- Those creaks are the most important sound in the video: they tell the ear *the tower is failing* while
  the eye is still being shown a man celebrating. **The audience knows before CHIEF does** — that gap is
  the entire pleasure of the beat.
- **No VO** in this window (see file 03) except an optional whispered "…mostly." ≤0.6 s at ~0:26.
- Getting this silence right is what makes the twist pop — do not fill it with music or heavy VO.

---

## 3. SFX map (priority-ordered; synced to shots)
| Pri | SFX | Asset | Time / Shot | Purpose |
|---|---|---|---|---|
| 1 (hero) | **Block clack** | `SFX_blockclack_v1` | 0:01, 0:03–0:05 (C2), 0:06–0:11 (C3), 0:11–0:16 (C4), 0:32 (C8) | **v3's signature sound** — single/deliberate for PIP, doubled/careless for CHIEF |
| 1 (hero) | **Wooden creak** | `SFX_creak_v1` | 0:04 (seeded), 0:14–0:16, **0:22 / 0:24 / 0:26 (C6)** | The dread engine; three staged grinding slips in the silence |
| 1 (hero) | **Collapse crash** | `SFX_crash_v1` | **~0:29 (C7)** | The twist impact — big hollow wooden crash + clatter tail |
| 2 | Trophy "ting" | `SFX_ting_v1` | ~0:30 (C7) | The trophy landing on PIP's tower — must be heard **clean** |
| 2 | Target-met tick | `SFX_ting_v1` (soft) | ~0:09 (C3) | Confirms PIP hit the line without text |
| 2 | Dust trickle | `SFX_dust_v1` | 0:23, 0:25 (C6) | Texture inside the silence |
| 3 | Strut boings | `SFX_button_v1` set | 0:00–0:02 (C1) | CHIEF's vain walk |
| 3 | Sneer / dismissive "pfft" | `SFX_button_v1` set | ~0:03 (C2) | CHIEF mocking PIP's care |
| 3 | Confetti pop | `SFX_confetti_v1` | ~0:17 (C5) | The false celebration |
| 3 | Proud fanfare stab | `SFX_button_v1` set | ~0:15 (C4) | Vanity texture at the summit |
| 3 | Record-scratch | `SFX_scratch_v1` | ~0:29 (C7) | Reversal punctuation |
| 3 | Suspense tick | `SFX_button_v1` set | ~0:25 (C6) | One of only three sounds in the silence |
| 3 | Final block clack + button ding | `SFX_button_v1` | 0:32 (C8) | Likeable close |

**Deliberate absence:** no crowd/cheer audio anywhere — there is no audience in the yard, so crowd
sound would contradict the visuals. The false celebration is carried by the confetti pop, the fanfare
stab and the music peak instead. **This matters more in v3 than v1/v2:** a cheering crowd at 0:17 would
tell the ear the win was real, and the twist would feel like a cheat rather than a reveal.

---

## 4. Master sync map (all layers on one timeline)
```
Time   | Video (file 04)                | VO (file 03)         | Music              | SFX
-------+--------------------------------+----------------------+--------------------+---------------------------
0:00   | C1 strut in / red-band seed    | VO1                  | comedy bed (low)   | strut boings, block clack
0:02   | C2 PIP careful / CROOKED block | VO2–VO3              | bed                | single clacks, double-slams, CREAK
0:06   | C3 PIP hits the line, stops    | VO4                  | bed (build)        | target-met tick, fast clacks
0:11   | C4 spire + climb + flag        | (VO4 tail)           | bed (ramp)         | stacking combo, groans, fanfare
0:16   | C5 FALSE VICTORY, trophy up    | VO6 "He'd won." stop | ** CUT TO SILENCE**| confetti pop, then (music out)
0:18   | C5 held victory tableau        | (silence)            | silence            | faint creak only
0:22   | C6 crooked block slip #1       | (silence)            | silence            | CREAK #1, dust trickle
0:24   | C6 slip #2, lean increases     | (silence)            | silence            | CREAK #2
0:25   | C6 PIP looks up                | opt. whisper         | silence            | suspense tick, dust
0:26   | C6 slip #3, tilt up the tower  | (silence)            | silence            | CREAK #3 (longest)
0:27   | C7 base gives way              | VO7 "…for about—"    | (about to slam)    | first block breaks free
0:29   | C7 COLLAPSE + punch-in         | (VO7 "ten seconds.") | SLAM back          | CRASH + clatter + scratch
0:30   | C7 trophy lands on PIP's tower | (VO7 tail)           | stinger            | trophy TING (clean), impact star
0:31   | C8 CHIEF buried, PIP waves     | VO8 "Every time."    | warm resolve       | final block clack, button ding
0:32   | hard cut → loop to C1          | —                    | tail out           | —
```

---

## 5. Loudness / delivery (platform-ready)
- Integrated target **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- **Duck** the BGM ~4–6 dB under VO1–VO5; release fully into the 0:16–0:27 silence.
- VO peaks ≈ -12 to -10 dBFS, ~3 dB above the ducked bed.
- The twist hit (CRASH + music slam, ~0:29) is the loudest moment — leave ~2 dB headroom before it so it
  lands as a genuine impact. The 11 s of near-silence before it does most of the work.
- **The three creaks must survive the quiet mix** — check on phone speakers, not headphones. If a viewer
  on a phone at low volume can't hear the creaks, raise them; they are the setup for the whole payoff.
- **Do not let the CRASH mask the trophy "ting."** Duck the clatter tail ~3 dB at ~0:30 so the ting
  reads clean — that little sound is the moment the real winner is announced.
- Everything must remain legible **with audio off** (mute-first). If a viewer can't follow it muted, fix
  the video, not the audio.

---

## 6. Sourcing notes
- Use original or royalty-free/licensed audio only (advertiser-safe, monetization-safe).
- Clone/lock the SFX and bed once and reuse across the series for a consistent sonic identity. Reuse
  v1's `MUS_comedy_bed_v1`, `SFX_button_v1` set, `SFX_scratch_v1` and the narrator voice; new to v3 and
  worth locking for future build/stack episodes: `SFX_blockclack_v1`, `SFX_creak_v1`, `SFX_crash_v1`,
  `SFX_ting_v1`, `SFX_dust_v1`.
- **Signature-sound principle (shared across the series):** v1 recontextualised the *stamp*, v2 the
  *booster*. v3 uses the **block clack** — it starts as the sound of CHIEF's careless, greedy piling,
  and returns at the very end as one small lonely clack from the rubble. One signature sound,
  escalated, then inverted at the payoff.
