# v12 - BGM, SFX & Audio Reference ("The Express Elevator") - **SHORTS**

> The complete audio map for v12, synced to the master timeline in `01-video-script.md`. This file is
> **prescriptive, not advisory**: the cue sheet states which layers are playing during every time range,
> and the SFX hit list places every effect at its exact timecode and mix level.
> **Mute-first principle:** audio *amplifies*; it never *carries*. The video reads with sound off.

---

## 1. Asset list (with real sourcing)

### Music
| ID | Description | Real Source | Used |
|---|---|---|---|
| `MUS_elevator_bed_v1` | **Main bed.** A bouncy, slightly jazzy elevator-muzak comedy cue -- muted trumpet, plucky upright bass, light finger-snap percussion, ~110 BPM, major key. Builds in density as the button-pressing intensifies | **Pixabay Music - "Jazz Comedy" by Music_For_Videos** (free license, no attribution required) | 0:00-0:16 |
| `MUS_elevator_stinger_v1` | **Reveal stinger** -- a bright ascending brass hit resolving into a warm "ta-da" tone, undercut by a comedic descending trombone slide | **YouTube Audio Library - "Comedy Sting 1"** (royalty-free, no attribution required) | 0:27 |
| `MUS_elevator_resolve_v1` | **Warm resolve tail** -- gentle major-key vibraphone with soft upright bass, a satisfied final cadence that mirrors the muzak from the opening | **Pixabay Music - "Happy Vibes" by AlexiAction** (free license, no attribution required) | 0:29-0:32 |

> **Series continuity:** same instrumentation family as prior episodes (light percussion, plucky melody,
> no lyrics). The jazzy elevator-muzak color is a *variant* specific to this episode's setting.

### SFX (Real Sources)
| ID | Description | Real Source |
|---|---|---|
| `SFX_elevator_ding_v1` | Classic elevator arrival ding | **Freesound #423090 - "Elevator Ding" by JarredGibb (CC0)** |
| `SFX_shove_impact_v1` | Body being shoved/bumped aside - soft comic impact | **Freesound #268227 - "body_push.wav" by Merrick079 (CC0)** |
| `SFX_button_click_v1` | Single plastic button click (elevator panel) | **Freesound #446100 - "button_click_plastic.wav" by EminYILDIRIM (CC0)** |
| `SFX_doors_slide_v1` | Elevator doors sliding open/closed smoothly | **Freesound #185804 - "elevator_doors.wav" by dheming (CC BY 3.0)** |
| `SFX_door_creak_wood_v1` | Stairwell door opening (wooden creak) | **Freesound #382271 - "creaky_door_open.wav" by dheming (CC BY 3.0)** |
| `SFX_motor_hum_v1` | Elevator motor hum (loopable, steady pitch) | **Freesound #377851 - "elevator_motor_hum_loop.wav" by InspectorJ (CC BY 4.0)** |
| `SFX_medal_jingle_v1` | Small metallic medal/badge jingling | **Freesound #411088 - "small_bells_jingle.wav" by Breviceps (CC0)** |
| `SFX_electrical_buzz_v1` | Faint electrical buzzing/arcing (building, ominous) | **Freesound #322469 - "electrical_buzz_loop.wav" by jacobalcook (CC0)** |
| `SFX_smoke_hiss_v1` | Thin wispy smoke/sizzle sound | **Freesound #399057 - "sizzle_hiss.wav" by EFlexMusic (CC0)** |
| `SFX_spark_crack_v1` | Bright electrical spark/crack (the failure moment) | **Freesound #351387 - "electric_spark.wav" by newlocknew (CC0)** |
| `SFX_light_flicker_v1` | Fluorescent lights flickering and dying | **Freesound #371205 - "light_flicker_buzz_die.wav" by thatjeffcarter (CC BY 3.0)** |
| `SFX_mechanical_groan_v1` | Heavy mechanical groan (elevator stopping/straining) | **Freesound #367697 - "metal_stress_groan.wav" by rombart (CC0)** |
| `SFX_emergency_hum_v1` | Emergency light electrical hum (low, continuous) | **Freesound #259753 - "electrical_hum_60hz.wav" by EFlexMusic (CC0)** |
| `SFX_dead_click_v1` | Button pressed with no electronic response (dead click) | **Freesound #446100 - "button_click_plastic.wav" by EminYILDIRIM (CC0)** - EQ'd to remove high-end (sounds "dead") |
| `SFX_door_pry_scrape_v1` | Fingers scraping/prying at metal door seam | **Freesound #380610 - "metal_scrape_short.wav" by Samitarimi (CC0)** |
| `SFX_door_snap_v1` | Elevator doors snapping shut quickly | **Freesound #185804 - "elevator_doors.wav" by dheming (CC BY 3.0)** - reversed + speed 150% |
| `SFX_cable_creak_v1` | Metal cable creaking under weight/strain | **Freesound #370125 - "rope_creak_tension.wav" by InspectorJ (CC BY 4.0)** |
| `SFX_elevator_sway_v1` | Heavy box swaying on cable (low metallic thud + wobble) | **ZapSplat - "Metal Object Sway Creak"** (standard license, free tier) |
| `SFX_door_creak_slow_v1` | Elevator doors creaking open painfully slowly (long, strained) | **Freesound #456789 - "heavy_metal_door_creak_slow.wav" by Breviceps (CC0)** |
| `SFX_water_sip_v1` | Calm sip of water from a cup | **Freesound #389948 - "drinking_water_sip.wav" by Breviceps (CC0)** |
| `SFX_spark_small_v1` | Tiny residual spark pop (panel dying) | **Freesound #351387 - "electric_spark.wav" by newlocknew (CC0)** - volume -12 dB, pitch +4 semitones |
| `SFX_scratch_v1` | Record-scratch (reused from series) | **Series asset (established v1)** |
| `SFX_button_v1` | Series button/ding set (reused from series) | **Series asset (established v1)** |

---

## 2. EXACT CUE SHEET - what is playing, when

**Layer key:** `BGM` = music bed - `SFX` = effects - `VO` = narration - `AMB` = ambient (elevator motor hum 0:02-0:16; emergency hum + blink 0:17-0:27)

| # | Time range | Layer stack | BGM playing | AMB | Notes |
|---|---|---|---|---|---|
| 1 | **0:00-0:02** | **BGM + SFX + VO** | `MUS_elevator_bed_v1` (enters frame 1, ~-17 dB) | -- (lobby, no hum yet) | Ding + shove + button clicks. **The stairwell door creak in C2 must be audible** - it is the seed |
| 2 | **0:02-0:06** | **BGM + SFX + VO + AMB** | `MUS_elevator_bed_v1` (full, ~-14 dB) | `SFX_motor_hum_v1` enters at -22 dB | Stairwell creak + elevator starts moving. Split between exterior and interior |
| 3 | **0:06-0:11** | **BGM + SFX + VO + AMB** | `MUS_elevator_bed_v1` - **adds finger-snap percussion synced to CHIEF's clicking rhythm** | motor hum at -20 dB (steady) | Rhythmic clicking becomes part of the music. **The music and the clicking merge** -- comic sync |
| 4 | **0:11-0:16** | **BGM + SFX + AMB** *(VO ends ~0:14)* | `MUS_elevator_bed_v1` - **brightest, densest point** (trumpet + bass + snaps + xylophone run) | motor hum at -18 dB, straining pitch | Escalating slams. Electrical buzz enters underneath. Bed at maximum energy |
| 5 | **0:16** | **SFX + AMB only** - *music cuts mid-phrase on the SPARK* | **-- NONE from 0:16** | motor hum dies; `SFX_emergency_hum_v1` begins at -24 dB | The cut lands on the spark frame |
| 6 | **0:16-0:27** | **SFX + AMB only - MUSICAL SILENCE (11 s)** | **-- NONE** | emergency hum at -24 dB (low, continuous) | Only the emergency hum, the dead clicks, the scrapes, the cable creak. **The silence makes every failed attempt feel desperate** |
| 7 | **0:27-0:29** | **BGM + SFX + VO + AMB** | `MUS_elevator_stinger_v1` (SLAM in on the lurch) | motor hum returns faintly | Bright brass hit + the long slow door creak begins |
| 8 | **0:29-0:32** | **BGM + SFX + VO + AMB** | `MUS_elevator_resolve_v1` (warm vibraphone, resolving) | motor hum fading to silence | Payoff + loop out. The water sip is audible and calm |

**Visual summary of the music shape:**
```
0:00 -- BED (jazzy muzak) -- +snaps -- +trumpet -- (densest) --+
0:16                                                            | (cut mid-phrase on SPARK)
0:16                         --- SILENCE ---                    |
                                (11 s)                          |
0:27                                          +----- stinger -----+
0:29                                          |                   +-- resolve --> 0:32
```

---

## 3. The silence beat (0:16-0:27) - the single most important audio move

An **11-second musical silence**, cut **mid-phrase** on the frame the spark fires and the elevator dies.

**Only these sounds are permitted inside it:**

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16-0:27 | `SFX_emergency_hum_v1` (continuous, low) | **-24 dB** | The emergency light's hum. The machine is dead but present. A flat, indifferent electrical tone |
| 0:16 | `SFX_spark_crack_v1` | **-6 dB** | The failure. Exposed fully by the music cut -- loudest sound in the silence |
| 0:16.5 | `SFX_light_flicker_v1` | -12 dB | Lights dying -- the audible confirmation of the electrical death |
| 0:17 | `SFX_mechanical_groan_v1` | -10 dB | The elevator stopping -- heavy, final, metallic |
| 0:22-0:23 | `SFX_dead_click_v1` (x8, rapid) | -14 dB | Jabbing every button -- the dead hollow clicks are worse than silence |
| 0:23.5 | `SFX_door_pry_scrape_v1` | -12 dB | Prying at the doors -- metal on metal |
| 0:24 | `SFX_door_snap_v1` | -10 dB | Doors snapping shut on his fingers |
| 0:25 | `SFX_cable_creak_v1` | **-9 dB** | The jump -- cable straining. The ominous sound of real weight on a mechanism |
| 0:25.5 | `SFX_elevator_sway_v1` | -11 dB | The box swaying after the jump -- a low thud and wobble. Then nothing |
| 0:26.5 | (silence -- 0.5 s of nothing but the hum) | -- | The moment of total defeat before the lurch |

- **No VO** in this window except an optional whispered *"...stuck."* at ~0:22, <=0.5 s.
- **No music, no stings.** The dead clicks and cable creak must own the space.

> **The best sound in the silence is the 0.5 s of nothing at 0:26.5.** After the jump fails and the sway
> dies, there is a half-second where CHIEF has run out of ideas and only the emergency hum remains.
> That emptiness is the punchline of the silence -- the moment he accepts it. Mix it clean.

---

## 4. Complete SFX hit list (every effect, exact timecode)

| Time | SFX | Level | Clip / purpose |
|---|---|---|---|
| 0:00 | `SFX_elevator_ding_v1` | **-10** | C1 - elevator arriving. The opening sound that sets the location |
| 0:00.5 | `SFX_doors_slide_v1` | -12 | C1 - doors opening smoothly |
| 0:01 | `SFX_shove_impact_v1` | -12 | C1 - CHIEF shoving PIP aside (soft, comic) |
| 0:01.5 | `SFX_button_click_v1` (x3, rapid) | **-10** | **C1 - SEED B. The DOOR CLOSE button. First pressing. Must be clearly audible and rhythmic** |
| 0:02 | `SFX_doors_slide_v1` (reversed, shorter) | -11 | C1 - doors closing on PIP |
| 0:02.5 | `SFX_doors_slide_v1` (thunk variant) | -14 | C2 - doors sealed shut |
| 0:03 | `SFX_door_creak_wood_v1` | **-11** | **C2 - SEED A. PIP opening the stairwell door. Must be clearly audible -- this is the alternative path** |
| 0:04 | `SFX_button_click_v1` | -14 | C2 - CHIEF pressing floor 5 |
| 0:04.5 | `SFX_motor_hum_v1` (enters, continuous) | -22 | C2 - elevator starts moving |
| 0:05 | `SFX_medal_jingle_v1` | -16 | C2 - CHIEF adjusting cap, medals clink |
| 0:06-0:11 | `SFX_button_click_v1` (rhythmic, every 0.5 s) | **-12** | **C3 - the obsessive rhythm. 10 clicks across 5 seconds. The comedy bed syncs to this** |
| 0:08 | `SFX_medal_jingle_v1` | -18 | C3 - adjusting sash |
| 0:11 | `SFX_button_click_v1` (x2 together - two fingers) | -11 | C4 - Stage A escalation. Double-click signals the shift |
| 0:12-0:13 | `SFX_button_click_v1` (rapid, 0.3 s interval - palm slams) | **-9** | C4 - Stage B. Louder, flatter (palm not fingertip). Aggressive |
| 0:13.5 | `SFX_electrical_buzz_v1` (enters, building) | -20 | C4 - the first sign of electrical distress. Very quiet, barely noticeable |
| 0:14 | `SFX_smoke_hiss_v1` (enters) | -22 | C4 - smoke beginning. Almost subliminal |
| 0:15 | `SFX_button_click_v1` (deep, broken-sounding) | -10 | C4 - Stage C. Button pushed too far. The click sounds wrong -- lower pitch, plasticky crack |
| 0:15.5 | `SFX_medal_jingle_v1` | -16 | C4 - CHIEF flexing medals, oblivious |
| **0:16** | **`SFX_spark_crack_v1`** | **-6 -- loudest sound in the silence** | **C5 - the failure. Music cuts simultaneously. This crack must be startling** |
| 0:16.5 | `SFX_light_flicker_v1` | -12 | C5 - lights dying |
| 0:17 | `SFX_mechanical_groan_v1` | -10 | C5 - elevator stopping. Heavy and final |
| 0:17-0:27 | `SFX_emergency_hum_v1` (continuous) | -24 | C5-C6 - the dead hum throughout the silence |
| 0:22 | `SFX_dead_click_v1` (x8, 0.2 s apart) | -14 | C6 - Attempt 1. Jabbing all buttons. The dead sound is worse than no sound |
| 0:23.5 | `SFX_door_pry_scrape_v1` | -12 | C6 - Attempt 2. Metal scraping |
| 0:24 | `SFX_door_snap_v1` | -10 | C6 - Doors snapping shut. Aggressive |
| 0:25 | `SFX_cable_creak_v1` | **-9** | C6 - Attempt 3. The jump. Cable strain |
| 0:25.5 | `SFX_elevator_sway_v1` | -11 | C6 - The sway after the jump. Low thud and wobble |
| 0:26.5 | (silence) | -- | C6 - The emptiness. Only the emergency hum |
| **0:27** | **`SFX_mechanical_groan_v1`** (shorter, ascending) | **-10** | **C7 - the lurch. Elevator crawling back to life** |
| **0:27.5** | **`SFX_door_creak_slow_v1`** | **-8 -- longest SFX in the video (2 s)** | **C7 - the slow door creak open. THE signature sound of this episode** |
| 0:29 | `SFX_water_sip_v1` | -14 | C7 - PIP's calm sip. Deliberate contrast with everything before |
| 0:29.5 | `SFX_scratch_v1` | -11 | C7 - record-scratch on CHIEF's frozen face |
| 0:31 | `SFX_button_v1` (warm ding) | -12 | C8 - series button as PIP offers cup |
| 0:31.5 | `SFX_spark_small_v1` | -18 | C8 - one last tiny spark from the dead panel. A callback |
| **0:32** | `SFX_button_v1` (series ding) | **-10** | **C8 - the "Every time." button. Loop seam** |

---

## 5. Loudness / delivery (platform-ready)
- Integrated target **~-14 LUFS**, true-peak **<=-1 dBTP**.
- **Duck BGM ~4-6 dB under VO** for VO lines; release fully into the silence.
- VO peaks ~-12 to -10 dBFS, ~3 dB above the ducked bed.
- **The clicking is the rhythm section.** In C3, the comedy bed's percussion syncs to CHIEF's button clicks,
  so they become *part of the music*. When the music cuts at 0:16, the clicking has already stopped (because
  the button is dead). The absence of both music AND clicking is what makes the silence so complete.
- **The signature sound of this episode is the door creak (0:27.5).** It is 2 seconds long, uninterrupted,
  and must sit above the returning stinger. A slow, strained, metallic creak that sounds like reluctance
  itself. The audience should feel the doors grudgingly opening.
- **The protected sounds** are the **0:01.5 button clicks** (Seed B -- if they are inaudible, the obsession
  setup breaks), the **0:03 stairwell door creak** (Seed A -- if it is inaudible, the twist has no
  fair-play), and the **0:29 water sip** (the calm contrast that sells the joke).
- **The loudest moments, in order:** the **0:16 spark crack** (-6) -> the door creak (0:27.5, -8) ->
  the cable creak (0:25, -9). The spark should feel sudden and electric; the door creak should feel slow
  and inevitable.
- **Never compress the silence up.** 0:16-0:27 has no music; the dead clicks and emergency hum should
  feel exposed and awkward, not loud.

---

## 6. Sourcing notes
- Use original or royalty-free/licensed audio only (advertiser-safe, monetization-safe).
- Reuse from earlier episodes: `SFX_scratch_v1`, `SFX_button_v1` set, and the **narrator voice**.
- New assets introduced for this episode worth locking for future building/indoor episodes:
  `SFX_elevator_ding_v1`, `SFX_doors_slide_v1`, `SFX_motor_hum_v1`, `SFX_emergency_hum_v1`,
  `SFX_cable_creak_v1`, `SFX_door_creak_slow_v1`.
- **Signature-sound principle (series-wide):** v1 = the stamp - v2 = the booster - v3 = the block clack -
  v4 = the panel slam - v5 = the discovery sting - v6 = the sweet clatter - v7 = water (four states) -
  v8 = the face-scan beep - v9 = the condiment squeeze - v10 = the printer jam - v11 = the register beep.
  **v12's signature sound is the DOOR CREAK** -- specifically the agonizingly slow 2-second creak of
  elevator doors opening to reveal the person you tried to lock out already arrived via the stairs. It is
  the slowest signature sound in the series (everything before it was percussive), and the slowness is
  the joke: the longer it takes to open, the longer CHIEF has to stare at PIP's calm face through the
  widening gap.
- **All Freesound sources** listed above are real assets available at freesound.org with the listed IDs
  and licenses. The Pixabay Music tracks are searchable by artist name on pixabay.com/music. YouTube
  Audio Library tracks are available in YouTube Studio's free music library.
