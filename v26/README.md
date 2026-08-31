# v26 — "The Ferry" · **SHORTS** · Compact package

**Package shape:** **Compact** (3 numbered files + this README) — the v24/v25 shape.
**Video ID:** `IPPA_0026_boat_shorts_v1` · 9:16, ~32 s, mute-first.

**Idea A24 · Mode A** — `NP8` Ironic Backfire × `SC10` Animals-as-People · `CM-C2` Overconfidence Collapse ·
`TW1` Role Reversal · **FinalScore 8.7** · **Confidence 1.00** · **all four chain edges 5/5**.

| # | File |
|---|---|
| 1 | [`01-video-script.md`](01-video-script.md) — beats, timeline, retention architecture, timed VO, quality gate |
| 2 | [`02-video-animation-prompt.md`](02-video-animation-prompt.md) — per-shot prompts, the five load states, motion/camera/FX |
| 3 | [`03-audio-bgm-sfx-reference.md`](03-audio-bgm-sfx-reference.md) — exact cue sheet with mix levels |

**Story:** a pond crossing where every hull carries a load line. PIP takes a small raft and loads it light.
CHIEF piles cargo into the big boat to look grander — which pushes his gunwale down until it's level with
the water. A low gunwale is a step. One duck steps aboard, then the queue. He launches first and is winning,
then settles to the line and **stops dead** mid-pond as a floating platform, while PIP's light raft glides
past and lands.

**Seeds:** the hull's load line, and the cargo he stacks at 0:04 that lowers the gunwale to duck height.

---

## Built on what made v24/v25 work
Four things those two had in common, applied deliberately here:

1. **Full confidence, proven nodes.** v24 was the only episode in the last batch at Confidence 1.00 — and it scored highest (8.8). v26 is also **1.00**, with every chain edge at 5/5 and no Medium-tier node anywhere.
2. **A mechanism explainable in one sentence.** v24: harder push → faster spin → the wedged compartment never clears. v26: **more cargo → lower gunwale → boardable → heavier → stops.**
3. **One measurement carries the episode.** v25 had two tile tokens; v26 has the **gunwale-to-waterline gap**, charted `L0`→`L4`, with the **wake chevron count** (3→3→2→1→**0**) as the second half of the same instrument. When the chevrons hit zero the audience knows he's stopped without being told.
4. **Audio doing narrative work.** v24 tied the bed's *tempo* to the door; v26 ties its **sway depth** to the load — a 6/8 lilt that leans further with every crate. And the lap SFX has **four variants keyed to the four load states**, so the water reports the boat's condition throughout.

---

## Issues from the last batch, and how v26 fixes them

**Score erosion from unproven nodes.** v19 (6.1) and v23 (6.0) dragged because I opened Medium-confidence tiers. Fixed: `NP8` is a *daily-viable* pattern per the base audit, `SC10` is Daily tier, `CM-C2` and `TW1` are both proven. Confidence **1.00**.

**Loose 4/5 compatibility edges.** v19's `CM-B3↔TW9` and v23's `NP5↔SC6` were genuinely adjacent joins and cost real score. Fixed: **all four edges here are 5/5** because the axes are semantically far apart.

**The near-collapse I had to actively avoid.** The obvious container for `NP8 Ironic Backfire` is `TW2 Irony Reversal` — and that would be **one core wearing two hats**, precisely the defect the audit found on v7/v8/v10/v13. I used `TW1 Role Reversal` instead. Worth noting because it's the kind of pairing that looks correct and quietly fails the Rule of One.

**Compression.** Writing eight at once forced me to tighten the last few. With two, v26/v27 carry the density of v24/v25.

---

## The craft point I'm most pleased with
The **largest sound in the episode is a thing ceasing.** `SFX_hull_stop_v1` is a long, low, subtractive
slide into nothing — the soundtrack running out of water. v20 made an *absence* the loudest moment (an empty
cart); v26 makes a *deceleration* the loudest moment, which is the same trick performed on time rather than
on volume. And the silence escalates by **descending pitch**: three small dry webbed footsteps, each
answered by the hull dropping a semitone. The cheapest sound available moves the biggest object in frame.

## Compliance notes
- Comedy core ≠ twist core ✓ · no invented IDs ✓ · score inputs shown ✓ · `NP8×SC10` fresh ✓ · idea `A24` next unused ✓.
- Distinct from **v22**, the other `SC10` episode: v22 was a pictogram misread on land; v26 is buoyancy, sharing no pattern, mechanic or twist.
- **Advertiser-safe — water is the constraint.** The boat **never sinks, never takes water over the gunwale, never capsizes.** Nobody enters the water. CHIEF is **dry in every frame including the payoff** — he is stopped, not swamped. There is no splash, swamp or immersion asset in the project folder at all.
- Ducks are Crowd class — desaturated silhouettes, no faces, calm, boarding of their own accord. None harmed, herded or startled, and no animal distress sounds exist.
- Colour tokens only — water `SKY`, boat `ASPHALT`, raft/jetty/cargo `PAPER`, foliage `POP_TEAL`, load line `ALERT_RED`.
- CHIEF keeps cap + sash + medals throughout.

Canon: [`intelligence/`](../intelligence/) · standards: [`.kiro/steering/video-generation-standards.md`](../.kiro/steering/video-generation-standards.md) · ledger: [`intelligence/09-freshness-log.md`](../intelligence/09-freshness-log.md)
