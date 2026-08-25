# A1 — Voice & Audio Package (Stage 6 output)

Audio map for A1. The video is **mute-first with 0 spoken words**, so there is **no VO/dialogue**;
audio is music + SFX + one deliberate silence. Voice tooling ([ElevenLabs](../tools/elevenlabs-usage.md))
is **not used for A1** but the setup is documented so the pipeline is ready for future dialogue videos.

## Narration / dialogue
- **None.** Do not generate VO for A1. (This maximizes global Reach — the chosen Goal.)

## Music
| Cue | Asset | Time | Behavior |
|---|---|---|---|
| Comedy bed (rising) | `MUS_comedy_bed_v1` | 0:00–0:16 | Light, jaunty; builds with the escalation |
| **Silence** | — | 0:16–0:27 | Music cuts at the victory pose → tension (the pattern break) |
| Slam back + resolve | `MUS_comedy_bed_v1` (stinger + tail) | 0:27–0:32 | Music SLAMS back on the twist, resolves warm on the button |

## SFX priority map
| Priority | SFX | Asset | Scene | Purpose |
|---|---|---|---|---|
| 1 (hero) | Stamp thunk | `SFX_stamp_v1` | 3,4,7 | The signature "power" sound; recontextualized on CHIEF at the twist |
| 1 (hero) | Impact punch | `SFX_punch_v1` | 7 | Lands the karma |
| 2 | Boot clamp | `SFX_clamp_v1` | 3 | Injustice beat |
| 2 | Truck rumble | `SFX_truck_v1` | 6,7 | Signals the incoming reversal |
| 3 | Record-scratch | `SFX_scratch_v1` | 7 | Reversal punctuation |
| 3 | Strut boings / fanfare | `SFX_button_v1` set | 1,4,5 | Comedy texture / CHIEF's vanity |
| 3 | Button ding + pop | `SFX_button_v1` | 8 | Likeable close + boot pop-off |

## Silence design (the key audio move)
The deliberate **11-second musical silence (0:16–0:27)** is the single most important audio choice:
it flags "something is about to happen," holding viewers to the twist. Only faint truck rumble +
one suspense "tick" break it. This directly serves L5 (withhold resolution → completion).

## Loudness / delivery
- Target ~ -14 LUFS integrated (platform-friendly), true-peak ≤ -1 dBTP.
- Everything readable **without** audio (mute-first). Audio *amplifies*; it never *carries*.

## ElevenLabs (future videos only — not A1)
When a future video needs VO/dialogue, clone the fixed-cast voices once and reuse. Full setup,
voice IDs, and batch settings live in the [ElevenLabs usage guide](../tools/elevenlabs-usage.md).
