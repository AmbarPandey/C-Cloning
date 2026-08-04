# v1 — BGM, SFX & Audio Reference ("The Wrong Scooter")

> The complete audio map for v1 — music, sound effects, and the all-important **silence beat** —
> synced to the master timeline in `01-video-script.md`. Built so that when the video (file 04) is
> generated and VO (file 03) is laid in, **everything locks to the same timecodes** and produces a
> clean, share-ready mix with minimal editing. **Mute-first principle:** audio *amplifies* the
> comedy; it never *carries* the story (the video reads with sound off).

---

## 1. Music (BGM)
| Cue | Asset | Time | Behavior |
|---|---|---|---|
| Comedy bed (rising) | `MUS_comedy_bed_v1` | 0:00–0:16 | Light, jaunty; swells as the escalation builds |
| **SILENCE** | — | 0:16–0:27 | Music **cuts out** at the victory-pose freeze → tension (the pattern break) |
| Slam-back + resolve | `MUS_comedy_bed_v1` (stinger + warm tail) | 0:27–0:32 | SLAMS back on the twist, resolves warm on the button |

**Style of bed:** playful cartoon/mischief cue, light percussion + plucky bass, ~120–130 BPM, major
key, no lyrics, loopable, royalty-free/original. Keep it out of the vocal midrange so VO sits on top.

---

## 2. The silence beat (the single most important audio move)
- A deliberate **~11-second musical silence from 0:16 to 0:27.** It signals "something is about to
  happen" and holds viewers to the twist (serves L5: withhold resolution → completion).
- During the silence, allow **only**: a low truck rumble (from ~0:23) and **one** suspense "tick" (~0:25–0:26).
- **No VO** in this window (see file 03) except an optional whispered "…he didn't." ≤0.6 s at ~0:26.
- Getting this silence right is what makes the twist pop — do not fill it with music or heavy VO.

---

## 3. SFX map (priority-ordered; synced to shots)
| Pri | SFX | Asset | Time / Shot | Purpose |
|---|---|---|---|---|
| 1 (hero) | Stamp thunk | `SFX_stamp_v1` | 0:07 (C3), 0:12–0:14 combo (C4), **0:29 (C7)** | Signature "power" sound; recontextualized *on* CHIEF at the twist |
| 1 (hero) | Impact punch | `SFX_punch_v1` | ~0:29 (C7) | Lands the karma (the big hit) |
| 2 | Boot clamp | `SFX_clamp_v1` | ~0:08 (C3) | Injustice beat |
| 2 | Truck rumble | `SFX_truck_v1` | 0:23–0:30 (C6→C7) | Signals the incoming reversal (breaks the silence) |
| 3 | Record-scratch | `SFX_scratch_v1` | ~0:29 (C7) | Reversal punctuation |
| 3 | Strut boings | `SFX_button_v1` set | 0:00–0:02 (C1) | CHIEF's vain walk |
| 3 | "Aha" sting | `SFX_button_v1` set | ~0:03 (C2) | Spots the infraction |
| 3 | Tiny fanfare / medal shine | `SFX_button_v1` set | 0:05, 0:14 (C4/C5) | Vanity texture |
| 3 | Suspense tick | `SFX_button_v1` set | ~0:25 (C6) | The one sound in the silence |
| 3 | Button ding + boot pop | `SFX_button_v1` | 0:31–0:32 (C8) | Likeable close + boot pop-off |

---

## 4. Master sync map (all layers on one timeline)
```
Time   | Video (file 04)              | VO (file 03)          | Music            | SFX
-------+------------------------------+-----------------------+------------------+--------------------------
0:00   | C1 strut in / seed           | VO1–VO2               | bed (low, rising)| strut boings
0:02   | C2 draws stamp (push-in)     | VO3                   | bed              | aha sting, paper riffle
0:06   | C3 stamp + boot (impact hold)| VO4                   | bed              | STAMP, CLAMP, aww bell
0:11   | C4 ticket pile / medals      | VO5                   | bed (swell)      | stamp combo, fanfare
0:16   | C5 podium victory freeze     | VO6 → stop            | ** CUT TO SILENCE**| (music out)
0:18   | C5 held pose                 | (silence)             | silence          | (nothing)
0:22   | C6 tow truck rolls in        | (silence)             | silence          | truck rumble (low)
0:25   | C6 hook aligns               | opt. whisper          | silence          | suspense tick
0:27   | C7 TWIST punch-in            | VO7                   | SLAM back        | STAMP+PUNCH+record-scratch
0:29   | C7 "TOWED" freeze (0.5s)     | (VO7 tail)            | stinger          | impact star hit
0:31   | C8 boot pop + PIP wave       | VO8 "Every time."     | warm resolve     | pop + button ding
0:32   | hard cut → loop to C1        | —                     | tail out         | —
```

---

## 5. Loudness / delivery (platform-ready)
- Integrated target **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- **Duck** the BGM ~4–6 dB under VO1–VO5; release fully into the 0:16–0:27 silence.
- VO peaks ≈ -12 to -10 dBFS, ~3 dB above the ducked bed.
- The twist hit (PUNCH+STAMP, ~0:29) is the loudest moment — leave ~2 dB headroom before it so it feels like an impact.
- Everything must remain legible **with audio off** (mute-first). If a viewer can't follow it muted, fix the video, not the audio.

---

## 6. Sourcing notes
- Use original or royalty-free/licensed audio only (advertiser-safe, monetization-safe).
- Clone/lock the SFX and bed once and reuse across the series for a consistent sonic identity.
- `SFX_stamp_v1` is the series' signature sound — keep it identical every episode so the karma
  callback (its use *against* the antagonist) reads instantly to returning viewers.
