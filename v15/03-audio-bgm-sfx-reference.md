# v15 - BGM, SFX & Audio Reference ("The Last Dryer") - **SHORTS**

> The complete audio map for v15, synced to the master timeline in `01-video-script.md`. This file is
> **prescriptive, not advisory**: the cue sheet states which layers are playing during every time range,
> and the SFX hit list places every effect at its exact timecode and mix level.
> **Mute-first principle:** audio *amplifies*; it never *carries*. The video reads with sound off.

---

## 1. Asset list (with real sourcing)

### Music
| ID | Description | Real Source | Used |
|---|---|---|---|
| `MUS_laundro_bed_v1` | **Main bed.** A quirky, bouncy comedy cue -- pizzicato strings, bass clarinet staccato, light rim-click percussion, ~112 BPM, major key with playful chromatic runs. Slightly mechanical feel (evokes spinning machines) | **Pixabay Music - "Quirky Comedy" by Lexin_Music** (free license, no attribution required) | 0:00-0:16 |
| `MUS_laundro_stinger_v1` | **Eruption stinger** -- a dramatic ascending brass fanfare that immediately deflates into a descending trombone "wah-wah" slide, punctuated by a cymbal crash | **YouTube Audio Library - "Funny Comedy Accent"** (royalty-free, no attribution required) | 0:27 |
| `MUS_laundro_resolve_v1` | **Warm resolve tail** -- gentle pizzicato melody with soft glockenspiel chimes, a cozy satisfied cadence that mirrors the opening bed's key | **Pixabay Music - "Cute Funny" by Daddy_s_Music** (free license, no attribution required) | 0:29-0:32 |

> **Series continuity:** same instrumentation family as prior episodes (light percussion, plucky melody,
> no lyrics). The pizzicato-bass-clarinet mechanical color is a *variant* specific to this episode's
> laundromat setting (the rhythm evokes spinning drums).

### SFX (Real Sources)
| ID | Description | Real Source |
|---|---|---|
| `SFX_shove_impact_v1` | Body being shoved aside (comic impact, no pain) | **Freesound #268227 - "body_push.wav" by Merrick079 (CC0)** |
| `SFX_clothes_crumple_v1` | Fabric being crumpled/stuffed into a space | **Freesound #394825 - "cloth_grab_fast.wav" by Breviceps (CC0)** |
| `SFX_dryer_door_slam_v1` | Heavy metal dryer door slamming shut | **Freesound #344685 - "locker_slam_shut.wav" by SpliceSound (CC0)** |
| `SFX_coin_insert_v1` | Coin inserted into metal slot (clink + drop) | **Freesound #365083 - "coin_slot_insert.wav" by LittleRobotSoundFactory (CC BY 4.0)** |
| `SFX_dryer_tumble_v1` | Dryer drum tumbling sound -- muffled rhythmic thumps (loopable) | **Freesound #456308 - "washing_machine_loop.wav" by kyles (CC0)** - pitch shifted -2 semitones for dryer character |
| `SFX_dryer_rattle_v1` | Dryer vibrating/rattling against the floor (metallic, rhythmic) | **Freesound #370253 - "metal_rattle_vibration.wav" by LittleRobotSoundFactory (CC BY 4.0)** |
| `SFX_dryer_whine_v1` | High-pitched mechanical whine (overheating motor) | **Freesound #322469 - "electrical_buzz_loop.wav" by jacobalcook (CC0)** - pitch shifted +8 semitones |
| `SFX_door_pop_bang_v1` | Metal door popping open under pressure (a latch-break BANG) | **Freesound #351387 - "electric_spark.wav" by newlocknew (CC0)** layered with **Freesound #344685 - "locker_slam_shut.wav" by SpliceSound (CC0)** reversed |
| `SFX_fabric_launch_v1` | Fabric item launching through air (a soft fwip/whoosh) | **Freesound #398032 - "small_water_splash.wav" by Breviceps (CC0)** - time-stretched 50%, high-pass filtered for airy quality |
| `SFX_static_crackle_v1` | Static electricity crackling/popping | **Freesound #321025 - "static_crackle_pop.wav" by Robinhood76 (CC BY-NC 4.0)** |
| `SFX_fabric_stick_v1` | Fabric sticking to surface with static (soft thwap + crackle) | **ZapSplat - "Cloth Land on Surface Soft"** (standard license, free tier) |
| `SFX_dryer_walk_scrape_v1` | Heavy appliance scraping across floor (vibration-walking) | **Freesound #380610 - "metal_scrape_short.wav" by Samitarimi (CC0)** |
| `SFX_steam_hiss_v1` | Small gentle steam hiss (shirt on radiator) | **Freesound #399057 - "sizzle_hiss.wav" by EFlexMusic (CC0)** - volume -12 dB, low-pass filter for gentle quality |
| `SFX_chair_creak_v1` | Plastic chair creaking when sat upon | **Freesound #382271 - "creaky_door_open.wav" by dheming (CC BY 3.0)** - time-compressed, pitch +4 |
| `SFX_medal_jingle_v1` | Small metallic medal jingling | **Freesound #411088 - "small_bells_jingle.wav" by Breviceps (CC0)** |
| `SFX_fluorescent_hum_v1` | Overhead fluorescent light hum (continuous, low) | **Freesound #259753 - "electrical_hum_60hz.wav" by EFlexMusic (CC0)** - volume -28 dB |
| `SFX_fabric_peel_v1` | Fabric peeling off a warm surface (gentle separation) | **Mixkit - "Paper Peel Off"** (free license) |
| `SFX_fabric_fold_v1` | Soft fabric folding sound (precise, gentle) | **Freesound #394825 - "cloth_grab_fast.wav" by Breviceps (CC0)** - volume -8 dB, time-stretched 150% |
| `SFX_sock_fall_v1` | Single light fabric item falling and landing (plop) | **Freesound #350883 - "patting_sand.wav" by furbyguy (CC0)** - pitch -2 semitones |
| `SFX_scratch_v1` | Record-scratch (reused from series) | **Series asset (established v1)** |

---

## 2. EXACT CUE SHEET - what is playing, when

**Layer key:** `BGM` = music bed - `SFX` = effects - `VO` = narration - `AMB` = ambient (fluorescent hum + dryer tumble 0:02-0:16; fluorescent hum + rattling 0:16-0:27)

| # | Time range | Layer stack | BGM playing | AMB | Notes |
|---|---|---|---|---|---|
| 1 | **0:00-0:02** | **BGM + SFX + VO** | `MUS_laundro_bed_v1` (enters frame 1, ~-17 dB) | `SFX_fluorescent_hum_v1` at -28 dB | Shove + stuff + slam + coin. Comedy bed sets the quirky mechanical tone |
| 2 | **0:02-0:06** | **BGM + SFX + VO + AMB** | `MUS_laundro_bed_v1` (full, ~-14 dB, pizzicato lead) | fluorescent hum + `SFX_dryer_tumble_v1` enters at -20 dB (all 5 dryers running) | Tumble rhythm synced to bed tempo. Steam hiss from PIP's shirt on pipe |
| 3 | **0:06-0:11** | **BGM + SFX + VO + AMB** | `MUS_laundro_bed_v1` - **adds bass clarinet staccato synced to dryer #1's wobble rhythm** | tumble at -18 dB; dryer #1 rattle enters at -16 dB | The rattle becomes part of the music. Medal jingle punctuates |
| 4 | **0:11-0:16** | **BGM + SFX + AMB** *(VO ends ~0:14)* | `MUS_laundro_bed_v1` - **densest point** (pizzicato + bass clarinet + rim clicks + chromatic run) | all 5 dryers rattling at -14 dB; scrape from walking dryer | Bed at maximum density. The rattling is almost musical -- a wall of mechanical rhythm |
| 5 | **0:16** | **SFX + AMB only** - *music cuts on the door BANG* | **-- NONE from 0:16** | tumble dies to single dryer ticking down; rattle continues on #2-#5 at -16 dB | The bang is exposed by the music cut |
| 6 | **0:16-0:27** | **SFX + AMB only - MUSICAL SILENCE (11 s)** | **-- NONE** | rattling from remaining dryers (diminishing as each pops open) | Only rattles, bangs, fabric launches, static crackle, and CHIEF's muffled sounds |
| 7 | **0:27-0:29** | **BGM + SFX + VO + AMB** | `MUS_laundro_stinger_v1` (SLAM in on beat 1 of the aftermath reveal) | fluorescent hum returns to prominence at -24 dB (machines all stopped) | Brass fanfare + trombone deflate. Static crackling continuous under the stinger |
| 8 | **0:29-0:32** | **BGM + SFX + VO + AMB** | `MUS_laundro_resolve_v1` (warm pizzicato + glockenspiel) | fluorescent hum at -28 dB | Payoff + loop out. The fabric peel and fold sounds are featured |

**Visual summary of the music shape:**
```
0:00 -- BED (pizzicato bounce) -- +bass clarinet -- +rim clicks -- (densest) --+
0:16                                                                             | (cut on door BANG)
0:16                              --- SILENCE ---                                |
                                     (11 s)                                      |
0:27                                               +----- stinger (aftermath) ------+
0:29                                               |                                +-- resolve --> 0:32
```

---

## 3. The silence beat (0:16-0:27) - the single most important audio move

An **11-second musical silence**, cut **mid-phrase** on the frame dryer #1's door pops open.

**Only these sounds are permitted inside it:**

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16-0:27 | Remaining dryers rattling (diminishing) | **-16 dB** dropping to -20 dB as each pops open | The rattle of the remaining machines is the countdown -- each pop silences one dryer |
| 0:16 | `SFX_door_pop_bang_v1` | **-4 dB** | The first bang. Loudest sound in the video. Exposed fully by the music cut |
| 0:16.5 | `SFX_fabric_launch_v1` + `SFX_static_crackle_v1` | -10 dB | Single sock launching and sticking to face |
| 0:18 | `SFX_static_crackle_v1` (soft, continuous on CHIEF) | -18 dB | Residual static on the sock -- continuous crackle baseline |
| 0:20 | `SFX_fabric_peel_v1` (sock pulled off face) | -12 dB | The slow peel -- static resistance audible |
| 0:22 | `SFX_door_pop_bang_v1` (#2) | **-6 dB** | Second eruption -- bang + fabric launch |
| 0:22.5 | `SFX_fabric_launch_v1` (x3 items) + `SFX_fabric_stick_v1` (x2) | -10 dB | Shirts draping on CHIEF, sticking |
| 0:23.5 | `SFX_door_pop_bang_v1` (#3) | **-6 dB** | Third eruption |
| 0:24 | `SFX_fabric_launch_v1` (x2) + `SFX_fabric_stick_v1` (wall stick + cap land) | -10 dB | Pants flying, underwear on cap |
| 0:25 | `SFX_door_pop_bang_v1` (x2, #4 and #5 simultaneous) | **-4 dB** | Double bang -- the biggest eruption. Matches volume of the first bang |
| 0:25.5 | `SFX_fabric_launch_v1` (x10, rapid overlapping) + `SFX_static_crackle_v1` (intense) | -8 dB | The blizzard -- a wall of fabric and static sound |
| 0:26.5 | (silence -- 0.5 s of just the fluorescent hum + soft static pops) | -- | The aftermath moment. All dryers stopped. Only the hum and fading crackle |

- **No VO** in this window except an optional muffled *"...mmph!"* at ~0:23 (CHIEF's face covered), <=0.4 s.
- **No music, no stings.** The door bangs and fabric sounds must own the space.

> **The best sound in the silence is the 0.5 s at 0:26.5.** After the blizzard settles, just the
> fluorescent hum and soft static pops remain. The machines have all stopped. The air is still.
> That 0.5 s of aftermath silence is the setup for the stinger.

---

## 4. Mix notes

| Parameter | Value |
|---|---|
| Overall loudness target | -14 LUFS (YouTube Short standard) |
| BGM ducking under VO | -6 dB duck, 100 ms attack, 400 ms release |
| SFX priority during silence | door bangs > fabric launches > static crackle > ambient rattle |
| The door_pop_bang at 0:16 | must be the loudest single SFX hit in the entire video (exposed by music absence) |
| Dryer rattle behavior | starts at 0:02 (low), builds to 0:16 (all 5 at full), then diminishes as each dryer pops open (one fewer rattle per eruption) |
| VO style | dry, close-mic, deadpan, short phrases only. Never more than 6 words. American male neutral |
| Stereo width | SFX: 70% width (fabric items pan to match screen position). BGM: 80% width. VO: center mono. AMB: 100% width |
| Static crackle stereo | follows CHIEF's position -- when items stick to his left, crackle pans left |

---

## 5. VO cue list (optional layer - story reads without it)

| Time | Line | Duration | Style |
|---|---|---|---|
| 0:00 | `SFX_coldopen_impact_v1` | -8 | **C1a cold payoff** - the event already in motion; loudest transient in the first second, no music under it |
| 0:00.5 | `SFX_coldopen_tail_v1` | -14 | C1a - the decay of that event (debris, servo, water, fabric, line) |
| 0:01.5 | `BGM_bed_v1` **(entry)** | -18 | **C1b** - the comedy bed enters *on the hard cut to the goal diagram*, not at 0:00. The cold payoff plays against near-silence so it reads as an event rather than an intro |
| 0:02 | *"All five. Just because he could."* | 3.0 s | slightly amused, incredulous |
| 0:06 | *"Full load. Every one."* | 2.0 s | dry emphasis |
| 0:11 | *"Hotter. Fuller. Faster."* | 2.5 s | building rhythm (mock tension) |
| 0:16 | *"Uh-oh."* | 0.5 s | cut off abruptly with the music |
| 0:27 | *"One shirt. Nice and warm."* | 1.8 s | calm, warm, amused contrast |
| 0:31 | *"Every time."* | 1.0 s | series catchphrase, warm |
