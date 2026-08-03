# Pose Library

> **Status:** Locked · **Applies to:** every body pose / physical-acting asset generated for any
> C-Cloning character · **Owner role:** Body Language Director / Character Animator / Asset Librarian
>
> **This is the canonical body-language system of the cast.** It defines how characters communicate
> through posture, balance, gesture, silhouette, and physical acting — the pose taxonomy, intensity
> levels, universal body-language rules, pose+expression pairing, per-character overrides, pose asset
> IDs, prompt standards, and reuse/approval rules. **Future image generation must pick a pose from this
> library rather than inventing one.**
>
> **The [Expression Library](EXPRESSION_LIBRARY.md) explains the face; this document explains the
> body.** Together with the face they form one performance.

## Inheritance banner

This document is a **child of the character system** and inherits from all four foundation documents;
it never overrides them:

- **Appearance** → the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md). Silhouette philosophy, shape
  language (round = kind, stiff/angular = arrogance), visual weight, composition, negative space, and
  all rendering law are inherited. This library adds *body-acting* rules, not new visual law. On a
  visual question, the Lock wins.
- **Meaning / acting tone** → the [Brand Bible](BRAND_BIBLE.md). Poses serve the
  [emotional design arc](BRAND_BIBLE.md#emotional-design) and the "prefer a *pose* over a line"
  rule ([Brand Voice](BRAND_BIBLE.md#brand-voice)); they stay **advertiser-safe** (punch up at
  arrogance, never down at the weak — [content pillars](BRAND_BIBLE.md#content-pillars)).
- **Character system** → the [Character Bible](CHARACTER_BIBLE.md). The pose *system* rule — every
  character ships a reusable `CHAR_[NAME]_pose_[name]` set for the story beats it plays — and each
  character's **pose philosophy** are defined there
  ([Asset Standards](CHARACTER_BIBLE.md#character-asset-standards),
  [PIP → Pose philosophy](CHARACTER_BIBLE.md#pip)). This library canonicalizes and extends that set.
- **Faces / pairing** → the [Expression Library](EXPRESSION_LIBRARY.md). Body language backs the face
  ("shoulders up = tension, open = relief, puffed = pride, shrunk = fear"); this library owns the
  **body** half of each beat and the [pose+expression pairing](#pose--expression-pairing) that joins
  them. The Expression Library explicitly hands "body language becomes pose entries" to this document.

It also **defers to** (references, never restates):
- Naming & reuse → [Stage 2](../../docs/12-stage-2-channel-operating-system.md) and the
  [Visual Identity Lock asset-ID table](VISUAL_IDENTITY_LOCK.md#asset-id-naming).
- The shared art grammar → [Cast Style Guide](../characters/cast-style-guide.md) ("snappy,
  pose-to-pose; strong silhouettes; oversized head + hands for expression and prop gags").
- Locked per-character build/stance → the model sheets ([PIP](../characters/pip.md), [CHIEF](../characters/chief.md)).
- Worked staging examples → the [A1 storyboard](../A1-first-video/03-storyboard.md) and
  [V1 script](../../V1/01-script.md).

> **Ownership boundary (important).** This library owns the **static pose** — the body's *shape at a
> single beat*. **Motion, timing, and the transitions between poses** (easing, the pose-to-pose snap,
> holds, the loop) belong to the future **Animation Language** doc; they are referenced here, not
> claimed. A pose is a *frame*; animation is the *change between frames*.

---

## Table of contents

1. [Purpose](#purpose)
2. [Pose Philosophy](#pose-philosophy)
3. [Pose Taxonomy](#pose-taxonomy)
4. [Pose Intensity](#pose-intensity)
5. [Universal Body Language Rules](#universal-body-language-rules)
6. [Pose + Expression Pairing](#pose--expression-pairing)
7. [Character Overrides](#character-overrides)
8. [Pose Asset Naming](#pose-asset-naming)
9. [Prompt Standards](#prompt-standards)
10. [Production Workflow](#production-workflow)
11. [Quality Checklist](#quality-checklist)
12. [Future Integration](#future-integration)
13. [Repository Integration](#repository-integration)
14. [Change Control](#change-control)

---

## Purpose

The channel is **mute-first and expression-first**, and in a wordless, minimal-motion format the
*body* is the other half of the acting. A viewer must read "who has power, who is the underdog, and
what just happened" from **silhouette and posture alone**, muted, at thumbnail size
([Visual Identity Lock](VISUAL_IDENTITY_LOCK.md#core-visual-principles)). Where the
[Expression Library](EXPRESSION_LIBRARY.md) makes the *face* carry emotion, the pose makes the *body*
carry **status, intent, and story beat**.

Body language is critical because:

- **It is half the performance.** The [Brand Bible](BRAND_BIBLE.md#brand-voice) mandates "a *pose* over
  a line": the situation must read from staging, not words.
- **It signals status instantly.** The whole [NP1 Comeuppance](../../intelligence/06-narrative-pattern-library.md)
  engine depends on an instant read of *arrogant vs. sympathetic* — and that read is carried by posture
  (chest-out strut vs. timid hunch) before the face is even parsed.
- **It is a recognition signal.** CHIEF's heels-together strut and PIP's soft slouch are part of the
  [brand recognition system](BRAND_BIBLE.md#brand-recognition-system). Drift in body-acting erodes it.
- **Reuse is the cost model.** A fixed, named, reusable pose set per character lets a video be
  *assembled by posing the cast* rather than redrawn ([Stage 2 reuse economics](../../docs/12-stage-2-channel-operating-system.md)).
- **Automation needs a closed vocabulary.** Prompt frameworks and shot generation must select from a
  finite, named pose set — never invent ad-hoc body shapes — so output stays on-model at scale.

> **Rule of thumb:** if the beat (who has power, what they're doing) is not clear from the black
> **silhouette** alone, the pose has failed — no matter how well the face is drawn.

---

## Pose Philosophy

The acting principles every pose obeys. These apply the roots to the *body*; they do not restate them.

- **Readable silhouettes.** The pose must be identifiable filled 100% black
  ([Visual Identity Lock — Shape Language](VISUAL_IDENTITY_LOCK.md#shape-language)). Limbs and props
  read *outside* the torso silhouette (no arms lost against the body); the action is legible as a
  black shape.
- **Exaggerated clarity.** Push the pose past life — a strut is *very* puffed, a cower is *very* small.
  Clear beats a subtle pose that "reads real." Exaggeration scales with [intensity](#pose-intensity)
  but **never breaks the locked silhouette** (proportions, signature accents stay fixed).
- **Visual simplicity.** One clear line of action, few big shapes, one key action per pose
  ([Composition Rules](VISUAL_IDENTITY_LOCK.md#composition-rules)). No busy or twisted contortions.
- **Mobile-first readability.** The pose must survive a vertical 9:16 frame viewed a few inches tall.
  Test at thumbnail size; if the action disappears, enlarge/simplify the pose.
- **Advertiser-safe acting.** Physical comedy stays benign ([Brand Bible](BRAND_BIBLE.md#content-pillars)):
  no real violence, no cruelty, no humiliating the underdog. A "fall" or "flail" is *comic*, never
  painful; karma lands on the arrogant, never on the weak.
- **Emotional clarity.** The body must agree with the face. Posture and expression express the *same*
  beat at the *same* intensity ([Pose + Expression Pairing](#pose--expression-pairing)); a mismatched
  body and face is off-model.
- **Status-first staging.** Pose is the channel's primary **status** instrument: big/upright/open =
  power/arrogance; small/hunched/closed = underdog/fear. This is what makes the audience pick a side.

---

## Pose Taxonomy

The canonical **pose categories** and the **controlled vocabulary** of pose names. This is the closed
set generation must choose from (mirrors the [Expression Library](EXPRESSION_LIBRARY.md#expression-taxonomy)
model).

- **IN USE** = the pose appears in the shipped [A1/V1](../A1-first-video/03-storyboard.md) work and
  should be captured as a named pose asset for its character.
- **AVAILABLE** = a reserved canonical name to *use when a story first needs it* (mint it editorially,
  then it becomes in use for that character). Do **not** invent a synonym for an AVAILABLE name.

| # | Category | Canonical pose name | Family | Status | Natural expression pairing |
|---|---|---|---|---|---|
| 1 | **Idle** | `idle` | Base | IN USE | resting face (`worried`/`smug`) |
| 2 | **Standing** | `stand` | Base | AVAILABLE | `neutral` |
| 3 | **Waiting** | `wait` | Base | AVAILABLE | `neutral`/`worried` |
| 4 | **Walking** | `walk` | Locomotion | AVAILABLE | `neutral` |
| 5 | **Running** | `run` | Locomotion | AVAILABLE | `panicked`/`eager` |
| 6 | **Strut** (proud walk) | `strut` | Locomotion | IN USE | `smug` |
| 7 | **Jumping** | `jump` | Locomotion | AVAILABLE | `gleeful` |
| 8 | **Falling** | `fall` | Locomotion | AVAILABLE | `shocked`/`panicked` |
| 9 | **Sitting** | `sit` | Base | AVAILABLE | any |
| 10 | **Pointing** | `point` | Gesture | IN USE | `gloating`/`smug` |
| 11 | **Holding** (a prop) | `hold` | Gesture | IN USE | any (prop-dependent) |
| 12 | **Reaching** | `reach` | Gesture | IN USE | `hopeful` |
| 13 | **Greeting / Goodbye** | `wave` | Gesture | IN USE | `relieved`/`neutral` |
| 14 | **Bowing** | `bow` | Gesture | AVAILABLE | `sheepish`/`gloating` |
| 15 | **Curiosity** (lean in) | `leanin` | Reaction | IN USE | `curious`/`hopeful` |
| 16 | **Thinking** | `ponder` | Reaction | AVAILABLE | `thinking` |
| 17 | **Surprised** (recoil) | `recoil` | Reaction | IN USE | `shocked` |
| 18 | **Scared** (cower/shrink) | `shrink` | Reaction | IN USE | `worried`/`teary` |
| 19 | **Flailing** (panic) | `flail` | Reaction | IN USE | `panicked` |
| 20 | **Celebrating** | `celebrate` | Payoff | IN USE | `gleeful` |
| 21 | **Victory** (hero pose) | `victory` | Payoff | IN USE | `triumphant` |
| 22 | **Defeat** (slump) | `slump` | Payoff | IN USE | `teary`/`defeated` |
| 23 | **Relieved** (relaxed open) | `relaxed` | Payoff | IN USE | `relieved` |

**Taxonomy rules**
- **Families** group poses by function (Base, Locomotion, Gesture, Reaction, Payoff) so a character's
  pose set is planned for coverage, not collected ad hoc.
- **One name per body-beat per character.** If PIP needs "cowering," that is `shrink` — do not add a
  synonym. New body-beats require a new *category* entry here first (via [Change Control](#change-control)).
- **Not every character carries every pose.** A character's set lists only the poses its role plays
  (PIP has no `strut`/`victory`; CHIEF has no `shrink`/`relaxed`). See [Character Overrides](#character-overrides).
- **Composite buttons.** A signature "button" like PIP's wave is a **pose + expression composite**:
  the `wave` pose paired with the `relieved` expression (surfaced as the
  [`CHAR_PIP_expr_wave`](EXPRESSION_LIBRARY.md#character-overrides) button). The **gesture** is owned
  here (`CHAR_PIP_pose_wave`); the **face** is owned by the Expression Library.

---

## Pose Intensity

Every pose supports **three intensity levels**. **Level 2 is the canonical baseline** (the stored
default with no suffix); L1 and L3 are optional variants generated only when a beat needs them. Body
exaggeration scales with level **while the locked silhouette is preserved** — proportions, head-to-body
ratio, and signature accents (PIP's scarf, CHIEF's cap+sash+medals) **never** change with intensity.

| Level | Meaning | How the body reads |
|---|---|---|
| **L1 — Subtle** | Restrained, quiet-beat or background version. | Small deviation from neutral stance: slight lean, arms near the body, modest weight shift. |
| **L2 — Standard** (baseline) | The default, clearly readable pose — the stored asset. | Clear line of action, defined weight shift, arms read outside the silhouette, one obvious key action. |
| **L3 — Extreme / comic peak** | The big "hero" beat (the strut, the victory, the flail) held on screen. | Maximum push: extreme lean/arch, wide limbs, big negative-space shape, whole-body commitment; benign comic FX allowed (`FX_motionlines_v1`, `FX_impact_star_v1`) per the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md#line-system). |

**What scales vs. what is fixed:**

| Scales with intensity | Locked at every level |
|---|---|
| Line-of-action curvature, lean/arch angle | Head-to-body proportion ([model sheet](../characters/README.md)) |
| Limb spread, arm/hand amplitude | Signature silhouette accents (scarf; cap+sash+medals) |
| Weight-shift extremity, negative-space size | Palette roles, outline weight ([Visual Identity Lock](VISUAL_IDENTITY_LOCK.md)) |
| Comic FX (L3 only) | Advertiser-safe ceiling (benign, no real harm) |

> **Match the face.** A pose's intensity should match its paired expression's
> [intensity](EXPRESSION_LIBRARY.md#expression-intensity) (an L3 `victory` pose pairs with an L3
> `triumphant` face). Body and face escalate together.

---

## Universal Body Language Rules

The body-mechanics rules every pose obeys, for every character. These are the **net-new knowledge this
library owns**; they extend the [silhouette](VISUAL_IDENTITY_LOCK.md#shape-language) and
[composition](VISUAL_IDENTITY_LOCK.md#composition-rules) rules of the Visual Identity Lock into physical
acting.

- **Head tilt.** Chin **up** = pride/superiority (CHIEF); chin **down / tucked** = worry, submission,
  sadness (PIP); **tilt** = curiosity/hope. The head leads the read and must agree with the face.
- **Shoulder angle.** **Raised/squared** = tension or aggression; **puffed/back** = pride; **rounded/
  dropped** = fear, defeat, or relief (dropped-open). Shoulders are the fastest status tell after
  height.
- **Arm spacing.** Arms **wide/away from body** = confidence, celebration, threat-display; arms **tucked/
  crossed/clutched** = fear, timidity, self-protection. Arms must read **outside** the torso silhouette
  so the pose is legible in black.
- **Hand visibility.** Hands are oversized for gesture ([Cast Style Guide](../characters/cast-style-guide.md));
  keep them **visible and unambiguous** — a point, a hold, a wave, a flail. Never bury both hands where
  the gesture is lost.
- **Leg positioning.** **Heels-together / stiff** = pomposity (CHIEF's strut); **feet planted wide** =
  stability/confidence; **knees-together / small stance** = timidity (PIP); **off-balance / mid-air** =
  fall/flail. Legs set the character's relationship to the ground.
- **Center of gravity.** **High and forward** = eager/aggressive/proud; **low and back** = timid/
  retreating/defeated. Shifting the CoG is the core of a status pose.
- **Weight distribution.** Show *where the weight is* — planted on one hip (smug), on the back foot
  (recoil), collapsed down (slump), lifted onto toes (celebrate). A weightless pose reads as floaty and
  off-model.
- **Balance.** A held pose is **stably balanced** (readable, poster-clear); an action beat may be
  **deliberately off-balance** (mid-fall, yanked, flailing) — but only for reaction/locomotion poses,
  never for a "held" status pose.
- **Line of action.** One **single, clear line of action** through the whole body (a C-curve for a
  cower, a proud back-arch for a strut, a big diagonal for a victory reach). No conflicting curves; the
  line is the pose.
- **Negative space.** Use the space *between* limbs and around the body as a shape
  ([Composition Rules](VISUAL_IDENTITY_LOCK.md#composition-rules)): open negative space = confidence/
  celebration; closed/compact = fear. Keep the key action's negative space clean and thumb-safe.
- **Silhouette readability.** The final test: fill the pose 100% black — the character, the signature
  accent, and the action must all still read. If two poses look identical in silhouette, differentiate
  them.

---

## Pose + Expression Pairing

The body and face express the **same beat at the same intensity**. This table is the reusable mapping
that joins this library to the [Expression Library](EXPRESSION_LIBRARY.md); shot/idea generation names
*both* an expression and a pose for each character in a beat.

| Story beat | Emotion (face) | Body pose | Body read |
|---|---|---|---|
| Establish underdog | `worried` | `idle` / `shrink` | small, hunched, tucked arms, low CoG |
| Establish authority | `smug` | `strut` / `stand` | chest-out, chin-up, heels-together, high CoG |
| Bully acts | `gloating` | `point` / `hold` | arm wide to point/brandish a prop |
| Injustice peaks | `teary` | `slump` | collapsed down, weight dropped |
| The turn arrives | `hopeful` | `leanin` / `reach` | head-up tilt, reaching toward the payoff |
| Peak arrogance | `triumphant` | `victory` | podium, arms/prop raised, max open negative space |
| Twist hits (antagonist) | `shocked` → `panicked` | `recoil` → `flail` | weight thrown back → limbs flailing, off-balance |
| Payoff (underdog) | `gleeful` | `celebrate` | open, lifted, wide arms |
| Warm button | `relieved` | `relaxed` + `wave` | shoulders dropped-open, small friendly wave to camera |

**Pairing rules**
- **Never mismatch band or intensity.** A `triumphant` face on a `shrink` body (or an L1 pose with an
  L3 face) is off-model — regenerate.
- **Composite buttons** (e.g. PIP's `wave`) are stored once as a pose+expression pair; see
  [Character Overrides](#character-overrides).
- The **status contrast** must hold in every shared shot: the antagonist reads *bigger/higher/opener*
  than the underdog, always.

---

## Character Overrides

Each character **plays a subset of the taxonomy** tuned to its role and locked build, per the
[Character Bible pose philosophy](CHARACTER_BIBLE.md#pip). Model sheets remain authoritative for
*build and stance*; this section canonicalizes each character's *pose vocabulary*.

### PIP — the underdog / mascot
Full profile: [Character Bible → PIP](CHARACTER_BIBLE.md#pip). Build/stance: [PIP model sheet](../characters/pip.md)
("small, round, gentle slouch; timid stance"). **Movement is low-amplitude** — PIP is the small mover;
the antagonist is the big mover.

- **How PIP moves.** Small, soft, a little timid: nervous fidgets (the [coin fumble](../../V1/01-script.md)),
  short steps, quick hopeful head-turns. Never large, never aggressive.
- **How PIP stands.** `idle` / `stand` with a gentle slouch, knees close, arms near the body, low CoG —
  the "small and harmless" read.
- **How PIP becomes scared.** `shrink` — compact C-curve, shoulders up around the head, arms clutched
  in, weight back and down (paired with `worried`/`teary`).
- **How PIP shows hope.** `leanin` / `reach` — head tilts up, a small reach toward the incoming payoff,
  CoG lifts slightly (paired with `hopeful`).
- **How PIP celebrates / reacts to success.** `celebrate` — open, lifted, a small jump of the shoulders
  (paired with `gleeful`), then settles to the button.
- **How PIP celebrates the button.** `wave` + `relaxed` — shoulders drop open, upright, a small friendly
  wave to camera. This is `CHAR_PIP_pose_wave` (the gesture) paired with `CHAR_PIP_expr_relieved`,
  surfaced as PIP's signature [`expr_wave` button](EXPRESSION_LIBRARY.md#character-overrides).
- **PIP never** plays `strut`, `victory`, `point` (aggressive), `flail` (as an aggressor), or any
  dominant/threatening pose — PIP is acted upon and vindicated, never the aggressor
  ([Character Bible — things PIP can never do](CHARACTER_BIBLE.md#pip)).

PIP's pose arc across a typical video: `idle` → `shrink` → `slump` → `leanin` → `celebrate` →
`relaxed`+`wave`.

### CHIEF — the antagonist (contrast reference)
Build/stance: [CHIEF model sheet](../characters/chief.md) ("rotund, puffed-up; stiff upright posture;
heels-together strut"). CHIEF owns the **dominance ladder**: `strut` (entrance) → `point`/`hold`
(brandishing the stamp) → `victory` (podium, stamp to sky, L3) — then the **collapse** `recoil` →
`flail` at the twist. CHIEF **never** plays `shrink`, `slump`, or `relaxed` — those are the underdog's
band. The deliberate *opposite pose vocabulary* (big/high/open vs. small/low/closed) is what makes the
status gap read instantly.

### Future characters
Every new recurring character, at [creation](CHARACTER_BIBLE.md#character-lifecycle), declares the
**subset of the pose taxonomy** its role plays and its **default stance**, and reuses canonical pose
names — it does **not** invent synonyms. Variation is allowed in *which poses it favors and how its
build shapes them*, never in the *shared pose vocabulary or the body-language rules*. Capture this in
the [Future Character Template](CHARACTER_BIBLE.md#future-character-template).

---

## Pose Asset Naming

Extends the locked convention in the [Visual Identity Lock asset-ID table](VISUAL_IDENTITY_LOCK.md#asset-id-naming)
and [Character Bible naming standards](CHARACTER_BIBLE.md#character-naming-standards). No base rule is
redefined here; this mirrors the [Expression Library naming](EXPRESSION_LIBRARY.md#expression-asset-naming).

| Thing | Convention | Example |
|---|---|---|
| Pose (baseline, = L2) | `CHAR_[NAME]_pose_[name]` | `CHAR_CHIEF_pose_strut` |
| Pose intensity variant | `CHAR_[NAME]_pose_[name]_l[1\|2\|3]` | `CHAR_CHIEF_pose_victory_l3` |
| Pose + prop composite | `CHAR_[NAME]_pose_[name]` + `PROP_[name]_v#` referenced in the prompt | `CHAR_CHIEF_pose_hold` + `PROP_stamp_v1` |

**Naming rules (extensions):**
- `[name]` is a **canonical pose name from the [taxonomy](#pose-taxonomy)** — lowercase, hyphen-free,
  single concept ([Character Bible](CHARACTER_BIBLE.md#character-naming-standards)). Never a synonym or
  an invented word.
- **Intensity suffix is optional.** No suffix = the **L2 baseline**. Add `_l1` / `_l3` only for stored
  intensity variants.
- **Adding a pose is editorial** — it does **not** bump the character `_v#`
  ([Character Bible lifecycle](CHARACTER_BIBLE.md#character-lifecycle)). Only a locked-silhouette change
  bumps the version.
- **Composite buttons** (pose + expression, e.g. `wave`+`relieved`) are cross-referenced with the
  [Expression Library](EXPRESSION_LIBRARY.md#character-overrides); the pose asset stays
  `CHAR_[NAME]_pose_[name]`.

---

## Prompt Standards

The **prompt architecture** for pose assets. This section defines structure only; it does **not**
restate the style prefix or the paste-ready scaffolds — those live in the
[visual-prompt template](../templates/visual-prompt-template.md) (style prefix + slots incl.
`ACTION/POSE`, and §4 character-asset) and the worked staging in the
[A1 storyboard](../A1-first-video/03-storyboard.md). Every pose prompt **must**:

- **prepend the locked style prefix + palette** from the [visual-prompt template](../templates/visual-prompt-template.md);
- **attach the character's approved reference sheet** (reference image / fixed seed) so identity/build holds;
- **name the target asset ID** and the **canonical pose name + intensity** from this library;
- request **"full body, centered, one key action, strong silhouette"** (the pose read).

| Prompt type | Purpose | Structure (beyond style prefix + reference sheet) | Reference scaffold |
|---|---|---|---|
| **Single pose** | One body asset | "full body, `<NAME>` in a `<pose>` pose, `<line-of-action note>`, strong silhouette" + intensity | [visual-prompt template §2 slots](../templates/visual-prompt-template.md) |
| **Pose sheet** | The whole set at once | "pose sheet: `<list the character's pose names>`, consistent proportions, full body each" | [visual-prompt template §4](../templates/visual-prompt-template.md) |
| **Pose turnaround** | Front / 3/4 / side of one pose | "`<pose>` turnaround: front, 3/4, side; identical proportions across views" | [visual-prompt template §4](../templates/visual-prompt-template.md) |
| **Pose + expression** | Body + matching face (a full beat) | pose descriptor + the paired [expression](EXPRESSION_LIBRARY.md#character-overrides) name + intensity | [Expression Library prompt standards](EXPRESSION_LIBRARY.md#prompt-standards) |
| **Pose + prop** | Character interacting with a prop | pose descriptor + prop asset ID + one key action (mute-readable) | [Prop Library — interaction rules](PROP_LIBRARY.md#interaction-rules) · [Character Bible — prop interaction](CHARACTER_BIBLE.md#character-prompt-standards) |
| **Pose sequence** | Ordered beats across a shot | "sequence: `<poseA>` → `<poseB>` → `<poseC>`, same character, pose-to-pose" *(timing owned by Animation Language)* | [A1 storyboard](../A1-first-video/03-storyboard.md) |

**One key action per pose prompt.** Keep the silhouette clear and the hands legible; request benign FX
by asset ID at L3 only.

---

## Production Workflow

Poses follow the [Character Bible lifecycle](CHARACTER_BIBLE.md#character-lifecycle) as **editorial
additions** to an already-locked character.

1. **Generation.** Pick the canonical pose + intensity from the [taxonomy](#pose-taxonomy); generate
   with the character's reference sheet attached and the [prompt standards](#prompt-standards).
2. **Review.** Run the [Quality Checklist](#quality-checklist) plus the
   [Visual Identity Lock quality checklist](VISUAL_IDENTITY_LOCK.md#quality-checklist) and the
   [Character Bible quality checklist](CHARACTER_BIBLE.md#character-quality-checklist). Off-model →
   regenerate, never settle.
3. **Approval.** The beat and status must read from the **silhouette alone**, the body must match the
   paired face's band/intensity, and it must stay advertiser-safe.
4. **Versioning.** File as `CHAR_[NAME]_pose_[name]` (optional `_l#`). Adding a pose is **editorial —
   no `_v#` bump**. If the character's *silhouette* changes, the whole set re-versions with the character.
5. **Reuse.** Shots **select** an existing pose at an intensity — they do **not** generate new assets
   unless a genuinely new body-beat is needed. Reuse-first is the cost moat
   ([Stage 2](../../docs/12-stage-2-channel-operating-system.md)).
6. **Deprecation.** Retire a pose only by a logged decision
   ([Decision Log](../../docs/21-decision-log.md)); mark it `deprecated` in the model sheet, keep the
   asset (published videos reference it), and stop using it in new videos. Replacements use a **new
   canonical name**, never a silent redefinition of the old one.

---

## Quality Checklist

Run before accepting **any** pose asset (in addition to the
[Visual Identity Lock](VISUAL_IDENTITY_LOCK.md#quality-checklist),
[Character Bible](CHARACTER_BIBLE.md#character-quality-checklist), and
[Expression Library](EXPRESSION_LIBRARY.md#quality-checklist) checklists). One failure = reject and
regenerate.

- [ ] **Silhouette reads the beat** — the action and status are unmistakable filled 100% black.
- [ ] **One clear line of action**; no conflicting curves or contortion.
- [ ] **Canonical name** — the pose is a name from the [taxonomy](#pose-taxonomy) (no invented synonym),
      correctly mapped to its beat.
- [ ] **Correct intensity** — matches the intended L1 / L2 / L3 and the paired expression's intensity.
- [ ] **In the character's band** — the pose is one this character is allowed to play (e.g. PIP never
      struts/points aggressively; CHIEF never shrinks).
- [ ] **Body matches face** — posture and the paired [expression](#pose--expression-pairing) express the
      same beat.
- [ ] **Locked build preserved** — proportions and signature accents (scarf / cap+sash+medals) unchanged.
- [ ] **Hands legible; arms read outside the silhouette**; weight/CoG clearly placed.
- [ ] **Advertiser-safe** — benign physical comedy; the underdog is never humiliated or harmed.
- [ ] **Mobile-first** — reads at thumbnail size; key action clear of the top ~15% / bottom ~20% UI zones.
- [ ] **Correct ID** — `CHAR_[NAME]_pose_[name]` (+ optional `_l#`), filed in the library.

---

## Future Integration

This library is a **parent** to the remaining shot- and motion-level documents. Each must reference a
pose by its canonical name rather than describing a body from scratch.

| Consumer (future doc / stage) | How it uses this library |
|---|---|
| **Animation Language** | Consumes the pose set as the **keyframes** it moves *between* — it owns the timing, easing, pose-to-pose snap, holds, and the loop; this library owns the static poses at each end. The boundary is explicit ([banner](#pose-library)). |
| **Wallpaper Prompt Framework** | Selects a **hero pose** (usually an L3 `victory` / `celebrate` / `wave`) + its paired expression for channel art, thumbnails, and wallpapers per the [thumbnail spec](../templates/thumbnail-spec.md). |
| **Shot Generation** | Each shot names the character's **pose + expression + intensity**, driving the [visual-prompt template](../templates/visual-prompt-template.md) `ACTION/POSE` and `SUBJECT` slots. |
| **Storyboard generation** | The [storyboard](../A1-first-video/03-storyboard.md) "Key action" column is expressed as canonical pose names, making staging reusable and machine-selectable. |
| **Video production pipeline** | The [Stage 6 production compiler](../../docs/15-stage-6-production-compiler.md) assembles shots by **posing the reusable cast** (pose + expression + prop) instead of redrawing — the core of the sub-30-minute reuse target. |

---

## Repository Integration

Additive one-line pointers are added in this branch at the highest-traffic entry points; deeper links
are recommendations to avoid over-editing locked docs.

| Document | Relationship | Action |
|---|---|---|
| [`production/design/README.md`](README.md) | Design/identity folder index | Add the Pose Library + update planned-children note (done) |
| [`production/design/CHARACTER_BIBLE.md`](CHARACTER_BIBLE.md) | Parent (character system) | Link the "Pose Library" future-doc row to this now-existing doc (done) |
| [`production/design/EXPRESSION_LIBRARY.md`](EXPRESSION_LIBRARY.md) | Sibling (the face half) | Point its "Pose Library" future-integration row here (done) |
| [`docs/00-index.md`](../../docs/00-index.md) | Master doc map | List the Pose Library under Design standards (done) |
| [`production/README.md`](../README.md) | Production folder map | Add to the `design/` tree + a traceability row (done) |
| [`production/characters/pip.md`](../characters/pip.md) · [`chief.md`](../characters/chief.md) | Build/stance specs | Recommend a "pose vocabulary → Pose Library" pointer (follow-up) |

**Anti-duplication (ownership map).** Where a requested topic is already owned elsewhere, this library
**references and extends** rather than competing:
- **Silhouette & negative space & composition** → owned by the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md#shape-language);
  this library applies them to *body mechanics* only.
- **Advertiser-safe acting & emotional design** → owned by the [Brand Bible](BRAND_BIBLE.md); referenced.
- **The face / emotion** → owned by the [Expression Library](EXPRESSION_LIBRARY.md); this library owns
  the **body** and the pairing.
- **Motion, timing, transitions, the loop** → will be owned by the future **Animation Language**; this
  library owns only the **static pose** and defers motion.
- **Character build/stance, lifecycle, naming base** → owned by the [Character Bible](CHARACTER_BIBLE.md)
  and model sheets; referenced.

This library owns only the **pose taxonomy, pose intensity, universal body-language rules, pose+expression
pairing, and per-character pose vocabulary**.

---

## Change Control

A **locked** document, governed like the [Locked Roadmap](../../docs/03-locked-roadmap.md) and
[Decision Log](../../docs/21-decision-log.md).

- **Editorial changes** (adding a pose to a character, a new intensity variant, a new AVAILABLE name,
  clarifications, cross-links) may be made freely; **no version bump**.
- **Substantive changes** (adding/removing a **pose category**, changing the intensity model or a
  universal body-language rule, changing a character's default stance) require: (1) a rationale in the
  [Decision Log](../../docs/21-decision-log.md), (2) a pass through the
  [Stage 2 5-Gate test](../../docs/12-stage-2-channel-operating-system.md), and (3) confirmation that no
  [locked decision](../../docs/03-locked-roadmap.md) or root document is contradicted.
- **New pose names** must be added to the [taxonomy](#pose-taxonomy) here **before** they may appear in
  any prompt or asset — this is what keeps generation from inventing body shapes.

> **The body is the other half of the performance.** When in doubt, choose the pose whose *silhouette*
> makes the beat and the status unmistakable with the sound off.
