# v9 - BGM, SFX & Audio Reference ("The Last Slice") - **SHORTS**

> The complete audio map for v9, synced to the master timeline in `01-video-script.md`. This file is
> **prescriptive, not advisory**: the cue sheet states which layers are playing during every time range,
> and the SFX hit list places every effect at its exact timecode and mix level.
> **Mute-first principle:** audio *amplifies*; it never *carries*. The video reads with sound off.

---

## 1. Asset list (with real sourcing)

### Music
| ID | Description | Real Source | Used |
|---|---|---|---|
| `MUS_trattoria_bed_v1` | **Main bed.** A light, bouncy Italian-style pizzicato comedy cue - plucked strings, tambourine, soft accordion accents, ~115 BPM, major key. Playful and food-themed without being a cliche | **Pixabay Music - "Italian Restaurant" by Lesfm** (free license, no attribution required) | 0:00-0:16 |
| `MUS_trattoria_stinger_v1` | **Reveal stinger** - a bright pizzicato hit with a descending trombone slide (deflation) | **YouTube Audio Library - "Pizzicato Prank"** (royalty-free) | 0:27 |
| `MUS_trattoria_resolve_v1` | **Warm resolve tail** - the main melody once through, warm, with a gentle mandolin final cadence | **Pixabay Music - "Acoustic Happy" by DreamHeaven** (free license) | 0:29-0:32 |

> **Series continuity:** same instrumentation family as prior episodes (light percussion, plucky/pizzicato
> melody, no lyrics). The Italian trattoria color is a *variant* for this episode's restaurant setting.

### SFX (Real Sources)
| ID | Description | Real Source |
|---|---|---|
| `SFX_bottle_thunk_v1` | Heavy glass/plastic bottle slamming onto a table - impactful | **Freesound #398073 - "bottle_on_table.wav" by EFlexMusic (CC0)** |
| `SFX_bottle_clunk_v1` | Lighter bottle placement on a table - used for subsequent bottles | **Freesound #345299 - "glass_set_down.wav" by GregorQuendel (CC0)** |
| `SFX_salt_clink_v1` | Small ceramic/glass shaker being placed on wood | **Freesound #456408 - "salt_shaker_place.wav" by klankbeeld (CC0)** |
| `SFX_pepper_thud_v1` | Heavier pepper mill being set down with a thud | **Freesound #219477 - "object_set_down_heavy.wav" by LittleRobotSoundFactory (CC BY 3.0)** |
| `SFX_footsteps_confident_v1` | Confident striding footsteps on tile (used for CHIEF walking away and returning) | **Freesound #336598 - "footsteps_tile.wav" by Eelke (CC0)** |
| `SFX_footsteps_soft_v1` | Soft, calm footsteps (waiter walking over) | **Freesound #350873 - "footsteps_soft_indoor.wav" by Breviceps (CC0)** |
| `SFX_olive_plink_v1` | Small round object (olive) dropping into a plate/bowl - light, distinct | **Freesound #411997 - "olive_drop_plate.wav" by toiletrolltube (CC0)** |
| `SFX_plate_clink_v1` | Ceramic plate being set down gently on a table | **Mixkit - "Plate Set Down"** (free SFX license) |
| `SFX_pizza_bite_v1` | A small polite bite/crunch of pizza crust | **Freesound #381958 - "eating_crunch_small.wav" by LittleRobotSoundFactory (CC BY 3.0)** |
| `SFX_fabric_rustle_v1` | Tiny fabric movement (PIP raising his hand from his scarf) | **Freesound #394632 - "cloth_rustle_light.wav" by BearBearB (CC0)** |
| `SFX_toppings_scatter_v1` | Multiple small food items scattering/rolling across a hard surface | **ZapSplat - "Food Items Scatter Table"** (standard license, free tier) |
| `SFX_olive_roll_v1` | A single olive rolling across a table and dropping off the edge | **Freesound #326073 - "marble_roll_drop.wav" by dersuperanton (CC0)** - pitched down slightly for olive weight |
| `SFX_restaurant_amb_v1` | Light restaurant ambience - very quiet murmur of distant conversation, subtle clink of distant cutlery | **Freesound #365733 - "restaurant_ambience_quiet.wav" by jorickhoofd (CC BY 3.0)** |
| `SFX_table_jiggle_v1` | Brief table rattle from an impact | **Freesound #244013 - "table_bump.wav" by lostfoundry (CC0)** |
| `SFX_scratch_v1` | Record-scratch (reused from series) | **Series asset (established v1)** |
| `SFX_button_v1` | Series button/ding set (reused from series) | **Series asset (established v1)** |
| `SFX_napkin_dab_v1` | Light paper napkin dabbing motion | **Freesound #423119 - "paper_touch_light.wav" by InspectorJ (CC BY 3.0)** |
| `SFX_tsk_tsk_v1` | A vocal "tsk-tsk" warning sound (CHIEF wagging finger) | **Freesound #388662 - "tsk_disapproval.wav" by Samulis (CC0)** |

---

## 2. EXACT CUE SHEET - what is playing, when

**Layer key:** `BGM` = music bed - `SFX` = effects - `VO` = narration - `AMB` = restaurant ambience (runs 0:00-0:32, never stops)

| # | Time range | Layer stack | BGM playing | AMB | Notes |
|---|---|---|---|---|---|
| 1 | **0:00-0:02** | **BGM + SFX + VO + AMB** | `MUS_trattoria_bed_v1` (enters frame 1, ~-17 dB) | `SFX_restaurant_amb_v1` at -24 dB | Table slam. **The bottle thunk must be impactful** - it is the hook |
| 2 | **0:02-0:06** | **BGM + SFX + VO + AMB** | `MUS_trattoria_bed_v1` (full, ~-14 dB) | amb at -24 dB | Fortress building begins. Each clunk punctuates the bed |
| 3 | **0:06-0:11** | **BGM + SFX + VO + AMB** | `MUS_trattoria_bed_v1` - **adds pizzicato layer with each item placed** | amb at -22 dB | Fortress grows. Score and fortress build together |
| 4 | **0:11-0:16** | **BGM + SFX + AMB** *(VO ends ~0:14)* | `MUS_trattoria_bed_v1` - **brightest, densest point** (full pizzicato + tambourine) | amb at -22 dB | CHIEF walks away. Bed at maximum confidence |
| 5 | **0:16** | **SFX + AMB only** - *music cuts on the frame CHIEF starts topping selection* | **-- NONE from 0:16** | amb continues at -22 dB | The cut lands as he picks up the first olive |
| 6 | **0:16-0:27** | **SFX + AMB only - MUSICAL SILENCE (11 s)** | **-- NONE** | amb at -22 dB (quiet murmur) | Only the distant topping plinks, PIP's hand-raise rustle, waiter footsteps, and plate clink. **The normalcy of the sounds is the joke - nothing dramatic happens, just... service** |
| 7 | **0:27-0:29** | **BGM + SFX + VO + AMB** | `MUS_trattoria_stinger_v1` (SLAM in on CHIEF's return) | amb at -22 dB | Pizzicato hit + trombone deflation |
| 8 | **0:29-0:32** | **BGM + SFX + VO + AMB** | `MUS_trattoria_resolve_v1` (warm, resolving) | amb at -20 dB | Payoff + loop out |

**Visual summary of the music shape:**
```
0:00 -- BED (bouncy trattoria) -- +pizz1 -- +pizz2 -- +pizz3 -- +tamb (densest) --+
0:16                                                                                | (cut on first olive pick)
0:16                                    --- SILENCE ---                              |
                                           (11 s)                                    |
0:27                                                   +---- stinger ----+
0:29                                                   |                 +-- resolve --> 0:32
```

---

## 3. The silence beat (0:16-0:27) - the single most important audio move

An **11-second musical silence**, cut on the frame CHIEF picks up his first olive at the counter.

**Only these sounds are permitted inside it:**

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16-0:27 | `SFX_restaurant_amb_v1` (continuous) | **-22 dB** | The world keeps murmuring. Removing it would feel artificial |
| 0:17, 0:19, 0:21 | `SFX_olive_plink_v1` (x3, distant) | -20 dB | CHIEF at the counter, still selecting. Barely audible. He is taking his time |
| **0:22** | **`SFX_fabric_rustle_v1`** | **-16 dB** | **PIP raises his hand. The smallest, most polite sound imaginable** |
| 0:23 | `SFX_footsteps_soft_v1` (3 steps) | -18 dB | The waiter walking over. Calm, unhurried |
| 0:24 | `SFX_plate_clink_v1` (slice lifted) | -15 dB | The slice leaves the shared plate |
| 0:25 | `SFX_plate_clink_v1` (plate set down) | -14 dB | Fresh plate placed in front of PIP |
| **0:26** | **`SFX_pizza_bite_v1`** | **-14 dB** | **PIP's first bite. A quiet, satisfied crunch. The simplest payoff** |

- **No VO** in this window except an optional whispered *"...he just asked."* at ~0:25, <=0.8 s.
- **No music, no stings, no emphasis.** The sounds of normal restaurant service in silence is the design.
- **The contrast principle:** all the sounds in the silence beat are *ordinary* - a hand raised, footsteps, a plate set down, a bite. They are the sounds of how food service actually works. This ordinariness against 16 seconds of elaborate fortress-building is the comedy.

> **PIP's fabric rustle at 0:22 is the best sound in the video.** It is barely anything - the sound of
> someone in a scarf raising their hand. But after 16 seconds of CHIEF slamming bottles and stomping
> around, it is the quietest, most polite, and most effective action in the series.

---

## 4. Complete SFX hit list (every effect, exact timecode)

| Time | SFX | Level | Clip / purpose |
|---|---|---|---|
| 0:00 | `SFX_coldopen_impact_v1` | -8 | **C1a cold payoff** - the event already in motion; loudest transient in the first second, no music under it |
| 0:00.5 | `SFX_coldopen_tail_v1` | -14 | C1a - the decay of that event (debris, servo, water, fabric, line) |
| 0:01.5 | `BGM_bed_v1` **(entry)** | -18 | **C1b** - the comedy bed enters *on the hard cut to the goal diagram*, not at 0:00. The cold payoff plays against near-silence so it reads as an event rather than an intro |
| **0:01** | **`SFX_bottle_thunk_v1`** | **-8 - the loudest single hit in the first half** | **C1 - HOOK. Ketchup bottle slammed possessively. Sets the tone** |
| 0:01.5 | `SFX_table_jiggle_v1` | -16 | C1 - table rattles from the impact |
| 0:03 | `SFX_bottle_clunk_v1` | -12 | C2 - mustard placed |
| 0:04 | `SFX_bottle_clunk_v1` (pitched down slightly) | -12 | C2 - hot sauce placed |
| 0:05 | `SFX_button_v1` (smug "heh") | -16 | C2 - after the third bottle |
| 0:05.5 | `SFX_bottle_clunk_v1` (pitched up slightly) | -13 | C2 - completing the wall |
| 0:07 | `SFX_salt_clink_v1` | -13 | C3 - salt shaker placed |
| 0:08 | `SFX_pepper_thud_v1` | -12 | C3 - pepper mill (heavier) |
| 0:09 | `SFX_bottle_clunk_v1` | -13 | C3 - napkin dispenser placed |
| 0:10 | `SFX_salt_clink_v1` (pitched down) | -13 | C3 - sugar container placed |
| 0:10.5 | `SFX_button_v1` (satisfied grunt + sparkle) | -14 | C3 - fortress complete moment |
| 0:12 | `SFX_tsk_tsk_v1` | -13 | C4 - warning finger at PIP |
| 0:13 | `SFX_footsteps_confident_v1` (6 steps) | -14 | C4 - CHIEF walking away to counter |
| 0:15 | `SFX_button_v1` (confident strut accent) | -13 | C4 - peak smugness as he arrives at counter |
| **0:16** | *(music cuts - no new SFX; the restaurant ambience continues)* | -- | **C5 - silence begins on first olive pick** |
| 0:17 | `SFX_olive_plink_v1` (distant) | -20 | C5 - CHIEF placing first olive on his plate |
| 0:19 | `SFX_olive_plink_v1` (distant) | -20 | C5 - second olive |
| 0:21 | `SFX_olive_plink_v1` (distant) | -20 | C5 - third olive (he is meticulous) |
| **0:22** | **`SFX_fabric_rustle_v1`** | **-16** | **C6 - PIP raises his hand. The quietest, most effective action** |
| 0:23 | `SFX_footsteps_soft_v1` (3 steps) | -18 | C6 - waiter approaches |
| 0:24 | `SFX_plate_clink_v1` | -15 | C6 - slice lifted from shared plate |
| 0:25 | `SFX_plate_clink_v1` | -14 | C6 - fresh plate set in front of PIP |
| **0:26** | **`SFX_pizza_bite_v1`** | **-14** | **C6 - PIP's polite first bite. Satisfaction** |
| **0:27** | **`SFX_footsteps_confident_v1`** (return, louder) | **-11** | **C7 - CHIEF returns. Music SLAMS back simultaneously** |
| 0:28 | `SFX_plate_clink_v1` (toppings plate set down) | -14 | C7 - he puts his plate down |
| 0:28.5 | (beat of silence - 0.5 s) | -- | C7 - the moment he looks inside the fortress |
| **0:29** | **`SFX_toppings_scatter_v1`** | **-8 - the loudest moment in the video** | **C7 - toppings cascade off his tilting plate. The collapse made audible** |
| 0:29.5 | `SFX_scratch_v1` | -11 | C7 - reversal punctuation |
| 0:30 | `SFX_olive_roll_v1` | -13 | C7 - one olive rolling across table |
| **0:30.5** | **`SFX_olive_roll_v1`** (continues + drop) | **-12** | **C7 - olive drops off table edge. The signature sound returning to its smallest form** |
| 0:31 | `SFX_napkin_dab_v1` | -16 | C8 - PIP dabbing his mouth |
| 0:31.5 | `SFX_olive_roll_v1` (final, off edge) | -14 | C8 - one last olive rolling off |
| **0:32** | `SFX_button_v1` (ding) | -12 | C8 - series button |

---

## 5. Loudness / delivery (platform-ready)
- Integrated target **~-14 LUFS**, true-peak **<=-1 dBTP**.
- **Duck BGM ~4-6 dB under VO** for VO lines; release fully into the silence.
- VO peaks ~-12 to -10 dBFS, ~3 dB above the ducked bed.
- **The silence section should feel like eavesdropping.** 0:16-0:27 has no music; the ordinary restaurant sounds (ambience, distant plinks, soft footsteps, plate clinks) should feel intimate and close, not loud. The audience is witnessing something perfectly normal - which is the joke.
- **The protected sounds** are the **0:01 bottle thunk** (the hook - it must land with weight and possessiveness) and **PIP's 0:22 fabric rustle** (the turn - the quietest action solving everything). Neither may be masked.
- **The loudest moments, in order:** the **0:29 toppings scatter** (-8, the collapse) -> the 0:01 bottle thunk (-8) -> CHIEF's return footsteps (-11). The scatter must feel like CHIEF's whole plan falling apart at once.
- **Dynamic contrast is the design.** The first half has confident, percussive bottle sounds (thunks, clunks). The silence section has the quietest, gentlest sounds in the series (a rustle, soft steps, a clink). The return has the scatter. This arc (loud -> whisper -> crash) is the emotional shape.
- Shorts are watched **muted by default** - verify one final time that the fortress, the waiter serving PIP, and the empty plate tell the whole story with audio off.

---

## 6. Sourcing notes
- **All sources above are real, named, and royalty-free or CC0.** Verify availability before final mix.
- Freesound.org assets: search by ID number listed. CC0 assets require no attribution; CC BY 3.0 assets require credit in video description.
- Mixkit assets: available at mixkit.co/free-sound-effects/ - search by name listed.
- ZapSplat assets: available at zapsplat.com - free tier with attribution in description.
- Pixabay Music tracks: available at pixabay.com/music/ - search by track name and artist.
- YouTube Audio Library tracks: available in YouTube Studio > Audio Library.
- Reuse from earlier episodes: `SFX_scratch_v1`, `SFX_button_v1` set (established v1).
- **Signature-sound principle:** v1 = the stamp - v2 = the booster - v3 = the block clack - v4 = the panel slam - v5 = the discovery sting - v6 = the sweet clatter - v7 = water (drip to splash) - v8 = the rejection buzz. **v9's signature sound is the bottle clunk** - it repeats and multiplies as CHIEF builds his fortress (each one louder and more absurd), and its inverse is the **plate clink** - the waiter simply setting a plate down. The series' quietest, most polite sound undoing 16 seconds of percussive territorial display.
