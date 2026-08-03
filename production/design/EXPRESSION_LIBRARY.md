# Expression Library

> **Status:** Locked · **Applies to:** every facial expression / reaction asset generated for any
> C-Cloning character · **Owner role:** Facial Acting Director / Animation Expression Designer /
> Asset Librarian
>
> **This is the canonical emotional language of the cast.** It defines the emotion taxonomy, the
> controlled vocabulary of expression names, intensity levels, the universal facial-acting standards,
> per-character overrides, expression asset IDs, prompt standards, and reuse/approval rules. **Future
> image generation must pick an expression from this library rather than inventing one.**

## Inheritance banner

This document is a **child of the character system** and inherits from all three foundation documents;
it never overrides them:

- **Appearance** → the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md). All line, color, shading, and
  rendering rules for faces (INK pupils, flat color, no gradients, one shadow tone, FX stroke rules)
  are inherited. This library adds *facial-acting* rules, not new visual law. On a visual question, the
  Lock wins.
- **Meaning / emotional arc** → the [Brand Bible](BRAND_BIBLE.md#emotional-design). Which emotions the
  brand needs, and the "worry → relief / smug → shock" arc that drives measurable behaviors, come from
  the Brand Bible. Expressions stay **advertiser-safe and benign** (sadness is cute, panic is comic).
- **Character system** → the [Character Bible](CHARACTER_BIBLE.md). The expression *system* rule —
  every character has a default resting face + a tailored core pack of ≥6 expressions — is defined
  there. **This document fulfils the Character Bible's promise** to
  *"canonicalize the universal emotional-beat taxonomy and map each character's pack onto it"*
  ([Character Bible → Asset Standards](CHARACTER_BIBLE.md#character-asset-standards)).

It also **defers to** (references, never restates):
- Naming & reuse → [Stage 2](../../docs/12-stage-2-channel-operating-system.md) and the
  [Visual Identity Lock asset-ID table](VISUAL_IDENTITY_LOCK.md#asset-id-naming).
- The shared face grammar → [Cast Style Guide](../characters/cast-style-guide.md).
- Locked per-character packs → the model sheets ([PIP](../characters/pip.md), [CHIEF](../characters/chief.md)).
- Ready-to-paste expression prompts & the worked reaction table → [visual-prompt template §4](../templates/visual-prompt-template.md)
  and [V1 characters-and-reactions](../../V1/02-characters-and-reactions.md).

---

## Table of contents

1. [Purpose](#purpose)
2. [Expression System](#expression-system)
3. [Expression Taxonomy](#expression-taxonomy)
4. [Expression Intensity](#expression-intensity)
5. [Universal Expression Standards](#universal-expression-standards)
6. [Character Overrides](#character-overrides)
7. [Expression Asset Naming](#expression-asset-naming)
8. [Prompt Standards](#prompt-standards)
9. [Production Workflow](#production-workflow)
10. [Quality Checklist](#quality-checklist)
11. [Future Integration](#future-integration)
12. [Repository Integration](#repository-integration)
13. [Change Control](#change-control)

---

## Purpose

The channel is **mute-first and expression-first**: with no dialogue and minimal motion, the *face
carries the story*. The [Brand Bible emotional design](BRAND_BIBLE.md#emotional-design) requires a
viewer to be moved through a precise arc (worry → hope → relief; smug → shock → panic) **with the sound
off**, and the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md) requires every frame to read at
thumbnail size. Expressions are therefore not decoration — they are the primary storytelling
instrument and a core recognition signal.

Expression consistency matters because:

- **It is the performance.** In a wordless format the expression *is* the acting; a wrong or off-model
  face breaks the beat the whole video is built around.
- **Recognition compounds.** A viewer learns PIP's worried eyes and CHIEF's smug half-smile; those
  faces are part of the [brand recognition system](BRAND_BIBLE.md#brand-recognition-system). Drift
  erodes it.
- **Reuse is the cost model.** A fixed, named, reusable expression pack per character is what lets a
  video be *assembled by swapping faces* rather than redrawn ([Cast Style Guide](../characters/cast-style-guide.md),
  [Stage 2 reuse economics](../../docs/12-stage-2-channel-operating-system.md)).
- **Automation needs a closed vocabulary.** Future tools and prompt frameworks must choose from a
  finite, named emotion set — never invent ad-hoc faces — so output stays on-model at scale.

> **Rule of thumb:** if the intended emotion is not clear from the face alone, muted, at thumbnail
> size — the expression has failed, no matter how well-rendered it is.

---

## Expression System

Six functional **types** of expression. Every expression asset is one of these; the type decides how it
is authored, stored, and used.

| Type | Definition | Stored as an asset? | Example |
|---|---|---|---|
| **Primary** | The character's **core pack** — the default emotional beats every recurring character ships at lock time (≥6, per the [Character Bible](CHARACTER_BIBLE.md#character-asset-standards)). | **Yes**, always | `CHAR_PIP_expr_worried` |
| **Secondary** | Additional canonical emotions minted **editorially** when a story needs one the core pack lacks (e.g. `curious`, `sheepish`). | Yes, when created | `CHAR_PIP_expr_curious` |
| **Micro** | A subtle single-feature shift held *within* a shot (a brow flick, a pupil shrink, a swallow) — a nuance layered on a stored expression. | Rarely; usually animated, not a separate asset | brow-raise on `smug` |
| **Reaction** | The **response face** to a story beat — a primary/secondary expression selected at a chosen [intensity](#expression-intensity) and mapped to a shot (the [V1 reaction→shot map](../../V1/02-characters-and-reactions.md)). | No new asset — it *selects* an existing one | Shot 7 PIP → `gleeful` (L3) |
| **Idle** | The character's **resting face** used during idle/loop motion (strut, fumble, wait). Equals the default resting expression. | Uses the neutral/default primary | PIP idle = `worried`; CHIEF idle = `smug` |
| **Transitional** | The **snap in-between** two states across a beat (the [3-stage snap](../A1-first-video/05-animation-spec.md) smug→shocked→panicked). Sequenced from stored endpoints; a unique in-between is minted **only** if a beat needs one. | Only when a unique in-between is required | `smug`→`shocked`→`panicked` |

**System rules**
- Every recurring character's **primary pack** must cover the six functional slots defined by the
  [Character Bible](CHARACTER_BIBLE.md#character-asset-standards): *neutral · a status face · a
  peak-emotion face · a shock/turn face · a payoff face · a signature button.*
- **Reaction and idle expressions do not create new assets** — they select an existing primary/secondary
  at an intensity. This keeps the library small and reuse high.
- **Transitions are sequenced, not painted** wherever possible (hold endpoint A → snap to endpoint B),
  matching the flat-2D pose-to-pose motion feel in the [animation spec](../A1-first-video/05-animation-spec.md).

---

## Expression Taxonomy

The canonical **emotion categories** and the **controlled vocabulary** of expression names that realize
them. This is the closed set generation must choose from.

- **LIVE** = the name is already a locked asset in a shipped character pack (do not rename).
- **AVAILABLE** = a reserved canonical name to *use when a story first needs it* (mint it editorially,
  then it becomes LIVE for that character). Do **not** invent a synonym for an AVAILABLE name.

| # | Emotion category | Canonical expression name(s) | Status | Brand/story role |
|---|---|---|---|---|
| 1 | **Neutral** | `neutral` | LIVE | Baseline / establishing; resting for a calm character |
| 2 | **Deadpan** (dry neutral) | `deadpan` | LIVE | Flat, unimpressed beat; comic underreaction |
| 3 | **Joy** | `gleeful` (peak `delighted` = AVAILABLE) | LIVE | The underdog's happiness; audience relief-share |
| 4 | **Sadness** | `teary` | LIVE | Cute, non-distressing hurt; cues injustice |
| 5 | **Fear / anxiety** | `worried` (low) · `panicked` (peak) | LIVE | Underdog worry; antagonist's comic panic at the turn |
| 6 | **Hope** | `hopeful` | LIVE | The turn toward the payoff; anticipation of justice |
| 7 | **Relief** | `relieved` | LIVE | The warm button; safe resolution |
| 8 | **Shock** | `shocked` | LIVE | The twist hit; the "didn't-see-it-coming" beat |
| 9 | **Pride / superiority** | `smug` (status) · `gloating` (active) · `triumphant` (peak) | LIVE | The antagonist's arrogance ladder that *earns* the karma |
| 10 | **Confusion** | `confused` | AVAILABLE | Setup for a reframe / misdirection beat |
| 11 | **Curiosity** | `curious` | AVAILABLE | Noticing the seed; leaning in |
| 12 | **Embarrassment** | `sheepish` | AVAILABLE | Benign, self-aware fluster (never humiliation of the weak) |
| 13 | **Suspicion** | `suspicious` | AVAILABLE | Narrow-eyed doubt; sensing something is off |
| 14 | **Thinking** | `thinking` | AVAILABLE | Scheming/plan beat (usually antagonist) |
| 15 | **Fatigue** | `weary` | AVAILABLE | Worn-down beat; comic exhaustion |
| 16 | **Determination** | `determined` | AVAILABLE | Resolve before an action (benign) |
| 17 | **Anticipation** | `eager` | AVAILABLE | Bracing for the payoff |
| 18 | **Indignation** (benign anger) | `indignant` | AVAILABLE | Comic huff — *never* rage; stays advertiser-safe |
| 19 | **Affection / warmth** | `fond` | AVAILABLE | Cast bonding beats (future ensemble) |

**Taxonomy rules**
- **Advertiser-safe ceiling** ([Brand Bible](BRAND_BIBLE.md#content-pillars)): no terror, rage, malice,
  or anguish. Fear reads as *comic panic*, anger as *indignant huff*, sadness as *cute/teary*.
- **One name per emotion per character.** If PIP needs "nervous," that is `worried` — do not add a
  synonym. New shades require a new *category* entry here first (via [Change Control](#change-control)).
- **Not every character carries every emotion.** A character's pack lists only the emotions its
  personality plays (PIP has no `smug`; CHIEF has no `teary`). See [Character Overrides](#character-overrides).
- **Reconciliation note.** The [Cast Style Guide](../characters/cast-style-guide.md) 6-slot template
  (`neutral · smug · shocked · gleeful · panicked · deadpan`) is the *generic default sheet*; this
  taxonomy is the canonical superset it draws from. Where a model sheet and this library differ on a
  character's live names, this library is authoritative and the model sheet is reconciled editorially
  (see [Repository Integration](#repository-integration)).

---

## Expression Intensity

Every expression supports **three intensity levels**. **Level 2 is the canonical baseline** (the stored
default with no suffix); L1 and L3 are optional variants generated only when a beat needs them.

| Level | Meaning | How it reads (within the flat-2D system) |
|---|---|---|
| **L1 — Subtle** | A restrained, low-key version for quiet beats and backgrounds. | Small deviation from neutral: slight brow tilt, eyes near-normal, small mouth change, no FX, upright/relaxed body. |
| **L2 — Standard** (baseline) | The default, clearly readable version — the stored asset. | Clear brow + eye + mouth change; head tilt; readable at thumbnail size; at most a single subtle FX (e.g. one sweat bead). |
| **L3 — Extreme / comic peak** | The big "hero" beat (the flex, the shock, the glee) held on screen. | Oversized shapes: eyes very wide or squeezed, mouth large, strong head/shoulder involvement, hands up; benign FX allowed (`FX_sparkle_v1`, `FX_impact_star_v1`, `FX_motionlines_v1`, sweat drop) per the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md#line-system). |

**Visual deltas that scale with intensity** (all stay within the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md) — flat color, INK pupils, no gradients, one shadow tone):

| Feature | L1 | L2 | L3 |
|---|---|---|---|
| **Eyes** | near-neutral aperture | clearly widened/narrowed | extreme (huge / squeezed shut) |
| **Brows** | small tilt | full angle (up=fear/hope, down=anger/focus) | pushed to the silhouette edge |
| **Mouth** | small change | clear shape (frown, grin, open) | oversized (gasp, beaming grin) |
| **Head/body** | head only | head tilt + shoulders | whole-body lean, hands up |
| **FX** | none | ≤1 subtle (sweat bead) | benign comic FX allowed |
| **Hold (timing)** | short | standard | **long hold** (~0.5–1.5 s peak) per the [animation spec](../A1-first-video/05-animation-spec.md) |

> **Advertiser-safe at every level.** L3 is *bigger and funnier*, never *darker*. Escalate scale and
> comedy, never distress.

---

## Universal Expression Standards

The facial-acting rules every expression obeys, for every character. These extend — and never
contradict — the face guidance in the [Cast Style Guide](../characters/cast-style-guide.md) ("big
readable eyes + bold brows; mouth secondary") and the render law in the
[Visual Identity Lock](VISUAL_IDENTITY_LOCK.md).

- **Eyes (the primary instrument).** Eyes carry ~70% of the read. Pupils are `INK`; shape and aperture
  do the work (wide = fear/shock/joy, narrowed = smug/suspicion, softly closed = relief/content).
  Glossy highlight shapes (flat, hard-edged) signal tears/hope — never gradients.
- **Mouth (secondary).** Supports, never leads (mute-first). Kept small by default; opens only for
  genuine peaks (gasp, big grin). Because the channel is **mute-first with no lip-sync**
  ([animation spec](../A1-first-video/05-animation-spec.md)), the mouth animates *for expression only*.
- **Brows (the amplifier).** Bold and readable; angle sets the emotion family (raised = fear/hope/
  surprise, lowered = anger/focus, asymmetric = smug/suspicion/skepticism).
- **Eyelids.** Aperture is an emotion dial: fully open = alarm/shock; half-lidded = smug/bored/deadpan;
  softly closed = relief/joy. Keep lids as clean flat shapes.
- **Head angle.** Chin up = pride/superiority; chin down/hunched = worry/sadness/submission; tilt =
  curiosity/hope. Head angle must reinforce, never fight, the face.
- **Body language.** The face is backed by posture at L2–L3 (shoulders up = tension, open = relief,
  puffed = pride, shrunk = fear). Ties into the [Pose Library](#future-integration).
- **Timing.** Snappy pose-to-pose; **hold the peak** (a beat of stillness sells the emotion), and use
  the **3-stage snap** for turns ([animation spec](../A1-first-video/05-animation-spec.md)). No easing
  mush; expressions change on clear poses.
- **Symmetry.** Default **symmetric**. Deliberate **asymmetry** (one raised brow, a cocked head, a
  half-smile) is reserved for *smug / suspicious / skeptical / gloating* reads — it is a status/irony
  cue, used intentionally.
- **Silhouette readability.** The expression must register in the head silhouette and at thumbnail size
  ([Visual Identity Lock — Shape Language](VISUAL_IDENTITY_LOCK.md#shape-language)): big shapes over
  fine detail; test by shrinking the face to grid-thumbnail size.

---

## Character Overrides

Each character **maps the shared taxonomy onto its own personality** — a subset of emotions, tuned to
its face and default resting state — per the [Character Bible expression system](CHARACTER_BIBLE.md#character-asset-standards).
Model sheets remain the authoritative source for each character's *face construction*; this section
canonicalizes each character's *emotional vocabulary*.

### PIP — the underdog / mascot
Full character profile: [Character Bible → PIP](CHARACTER_BIBLE.md#pip). Face spec:
[PIP model sheet](../characters/pip.md). **Default resting face:** `worried`. **Emotional band:**
soft, sympathetic, benign — sadness is *cute*, joy is *warm*, never manic.

| Expression | Emotion | Default level | Face read (eyes primary) | Typical use |
|---|---|---|---|---|
| `CHAR_PIP_expr_neutral` | Neutral | L1–L2 | Calm, soft small smile | Establishing / idle-calm |
| `CHAR_PIP_expr_worried` | Fear (low) | L2 | Big anxious eyes, tiny frown, slight hunch — **resting face** | Setup, being bullied |
| `CHAR_PIP_expr_teary` | Sadness | L2 | Glossy watery big eyes, quivering tiny mouth (cute, not distressing) | Peak injustice |
| `CHAR_PIP_expr_hopeful` | Hope | L2 | Look up, small hopeful spark, tiny open mouth | The turn / karma arriving |
| `CHAR_PIP_expr_gleeful` | Joy | L3 | Wide happy eyes, big cheerful grin | The payoff moment |
| `CHAR_PIP_expr_relieved` | Relief | L2 | Relaxed smile, eyes softly closed | The warm button |
| `CHAR_PIP_expr_wave` | Relief + gesture (**signature button**) | L2 | `relieved` face **paired with** a small friendly hand wave | Closing beat / loop seam |

> **Note on `wave`.** `CHAR_PIP_expr_wave` is PIP's *signature button*: the `relieved` face combined
> with a wave gesture. The **arm/hand gesture** itself is a pose owned by the future
> [Pose Library](#future-integration) (`CHAR_PIP_pose_wave`); this asset is the paired face+button.
> Descriptors for all PIP expressions are the paste-ready ones in
> [V1 characters-and-reactions](../../V1/02-characters-and-reactions.md).

PIP's arc across a typical video (the [reaction→shot map](../../V1/02-characters-and-reactions.md)):
**worried → teary → hopeful → gleeful → relieved (wave)**. PIP **never** carries `smug`, `gloating`,
`triumphant`, `indignant`, or any aggressive read (see [Character Bible — things PIP can never do](CHARACTER_BIBLE.md#pip)).

### CHIEF — the antagonist (contrast reference)
Face spec: [CHIEF model sheet](../characters/chief.md). **Default resting face:** `smug`. CHIEF owns
the **pride ladder** — `smug` (status) → `gloating` (active) → `triumphant` (L3 peak, with
`FX_sparkle_v1`) — then breaks via the **3-stage snap** `shocked → panicked` at the twist
([animation spec](../A1-first-video/05-animation-spec.md)). CHIEF **never** carries `teary`, `hopeful`,
or `relieved` — those are the underdog's band. This deliberate *opposite emotional vocabulary* is what
makes the two silhouettes and faces instantly distinguishable.

### Future characters
Every new recurring character, at [creation](CHARACTER_BIBLE.md#character-lifecycle), declares: (1) its
**default resting face**, and (2) the **subset of the taxonomy** its personality plays (with any
AVAILABLE names it activates). It reuses canonical names — it does **not** invent synonyms. Variation is
allowed in *face construction and which emotions it favors*, never in the *shared emotional vocabulary
or the render law*. Fill this in via the [Future Character Template](CHARACTER_BIBLE.md#future-character-template).

---

## Expression Asset Naming

Extends the locked convention in the [Visual Identity Lock asset-ID table](VISUAL_IDENTITY_LOCK.md#asset-id-naming)
and [Character Bible naming standards](CHARACTER_BIBLE.md#character-naming-standards). No base rule is
redefined here.

| Thing | Convention | Example |
|---|---|---|
| Expression (baseline, = L2) | `CHAR_[NAME]_expr_[name]` | `CHAR_PIP_expr_hopeful` |
| Expression intensity variant | `CHAR_[NAME]_expr_[name]_l[1\|2\|3]` | `CHAR_PIP_expr_gleeful_l3` |
| Transitional in-between (only if minted) | `CHAR_[NAME]_expr_[name]` (its own single-concept name) | `CHAR_CHIEF_expr_dawning` |

**Naming rules (extensions):**
- `[name]` is a **canonical expression name from the [taxonomy](#expression-taxonomy)** — lowercase,
  hyphen-free, single concept ([Character Bible](CHARACTER_BIBLE.md#character-naming-standards)). Never
  a synonym or an invented word.
- **Intensity suffix is optional.** No suffix = the **L2 baseline**. Add `_l1` / `_l3` only for stored
  intensity variants; most beats select the baseline and let animation scale it.
- **Adding an expression is editorial** — it does **not** bump the character `_v#`
  ([Character Bible lifecycle](CHARACTER_BIBLE.md#character-lifecycle)). Only a locked-silhouette change
  bumps the version.
- Transitions are normally **sequenced from existing endpoints** and get an asset ID only when a unique
  in-between is required.

---

## Prompt Standards

The **prompt architecture** for expression assets. This section defines structure only; it does **not**
restate the style prefix or the paste-ready scaffolds — those live in the
[visual-prompt template](../templates/visual-prompt-template.md) (§4 character-asset + the 6-expression
sheet) and the worked, per-expression descriptors in
[V1 characters-and-reactions](../../V1/02-characters-and-reactions.md). Every expression prompt **must**:

- **prepend the locked style prefix + palette** from the [visual-prompt template](../templates/visual-prompt-template.md);
- **attach the character's approved reference sheet** (reference image / fixed seed) so identity holds;
- **name the target asset ID** and the **canonical expression name + intensity** from this library.

| Prompt type | Purpose | Structure (beyond style prefix + reference sheet) | Reference scaffold |
|---|---|---|---|
| **Single expression** | One face asset | "close-up of \<NAME\>'s face and upper body" + the taxonomy descriptor + intensity | [V1 reactions table](../../V1/02-characters-and-reactions.md) |
| **Expression sheet** | The whole pack at once | "expression sheet: \<list the character's pack names\>, consistent proportions" | [visual-prompt template §4](../templates/visual-prompt-template.md) |
| **Emotion comparison** | Same emotion across L1/L2/L3 (calibration) | "three versions of \<name\>: subtle, standard, extreme — same character" | derived from the [Intensity](#expression-intensity) deltas |
| **Reaction sequence** | The snap across a beat | "sequence: \<endpoint A\> → \<endpoint B\> → \<endpoint C\>, same character, pose-to-pose" | [animation spec 3-stage snap](../A1-first-video/05-animation-spec.md) |

**One expression (or one clearly-ordered sequence) per prompt.** Keep the mouth minimal and the eyes
primary; request benign FX by asset ID at L3 only.

---

## Production Workflow

Expressions follow the [Character Bible lifecycle](CHARACTER_BIBLE.md#character-lifecycle) as **editorial
additions** to an already-locked character.

1. **Generation.** Pick the canonical expression + intensity from the [taxonomy](#expression-taxonomy);
   generate with the character's reference sheet attached and the
   [prompt standards](#prompt-standards).
2. **Review.** Run the [Quality Checklist](#quality-checklist) plus the
   [Visual Identity Lock quality checklist](VISUAL_IDENTITY_LOCK.md#quality-checklist) and the
   [Character Bible quality checklist](CHARACTER_BIBLE.md#character-quality-checklist). Off-model →
   regenerate, never settle.
3. **Approval.** The emotion must read muted at thumbnail size, sit inside the character's declared band,
   and stay advertiser-safe.
4. **Versioning.** File as `CHAR_[NAME]_expr_[name]` (optional `_l#`). Adding an expression is
   **editorial — no `_v#` bump**. If the character's *silhouette* changes, the whole pack re-versions
   with the character.
5. **Reuse.** Reaction/idle beats **select** an existing expression at an intensity — they do **not**
   generate new assets. Reuse-first is the cost moat
   ([Stage 2](../../docs/12-stage-2-channel-operating-system.md)).
6. **Deprecation.** Retire an expression only by a logged decision
   ([Decision Log](../../docs/21-decision-log.md)); mark it `deprecated` in the model sheet, keep the
   asset (published videos reference it), and stop using it in new videos. Replacements use a **new
   canonical name**, never a silent redefinition of the old one.

---

## Quality Checklist

Run before accepting **any** expression asset (in addition to the
[Visual Identity Lock](VISUAL_IDENTITY_LOCK.md#quality-checklist) and
[Character Bible](CHARACTER_BIBLE.md#character-quality-checklist) checklists). One failure = reject and
regenerate.

- [ ] **Reads muted at thumbnail size** — the emotion is unmistakable from the face alone.
- [ ] **Eyes lead** the read; mouth stays secondary (mute-first).
- [ ] **Canonical name** — the expression is a name from the [taxonomy](#expression-taxonomy) (no
      invented synonym), correctly mapped to its emotion.
- [ ] **Correct intensity** — matches the intended L1 / L2 / L3 for the beat.
- [ ] **In the character's band** — the emotion is one this character is allowed to play (e.g. PIP is
      never smug/gloating).
- [ ] **Advertiser-safe** — sadness cute, panic comic; no distress, rage, or malice.
- [ ] **On-model face** — proportions, INK pupils, flat color, one shadow tone; signature accents present.
- [ ] **Symmetry intentional** — asymmetry only for smug/suspicious/skeptical reads.
- [ ] **FX legal** — any FX is a benign, flat, INK/`BRAND_YELLOW` asset at L3 only.
- [ ] **Correct ID** — `CHAR_[NAME]_expr_[name]` (+ optional `_l#`), filed in the library.

---

## Future Integration

This library is a **parent** to the remaining character-scoped and shot-level documents. Each must
reference an expression by its canonical name rather than describing a face from scratch.

| Consumer (future doc) | How it uses this library |
|---|---|
| **[Pose Library](POSE_LIBRARY.md)** ✅ | Pairs each `expr_[name]` with body poses (`pose_[name]`); the **face+gesture buttons** like PIP's `wave` are pose+expression composites. Body language here becomes pose entries. |
| **[Animation Language & Motion System](ANIMATION_LANGUAGE_MOTION_SYSTEM.md)** ✅ | Consumes the [intensity holds](#expression-intensity), the **3-stage snap**, and the **no-lip-sync / expression-only mouth** rule to define timing curves and the emotional beat map. |
| **Wallpaper Prompt Framework** | Selects a **hero expression** (usually an L3 `gleeful` / `smug` / `shocked`) for channel art, thumbnails, and wallpapers per the [thumbnail spec](../templates/thumbnail-spec.md). |
| **Shot Generation** | Uses the [reaction→shot mapping](../../V1/02-characters-and-reactions.md) pattern: each shot names the character's expression + intensity, driving the [visual-prompt template](../templates/visual-prompt-template.md) `SUBJECT` slot. |
| **Character Assets** | Defines what a complete **expression pack** is, so a new character's [asset set](CHARACTER_BIBLE.md#character-asset-standards) is considered done only when its declared pack exists. |

---

## Repository Integration

Additive one-line pointers are added in this branch at the highest-traffic entry points; deeper links
are recommendations to avoid over-editing locked docs.

| Document | Relationship | Action |
|---|---|---|
| [`production/design/README.md`](README.md) | Design/identity folder index | Add the Expression Library + update planned-children note (done) |
| [`production/design/CHARACTER_BIBLE.md`](CHARACTER_BIBLE.md) | Parent (character system) | Point its "forthcoming Expression Library" references at this now-existing doc (done) |
| [`docs/00-index.md`](../../docs/00-index.md) | Master doc map | List the Expression Library under Design standards (done) |
| [`production/README.md`](../README.md) | Production folder map | Add to the `design/` tree + a traceability row (done) |
| [`production/characters/cast-style-guide.md`](../characters/cast-style-guide.md) | Holds the generic 6-slot template | Point its "standard expression pack" line to this canonical library (done) |
| [`production/characters/pip.md`](../characters/pip.md) | PIP's face spec | Add `gleeful` to PIP's pack (reconciliation) + pointer to this library (done) |
| [`production/characters/chief.md`](../characters/chief.md) | CHIEF's face spec | Pointer to this library (done) |

**Reconciliation performed (no contradiction left behind):**
- **PIP `gleeful`.** [V1](../../V1/02-characters-and-reactions.md) and the
  [Character Bible](CHARACTER_BIBLE.md#pip) use `CHAR_PIP_expr_gleeful`, but the
  [PIP model sheet](../characters/pip.md) pack omitted it. `gleeful` is added to PIP's pack in the model
  sheet as an **editorial** addition (no `_v#` bump), so the model sheet, V1, the Character Bible, and
  this library now agree.
- **Generic vs. per-character packs.** The [Cast Style Guide](../characters/cast-style-guide.md)
  6-slot template is confirmed as the *default sheet*; this library is the canonical superset. A pointer
  is added there so the relationship is explicit.

**No-duplication guarantee.** Render law stays in the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md);
emotional arc/tone in the [Brand Bible](BRAND_BIBLE.md); the character system and per-character face
specs in the [Character Bible](CHARACTER_BIBLE.md) and model sheets; naming/reuse in
[Stage 2](../../docs/12-stage-2-channel-operating-system.md). This library owns only the **emotion
taxonomy, intensity model, facial-acting standards, and per-character emotional vocabulary**,
referencing the rest.

---

## Change Control

A **locked** document, governed like the [Locked Roadmap](../../docs/03-locked-roadmap.md) and
[Decision Log](../../docs/21-decision-log.md).

- **Editorial changes** (adding an expression to a character, a new intensity variant, a new AVAILABLE
  name, clarifications, cross-links) may be made freely; **no version bump**.
- **Substantive changes** (adding/removing an **emotion category**, changing the intensity model or a
  universal standard, changing a character's default resting face) require: (1) a rationale in the
  [Decision Log](../../docs/21-decision-log.md), (2) a pass through the
  [Stage 2 5-Gate test](../../docs/12-stage-2-channel-operating-system.md), and (3) confirmation that no
  [locked decision](../../docs/03-locked-roadmap.md) or root document is contradicted.
- **New expression names** must be added to the [taxonomy](#expression-taxonomy) here **before** they
  may appear in any prompt or asset — this is what keeps generation from inventing faces.

> **The face is the performance.** When in doubt, choose the expression that makes the emotion
> unmistakable with the sound off.
