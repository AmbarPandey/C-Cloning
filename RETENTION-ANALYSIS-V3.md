# Why v3 Won — teardown, and the opening standard extracted from it

Analysis of `v3 "One Block Too Many"` against its Shorts cohort (`v1`, `v2`, `v4`, `v6`), measured
against the research in the `retention-formula` branch.

---

## 0. Reading the numbers honestly first

Reported: `v3` at **65%** with **~3k views**; four or five others between **70–90%**.

Taking "swipe rate" as **swipe-away rate**, `v3` is the best performer — fewest people swiped, most
views. That reading is the self-consistent one, since a better gate is what earns the distribution
that produces 3k views, and it matches the framing of the request. Everything below assumes it.

**But the honest version matters more than the ranking.** Converting to the metric YouTube actually
reports, [Stayed to Watch](https://www.creatoressentials.com/glossary/stayed-to-watch/):

| | Swipe-away | Stayed to Watch |
|---|---|---|
| `v3` (best) | 65% | **35%** |
| the rest | 70–90% | **10–30%** |

Creator consensus puts a failing hook [below 50%](https://www.shortimize.com/blog/how-does-youtube-shorts-algorithm-work), with
[top performers at 70–90% *stayed*](https://vidiq.com/blog/post/viral-video-hooks-youtube-shorts/).

> **So `v3` is the least-broken video in a cohort where every hook is failing the gate.** It is the
> right thing to learn from and the wrong thing to merely copy. Two jobs, not one: propagate what `v3`
> does structurally right, and fix the defect all five share.

Also worth knowing before drawing conclusions from 3k views: since **31 March 2025** a Short counts a
view on any playback of any length, and **every loop counts again**. `v3` has the most motivated loop
in the catalogue, so part of its view lead is its replay rate — which is a genuine win, but it means
views are partly a *loop* metric now, not a reach metric. Judge on Stayed to Watch × average % viewed.

---

## 1. The defect all seventeen share

Every single episode, `v1` through `v17`, opens on this:

```
**CAM:** Static wide establishing (this exact framing returns in C8).
**ACT:** CHIEF struts in from left, chest out.
```

That is not a house style, it is the top two entries in the swipe-away diagnostic table happening
simultaneously:

| Rank | Cause | Symptom | Present |
|---|---|---|---|
| 1 | **Setup before payoff** | Stayed to Watch low, % viewed fine | ✗ all 17 open on the situation assembling itself |
| 2 | **Static first frame** | Very low Stayed to Watch | ✗ all 17 open on a static wide |

The opening also spends its first two seconds on an **entrance** — a character walking into a location
so the story can start. In a feed where the decision window is
[1–2 seconds](https://www.shortimize.com/blog/how-does-youtube-shorts-algorithm-work), an entrance is
the most expensive shot available: it is pure preamble that resolves into "now the video may begin."

The inversion rule says whatever order you would naturally shoot in, reverse it. **A wide establishing
shot is the natural order.** That is precisely why it is wrong here.

There is a second-order problem in `v8`–`v17`. The opening narration has collapsed into one template:

| | VO |
|---|---|
| v10 | *"One printer. One problem."* |
| v12 | *"One elevator. One button."* |
| v14 | *"One beach. One wall."* |
| v15 | *"Five dryers. One guy."* |
| v16 | *"One table. One guy."* |
| v17 | *"One hill. One kite guy."* |

Six consecutive episodes with the same cadence. Word counts are disciplined and the lines are fine in
isolation, but a returning viewer hears the rhythm and reads it as *the same video again* — which is
a swipe. Anti-pattern: copying a phrasing instead of a trigger.

---

## 2. What v3 does that the others don't

Five things. In descending order of how much I think each is worth.

### 2.1 The win condition is a diagram in frame 1

`v3`'s first frame contains a measuring post with an `ALERT_RED` target band and a `BRAND_YELLOW`
**arrow pointing directly at it**, two platforms side by side, and the trophy on a table.

A viewer parses that in one pass, with no sound and no text: *there is a contest, that is the line to
reach, there are two competitors, that is the prize.* Category assignment — the 100–500 ms job — is
free, because the frame is **self-explaining**.

Now the same test on the others:

| | Frame 1 | What the viewer must do |
|---|---|---|
| **v3** | Target band + arrow + two platforms + trophy | **Perceive.** The goal is drawn |
| v2 | Race track, low finish tape, trophy, podium, ribbon | Perceive — closest to v3, and v2 is the next best structurally |
| v6 | Sweet stall, balance scale, rate pictogram | Read a pictogram, then infer an exchange rule |
| v1 | Parking lot, meter, no-parking zone, scooter inside it | **Infer** that a scooter in a red zone is ironic |
| v4 | Shade, sun, animals, fence panels, padlock | **Infer** that shade is contested and the panels matter |

`v1` and `v4` ask for a reasoning step inside the decision window. Reasoning is slower than the swipe.

> **This is the single most transferable lesson: draw the goal, don't imply it.** An arrow pointing at
> a line costs nothing and converts an inference into a perception.

### 2.2 It is a side-by-side scoreboard

Two platforms, two towers, rising in the same frame. That is hook type **E, comparison/versus** — a
game with a scoreboard, where the viewer picks a side within a second and stays for the result.

`v2` is also a versus, but a *race*: horizontal, sequential, and asymmetric in **equipment** (rocket
scooter vs roller skates). `v3` is asymmetric in **behaviour** — same blocks, same task, different
judgement. That is a fairer contest, so the outcome feels earned rather than rigged, and the viewer
has an actual opinion about who *should* win.

`v1`, `v4` and `v6` are not contests at all. They are one character imposing on another. There is no
scoreboard, so there is nothing to check back on.

### 2.3 The visual engine produces change every single second

The towers grow continuously from C2 to C4. That satisfies "visual change every 2–3 seconds"
structurally rather than through editing tricks — the subject itself is always different from how it
was a second ago.

It also uses the 9:16 frame the right way round: **vertical growth in a vertical format.** A tower
climbing out of the top of frame is a shape only Shorts can deliver well.

And it is one of the formats the loop research names as best-suited to replay: a satisfying process
with a visible progress bar.

### 2.4 The flaw is visible, physical, and causes the ending

Two seeds: the red line (the goal) and **the crooked bottom block** CHIEF slaps down in C2. The
crooked block is not decoration — it is the mechanical cause of the collapse in C7.

This is dramatic irony (hook **J**) in its strongest form, because the viewer isn't *told* something
the character doesn't know, they can **see** it. Every second CHIEF builds higher, the visible flaw
gets more load. That is an open loop with a tightening spring.

Compare `v1`: the seed is CHIEF's scooter in the no-parking zone — ironic, but the punishment arrives
via an **external agent**, a tow truck. Nothing the audience saw in frame 1 *causes* the ending; it
merely rhymes with it. The prediction-error research is specific that surprise also increases
attention to the cues that *preceded* it — which only pays if a preceding cue was actually the cause.

> Karma that arrives from outside the frame is a coincidence. Karma that arrives from something the
> viewer watched being planted is a mechanism. Mechanisms get rewatched.

### 2.5 The false victory is sold completely

`v3` is the only episode where the antagonist appears to **fully and finally win** — summit, trophy in
hand, confetti, held hero pose, music at its peak. The script is explicit about why: *"the false
victory must be sold completely here… or the reversal in C7 has nothing to invalidate."*

That is prediction error engineered on purpose. The viewer's model is allowed to fully commit, which
makes the break maximal. Elsewhere the outcome stays visibly pending, so the eventual reversal
confirms an expectation instead of breaking one.

Then the payoff is **one image that contains the whole story**: the spire collapses and the trophy
flies out of CHIEF's hands to land neatly on PIP's little tower, still standing exactly at the line.
Winner, loser, cause and rule in a single frame, readable muted, and screenshot-able — which is what
travels, since shares are the strongest engagement signal.

---

## 3. What v3 gets wrong too

Worth stating, because "be more like v3" is not sufficient.

- **It opens on a static wide establishing shot**, like everything else. Its frame-1 information is
  excellent; its frame-1 *motion* and framing are not. Fixing this in `v3`'s pattern is where the
  remaining upside is.
- **The stakes arrive before the conflict.** The contest is explained, then contested. Payoff-first
  ordering would show the collapse, or the trophy landing on the small tower, and then rewind.
- **No text layer.** The hook framework wants visual + text + verbal asserting one idea; `v3` runs on
  two. It happens to survive because its visual layer is unusually self-sufficient.
- **32 seconds for the idea.** Percentage viewed is the metric, and shortening a video raises it
  arithmetically. The 8-clip/32s skeleton is locked, but it is worth knowing that the locked length is
  above the 15–30s band the research keeps pointing at.

---

## 4. The extracted standard

What follows is the operative output of this analysis. It is now enforced in
[`.kiro/steering/video-generation-standards.md`](.kiro/steering/video-generation-standards.md) and is
applied to `v7`–`v17`.

### 4.1 The Cold-Open Inversion (replaces the establishing shot)

**C1 no longer establishes. C1 shows the outcome, mid-motion, and cuts away before it resolves.**

```
C1  0:00–0:015   COLD PAYOFF   the karma moment already in progress, tight,
                               mid-motion, one frame of it — no context
C1b 0:015–0:02   HARD CUT      to the goal-state diagram (the rule, drawn)
C2  0:02–0:06    REWIND        "four seconds earlier" — the setup, now
                               watched with the ending already known
```

The viewer is given the ending first, so the entire middle of the video becomes dramatic irony
instead of exposition. This satisfies the inversion rule, kills the static first frame, kills the
entrance, and lands the first micro-payoff **inside 1.5 seconds** instead of at 27.

Hard requirements for C1:
- **Motion is already underway.** Nothing enters frame. Something is falling, spilling, snapping, tipping.
- **Tight framing**, not wide. A subject filling significant frame area.
- **No character entrance.** Never again.
- **Reads muted, in one pass, with no reasoning step.**

### 4.2 The Goal Diagram (mandatory, from §2.1)

Every episode must contain, visible by 0:02, a **drawn win condition** — the `v3` arrow-at-the-line,
generalised:

| Premise type | The diagram |
|---|---|
| Contest | Target line + arrow, two positions, prize object |
| Limit / rule | The limit drawn as a pictogram, and the object that will exceed it |
| Capacity | A fill line, and the thing that will overflow it |
| Fairness | A balance, and the two things that will be weighed |

No words. An arrow, a line, a pictogram, a scale. If the rule of the world cannot be drawn, the
premise is not a Shorts premise.

### 4.3 The Scoreboard (from §2.2)

Both characters must be **doing the same task in the same frame**, so the contrast is behavioural, not
circumstantial. Where the premise has no natural contest, one must be constructed — PIP must be
visibly attempting the same goal by his own smaller method, in shot, not waiting offscreen.

### 4.4 The Load-Bearing Flaw (from §2.4)

The seed must be the **mechanical cause** of the ending, planted visibly, and it must accumulate
stress as the episode escalates. No external agents. If the karma arrives from outside the frame, the
episode is rebuilt until it doesn't.

### 4.5 The Full Commit (from §2.5)

The antagonist must **completely and convincingly win** before losing — trophy-in-hand, peak music,
held pose. Anything less and the reversal confirms rather than breaks.

### 4.6 The three-layer hook

Visual, text and verbal asserting **one** idea:

| Layer | Spec | Note |
|---|---|---|
| Visual | Cold payoff in motion | Carries the whole thing alone if needed |
| **Text** | **3–7 words, edit-layer overlay** | See below |
| Verbal | 5–10 words, no preamble | Never the same sentence as the text |

**On the text layer and the zero-text invariant.** The standards forbid baked-in on-frame text and the
hook framework requires a text layer. The resolution: the hook text is a **caption added in the edit,
never baked into the generated render** — which is exactly the carve-out the invariant already makes
for captions. So the rendered frames stay text-free and the published Short has a hook caption, placed
clear of the bottom bar and the right-hand action rail.

### 4.7 Ban the cadence

No two consecutive episodes may share an opening-line rhythm. `"One ___. One ___."` is retired.

---

## 5. Per-episode application

How the standard lands on each of `v7`–`v17`, and what had to change.

| | Cold payoff (C1) | Goal diagram | Verdict on the old opening |
|---|---|---|---|
| v7 | Umbrella inverting, ribs snapping | Dry patch outline under the awning | Entrance + weather report |
| v8 | The lock's rejection light, third refusal | Green/red scan pictogram on the panel | Entrance + delivery |
| v9 | The empty plate, fortress still standing | The single slice, centred on a shared plate | Entrance + table setting |
| v10 | 999 sheets erupting from the tray | Queue counter showing `999` vs `1` | Entrance + office wide |
| v11 | The barrier slamming down at item 11 | `10 ITEMS` pictogram + a counter at 11 | Entrance + store wide |
| v12 | Panel sparking under a jabbing glove | Floor indicator, stairs drawn beside it | Entrance + lobby wide |
| v13 | Rod snapping backward, gear in the air | Tackle box split, all-vs-nothing | Entrance + pond wide |
| v14 | The moat channelling the wave inward | Tide line drawn in the sand | Entrance + beach wide |
| v15 | Five doors bursting open at once | Capacity line inside a drum | Entrance + laundromat wide |
| v16 | The table splitting under the stack | A load-limit pictogram on the table leg | Entrance + library wide |
| v17 | The string snapping, spool spinning free | String-gauge comparison, thick vs thin | Entrance + hilltop wide |

`v17` additionally required its costume-lock break repaired (cap and medals no longer leave CHIEF) and
its advertiser-safe overshoot removed (no line wrapped around a wrist, no body towed) — both carried
over from the base audit.
