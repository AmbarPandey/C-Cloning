# v11 - BGM, SFX & Audio Reference ("The Express Lane") - **SHORTS**

> The complete audio map for v11, synced to the master timeline in `01-video-script.md`. This file is
> **prescriptive, not advisory**: the cue sheet states which layers are playing during every time range,
> and the SFX hit list places every effect at its exact timecode and mix level.
> **Mute-first principle:** audio *amplifies*; it never *carries*. The video reads with sound off.

---

## 1. Asset list (with real sourcing)

### Music
| ID | Description | Real Source | Used |
|---|---|---|---|
| `MUS_shop_bed_v1` | **Main bed.** A jaunty, upbeat ukulele and glockenspiel comedy cue - light strumming, bright mallet hits, snappy finger-snaps, ~118 BPM, major key. Builds density as the item count climbs | **Pixabay Music - "Ukulele" by JENOAH** (free license, no attribution required) | 0:00-0:16 |
| `MUS_shop_stinger_v1` | **Payoff stinger** - a bright mallet/bell hit resolving into a warm major chord | **YouTube Audio Library - "Comedy Accent 03"** (royalty-free) | 0:27 |
| `MUS_shop_resolve_v1` | **Warm resolve tail** - gentle ukulele reprise, soft glockenspiel resolution, satisfied ending cadence | **Pixabay Music - "Happy Ukulele" by Olexy** (free license, no attribution required) | 0:29-0:32 |

> **Series continuity:** same instrumentation family as prior episodes (light percussion, plucky melody,
> no lyrics). The ukulele/glockenspiel color is a *variant* for this episode's shopping theme.

### SFX (Real Sources)
| ID | Description | Real Source |
|---|---|---|
| `SFX_cart_rattle_v1` | Shopping cart wheels rattling at speed | **Freesound #370067 - "shopping_cart_rolling.wav" by InspectorJ (CC BY 3.0)** |
| `SFX_items_clatter_v1` | Items shifting/clinking in an overfull cart | **Freesound #392564 - "items_in_bag_shift.wav" by Breviceps (CC0)** |
| `SFX_body_bump_v1` | Soft body bump (PIP being shoved aside) | **Freesound #268227 - "body_push.wav" by Merrick079 (CC0)** |
| `SFX_scanner_beep_v1` | Self-checkout scanner beep (cheerful, clean) | **Freesound #421837 - "barcode_scanner_beep.wav" by elmasmansen1 (CC0)** |
| `SFX_item_thunk_v1` | Item placed on scanner belt/pad | **Freesound #351362 - "object_put_down_hard.wav" by Breviceps (CC0)** |
| `SFX_scanner_beep_warning_v1` | Scanner beep with slightly flat tone (warning at item 10) | **Freesound #421837 - "barcode_scanner_beep.wav" by elmasmassen1 (CC0)** - pitch-shifted -3 semitones |
| `SFX_screen_flash_v1` | Electronic screen changing/flashing (a digital pulse) | **Freesound #341695 - "power_on_chime.wav" by EminYILDIRIM (CC BY 3.0)** - short edit, first 0.3 s only |
| `SFX_wrong_buzz_v1` | Harsh electronic wrong-answer buzzer (the lockout sound) | **Freesound #331381 - "error_buzz.wav" by Breviceps (CC0)** |
| `SFX_barrier_drop_v1` | Mechanical barrier/gate arm dropping into place (heavy clunk) | **Freesound #156031 - "machine_stop_clunk.wav" by Benboncan (CC BY 3.0)** |
| `SFX_alarm_beacon_v1` | Slow spinning alarm beacon click (one rotation = one click) | **Freesound #399303 - "indicator_click.wav" by EFlexMusic (CC0)** - with 1.5 s loop |
| `SFX_rescan_buzz_v1` | Re-scan attempt followed by harsh rejection buzz | **Freesound #331381 - "error_buzz.wav" by Breviceps (CC0)** - layered with scanner bleep |
| `SFX_button_tap_dead_v1` | Rapid tapping on a touchscreen with no response (dull taps) | **Freesound #446100 - "button_click_plastic.wav" by EminYILDIRIM (CC0)** - low-pass filtered, no response chime |
| `SFX_barrier_rattle_v1` | Metal barrier being pulled/rattled but not moving | **Freesound #370244 - "metal_gate_open.wav" by InspectorJ (CC BY 3.0)** - first 0.5 s only (rattle without opening) |
| `SFX_clean_beep_v1` | One clean, satisfying checkout scanner beep (PIP's scan) | **Mixkit - "Correct Answer Tone"** (free SFX license) |
| `SFX_register_ding_v1` | Cheerful cash register completion ding | **Freesound #504847 - "scanner_beep.wav" by colorsCrimsonTears (CC0)** - pitch-shifted +5 semitones for brightness |
| `SFX_gate_slide_v1` | Smooth mechanical gate sliding open (checkout exit) | **Freesound #352036 - "sliding_door_auto.wav" by deleted_user_2906614 (CC0)** |
| `SFX_jaw_drop_v1` | Cartoon jaw-drop sound (descending slide) | **ZapSplat - "Cartoon Jaw Drop Slide Down"** (standard license, free tier) |
| `SFX_item_topple_v1` | One item falling off a pile/cart | **Freesound #351362 - "object_put_down_hard.wav" by Breviceps (CC0)** - reversed + pitched down |
| `SFX_scratch_v1` | Record-scratch (reused from series) | **Series asset (established v1)** |
| `SFX_button_v1` | Series button/ding set (reused from series) | **Series asset (established v1)** |
| `SFX_defeated_groan_v1` | A low defeated groan | **Freesound #351809 - "sigh_male_defeated.wav" by Wolfsinger (CC0)** - pitched down -2 semitones |

---

## 2. EXACT CUE SHEET - what is playing, when

**Layer key:** `BGM` = music bed - `SFX` = effects - `VO` = narration - `AMB` = ambient (store background hum, runs 0:00-0:32 at -24 dB; alarm beacon 0:16-0:27)

| # | Time range | Layer stack | BGM playing | AMB | Notes |
|---|---|---|---|---|---|
| 1 | **0:00-0:02** | **BGM + SFX + VO + AMB** | `MUS_shop_bed_v1` (enters frame 1, ~-17 dB) | store hum at -24 dB | Cart crash + shove. Establish both registers visually |
| 2 | **0:02-0:06** | **BGM + SFX + VO + AMB** | `MUS_shop_bed_v1` (full, ~-14 dB) | store hum at -24 dB | First three scans. Each beep adds energy |
| 3 | **0:06-0:11** | **BGM + SFX + VO + AMB** | `MUS_shop_bed_v1` - **adds rhythmic layer synced to scan beeps** | store hum at -24 dB | Scans 4-7. Bed and beeps sync into a rhythm |
| 4 | **0:11-0:16** | **BGM + SFX + AMB** *(VO ends ~0:14)* | `MUS_shop_bed_v1` - **brightest, densest point** (all layers) | store hum at -24 dB | Scans 8-9-10. Warning flash at 10. Bed peaks |
| 5 | **0:16** | **SFX + AMB only** - *music cuts mid-phrase on the barrier drop* | **-- NONE from 0:16** | `SFX_alarm_beacon_v1` begins at -22 dB | The cut lands on the frame of the barrier CLUNK |
| 6 | **0:16-0:27** | **SFX + AMB only - MUSICAL SILENCE (11 s)** | **-- NONE** | alarm beacon click at -22 dB (continuous, every 1.5 s) | Only the beacon click, re-scan buzzes, dead button taps, and barrier rattle. **The silence makes the rejection buzz devastating** |
| 7 | **0:27-0:29** | **BGM + SFX + VO + AMB** | `MUS_shop_stinger_v1` (SLAM in on PIP's footstep) | store hum returns to -24 dB | Bright mallet hit + warm chord |
| 8 | **0:29-0:32** | **BGM + SFX + VO + AMB** | `MUS_shop_resolve_v1` (warm, resolving) | store hum fading out | Payoff + loop out |

**Visual summary of the music shape:**
```
0:00 -- BED (jaunty ukulele) -- +rhythm layer -- (densest) --+
0:16                                                           | (cut mid-phrase on barrier drop)
0:16                          --- SILENCE ---                  |
                                 (11 s)                        |
0:27                                          +----- stinger -----+
0:29                                          |                   +-- resolve --> 0:32
```

---

## 3. The silence beat (0:16-0:27) - the single most important audio move

An **11-second musical silence**, cut **mid-phrase** on the frame the barrier drops.

**Only these sounds are permitted inside it:**

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16-0:27 | `SFX_alarm_beacon_v1` (continuous, every 1.5 s) | **-22 dB** | The spinning alarm. The machine has judged him. Relentless and indifferent |
| 0:16 | `SFX_wrong_buzz_v1` | -9 dB | The lockout buzz. Exposed by the music cut |
| 0:16.5 | `SFX_barrier_drop_v1` | -8 dB | The barrier arm slamming down. Heavy and final |
| 0:22 | `SFX_scanner_beep_v1` (scan attempt) | -14 dB | Re-scan attempt |
| 0:22.5 | `SFX_rescan_buzz_v1` | **-10 dB** | First "OVER LIMIT" rejection. Harsh |
| 0:23.5 | `SFX_button_tap_dead_v1` | -14 dB | Rapid button tapping - dead screen, no response |
| 0:24 | `SFX_button_tap_dead_v1` | -13 dB | More tapping, faster |
| 0:25 | `SFX_barrier_rattle_v1` | **-10 dB** | Pulling the barrier - metallic rattle, it holds |
| 0:25.5 | `SFX_barrier_rattle_v1` | **-9 dB** | Harder pull - louder rattle, still holds |
| 0:26 | (silence + beacon click only) | -- | The defeat. No sound except the indifferent machine |

- **No VO** in this window except an optional whispered *"...he was stuck."* at ~0:26, <=0.8 s.
- **No music, no stings.** The rejection buzz and barrier rattle in silence carry the desperation.
- **The contrast principle:** harsh buzzes and metallic rattling in silence vs. the one clean cheerful beep in C7. The *simple single scan* defeating the *overloaded 30+ item attempt*.

---

## 4. Complete SFX hit list (every effect, exact timecode)

| Time | SFX | Level | Clip / purpose |
|---|---|---|---|
| 0:00 | `SFX_coldopen_impact_v1` | -8 | **C1a cold payoff** - the event already in motion; loudest transient in the first second, no music under it |
| 0:00.5 | `SFX_coldopen_tail_v1` | -14 | C1a - the decay of that event (debris, servo, water, fabric, line) |
| 0:01.5 | `BGM_bed_v1` **(entry)** | -18 | **C1b** - the comedy bed enters *on the hard cut to the goal diagram*, not at 0:00. The cold payoff plays against near-silence so it reads as an event rather than an intro |
| 0:01 | `SFX_body_bump_v1` | -14 | C1 - PIP being shoved aside |
| 0:01.5 | `SFX_cart_rattle_v1` (short) | -15 | C1 - cart parking at express register |
| 0:02.5 | `SFX_scanner_beep_v1` | -13 | C2 - item 1 scanned |
| 0:03 | `SFX_item_thunk_v1` | -15 | C2 - item placed aside |
| 0:03.5 | `SFX_scanner_beep_v1` | -13 | C2 - item 2 scanned |
| 0:04 | `SFX_item_thunk_v1` | -15 | C2 - item placed |
| 0:04.5 | `SFX_scanner_beep_v1` | -12 | C2 - item 3 scanned (slightly louder) |
| 0:05 | `SFX_button_v1` (dismissive) | -16 | C2 - smug glance at PIP |
| 0:07 | `SFX_scanner_beep_v1` | -12 | C3 - item 4 |
| 0:08 | `SFX_scanner_beep_v1` | -12 | C3 - item 5 |
| 0:09 | `SFX_scanner_beep_v1` | -11 | C3 - item 6 (louder) |
| 0:10 | `SFX_scanner_beep_v1` | -11 | C3 - item 7 (louder still) |
| 0:12 | `SFX_scanner_beep_v1` | -11 | C4 - item 8 |
| 0:13 | `SFX_scanner_beep_v1` | -10 | C4 - item 9 (building) |
| **0:14** | **`SFX_scanner_beep_warning_v1`** | **-10** | **C4 - item 10. Flat/off tone. The warning beep** |
| 0:14.5 | `SFX_screen_flash_v1` | -13 | C4 - screen flashes BRAND_YELLOW warning |
| **0:16** | **`SFX_wrong_buzz_v1`** | **-9** | **C5 - item 11 scanned. OVER LIMIT. The lockout** |
| **0:16.5** | **`SFX_barrier_drop_v1`** | **-8** | **C5 - barrier arm drops. Heavy mechanical CLUNK. Exposed by music cut** |
| 0:17 | `SFX_alarm_beacon_v1` | -22 | C5 - alarm beacon starts spinning |
| 0:22 | `SFX_scanner_beep_v1` | -14 | C6 - re-scan attempt |
| **0:22.5** | **`SFX_rescan_buzz_v1`** | **-10** | **C6 - first rejection again. Harsh** |
| 0:23.5 | `SFX_button_tap_dead_v1` | -14 | C6 - rapid button tapping (dead) |
| 0:24 | `SFX_button_tap_dead_v1` | -13 | C6 - more tapping (faster, still dead) |
| **0:25** | **`SFX_barrier_rattle_v1`** | **-10** | **C6 - pulling the barrier. Metallic rattle, holds firm** |
| **0:25.5** | **`SFX_barrier_rattle_v1`** | **-9** | **C6 - harder pull. Louder rattle. Still holds** |
| **0:27** | **footsteps (PIP, light, x3)** | **-14** | **C7 - PIP walks to right register** |
| **0:28** | **`SFX_clean_beep_v1`** | **-7 - the most satisfying sound in the video** | **C7 - ONE clean scan. Simple, cheerful, final** |
| 0:28.5 | `SFX_register_ding_v1` | -10 | C7 - register completion ding |
| 0:29 | `SFX_gate_slide_v1` | -12 | C7 - exit gate slides open smoothly |
| 0:29.5 | `SFX_scratch_v1` | -11 | C7 - reversal punctuation |
| 0:30 | `SFX_jaw_drop_v1` | -14 | C7 - CHIEF's jaw drops |
| 0:31 | `SFX_item_topple_v1` | -16 | C8 - one item falls off cart |
| 0:31.5 | `SFX_defeated_groan_v1` | -15 | C8 - CHIEF's defeated groan |
| **0:32** | `SFX_button_v1` (ding) | -12 | C8 - series button |

---

## 5. Loudness / delivery (platform-ready)
- Integrated target **~-14 LUFS**, true-peak **<=-1 dBTP**.
- **Duck BGM ~4-6 dB under VO** for VO lines; release fully into the silence.
- VO peaks ~-12 to -10 dBFS, ~3 dB above the ducked bed.
- **The silence owns the room.** The barrier drop and rejection buzz start at -8/-9 dB; the barrier rattle escalates to -9 dB. Leave room above so the C7 clean beep can top everything at -7 dB.
- **The protected sounds** are the **0:14 warning beep** (the flat-tone foreshadowing - if it sounds identical to the others, the audience misses the signal) and the **0:28 clean beep** (the payoff - one cheerful scan defeating the overloaded lane). Neither may be masked.
- **The loudest moments, in order:** the **0:28 clean beep** (-7) -> the barrier drop (-8) -> the lockout buzz (-9). The clean beep must feel like relief after the harsh mechanical lockdown.
- **Never compress the silence up.** 0:16-0:27 has no music; the buzzes and rattles should feel exposed and punishing against the dead quiet, not loud. Push the beacon click to -22 dB so the rejection sounds sit forward.
- Shorts are watched **muted by default** - verify one final time that the overloaded cart, "OVER LIMIT" screen, red barrier arm, and one clean scan tell the whole story with audio off.

---

## 6. Sourcing notes
- **All sources above are real, named, and royalty-free or CC0.** Verify availability before final mix.
- Freesound.org assets: search by ID number listed. All CC0 assets require no attribution; CC BY 3.0 assets require credit in video description.
- Mixkit assets: available at mixkit.co/free-sound-effects/ - search by name listed.
- ZapSplat assets: available at zapsplat.com - free tier with attribution in description.
- Pixabay Music tracks: available at pixabay.com/music/ - search by track name and artist.
- YouTube Audio Library tracks: available in YouTube Studio > Audio Library.
- Reuse from earlier episodes: `SFX_scratch_v1`, `SFX_button_v1` set (established v1).
- **Signature-sound principle:** v1 = the stamp - v2 = the booster - v3 = the block clack - v4 = the panel slam - v5 = the discovery sting - v6 = the sweet clatter - v7 = water (drip to splash) - v8 = the rejection buzz - v10 = the paper rip. **v11's signature sound is the barrier drop** - a heavy mechanical CLUNK that seals CHIEF's fate, contrasted with the impossibly light and cheerful single beep of PIP's one-item checkout. Excess defeated by minimalism.
