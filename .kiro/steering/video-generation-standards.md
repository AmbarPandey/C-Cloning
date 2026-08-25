# Video Generation Standards (Execution branch)

Standing instructions for generating any video package on the `Execution` branch.

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
4. Respect the **freshness log** — do not reuse a pattern×scenario pair, and rotate scenarios and
   twist cores across episodes.
5. Reproduce the score in the package:
   `FinalScore = VP × CompatibilityChain(geometric mean) × Confidence − DifficultyPenalty`
6. Label Mode A (deterministic) vs **Mode B (exploration, ~1 per 5 Mode A, must state a hypothesis)**.

## Required files

Every package contains these, all locked to one shared master timeline:

| # | File | Notes |
|---|---|---|
| 1 | `01-video-script.md` | Beats, master timeline, scene-by-scene script, seeds, compliance checklist |
| 2 | `02-image-generation-reference.md` | Characters, reactions, surroundings, props, per-shot paste-ready image prompts |
| 3 | `03-voiceover-script.md` | Timed narration, sync rules, caption options, A/B variants |
| 4 | `04-video-generation-prompt.md` | Motion, camera angles, transitions, cut/freeze timing, FX per shot + one-shot master prompt |
| 5 | `05-audio-bgm-sfx-reference.md` | Exact BGM/SFX cue sheet (see below) |
| 6 | `06-thumbnail-prompt.md` | **Long form only** — high-CTR thumbnail prompts + title pairings |
| — | `README.md` | Index + one-line story + what's structurally new |

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

## The swipe gate (Shorts — read this before writing C1)

Shorts are swipe-discovered. There is no thumbnail and no title, so **the first frame is the thumbnail
and the first line is the title**, and they are consumed involuntarily in about one second. The gate
metric is **Stayed to Watch**; average % viewed is only computed on the people who already stayed, so
a good completion number on a failed gate means nothing. Full derivation in
[`RETENTION-ANALYSIS-V3.md`](../../RETENTION-ANALYSIS-V3.md).

### C1 is a cold payoff, never an establishing shot

The old house opening — *"Static wide establishing… CHIEF struts in from left"* — was present in all of
`v1`–`v17` and is the top two causes of swipe-away happening at once: **setup before payoff** and a
**static first frame**. It is retired. Do not reintroduce it.

```
C1  0:00–0:015  COLD PAYOFF  the karma moment already in progress — tight, mid-motion,
                             no context, cut away before it resolves
C1b 0:015–0:02  HARD CUT     to the goal diagram (the rule of the world, drawn)
C2  0:02–0:06   REWIND       the setup, now watched with the ending already known
```

Hard rules for C1:
- **Motion is already underway.** Nothing enters frame. No character entrance, ever.
- **Tight framing.** The subject fills significant frame area. Not a wide.
- **No reasoning step.** It must read muted, in one pass. If the viewer has to infer, it fails.
- **The first micro-payoff lands inside 1.5 s** — not evidence of a payoff, the payoff itself, partially.

### The five structural requirements

Extracted from the one episode in the catalogue that beat its cohort (`v3`):

1. **Draw the goal, don't imply it.** A win condition must be *visible* by 0:02 — a target line with an
   arrow at it, a limit pictogram, a fill line, a balance. No words. If the rule of the world cannot be
   drawn, it is not a Shorts premise.
2. **Build a scoreboard.** Both characters attempt **the same task in the same frame**, so the contrast
   is behavioural, not circumstantial. PIP is never waiting offscreen.
3. **Make the visual engine produce change every second.** Something must be measurably different from
   how it was a second ago — growing, filling, tilting, accumulating. In 9:16, prefer vertical.
4. **The flaw must be load-bearing.** The seed is the *mechanical cause* of the ending, planted visibly,
   accumulating stress as the episode escalates. **No external agents** — karma that arrives from
   outside the frame is a coincidence, not a mechanism, and coincidences don't get rewatched.
5. **Let the antagonist fully win first.** Trophy in hand, peak music, held pose, completely
   convincing. A reversal can only break a prediction the viewer was allowed to commit to.

### The three-layer hook

| Layer | Spec |
|---|---|
| Visual | The cold payoff, in motion. Must carry the idea alone |
| **Text** | **3–7 words** — a caption added **in the edit**, never baked into the render |
| Verbal | **5–10 words**, no preamble, and never the same sentence as the text |

All three assert **one** idea. If they disagree, the viewer spends the decision window reconciling them
and swipes. Alignment beats cleverness.

> The text layer and the zero-baked-in-text invariant coexist because the hook caption is added in the
> edit — the same carve-out the invariant already makes for captions. Rendered frames stay text-free.
> Keep the caption clear of the bottom bar and the right-hand action rail.

### Cadence ban

No two consecutive episodes may share an opening-line rhythm. **`"One ___. One ___."` is retired** — it
ran six episodes straight (`v10`, `v12`, `v14`, `v15`, `v16`, `v17`) and a returning viewer reads a
repeated cadence as *the same video again*.

### Before publishing — the silent half-second test

Mute it, play **0.5 s**, pause, and ask someone unfamiliar: *what is this about, who is it for, is
there a reason to keep watching?* Three answers or the hook is rewritten.

---

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
- **Costume lock:** CHIEF's cap + sash + medals and PIP's teal scarf are costume — never removed, never transferred.
- **Palette:** `INK #1A1A1A` · `BRAND_YELLOW #FFD400` · `PAPER #FFF7E0` · `SKY #BFE3F2` ·
  `ASPHALT #6E7076` · `ALERT_RED #E4322B` · `POP_TEAL #2FB6A3`. One dominant yellow focal hit per frame.
- **Render rules:** flat 2D, thick uniform `INK` outlines, no gradients, no blur, no glow, no camera rotation, hard cuts.
- **Mute-first:** the story must read with sound off. VO is an amplifier, never load-bearing.
- **Zero baked-in on-frame text** unless the premise requires it; captions are added in the edit.
- **Advertiser-safe:** karma lands on the arrogant, never the underdog. No injury, no distress, no animal harmed.
- **Signature-sound principle:** one signature sound per episode, escalated through the video, then inverted at the payoff.
- **Series sign-off:** the narration closes on **"Every time."**
- **Channel:** **IPPA** — *"The jerk always gets it."* Video ID format `IPPA_[####]_[premise]_[platform]_v#`.

## New assets

Any new character must be flagged as **proposed, not locked**, with a note that it needs a model sheet
and approval per the Character Bible lifecycle. Never silently add canon.
