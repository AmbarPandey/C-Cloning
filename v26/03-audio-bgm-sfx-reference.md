# v26 — BGM, SFX & Audio Reference ("The Ferry") · **SHORTS**

> Prescriptive cue sheet. §2 gives the layer stack per time range; §4 lists every hit with timecode and
> level. Locks to `01-video-script.md`. **Mute-first.**

## 1. Assets

**Music**
| ID | Description | Used |
|---|---|---|
| `MUS_water_bed_v1` | House cue, nautical variant — plucky bass, soft brushed percussion, a lilting clarinet lead over a gentle 6/8 sway, ~112 BPM, major. **The sway depth increases with each cargo crate** — the arrangement gets heavier as the boat does | 0:01.5–0:16 |
| `MUS_water_stinger_v1` | Bright hit that deflates into a low settling drone | 0:27 |
| `MUS_water_resolve_v1` | Main melody once through, slow, warm, coming to rest | 0:29–0:32 |

**SFX**
| ID | Description |
|---|---|
| **`SFX_water_lap_v1`** | **Signature, stage 1** — water against a hull. **Four variants keyed to load state**: high-and-light (`L1`) → mid (`L2`) → **flush and slapping at the gunwale** (`L3`) → dead-flat, almost nothing (`L4`) |
| **`SFX_hull_settle_v1`** | **Signature, stage 2** — a hull dropping one increment. Pitch **falls** with each use |
| **`SFX_web_step_v1`** | **Signature, stage 3** — one webbed foot onto wood. Small, dry, matter-of-fact |
| **`SFX_hull_stop_v1`** | **Signature, stage 4 (the payoff)** — a moving hull losing the last of its way. A long, low, deflating slide into **nothing** |
| `SFX_crate_thud_v1` | Cargo crate into a hull (reused from v19/v20) |
| `SFX_oar_dip_v1` | PIP's light oar stroke |
| `SFX_raft_land_v1` | A small raft touching a bank |
| `SFX_rope_toss_v1` | A tow line thrown and landing |
| `SFX_ting_v1` · `SFX_scratch_v1` · `SFX_button_v1` | Reused series set |
| `SFX_amb_pond_v1` | Very low pond ambience — distant birds, faint reeds |

> **There is no splash, swamp, glug or immersion asset in this episode, by design.** The boat stops; it
> does not sink. If a water-impact sound appears in the mix, the ad-safety guardrail has been broken.

## 2. ⭐ Exact cue sheet

`BGM` · `SFX` · `VO` · `AMB` (`SFX_amb_pond_v1`, 0:02→0:32)

| # | Time | Layer stack | BGM | Notes |
|---|---|---|---|---|
| 1 | **0:00–0:01.5** | **SFX + VO only** | **none** | Cold payoff. **No music.** `SFX_water_lap_v1` already at the `L3` **flush** variant + one `SFX_web_step_v1` |
| 2 | **0:01.5–0:02** | **BGM + SFX** | `MUS_water_bed_v1` **enters on the cut** (~-16 dB) | The rule arrives with the music |
| 3 | **0:02–0:06** | **BGM + SFX + VO + AMB** | bed (full, ~-14 dB), sway shallow | Rewind. **Protect the 0:04 crate thuds** — they are the seed |
| 4 | **0:06–0:11** | **BGM + SFX + VO + AMB** | bed, **sway deepens** | Escalation 1. Lap variant → `L2` |
| 5 | **0:11–0:16** | **BGM + SFX + VO + AMB** | bed, **deepest sway, densest point** | Escalation 2. Lap variant → `L3` flush |
| 6 | **0:16** | **SFX + AMB only** | **cut mid-phrase** | Lands on the frame the pose locks |
| 7 | **0:16–0:27** | **SFX + AMB — SILENCE (11 s)** | **none** | Only 3 sounds permitted (§3). AMB ducked to ~-28 dB |
| 8 | **0:27–0:29** | **BGM + SFX + VO + AMB** | `MUS_water_stinger_v1` slams in | The hull stops |
| 9 | **0:29–0:32** | **BGM + SFX + VO + AMB** | `MUS_water_resolve_v1` | Payoff + loop out |

```
0:00 (silence, lap already flush) ─┐
0:01.5                             └─ BED ── sway+ ── sway++ (peak) ─┐
0:16                                                  ╌╌ SILENCE ╌╌╌┘  0:27 ┌ stinger ┐ resolve ► 0:32
```

> **The music decision:** the bed's **sway depth is tied to the load**, not to the tempo. He isn't speeding
> up like v24's door — he's getting *heavier*, and a 6/8 lilt that leans further with every crate is the
> audible version of a hull sitting lower. When the music cuts at 0:16 the sway is at its deepest, and what
> remains is a lap that is already slapping at the gunwale.

## 3. The silence beat (0:16–0:27)

11 s of total musical silence, cut mid-phrase on the pose lock.

| Time | Sound | Level | Why |
|---|---|---|---|
| 0:16–0:27 | `SFX_amb_pond_v1` | -28 | The pond stays alive without filling the space |
| **0:16–0:27** | **`SFX_water_lap_v1`** — variant **stepping `L3` → `L4`** across the window | **-14, thinning to -20** | **The instrument.** The lap starts slapping at a flush gunwale and gradually goes *flat and quiet* as the hull loses way. The payoff is announced by the water getting **less** interesting |
| **0:22 / 0:24 / 0:26** | **`SFX_web_step_v1` ×3** + **`SFX_hull_settle_v1` ×3, pitch falling** | **-15 / -16** | **The countdown, paired.** Each duck's step is answered immediately by the hull dropping a semitone. Three steps, three drops |

No VO except an optional whispered *"…the gunwale."* at ~0:25 (≤0.6 s). No music, no stings.

> **The craft point:** this silence escalates by **descending pitch**, not by volume — three hull settles,
> each lower than the last, each triggered by a small dry footstep. It is the cheapest possible sound
> (a webbed foot) repeatedly moving the largest object in the frame, and a listener can hear the boat
> *losing* without being told anything.

## 4. Complete SFX hit list

| Time | SFX | Level | Purpose |
|---|---|---|---|
| 0:00 | `SFX_water_lap_v1` (`L3` flush) | **-10** | C1 — first sound, over no music. Already the wrong, flush lap |
| 0:01 | `SFX_web_step_v1` | -14 | C1 — the duck's foot on the gunwale |
| 0:01.5 | `SFX_ting_v1` | -14 | C1b — the load line reads |
| 0:03 | `SFX_water_lap_v1` (`L1` high) | -18 | C2 — PIP's raft, riding light |
| **0:04** | **`SFX_crate_thud_v1` ×3** | **-15 (unremarkable)** | **C2 — SEED B. The cargo going in. Audible, not highlighted** |
| 0:05 | `SFX_button_v1` "pfft" | -16 | C2 — the sneer |
| 0:07 | `SFX_oar_dip_v1` ×2 | -17 | C3 — PIP casting off, light |
| 0:08 / 0:09.5 | `SFX_crate_thud_v1` ×2 | -14 | C3 — more cargo |
| 0:09 | `SFX_hull_settle_v1` | -16 | C3 — gunwale reaching the line |
| 0:10 | `SFX_water_lap_v1` (`L2`) | -16 | C3 — the lap changing character |
| 0:12 / 0:14 | `SFX_crate_thud_v1` ×2 | -13 | C4 — the last crates |
| **0:14.5** | **`SFX_web_step_v1`** (single, quiet) | **-18** | **C4 — the first duck boards. Deliberately underplayed** |
| 0:15 | `SFX_water_lap_v1` (`L3` flush) | -14 | C4 — flush at the gunwale |
| 0:15 | `SFX_button_v1` fanfare stab | -12 | C4 — vanity punctuation |
| 0:16 | *(music cuts — no new SFX; the flush lap becomes exposed)* | — | C5 — the turn by subtraction |
| **0:22 / 0:24 / 0:26** | **`SFX_web_step_v1` ×3 + `SFX_hull_settle_v1` ×3 (falling pitch)** | **-15 / -16** | **C6 — inside the silence. Step, then drop. Three times** |
| **0:29** | **`SFX_hull_stop_v1`** | **-6 — loudest in the video** | **C7 — a long low deflating slide into nothing. The largest sound in the episode is a thing *ceasing*** |
| 0:29 | `SFX_scratch_v1` | -11 | C7 — reversal punctuation |
| 0:30 | `SFX_raft_land_v1` | -12 | C7 — PIP touches the far bank |
| 0:30.5 | `SFX_water_lap_v1` (`L4` dead-flat) | -20 | C7 — the water gone quiet around him |
| 0:31 | `SFX_rope_toss_v1` | -14 | C8 — PIP throws the tow line |
| 0:32 | `SFX_button_v1` ding | -12 | C8 — series close |

## 5. Loudness / delivery
- Integrated **≈ -14 LUFS**, true-peak **≤ -1 dBTP**.
- Duck BGM ~5 dB under VO1–VO5; release into the silence. **Never duck the lap** — it is the instrument.
- **Protected sounds:** the **0:04 crate thuds** (the seed) and the **three paired step/settle events**, where the settle must be clearly *lower in pitch* than the one before.
- **Loudest, in order:** 0:29 hull stop (-6) → 0:00 flush lap (-10) → 0:29 scratch (-11). ~3 dB headroom before the stop.
- **The mix judgement that carries the episode:** the payoff is a **deceleration**, not an impact. `SFX_hull_stop_v1` must be long, low and *subtractive* — it should feel like the soundtrack running out of water. Do not add a transient to it and do not let a limiter clip its tail; the point is that the biggest moment in the video is something going quiet, mirroring v20's empty cart but with duration instead of emptiness.
- **The lap must audibly change character four times.** If all four variants sound the same, the primary instrument is lost and the twist becomes a surprise instead of a conclusion.
- Never compress the silence up.
- Shorts play muted by default: confirm the gunwale gap and the disappearing wake chevrons carry the story with audio off.

## 6. Sourcing & signature
- Original or royalty-free/licensed only. **No splash, swamp, glug or immersion sounds may exist in this project folder.** **No animal distress vocalisations** — the ducks step, nothing more.
- Reused: `SFX_crate_thud_v1` (v19/v20), `SFX_ting_v1`, `SFX_scratch_v1`, `SFX_button_v1`, narrator voice.
- **Signature-sound principle:** v18 jug · v19 plank · v20 cart · v21 pressure · v22 water height · v23 powder · v24 bearing · v25 tile. **v26's signature is the lap** — four variants keyed directly to the four load states, so the water itself reports the boat's condition all the way through. The inversion is the quietest in the series: the signature's final state is **almost silence**, a dead-flat lap around a stopped hull, and the payoff sound is a **deceleration**. v20 made an absence the loudest thing in the video; v26 makes a *slowing* the loudest thing, which is the same trick performed on time rather than on volume.
