# v8 - BGM, SFX & Audio Reference ("The Smart Lock") - **SHORTS**

> The complete audio map for v8, synced to the master timeline in `01-video-script.md`. This file is
> **prescriptive, not advisory**: the cue sheet states which layers are playing during every time range,
> and the SFX hit list places every effect at its exact timecode and mix level.
> **Mute-first principle:** audio *amplifies*; it never *carries*. The video reads with sound off.

---

## 1. Asset list (with real sourcing)

### Music
| ID | Description | Real Source | Used |
|---|---|---|---|
| `MUS_tech_bed_v1` | **Main bed.** A bouncy, playful electronic/chiptune-inspired comedy cue - synth plucks, light 8-bit arpeggios, snappy percussion, ~120 BPM, major key. Builds density as CHIEF adds more features | **Pixabay Music - "Funny Chiptune" by Alexiaction** (free license, no attribution required) | 0:00-0:16 |
| `MUS_tech_stinger_v1` | **Reveal stinger** - a bright synth hit that resolves into a warm analog key-turn sound | **YouTube Audio Library - "Comedy Accent 01"** (royalty-free) | 0:27 |
| `MUS_tech_resolve_v1` | **Warm resolve tail** - the main melody once through, slowed down, warm major synth pad, gentle final cadence | **Pixabay Music - "Happy Day" by FASSounds** (free license) | 0:29-0:32 |

> **Series continuity:** same instrumentation family as prior episodes (light percussion, plucky melody,
> no lyrics). The tech/chiptune color is a *variant* for this episode's gadget theme.

### SFX (Real Sources)
| ID | Description | Real Source |
|---|---|---|
| `SFX_van_door_v1` | Delivery van sliding door slam | **Freesound #456951 - "van_door_close.wav" by InspectorJ (CC0)** |
| `SFX_key_clink_v1` | Small metallic key being handed over - a light brass clink | **Freesound #183024 - "keys_clink.wav" by Samulis (CC0)** |
| `SFX_power_up_v1` | Tech device powering on - a rising electronic chime | **Freesound #341695 - "power_on_chime.wav" by EminYILDIRIM (CC BY 3.0)** |
| `SFX_scan_bleep_v1` | Digital face-scanning bleep (two-tone) | **Freesound #504847 - "scanner_beep.wav" by colorsCrimsonTears (CC0)** |
| `SFX_green_ding_v1` | Positive confirmation ding - bright, short | **Mixkit - "Correct Answer Tone"** (free SFX license) |
| `SFX_feature_bloop_v1` | Digital UI bloop for adding a feature (used x4, ascending pitch each time) | **Freesound #341247 - "ui_click_digital.wav" by EminYILDIRIM (CC0)** - pitch-shifted +2, +4, +6, +8 semitones |
| `SFX_lock_hum_v1` | Low ambient electronic hum of the smart lock idling | **Freesound #171510 - "electronics_hum_loop.wav" by Eelke (CC0)** |
| `SFX_gate_beep_green_v1` | Gate opening beep - cheerful two-note (used x2 in C4, x0 in C6) | **Mixkit - "Achievement Bell"** (free SFX license) |
| `SFX_chomp_v1` | Big exaggerated bite into soft food | **Freesound #389939 - "eating_bite_big.wav" by TheBuilder15 (CC0)** |
| `SFX_splat_v1` | Icing/cream splatting across a surface | **ZapSplat - "Cartoon Splat Cream Pie"** (standard license, free tier) |
| `SFX_rejection_buzz_v1` | Negative buzzer - harsh short electronic rejection (used x3, increasing volume) | **Freesound #331381 - "error_buzz.wav" by Breviceps (CC0)** |
| `SFX_wipe_smear_v1` | Glove wiping against a messy surface | **Freesound #434610 - "cloth_wipe.wav" by BearBearB (CC0)** |
| `SFX_key_insert_v1` | Key sliding into a manual lock - metallic, precise | **Freesound #178477 - "key_in_lock.wav" by cedarstroke (CC0)** |
| `SFX_lock_click_v1` | Mechanical lock clicking open - satisfying, analog | **Freesound #104952 - "lock_open_click.wav" by Ekokubza123 (CC0)** |
| `SFX_gate_creak_v1` | Metal gate creaking open slowly | **Freesound #370244 - "metal_gate_open.wav" by InspectorJ (CC BY 3.0)** |
| `SFX_jaw_drop_v1` | Cartoon jaw-drop sound (descending slide) | **ZapSplat - "Cartoon Jaw Drop Slide Down"** (standard license, free tier) |
| `SFX_icing_drip_v1` | A single thick drop of icing hitting the ground | **Freesound #398032 - "single_drip_thick.wav" by EFlexMusic (CC0)** |
| `SFX_scratch_v1` | Record-scratch (reused from series) | **Series asset (established v1)** |
| `SFX_button_v1` | Series button/ding set (reused from series) | **Series asset (established v1)** |
| `SFX_shuffle_step_v1` | Defeated shuffling footstep | **Freesound #221616 - "footstep_shuffle.wav" by Breviceps (CC0)** |

---

## 2. EXACT CUE SHEET - what is playing, when

**Layer key:** `BGM` = music bed - `SFX` = effects - `VO` = narration - `AMB` = ambient (lock hum, runs 0:02-0:32)

| # | Time range | Layer stack | BGM playing | AMB | Notes |
|---|---|---|---|---|---|
| 1 | **0:00-0:02** | **BGM + SFX + VO + AMB** | `MUS_tech_bed_v1` (enters frame 1, ~-17 dB) | -- (lock not yet installed) | Delivery moment. **The key clink must be audible** - it is the seed |
| 2 | **0:02-0:06** | **BGM + SFX + VO + AMB** | `MUS_tech_bed_v1` (full, ~-14 dB) | `SFX_lock_hum_v1` enters at -22 dB | Lock installation + first scan success |
| 3 | **0:06-0:11** | **BGM + SFX + VO + AMB** | `MUS_tech_bed_v1` - **adds arpeggiated layer with each feature** | hum at -20 dB | Each bloop adds a music layer - score and lock "grow" together |
| 4 | **0:11-0:16** | **BGM + SFX + AMB** *(VO ends ~0:14)* | `MUS_tech_bed_v1` - **brightest, densest point** (all layers) | hum at -18 dB | Gate demos. Bed at maximum energy |
| 5 | **0:16** | **SFX + AMB only** - *music cuts mid-phrase on the bite* | **-- NONE from 0:16** | hum continues at -20 dB | The cut lands on the frame of the bite |
| 6 | **0:16-0:27** | **SFX + AMB only - MUSICAL SILENCE (11 s)** | **-- NONE** | hum at -20 dB (the only continuous sound) | Only the lock hum, the chomp/splat, and the rejection buzzes. **The silence makes the buzzes devastating** |
| 7 | **0:27-0:29** | **BGM + SFX + VO + AMB** | `MUS_tech_stinger_v1` (SLAM in on key reveal) | hum at -20 dB | Bright synth hit + key-turn warmth |
| 8 | **0:29-0:32** | **BGM + SFX + VO + AMB** | `MUS_tech_resolve_v1` (warm, resolving) | hum fading out | Payoff + loop out |

**Visual summary of the music shape:**
```
0:00 -- BED (bouncy chiptune) -- +arp1 -- +arp2 -- +arp3 -- +arp4 (densest) --+
0:16                                                                            | (cut mid-phrase on bite)
0:16                                 --- SILENCE ---                            |
                                        (11 s)                                  |
0:27                                                +----- stinger -----+
0:29                                                |                   +-- resolve --> 0:32
```

---

## 3. The silence beat (0:16-0:27) - the single most important audio move

An **11-second musical silence**, cut **mid-phrase** on the frame CHIEF bites the cake.

**Only these sounds are permitted inside it:**

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16-0:27 | `SFX_lock_hum_v1` (continuous) | **-20 dB** | The device is still alive, still judging. An indifferent machine |
| 0:16 | `SFX_chomp_v1` | -10 dB | The bite that starts the disaster. Exposed by the music cut |
| 0:16.5 | `SFX_splat_v1` | -11 dB | Icing smearing across his face |
| 0:22 | `SFX_scan_bleep_v1` | -14 dB | First scan attempt |
| 0:22.5 | `SFX_rejection_buzz_v1` | **-12 dB** | First RED X - the shock |
| 0:23.5 | `SFX_wipe_smear_v1` | -16 dB | Frantic wiping |
| 0:24 | `SFX_scan_bleep_v1` | -14 dB | Second scan attempt |
| 0:24.5 | `SFX_rejection_buzz_v1` | **-10 dB** | Second RED X - louder, worse |
| 0:25.5 | `SFX_wipe_smear_v1` | -15 dB | More frantic wiping |
| 0:26 | `SFX_scan_bleep_v1` | -14 dB | Third scan attempt |
| 0:26.5 | `SFX_rejection_buzz_v1` | **-8 dB** | Third RED X - **the loudest rejection, the death knell** |

- **No VO** in this window except an optional whispered *"...it didn't recognize him."* at ~0:26, <=0.8 s.
- **No music, no stings.** The rejection buzzes escalating in volume against dead silence is the design.
- **The contrast principle:** digital rejections (harsh, electronic) in silence vs. the warm mechanical click in C7. The *analog* key defeating the *digital* fortress.

---

## 4. Complete SFX hit list (every effect, exact timecode)

| Time | SFX | Level | Clip / purpose |
|---|---|---|---|
| 0:00 | `SFX_coldopen_impact_v1` | -8 | **C1a cold payoff** - the event already in motion; loudest transient in the first second, no music under it |
| 0:00.5 | `SFX_coldopen_tail_v1` | -14 | C1a - the decay of that event (debris, servo, water, fabric, line) |
| 0:01.5 | `BGM_bed_v1` **(entry)** | -18 | **C1b** - the comedy bed enters *on the hard cut to the goal diagram*, not at 0:00. The cold payoff plays against near-silence so it reads as an event rather than an intro |
| **0:01** | **`SFX_key_clink_v1`** | **-13** | **C1 - SEED A. The backup key handed to PIP. Must be audible** |
| 0:01.5 | `SFX_button_v1` (eager grab) | -16 | C1 - CHIEF snatching the box |
| 0:02.5 | sparks SFX (brief drill) | -15 | C2 - bolting the lock on |
| 0:03 | `SFX_power_up_v1` | -12 | C2 - lock powering on for the first time |
| 0:04 | `SFX_scan_bleep_v1` | -14 | C2 - face scan |
| 0:04.5 | `SFX_green_ding_v1` | **-10** | C2 - GREEN checkmark. Bright and satisfying (for now) |
| 0:05 | `SFX_button_v1` (dismissive "heh") | -16 | C2 - finger wag at PIP |
| 0:07 | `SFX_feature_bloop_v1` (pitch +2) | -14 | C3 - first feature added |
| 0:08 | `SFX_feature_bloop_v1` (pitch +4) | -14 | C3 - second feature added |
| 0:09 | `SFX_feature_bloop_v1` (pitch +6) | -13 | C3 - third feature added |
| 0:10 | `SFX_feature_bloop_v1` (pitch +8) | -12 | C3 - fourth feature added. Each louder and higher = more overreach |
| 0:11.5 | `SFX_gate_beep_green_v1` | -12 | C4 - first gate pass |
| 0:13 | `SFX_button_v1` (celebratory arm raise) | -15 | C4 - victory gesture |
| 0:14 | `SFX_gate_beep_green_v1` | -12 | C4 - second gate pass |
| 0:15 | `SFX_button_v1` (strut fanfare) | -12 | C4 - peak smugness |
| **0:16** | **`SFX_chomp_v1`** | **-10** | **C5 - the bite. Exposed by music cut. The beginning of the end** |
| **0:16.5** | **`SFX_splat_v1`** | **-11** | **C5 - icing smear. The trap is sprung on himself** |
| 0:22 | `SFX_scan_bleep_v1` | -14 | C6 - first scan attempt |
| **0:22.5** | **`SFX_rejection_buzz_v1`** | **-12** | **C6 - first RED X** |
| 0:23.5 | `SFX_wipe_smear_v1` | -16 | C6 - wiping attempt |
| 0:24 | `SFX_scan_bleep_v1` | -14 | C6 - second scan attempt |
| **0:24.5** | **`SFX_rejection_buzz_v1`** | **-10** | **C6 - second RED X (louder)** |
| 0:25.5 | `SFX_wipe_smear_v1` | -15 | C6 - more frantic wiping |
| 0:26 | `SFX_scan_bleep_v1` | -14 | C6 - third scan attempt |
| **0:26.5** | **`SFX_rejection_buzz_v1`** | **-8** | **C6 - third RED X (loudest - the death knell)** |
| **0:27.5** | **`SFX_key_insert_v1`** | **-9** | **C7 - the brass key slides in. Analog warmth vs. digital failure** |
| **0:28** | **`SFX_lock_click_v1`** | **-7 - the most satisfying sound in the video** | **C7 - the manual lock opens. Simple, mechanical, final** |
| 0:28.5 | `SFX_gate_creak_v1` | -12 | C7 - gate swinging open |
| 0:29 | `SFX_scratch_v1` | -11 | C7 - reversal punctuation |
| 0:29.5 | `SFX_jaw_drop_v1` | -14 | C7 - CHIEF's jaw hits the floor |
| 0:30.5 | `SFX_icing_drip_v1` | -15 | C7 - one drip of icing off his face |
| 0:31 | `SFX_shuffle_step_v1` | -16 | C8 - CHIEF shuffling through |
| **0:31.5** | **`SFX_icing_drip_v1`** | **-15** | **C8 - one last drip off his nose. Returns to the splat motif at its smallest** |
| **0:32** | `SFX_button_v1` (ding) | -12 | C8 - series button |

---

## 5. Loudness / delivery (platform-ready)
- Integrated target **~-14 LUFS**, true-peak **<=-1 dBTP**.
- **Duck BGM ~4-6 dB under VO** for VO lines; release fully into the silence.
- VO peaks ~-12 to -10 dBFS, ~3 dB above the ducked bed.
- **The rejection buzzes own the silence.** They escalate from -12 to -8 dB across three attempts. Leave room above the third buzz so the C7 lock-click can top it at -7 dB.
- **The protected sounds** are the **0:01 key clink** (the seed - if it is inaudible, the fair-play contract breaks) and the **0:28 mechanical lock click** (the payoff - analog simplicity defeating digital complexity). Neither may be masked.
- **The loudest moments, in order:** the **0:28 lock click** (-7) -> the third rejection buzz (-8) -> the chomp (-10). The lock click must feel like relief after the escalating buzzers.
- **Never compress the silence up.** 0:16-0:27 has no music; the rejection buzzes should feel exposed and punishing against the dead quiet, not loud. Push the lock hum to -20 dB so the buzzes sit forward.
- Shorts are watched **muted by default** - verify one final time that the icing on face + RED X icons tell the whole story with audio off.

---

## 6. Sourcing notes
- **All sources above are real, named, and royalty-free or CC0.** Verify availability before final mix.
- Freesound.org assets: search by ID number listed. All CC0 assets require no attribution; CC BY 3.0 assets require credit in video description.
- Mixkit assets: available at mixkit.co/free-sound-effects/ - search by name listed.
- ZapSplat assets: available at zapsplat.com - free tier with attribution in description.
- Pixabay Music tracks: available at pixabay.com/music/ - search by track name and artist.
- YouTube Audio Library tracks: available in YouTube Studio > Audio Library.
- Reuse from earlier episodes: `SFX_scratch_v1`, `SFX_button_v1` set (established v1).
- **Signature-sound principle:** v1 = the stamp - v2 = the booster - v3 = the block clack - v4 = the panel slam - v5 = the discovery sting - v6 = the sweet clatter - v7 = water (drip to splash). **v8's signature sound is the rejection buzz** - it escalates through three increasingly harsh repetitions during the silence beat, and its *opposite* (the warm mechanical click of an analog key) is the payoff. Digital complexity defeated by analog simplicity.
