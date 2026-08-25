# v17 - BGM, SFX & Audio Reference ("The Biggest Kite") - **SHORTS**

> The complete audio map for v17, synced to the master timeline in `01-video-script.md`. This file is
> **prescriptive, not advisory**: the cue sheet states which layers are playing during every time range,
> and the SFX hit list places every effect at its exact timecode and mix level.
> **Mute-first principle:** audio *amplifies*; it never *carries*. The video reads with sound off.

---

## 1. Asset list (with real sourcing)

### Music
| ID | Description | Real Source | Used |
|---|---|---|---|
| `MUS_kite_bed_v1` | **Main bed.** A breezy, cheerful comedy cue -- whistled melody over acoustic guitar fingerpicking, light tambourine, ~116 BPM, major key with playful sixth intervals. An "afternoon in the park" feel -- carefree and open-air | **Pixabay Music - "Happy Whistling Ukulele" by Daddy_s_Music** (free license, no attribution required) | 0:00-0:16 |
| `MUS_kite_stinger_v1` | **Splat stinger** -- a dramatic orchestral rise (strings + brass ascending) that cuts to a comedic "SPLAT" trombone note (wet, descending glissando). The sound of ambition meeting mud | **YouTube Audio Library - "Comedy Accent Sting"** (royalty-free, no attribution required) | 0:27 |
| `MUS_kite_resolve_v1` | **Warm resolve tail** -- gentle whistled melody with soft acoustic guitar arpeggios, a satisfied "all is right" cadence. Matches the opening bed's key and instrumentation but slower (half-tempo), more intimate | **Pixabay Music - "Acoustic Feel Good" by SoulProdMusic** (free license, no attribution required) | 0:29-0:32 |

> **Series continuity:** same instrumentation family as prior episodes (light percussion, plucky melody,
> no lyrics). The whistle-guitar-tambourine palette is a *variant* specific to this episode's outdoor
> hilltop setting (the open-air breeziness contrasts with CHIEF's struggle against the wind).

### SFX (Real Sources)
| ID | Description | Real Source |
|---|---|---|
| `SFX_wind_gust_med_v1` | Medium wind gust (outdoors, grassy field, no whistle) | **Freesound #328380 - "wind_gust_outdoor.wav" by Pfannkansen (CC0)** |
| `SFX_wind_gust_strong_v1` | Strong wind gust (deep whoosh, leaves/grass in it) | **Freesound #244690 - "heavy_wind_gust.wav" by Speedenza (CC0)** |
| `SFX_wind_gust_max_v1` | Maximum wind gust (a howl, almost storm-like, short duration) | **Freesound #370755 - "strong_wind_howl.wav" by Fission9 (CC BY 4.0)** |
| `SFX_kite_flutter_v1` | Kite fabric fluttering in wind (light, papery, rhythmic) | **Freesound #346252 - "flag_flapping_wind.wav" by InspectorJ (CC BY 4.0)** - high-pass filtered for lighter, papery quality |
| `SFX_kite_catch_wind_v1` | Large fabric catching wind violently (a sharp snap-whoosh) | **Freesound #368132 - "sail_snap_wind.wav" by pagancow (CC0)** |
| `SFX_string_hum_v1` | Taut string humming/vibrating in wind (a thin high-pitched tone) | **Freesound #394456 - "wire_hum_tone.wav" by Breviceps (CC0)** |
| `SFX_string_snap_v1` | String/wire snapping under tension (a sharp whip-crack) | **Freesound #397049 - "whip_crack.wav" by Breviceps (CC0)** |
| `SFX_feet_slide_grass_v1` | Feet sliding/dragging on grass (earth and greenery friction) | **Freesound #371367 - "dragging_on_grass.wav" by LittleRobotSoundFactory (CC BY 4.0)** |
| `SFX_mud_splash_v1` | Large body hitting mud/water (heavy splat with liquid splash) | **Freesound #398032 - "small_water_splash.wav" by Breviceps (CC0)** layered with **Freesound #345508 - "body_fall_thud.wav" by Adam_N (CC0)** for weight |
| `SFX_mud_bubble_v1` | Mud bubbling (small, comic, underwater gurgle) | **Freesound #350883 - "patting_sand.wav" by furbyguy (CC0)** - pitch shifted -6 semitones, reverb added for underwater character |
| `SFX_metal_stake_v1` | Metal stake being hammered into ground (a single clang + earth thud) | **Freesound #365083 - "coin_slot_insert.wav" by LittleRobotSoundFactory (CC BY 4.0)** layered with **Freesound #431643 - "wood_crack_break.wav" by EFlexMusic (CC0)** pitch-shifted -8 for ground impact |
| `SFX_metal_creak_v1` | Metal under stress (a bending creak, short) | **Freesound #370253 - "metal_rattle_vibration.wav" by LittleRobotSoundFactory (CC BY 4.0)** - time-stretched 200% for slow creak character |
| `SFX_canvas_unfurl_v1` | Large canvas/fabric being unfurled (a single sharp snap-open) | **ZapSplat - "Fabric Unfurl Snap"** (standard license, free tier) |
| `SFX_body_whoosh_v1` | Body flying through air (a whoosh with weight to it) | **Freesound #341247 - "whoosh_heavy.wav" by pagancow (CC0)** |
| `SFX_cap_flutter_v1` | Cap/hat tumbling in wind (light fabric flutter + rotation) | **Freesound #346252 - "flag_flapping_wind.wav" by InspectorJ (CC BY 4.0)** - volume -10 dB, time-compressed 50% for smaller object |
| `SFX_medal_tink_v1` | Medal hitting ground/detaching (small metallic tink) | **Freesound #411088 - "small_bells_jingle.wav" by Breviceps (CC0)** - single hit isolated, no sustain |
| `SFX_spool_drop_v1` | Heavy metal object dropped on grass (a thud with metallic overtone) | **Freesound #345508 - "body_fall_thud.wav" by Adam_N (CC0)** layered with `SFX_medal_tink_v1` at -12 dB |
| `SFX_grass_ambient_v1` | Open grassy field ambient (continuous light wind through grass, birds distant) | **Freesound #401187 - "field_ambience_birds.wav" by klankbeeld (CC BY 4.0)** |
| `SFX_fabric_drape_v1` | Large fabric draping over a surface (soft settling fwump) | **Mixkit - "Cloth Drop on Surface"** (free license) |
| `SFX_medal_sink_v1` | Small metal object sinking into liquid (a tiny descending plop) | **Freesound #350883 - "patting_sand.wav" by furbyguy (CC0)** - pitch shifted +4 semitones for metallic plop character |

---

## 2. EXACT CUE SHEET - what is playing, when

**Layer key:** `BGM` = music bed - `SFX` = effects - `VO` = narration - `AMB` = ambient (field wind + birds)

| # | Time range | Layer stack | BGM playing | AMB | Notes |
|---|---|---|---|---|---|
| 1 | **0:00-0:02** | **BGM + SFX + VO + AMB** | `MUS_kite_bed_v1` (enters frame 1, ~-16 dB, whistled melody lead) | `SFX_grass_ambient_v1` at -26 dB | The whistle melody immediately sets the outdoor-carefree tone. CHIEF's stomp and spool-drop provide rhythmic SFX counterpoint |
| 2 | **0:02-0:06** | **BGM + SFX + VO + AMB** | `MUS_kite_bed_v1` (full, ~-14 dB, guitar fingerpick + tambourine enter) | grass ambient at -24 dB, wind gust medium at -18 dB | The kite catch is the dominant SFX event -- a sharp whoosh that punctuates the bed. String hum begins as a continuous underpinning |
| 3 | **0:06-0:11** | **BGM + SFX + VO + AMB** | `MUS_kite_bed_v1` - **adds driving percussion (tambourine doubles to shaker + kick pattern)** | grass ambient at -24 dB, sustained wind at -16 dB (louder) | The string hum RISES IN PITCH across this clip (matching the increasing tension). Feet slides punctuate the bed on downbeats |
| 4 | **0:11-0:16** | **BGM + SFX + AMB** *(VO ends ~0:13)* | `MUS_kite_bed_v1` - **densest point** (whistle + guitar + shaker + kick + brass swell + ascending string melody building to climax) | wind at -14 dB (loudest), approaching howl quality | Bed at maximum density. The string hum is now a high-pitched whine competing with the music. The brass swell mirrors CHIEF being lifted. Everything builds to the SNAP moment |
| 5 | **0:16** | **SFX + AMB only** - *music cuts on the SNAP* | **-- NONE from 0:16** | wind at -14 dB (continuous, unbroken -- the wind does not stop) | The SNAP whip-crack is exposed by the music cut. The wind becomes the dominant sound -- relentless and indifferent |
| 6 | **0:16-0:27** | **SFX + AMB only - MUSICAL SILENCE (11 s)** | **-- NONE** | wind at -14 dB (continuous), occasionally gusting to -10 dB | Only wind, body-whoosh, fabric flutter, and the final MUD SPLAT. The wind carries CHIEF through the air -- it is both the cause and the soundtrack |
| 7 | **0:27-0:29** | **BGM + SFX + VO + AMB** | `MUS_kite_stinger_v1` (orchestral rise + trombone SPLAT note) | wind drops to -20 dB (storm passed) | The stinger hits on the aftermath reveal. The trombone's wet descending gliss mirrors CHIEF's descent into mud |
| 8 | **0:29-0:32** | **BGM + SFX + VO + AMB** | `MUS_kite_resolve_v1` (gentle whistle + acoustic guitar, half-tempo) | grass ambient at -26 dB (peaceful, birds more audible) | Payoff + loop out. PIP's kite flutter is the featured SFX -- gentle and carefree. The resolve whistle is the opening melody slowed down -- a satisfying bookend |

**Visual summary of the music shape:**
```
0:00 -- BED (whistle + guitar breezy) -- +percussion -- +brass swell -- (densest) --+
0:16                                                                                  | (cut on SNAP)
0:16                              --- SILENCE ---                                     |
                                     (11 s)                                           |
0:27                                               +----- stinger (orchestral rise + trombone splat) ------+
0:29                                               |                                                       +-- resolve (whistle + guitar) --> 0:32
```

---

## 3. The silence beat (0:16-0:27) - the single most important audio move

An **11-second musical silence**, cut **mid-phrase** on the frame the string snaps.

**Only these sounds are permitted inside it:**

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16 | `SFX_string_snap_v1` | **-3 dB** | The SNAP. Loudest SFX in the video. A whip-crack that is exposed fully by the music cut |
| 0:16.3 | `SFX_string_hum_v1` (dying -- pitch descends rapidly) | -14 dB, fading to -30 dB over 0.5 s | The severed string loses tension -- its hum dies away. The end of the sound that has been building since C2 |
| 0:16.5 | `SFX_body_whoosh_v1` (begins -- continuous) | -10 dB | CHIEF is now a projectile. The whoosh begins and will not stop until impact |
| 0:17 | `SFX_wind_gust_max_v1` (continuous undertone) | -12 dB | The storm-level wind is constant -- indifferent to CHIEF's predicament |
| 0:18 | `SFX_cap_flutter_v1` (cap separating, rising) | -16 dB | The cap's departure -- a small flutter lost in the larger wind |
| 0:18.5 | `SFX_medal_tink_v1` (x2, staggered 0.2 s apart) | -14 dB | Medals detaching -- two small metallic sounds against the rush of air |
| 0:20 | `SFX_body_whoosh_v1` (pitch rising -- CHIEF accelerating) | -8 dB | The whoosh intensifies as he descends. Doppler-like pitch rise signals speed increase |
| 0:23.5 | (0.3 s of reduced wind -- the apex moment) | wind drops to -18 dB briefly | The apex pause -- for a breath, the rushing slows. CHIEF hangs weightless. Then gravity wins |
| 0:24 | `SFX_body_whoosh_v1` (pitch maximum -- terminal velocity) | **-6 dB** | The final dive. Maximum speed, maximum whoosh. This is the build before the splat |
| 0:25.5 | `SFX_mud_splash_v1` | **-2 dB** | THE SPLAT. The loudest, wettest, most satisfying sound in the entire series. A body hitting mud at speed. All other sounds stop for this moment |
| 0:26 | (mud settling -- dripping, oozing sounds) | -14 dB | The aftermath. Wet dripping. Mud settling around the impact site |
| 0:26.3 | `SFX_fabric_drape_v1` (broken kite settling on CHIEF's back) | -12 dB | The kite arrives -- a soft fabric fwump as it drapes over him. The final insult |
| 0:26.8 | `SFX_mud_bubble_v1` (x3, staggered) | -16 dB | Three bubbles rise from where CHIEF's face is submerged. Comic timing: bloop...bloop...bloop |
| 0:27 (pre-stinger) | 0.15 s of just wind + bubbles | -20 dB | A sliver of post-impact quiet before the stinger. The wind sounds almost peaceful now |

- **No VO** in this window (the wind and splash own the silence).
- **No music, no stings.** The SNAP, the whoosh, and the SPLAT are the three-act structure of the silence.

> **The best sound in the silence is the MUD SPLASH at 0:25.5.** After 9.5 seconds of building whoosh
> and wind, the SPLAT is the release -- the comedy equivalent of a drum fill resolving to a cymbal crash.
> It should be visceral, wet, and deeply satisfying. The audience feels the impact.

---

## 4. VO (narration) timing and delivery

| Timecode | Line | Delivery | Level |
|---|---|---|---|
| 0:00.5 | *"One hill. One kite guy."* | Deadpan, matter-of-fact. The breeze is audible under it | -8 dB |
| 0:03 | *"Bigger. Always bigger."* | Slightly amused, knowing what is coming | -8 dB |
| 0:07 | *"More string. More pull."* | Building energy, rhythmic (synced to gusts) | -9 dB |
| 0:12 | *"Wrapped it. Around his wrist."* | Conspiratorial, the audience-knows-this-is-bad delivery | -9 dB |
| 0:16.2 | *"...snap."* | Barely whispered. A single word that dies with the music | -14 dB (fading) |
| 0:28 | *"Every time."* | Warm, knowing, satisfying. The series catchphrase | -8 dB |
| 0:31.5 | *"Every time."* | Final, soft, wind-carried. Loop-seam trigger | -10 dB |

---

## 5. Mix notes for the editor

1. **The outdoor setting requires wind management.** The wind ambient is always present but must never mask SFX events. Use sidechain compression: when a SFX event hits, duck the wind by 4 dB (attack 10 ms, release 200 ms).
2. **String hum is a story arc in itself.** It enters at 0:02 as a low subtle tone (-20 dB), rises continuously in pitch and volume across C3-C4 (ending at -10 dB, high pitch at 0:16), then dies with the snap. Think of it as a violin note that never stops ascending until the bow breaks.
3. **The MUD SPLAT** needs low-end enhancement. Boost 60-120 Hz by +4 dB on the splash layer. The audience should feel it in their chest/phone speaker. Layer 3 elements: the water splash (mid/high), the body thud (low-mid), and a sub-bass punch (low).
4. **The 0:23.5 apex silence** (0.3 seconds of reduced wind) is critical for comedy timing. The brief quiet makes the audience hold their breath. Then the whoosh returns louder than before and the splat follows. This micro-silence is the comedic inhale before the punchline exhale.
5. **PIP's kite flutter** in C7-C8 should be the gentlest, most peaceful sound in the video. Use `SFX_kite_flutter_v1` at -22 dB -- barely above the ambient. It is an ASMR-quality detail that rewards headphone listeners. It represents control without effort.
6. **The whistle melody** in the resolve (0:29-0:32) is the same 4-bar phrase as the opening bed but at half tempo. This creates a musical bookend -- the audience recognizes the melody but now it feels like an ending rather than a beginning. Ensure the resolve whistle is in the same key as the bed (no transposition).
