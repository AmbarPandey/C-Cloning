# Video Generation Standards (Execution branch)

Standing instructions for generating any video package on the `Execution` branch.

> **The canon lives in this repo.** Every path referenced below resolves from the repository root:
> `intelligence/` holds the eight libraries the idea funnel reads, `production/design/` holds the
> visual bibles, `production/characters/` holds the cast sheets, and `IMAGE-GEN-REFERENCE.md` is the
> paste-ready distillation. If a reference does not resolve, **stop** — do not proceed from memory or
> invent a substitute. Everything drifted last time precisely because these paths were missing.

## Trigger

The user will say only a **video number + format**, e.g. `v10 (shorts)` or `v7 (long form)`.
Generate the full package into a folder named after the video number (`v10/`, `v7/`) on the
`Execution` branch, then commit and push.

If the format is omitted, ask — or infer from the number's neighbours and state the assumption.

## Idea selection (never brainstorm)

Every video's idea must be **computed** from the locked intelligence layer, not invented:

1. Read the Content Matrix funnel (`intelligence/08-content-matrix.md`) and the VID-Graph decision
   engine (`intelligence/07-virality-intelligence-database.md`).
2. Resolve `Goal → Behavior → Pattern → Scenario → Comedy → Twist (one core) → Formula`.
3. Enforce the hard constraints: one pattern; one twist core; AdSafe ≥ 4; not a forbidden combo;
   pattern↔scenario ≥ 4; **TM3 Seed required if goal = Replay**; mute-readable; recurring cast.
4. Respect the **freshness log** (`intelligence/09-freshness-log.md`) — do not reuse a
   pattern×scenario pair, and rotate scenarios and twist cores across episodes. **Update the log in
   the same commit as the package.**
5. Reproduce the score in the package:
   `FinalScore = VP × CompatibilityChain(geometric mean) × Confidence − DifficultyPenalty`
   Show the **inputs**, not just the result — a bare "FinalScore 8.5" is not a reproduction.
6. Label Mode A (deterministic) vs **Mode B (exploration, ~1 per 5 Mode A, must state a hypothesis)**.
7. Take the **next unused idea number** from the ledger in the freshness log. Idea numbers are a
   continuous sequence and are **not** tied to video numbers.

### The ID registry is closed — never invent an ID

Every ID you write must already exist in the library that owns it. There is no ad-hoc minting.

| Axis | Library | Valid IDs |
|---|---|---|
| Narrative pattern | `intelligence/06-narrative-pattern-library.md` | `NP1`–`NP8` only |
| Scenario | `intelligence/04-scenario-intelligence-library.md` | **`SC1`–`SC10` only** |
| Comedy mechanic | `intelligence/02-comedy-mechanics-library.md` | `CM-A1`–`A4`, `CM-B1`–`B3`, `CM-C1`–`C4`, `CM-D1`–`D4`, `CM-E1`–`E2` |
| Twist | `intelligence/03-narrative-twist-library.md` | `TW1`–`TW10`, mechanisms `TM1`–`TM3` |

**Write the canonical name verbatim next to the ID.** The name is not a free-text description of
your premise — it is the library's label. The scenario axis in particular is a *psychological
situation family*, **not a location**: a laundromat, a library, a lift and a beach are all
`SC8 Everyday Friction` or `SC3 Competition`, and none of them are new scenario IDs.

- `SC1` Authority · `SC2` Service Exchange · `SC3` Competition · `SC4` Family/Domestic ·
  `SC5` Romance/Dating · `SC6` Crime & Justice · `SC7` Danger/Survival · `SC8` Everyday Friction ·
  `SC9` Technology/Social *(quota-limited — max 3 evergreen)* · `SC10` Animals-as-People
- `CM-C1` Role Reversal · `CM-C2` Overconfidence Collapse · `CM-C3` Instant Karma ·
  `CM-C4` False Victory (the family-C names most often mislabelled).

> If the computed combination genuinely has no home in `SC1`–`SC10`, that is a **proposal to amend
> the Scenario Library** — raise it as its own change to `intelligence/04`, with a compatibility row
> added to the VID-Graph. Do not smuggle a new ID in through an episode package.

### Comedy core ≠ twist core

The comedy mechanic and the twist are **two different axes**. If your comedy mechanic and your twist
carry the same name, you have one core wearing two hats, and the Rule of One has silently failed:

- ✗ `CM-C4 False Victory` → `TW4 False Victory`
- ✗ `CM-C3 Instant Karma` → `TW3 Instant Karma`
- ✓ `CM-C2 Overconfidence Collapse` → `TW3 Instant Karma`
- ✓ `CM-E1 Escalation` → `TW2 Irony Reversal`

Pick the mechanic that supplies the *incongruity* and a twist that supplies a *different* container.

## Required files

Two package shapes are permitted. **State which shape you are building in the package README**, and
lock every file in the package to one shared master timeline.

### Full package (default — use this unless told otherwise)

| # | File | Notes |
|---|---|---|
| 1 | `01-video-script.md` | Beats, master timeline, scene-by-scene script, seeds, compliance checklist |
| 2 | `02-image-generation-reference.md` | Characters, reactions, surroundings, props, per-shot paste-ready image prompts |
| 3 | `03-voiceover-script.md` | Timed narration, sync rules, caption options, A/B variants |
| 4 | `04-video-generation-prompt.md` | Motion, camera angles, transitions, cut/freeze timing, FX per shot + one-shot master prompt |
| 5 | `05-audio-bgm-sfx-reference.md` | Exact BGM/SFX cue sheet (see below) |
| 6 | `06-thumbnail-prompt.md` | **Long form only** — high-CTR thumbnail prompts + title pairings |
| — | `README.md` | Index + one-line story + what's structurally new |

Used by `v1`–`v7`.

### Compact package (batch shape)

| # | File | Notes |
|---|---|---|
| 1 | `01-video-script.md` | As above |
| 2 | `02-video-animation-prompt.md` | Merges the image-generation reference and the video/motion prompt into one shot-by-shot document |
| 3 | `03-audio-bgm-sfx-reference.md` | As above |
| — | `README.md` | **Still required** — index + one-line story + which shape this is |

Used by `v8`–`v17`. The compact shape drops the standalone voiceover script, so `01` must carry the
timed `VO` line for every clip, and it drops the standalone image reference, so `02` must carry the
full paste-ready per-shot image prompt — not just motion notes. **A compact package is not a licence
to drop content, only to merge files.**

> `v8`–`v17` currently ship the three numbered files with **no `README.md`**. That is a gap tracked
> in [`BASE-AUDIT.md`](../../BASE-AUDIT.md), not a precedent to copy.

## Format specs

| | Shorts | Long form |
|---|---|---|
| Aspect / resolution | 9:16, 1080×1920 | **16:9, 1920×1080** |
| Duration | ~32 s | 1:00–2:00 (default 1:30) |
| Structure | 8 clips, fixed skeleton | 5 acts, 14–18 shots |
| Silence beat | 0:16–0:27 (11 s) | ~10 s immediately before the reveal |
| Thumbnail file | no | **yes** |

> **Critical:** any **vertical or square** video up to **3 minutes** is auto-classified as a YouTube
> Short ([YouTube Help](https://support.google.com/youtube/answer/15424877)). Long form must therefore
> be **16:9 horizontal**, or it will be treated as a Short regardless of length.

### The Shorts skeleton (do not drift)
`C1 0:00–0:02 · C2 0:02–0:06 · C3 0:06–0:11 · C4 0:11–0:16 · C5 0:16–0:22 · C6 0:22–0:27 ·
C7 0:27–0:31 · C8 0:31–0:32` — music cuts to silence at 0:16, twist impact ~0:29, loop seam at C8.

## Retention requirement (applies to BOTH formats)

The script must hold the viewer for the **entire** runtime:

- Hook in the first 2–3 seconds — no preamble, open with the strongest image or the unanswered question.
- Plant an **open loop** early and keep it unresolved until the twist.
- A **micro-payoff every ~10–15 s** (long form) so there is never a flat stretch.
- **Pattern interrupts** at the known drop-off points (~0:30 and ~1:00 in long form).
- **Escalation** — each beat must raise the stakes or absurdity above the last.
- **Silence beat** immediately before the reveal.
- End on a **loop/replay trigger**: the final frame returns to the opening composition so the seed can be re-spotted.

## Audio requirement (applies to BOTH formats)

`05-audio-bgm-sfx-reference.md` must specify **exactly what plays when**, not general guidance:

- A **cue sheet keyed to time ranges**, giving the **layer stack** for each range
  (e.g. `BGM only` / `BGM + SFX` / `SFX only` / `SILENCE`).
- Named asset IDs for every BGM and SFX hit, with its exact timecode.
- The silence window, and the short list of sounds permitted inside it.
- Loudness targets, ducking rules, and which single sound must never be masked.

## Locked creative invariants

- **Cast:** PIP (Hero/Underdog) + CHIEF (Bully/Antagonist) must lead every video (recurring-cast rule, D-02).
- **Costume lock:** CHIEF's cap + sash + medals and PIP's teal scarf are costume — never removed,
  never transferred. This holds **through the karma beat**: the cap does not fly off, medals do not
  scatter, the scarf does not come loose. They are his silhouette signature; strip them mid-video and
  the audience loses the character at the exact moment they need to read him. Knock him over, cover
  him, sit him in a puddle — but he lands **wearing the hat**.
- **Palette:** `INK #1A1A1A` · `BRAND_YELLOW #FFD400` · `PAPER #FFF7E0` · `SKY #BFE3F2` ·
  `ASPHALT #6E7076` · `ALERT_RED #E4322B` · `POP_TEAL #2FB6A3`. One dominant yellow **prop** focal
  hit per frame (costume yellow is exempt — see IMAGE-GEN-REFERENCE §3).
  **Name colours with tokens, never in English.** Writing "green checkmark", "brown puddle", "white
  clouds", "brass key" or "gold buttons" in a script hands the generator an off-palette instruction.
  Map first, then write: approval/success → `POP_TEAL`; rejection/hazard → `ALERT_RED`; metal, mud,
  stone, tarmac → `ASPHALT`; paper, cloth, foam, icing, cloud → `PAPER`; grass and foliage → flat
  `POP_TEAL` at low saturation or `ASPHALT`, never green.
- **Render rules:** flat 2D, thick uniform `INK` outlines, no gradients, no blur, no glow, no camera rotation, hard cuts.
- **Mute-first:** the story must read with sound off. VO is an amplifier, never load-bearing.
- **Zero baked-in on-frame text** unless the premise requires it; captions are added in the edit.
- **Advertiser-safe:** karma lands on the arrogant, never the underdog. No injury, no distress, no
  animal harmed. The ceiling is **comic indignity, not physical peril** — CHIEF may be buried,
  drenched, deflated or outclassed, but he is never genuinely endangered. Specifically avoid: cords
  or lines wrapped around a body part, being dragged or towed by one, falls that read as height,
  electrical contact, and anything a parent would flag. Fear = comic panic. Sadness = cute. Anger =
  indignant huff.
- **Named emotions and poses only:** every clip's emotion must use an exact name from the Expression
  Library and every pose an exact name from the Pose Library — **no synonyms, no improvised adjectives.**
  CHIEF plays `smug · gloating · triumphant · shocked · panicked · deadpan`; PIP plays
  `neutral · worried · teary · hopeful · gleeful · relieved · wave`; the shared mintable set is
  `confused · curious · sheepish · suspicious · thinking · weary · determined · eager · indignant ·
  fond · delighted`. Words like *terrified, ragdolled, aggressive, mortified, strained, content,
  patient, defeated* are **not** canon — pick the nearest real name, or the beat is unbuildable.
- **Signature-sound principle:** one signature sound per episode, escalated through the video, then inverted at the payoff.
- **Series sign-off:** the narration closes on **"Every time."**
- **Channel:** **IPPA** — *"The jerk always gets it."* Video ID format `IPPA_[####]_[premise]_[platform]_v#`.

## New assets

Any new character must be flagged as **proposed, not locked**, with a note that it needs a model sheet
and approval per the Character Bible lifecycle. Never silently add canon.

---

## Pre-commit quality gate

Run this against the package **before** committing. Any ✗ is a blocker, not a note.

**Traceability**
- [ ] Every `NP` / `SC` / `CM-` / `TW` ID exists in its library, with the library's **verbatim name**.
- [ ] Comedy core and twist core are **different** cores.
- [ ] Pattern×scenario pair is not already in the freshness log.
- [ ] `FinalScore` shows its inputs (VP, compatibility chain, confidence, difficulty penalty).
- [ ] Mode A / Mode B labelled; if Mode B, the hypothesis is stated.
- [ ] Idea number is the next unused one in the ledger.
- [ ] Freshness log updated **in this commit**.

**Format**
- [ ] Shorts → 9:16 1080×1920, ~32 s, the 8-clip skeleton, silence 0:16–0:27.
- [ ] Long form → **16:9** 1920×1080, 1:00–2:00, 5 acts, thumbnail file present.
- [ ] Package shape declared in the README, and the README exists.
- [ ] All files agree on one master timeline; the retention table's timecodes match the clip table's.

**Canon**
- [ ] CHIEF wears cap + sash + medals in **every** shot, including after the karma beat. PIP wears the scarf.
- [ ] Zero English colour words; every colour is a palette token.
- [ ] Every emotion and pose is a canonical name.
- [ ] Advertiser-safe ceiling respected — indignity, not peril.
- [ ] Mute-readable end to end; the VO is removable without losing the story.
- [ ] Final frame returns to the opening composition.

**Cross-check:** open the two nearest neighbouring episodes and confirm this one is *structurally*
different, not just re-skinned. Same pattern + same comedy mechanic + a new location is a re-skin.
