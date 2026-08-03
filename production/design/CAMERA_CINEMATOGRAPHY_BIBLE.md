# Camera & Cinematography Bible

> **Status:** Locked · **Applies to:** every shot, frame, and storyboard composition for any C-Cloning
> video · **Owner role:** Lead Cinematographer / Visual Storytelling Director / Animation Layout Supervisor
>
> **This is the canonical visual storytelling language of the cast's world.** It defines how every
> story is communicated through framing, composition, shot type, camera movement, lens intent, and
> shot sequencing. **Every future storyboard, wallpaper prompt, and shot description must inherit from
> this document** and describe its shots in this vocabulary rather than inventing framing ad hoc.
>
> The [Expression Library](EXPRESSION_LIBRARY.md) explains the face, the [Pose Library](POSE_LIBRARY.md)
> the body, the [Prop Library](PROP_LIBRARY.md) the objects, the [Environment Bible](ENVIRONMENT_BIBLE.md)
> the world — **this document explains where the camera stands and how it frames all of them into a shot.**

> **Cinematography is a storytelling language, not equipment.** Every shot here is chosen to communicate
> *emotion, focus, power, humor, timing, and clarity* through framing — never as a technical flourish.

## Inheritance banner

This document is a **child of the Identity Core** and inherits from all seven foundation documents; it
never overrides them:

- **Appearance & composition law** → the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md). The
  [Composition Rules](VISUAL_IDENTITY_LOCK.md#composition-rules) (9:16, one key action per frame,
  centered/thumb-safe subjects, negative space, seed continuity, loop seam), the
  [Lighting Rules](VISUAL_IDENTITY_LOCK.md#lighting-rules) (flat, **no gradients, no depth-of-field
  blur, no bloom**), and the [Shape Language](VISUAL_IDENTITY_LOCK.md#shape-language) (silhouette read)
  are all inherited. This Bible adds *shot grammar*, not new visual law. On a visual question, the Lock
  wins.
- **Story rhythm & tone** → the [Brand Bible](BRAND_BIBLE.md). The emotional arc
  ([emotional design](BRAND_BIBLE.md#emotional-design)), the "silent beat before the turn," and the
  "prefer a *pose* over a line" mandate ([Brand Voice](BRAND_BIBLE.md#brand-voice)) drive what the
  camera covers; cinematography stays **advertiser-safe** (no distressing/horror framing). This Bible
  **fulfils** the Brand Bible's [recognition-row promise](BRAND_BIBLE.md#brand-recognition-system) to
  formalize the camera language.
- **What is in the frame** → the [Character Bible](CHARACTER_BIBLE.md),
  [Expression Library](EXPRESSION_LIBRARY.md), [Pose Library](POSE_LIBRARY.md),
  [Prop Library](PROP_LIBRARY.md), and [Environment Bible](ENVIRONMENT_BIBLE.md). The camera *frames*
  these assets; it never redefines them.

It also **defers to** (references, never restates):
- Naming & reuse → [Stage 2](../../docs/12-stage-2-channel-operating-system.md) and the
  [Visual Identity Lock asset-ID table](VISUAL_IDENTITY_LOCK.md#asset-id-naming).
- The worked shot list → the [A1 storyboard](../A1-first-video/03-storyboard.md),
  [animation spec](../A1-first-video/05-animation-spec.md), and [V1 video prompts](../../V1/05-video-prompts.md).

> **Ownership boundaries (important).**
> - **Framing vs. base composition.** The [Visual Identity Lock Composition Rules](VISUAL_IDENTITY_LOCK.md#composition-rules)
>   own negative space, thumb-safe zones, one-key-action, centered subjects, continuity, and the loop
>   seam. This Bible **extends** them with cinematographic framing (rule of thirds, headroom, look/lead
>   room, eye-line, depth staging) — it does not restate them.
> - **Within-shot camera move vs. shot-to-shot edit.** This Bible owns the **camera move *inside* a shot**
>   (static, push-in, punch-in, reveal…) and its *intent*. **Cuts, transitions, freezes, speed-ramps,
>   and captions between shots** belong to the **Editing workflow** (the [A1 editing spec](../A1-first-video/07-editing-spec.md)
>   / [Stage 6](../../docs/15-stage-6-production-compiler.md)).
> - **Shot vocabulary vs. motion execution.** This Bible owns the **shot grammar** — *which* move,
>   *why*, and *how it frames the beat*. The **timing, easing, and physical execution** of that move
>   (and all character/prop/ambient motion) belong to the future **Animation Language**.
> - **Optical vs. compositional lens.** The Lock forbids depth-of-field blur, bokeh, and perspective
>   gradients. [Lens Language](#lens-language) here is therefore **compositional intent** (crop, subject
>   scale, negative space), **never** a simulated real lens.

---

## Table of contents

1. [Purpose](#purpose)
2. [Cinematic Philosophy](#cinematic-philosophy)
3. [Camera Taxonomy](#camera-taxonomy)
4. [Camera Movement Taxonomy](#camera-movement-taxonomy)
5. [Composition Standards](#composition-standards)
6. [Lens Language](#lens-language)
7. [Shot Sequencing](#shot-sequencing)
8. [Camera + Character Relationship](#camera--character-relationship)
9. [Camera + Environment](#camera--environment)
10. [Camera + Props](#camera--props)
11. [Shot Descriptor Notation](#shot-descriptor-notation)
12. [Prompt Standards](#prompt-standards)
13. [Production Workflow](#production-workflow)
14. [Quality Checklist](#quality-checklist)
15. [Future Integration](#future-integration)
16. [Repository Integration](#repository-integration)
17. [Change Control](#change-control)

---

## Purpose

In a **mute-first, mobile-first, ~30-second** format, the camera is not a recording device — it is the
storyteller's hand, deciding *what the viewer looks at and how they feel about it* in each fraction of a
second. Framing is how the channel wins the 3-second anti-swipe, holds completion, and lands the twist.

Cinematography is essential for:

- **Storytelling.** The camera directs attention to the beat that matters — the seed in the hook, the
  flex, the karma — so the wordless story reads ([Brand Bible storytelling](BRAND_BIBLE.md#storytelling-philosophy)).
- **Comedy.** Timing *is* framing here: the low hero angle that inflates CHIEF's ego, the wide that
  isolates tiny PIP, the **punch-in** that snaps on the twist — the joke lands through the cut and the
  crop, not a caption.
- **Clarity.** One clear subject per frame, big and centered, is what keeps a muted vertical video
  legible at thumbnail size ([Composition Rules](VISUAL_IDENTITY_LOCK.md#composition-rules)).
- **Retention.** Deliberate coverage of the [beat arc](#shot-sequencing) (hook → escalation → silent
  beat → twist → button) is the anti-swipe/completion/replay engine
  ([Library 5](../../intelligence/05-viewer-psychology-library.md)).
- **Emotional impact.** Angle and distance carry status and vulnerability (low = power, wide = small)
  and intimacy (close = feel it) — the camera makes the audience *root and anticipate*.
- **Mobile-first viewing.** Every framing decision assumes a small, vertical, muted screen viewed at
  arm's length; the composition must survive that or it fails.

> **Rule of thumb:** if the viewer's eye doesn't land on the intended beat within a beat — or if the
> framing needs sound or text to make sense — the shot has failed, no matter how "cinematic" it looks.

---

## Cinematic Philosophy

The framing principles every shot obeys. These apply the roots to *the camera*; they do not restate them.

- **Clarity over complexity.** The simplest framing that lands the beat wins. One clear subject, one key
  action, generous negative space ([Composition Rules](VISUAL_IDENTITY_LOCK.md#composition-rules)). No
  busy, layered, or ambiguous compositions.
- **Emotion before spectacle.** The camera serves the *feeling and the beat*, not a flashy move. A move
  must earn its place by advancing the story (build, reveal, impact) — never decoration.
- **Readability.** Every shot reads muted, at thumbnail size, in the [silhouette](VISUAL_IDENTITY_LOCK.md#shape-language).
  If the subject or its action isn't instantly clear, re-frame.
- **Mobile-first framing.** Design for **9:16 vertical**; keep the subject and key action in the central
  [thumb-safe band](VISUAL_IDENTITY_LOCK.md#composition-rules) (out of the top ~15% / bottom ~20% UI
  zones). Favor bigger subject scale over wide emptiness that reads tiny on a phone.
- **Character-first composition.** The frame is built around the cast and the beat they play; the
  [environment](ENVIRONMENT_BIBLE.md) stays quieter and the camera never lets the world out-compete the
  subject.
- **Advertiser-safe cinematography.** No distressing, horror, or disorienting camera work — no shaky
  handheld dread, no vertiginous spins. Framing stays clean, stable, and benign
  ([Brand Bible](BRAND_BIBLE.md#content-pillars)).
- **Visual rhythm.** Shots alternate scale and stillness to create pace: mostly **locked/static** frames
  with deliberate, sparse moves, building to the twist. Stillness makes the one move land.
- **Comedic timing through framing.** The **hold** (a beat of stillness on a pose) and the **punch-in**
  (a snap on the reveal) are the channel's comedic camera signatures — timing executed by the
  [Animation Language](#future-integration), *framed* here.

---

## Camera Taxonomy

The canonical **shot types** (framing/distance + angle). This is the closed vocabulary a storyboard or
prompt selects from (mirrors the [Pose](POSE_LIBRARY.md#pose-taxonomy)/[Expression](EXPRESSION_LIBRARY.md#expression-taxonomy)
model).

- **IN USE** = appears in the shipped [A1/V1](../A1-first-video/03-storyboard.md) work.
- **AVAILABLE** = a reserved shot to use *when a beat first needs it*.
- **DISALLOWED** = off-brand; do not use.

### Framing / distance

| Shot type | Token | Story job | Status |
|---|---|---|---|
| **Establishing / Extreme Wide** | `EWIDE` | Set the whole location + plant the seed; the world at a glance | AVAILABLE (use `WIDE` by default) |
| **Wide** (establishing) | `WIDE` | Locate the scene, show the status gap, hold the seed; the loop plate | **IN USE** (A1 S1/6/8) |
| **Full Body** | `FULL` | One character's whole pose/action reads head-to-toe | **IN USE** (most A1 shots) |
| **Medium (two-shot)** | `MED` | The bully-and-underdog relationship; an interaction | **IN USE** (A1 S2) |
| **Medium Close-up** | `MCU` | Upper-body emphasis for a smaller reaction | AVAILABLE |
| **Close-up** (reaction) | `CU` | A face beat — the emotion carries the shot (thumbnail hero) | **IN USE** (reactions/thumbnail) |
| **Extreme Close-up** | `ECU` | A tiny detail beat (eyes welling, a hand on the stamp) — rare | AVAILABLE |
| **Reaction Insert** | `REACT` | Cut to the witness's face at a beat (PIP's hope/glee) | **IN USE** |
| **Cutaway / Reveal insert** | `CUT` | Show the incoming element (the tow truck) — the misdirection/reveal | **IN USE** (A1 S6) |

### Angle

| Angle | Token | Story job | Status |
|---|---|---|---|
| **Eye level** | `EYE` | Neutral, honest, default | **IN USE** |
| **Low angle (hero)** | `LOW` | Inflate power/ego — the arrogant flex | **IN USE** (A1 S5 victory) |
| **High angle** | `HIGH` | Emphasize smallness/vulnerability — used sparingly for the underdog | AVAILABLE |
| **Top-down** | `TOP` | A layout/map beat (rare, graphic) | AVAILABLE |
| **Over-the-shoulder** | `OTS` | Anchor a confrontation from one side | AVAILABLE |
| **Point-of-view** | `POV` | See through a character's eyes (rare) | AVAILABLE |
| **Dutch (tilted)** | `DUTCH` | A brief comedic off-kilter beat only | AVAILABLE (sparing, benign) |

**Taxonomy rules**
- **Default to `WIDE`/`FULL` at `EYE`.** The channel is wide-and-clear first; tighter/angled shots are
  deliberate beats, not the norm.
- **Angle carries status** ([Camera + Character](#camera--character-relationship)): `LOW` inflates the
  antagonist; `HIGH` (sparingly) shrinks the underdog; `EYE` is the honest default.
- **One shot type per frame.** A frame is one clear composition; don't blend intents.
- **No invented shot names** — use the tokens above; a genuinely new need adds a token here first via
  [Change Control](#change-control).

---

## Camera Movement Taxonomy

Camera moves are **rare and purposeful** — the channel is *mostly locked/static* for mute-first clarity
([animation spec](../A1-first-video/05-animation-spec.md): "only two moves… no handheld, no rotation").
This Bible names the move and its *intent*; the **timing/easing of executing it** belongs to the future
[Animation Language](#future-integration).

| Movement | Token | Story job | Status |
|---|---|---|---|
| **Static / Locked** | `STATIC` | The default — clarity, stillness, lets the pose/hold land | **IN USE** (default) |
| **Push In** (slow) | `PUSHIN` | Build focus/anticipation on a grin or the ego peak | **IN USE** (A1 S2, S5) |
| **Punch In** (fast snap) | `PUNCHIN` | The comedic impact on the twist/reveal; then settle | **IN USE** (A1 S7) |
| **Reveal** | `REVEAL` | Bring an incoming element into frame (tow truck) for misdirection→payoff | **IN USE** (A1 S6) |
| **Pull Out** | `PULLOUT` | Open up to reveal context/consequence | AVAILABLE |
| **Pan** (horizontal) | `PAN` | Follow lateral action or connect two elements | AVAILABLE |
| **Tilt** (vertical) | `TILT` | Reveal height (a ticket pile growing, a tall reveal) | AVAILABLE |
| **Tracking / Follow** | `TRACK` | Travel with a moving subject (a driving scooter) | AVAILABLE |
| **Whip Pan** | `WHIP` | A fast transition-adjacent move; the *cut* decision is Editing's | AVAILABLE (rare) |
| **Zoom** | (use `PUSHIN`/`PUNCHIN`) | — | (framed as push/punch-in, not optical zoom) |
| **Orbit / Rotation** | — | — | **DISALLOWED** (breaks flat 2D; anim-spec "no rotation") |
| **Handheld simulation** | — | — | **DISALLOWED** (off-brand; anim-spec "no handheld") |

**Movement rules**
- **≤1 meaningful move per shot**, and most shots are `STATIC`. Stillness is the norm; a move is an event.
- **Every move earns the beat** — build (`PUSHIN`), reveal (`REVEAL`/`TILT`/`PULLOUT`), or impact
  (`PUNCHIN`). No decorative drift.
- **No handheld, no orbit/rotation** — these contradict the locked flat-2D look and the mute-first
  clarity rule.
- **The punch-in is the signature** twist move: a quick snap in + small settle, paired with the
  [`recoil`→`flail`](POSE_LIBRARY.md#pose--expression-pairing) and the audio sting (audio is Editing's).
- **A `WHIP` is a camera/edit boundary** — this Bible defines the move; the shot-to-shot *cut* it may
  hide is an [editing](../A1-first-video/07-editing-spec.md) decision.

---

## Composition Standards

The [Visual Identity Lock Composition Rules](VISUAL_IDENTITY_LOCK.md#composition-rules) **already own**
9:16 framing, one-key-action, centered/thumb-safe subjects, negative space, seed continuity, and the
loop seam — those are inherited, not restated. This Bible adds the **cinematographic framing** the Lock
doesn't spell out:

- **Rule of thirds vs. center framing.** **Center-frame the hero beat** by default (mute-first, mobile,
  thumbnail-safe — the Lock's centered-subject rule). Use **thirds** for *relationship/tension* framing
  (bully on one third, underdog on the other, the status gap in the gap between them) and for placing a
  seed off-center while keeping it in a stable, repeatable spot.
- **Headroom.** Leave modest, consistent headroom above the oversized head; never crop the head at the
  top UI zone. Chunky 2–3-head proportions mean heads sit lower in frame than in live action.
- **Look room / lead room.** Give a character space in the direction they **look or move** (PIP's
  hopeful look toward the incoming payoff; a driving scooter leads into open frame). Empty space *behind*
  a subject reads as wrong.
- **Eye-line.** Keep cross-character eye-lines consistent so a two-shot or a reaction insert reads as the
  same space (CHIEF looks down at PIP; PIP looks up — reinforcing the [status gap](#camera--character-relationship)).
  The witness's eye-line points at the beat they react to.
- **Depth staging (for the camera).** Compose across the [Environment Bible's fg/mg/bg planes](ENVIRONMENT_BIBLE.md#background-standards):
  the subject on the **mg** stage, the seed readable in **fg**, the world quiet in **bg**. Depth is
  staged by *plane + scale*, **never** by depth-of-field blur or perspective gradient (forbidden by the
  [Lock](VISUAL_IDENTITY_LOCK.md#lighting-rules)).
- **Visual balance.** Balance the heavy subject against calm negative space, not competing detail
  ([Lock](VISUAL_IDENTITY_LOCK.md#composition-rules)); one `BRAND_YELLOW` focal hit guides the eye to the
  beat.
- **Continuity framing.** Seeds hold a **fixed screen position** and the **first/last frames match**
  (loop seam) — inherited from the Lock; the camera plate for the closing shot must equal the opening
  shot exactly.

---

## Lens Language

The channel renders **flat, with no depth-of-field, no bokeh, and no perspective gradients**
([Lighting](VISUAL_IDENTITY_LOCK.md#lighting-rules) / [Rendering](VISUAL_IDENTITY_LOCK.md#rendering-rules)).
"Lens" here is therefore a **compositional intent**, expressed through crop, subject scale, and negative
space — **never** a simulated optical lens, distortion, or blur.

| Virtual "lens" | Compositional intent | When to use |
|---|---|---|
| **Wide feel** | Small subject scale in generous negative space; the world/status gap visible; everything in equal flat focus | Establishing, isolating the tiny underdog, showing the seed in context (A1 wide shots) |
| **Normal feel** | Honest, human subject scale; balanced medium | Interactions/two-shots — the default relationship framing |
| **Long / tele feel** | Large subject scale, tight crop, minimal surrounding space; maximal intimacy or impact | Reaction close-ups, the twist punch-in, thumbnail hero faces |

**Lens rules**
- **Compositional, not optical.** A "close-up" is a *tighter crop and bigger subject*, not a shallow
  focus; the background stays flat, in-focus, and quieter (never blurred).
- **No lens distortion.** No fisheye, no barrel warp, no vignetting — these break the clean flat-vector
  look.
- **Scale is the lens.** Since perspective is flat, the primary "focal length" control is **how large
  the subject is drawn in the frame** — bigger = closer/more intimate/more impact.

---

## Shot Sequencing

How shots connect to cover the beat arc and maximize retention. The **story beat structure**
(setup → escalation → silent beat → twist → button) is owned by the
[Brand Bible](BRAND_BIBLE.md#storytelling-philosophy) and [Library 6](../../intelligence/06-narrative-pattern-library.md);
this Bible owns the **camera coverage** of each beat. The **cuts between shots** are the
[Editing workflow](../A1-first-video/07-editing-spec.md)'s.

| Beat | Camera coverage (default) | Why |
|---|---|---|
| **Establishing** | `WIDE.EYE.STATIC`, held; seed visible | Locate the world + status gap; plant the seed (anti-swipe) |
| **Setup** | `MED.EYE.PUSHIN` (slow) | Introduce the bully's intent; build focus |
| **Anticipation** | `FULL/LOW.PUSHIN` or a **hold** on the flex | Inflate the ego; set the wrong prediction; the silent beat |
| **Action** | `FULL/MED.STATIC` with a micro impact hold | The escalation beats read cleanly, one key action each |
| **Reaction** | `REACT`/`CU` insert on the witness | The underdog carries the audience's feeling (hope/glee) |
| **Payoff (twist)** | `WIDE→PUNCHIN` + settle | The comedic impact; the share moment |
| **Button** | return to the **establishing `WIDE` plate** | Warm close; **loop seam** (first frame = last frame) |
| **Transition** | *(Editing owns the cut)* — default **hard cut** | Snappy pace; no dissolves ([editing spec](../A1-first-video/07-editing-spec.md)) |

**Sequencing rules**
- **Cover every beat once, clearly** — the arc must be legible muted; a missing beat is a leaked
  behavior ([Library 5](../../intelligence/05-viewer-psychology-library.md)).
- **Alternate scale & stillness** for rhythm: wides and mediums mostly static, tightening toward the
  twist; the one big move (punch-in) lands because the rest were still.
- **The silent beat** (music drop before the turn, [Brand Bible](BRAND_BIBLE.md#storytelling-philosophy))
  is covered by a **hold** on the ego peak — stillness creates the anticipation.
- **The loop seam is a camera contract:** the button shot reuses the *exact* establishing plate
  ([Lock continuity](VISUAL_IDENTITY_LOCK.md#composition-rules)).
- **Keep the seed in frame** at the hook and the payoff so the rewatch pays off.

---

## Camera + Character Relationship

Framing is the channel's second **status** instrument (after [pose](POSE_LIBRARY.md)). The camera takes
a side by how it frames each character.

| Subject | Default framing | Why |
|---|---|---|
| **PIP** (underdog / mascot) | `EYE` or a gentle `HIGH`, often small in a `WIDE`; `CU`/`REACT` for the emotion | Reads small, sympathetic, and vulnerable; the reaction insert lets the audience feel *with* PIP. Never a heroic `LOW` on PIP. |
| **CHIEF** (antagonist) | `LOW` (hero angle) at the flex; `FULL` to show the puffed strut | The low angle inflates his ego so the fall is funnier; the camera flatters him *so the twist deflates him*. |
| **Future recurring characters** | Framed to their [taxonomy class](CHARACTER_BIBLE.md#character-taxonomy) | Heroes/underdogs framed sympathetically; authority/bully framed to inflate then collapse. Declared per character. |

**Framing for meaning**
- **Status / power** → **low angle + larger scale + more space above owned** = dominant (CHIEF's flex).
- **Vulnerability** → **higher angle + small scale + isolating negative space** = sympathetic (PIP).
- **Emotion** → **tighter crop** (`CU`/`REACT`) when the face must carry the beat
  ([Expression Library](EXPRESSION_LIBRARY.md)).
- **Relationship / conflict** → **two-shot on thirds**, consistent eye-lines, the status gap staged in
  the space between them.
- **Advertiser-safe always** — even the antagonist is framed as a "villain you enjoy," never with
  genuinely menacing or distressing camerawork.

---

## Camera + Environment

The [Environment Bible](ENVIRONMENT_BIBLE.md) builds the *space*; the camera decides how to *frame and
move through* it. The environment is always framed **quieter than the cast**.

- **Establish, then tighten.** Open on a `WIDE` that reads the location in under a second (its 1–2
  iconic elements + the seed), then move tighter for the interaction beats
  ([Environment depth planes](ENVIRONMENT_BIBLE.md#background-standards) place the subject in the mg).
- **Frame the status gap in space** — an authority's turf/elevation vs. the little guy's small spot
  ([Environmental Storytelling](ENVIRONMENT_BIBLE.md#environmental-storytelling)); the camera reinforces
  it with angle and scale.
- **Respect the ground line** — keep the cast at the location's consistent ground line and scale across
  shots so they "sit" in the space.
- **Keep set-carried seeds in frame** at their [fixed continuity position](VISUAL_IDENTITY_LOCK.md#composition-rules).
- **Flat depth only** — stage across planes; no atmospheric perspective/gradient/blur to fake distance.
- **Thumb-safe horizon** — keep the horizon and key set pieces out of the top ~15% / bottom ~20% UI
  zones.

---

## Camera + Props

Props are **storytelling anchors** the camera uses to point the eye ([Prop Library](PROP_LIBRARY.md)).

- **Hero-prop emphasis.** Frame the [hero prop / karma device](PROP_LIBRARY.md#prop-classification) large
  and let it take the single `BRAND_YELLOW` focal hit — the low-angle on the **raised stamp**, the
  emphasis on the **boot**.
- **The seed prop stays visible.** Compose the hook and payoff so the [seed](PROP_LIBRARY.md#prop-taxonomy)
  (CHIEF's mis-parked scooter) is readable and holds its screen position; the camera never loses it.
- **The reveal.** A `REVEAL`/`CUT` brings the incoming prop (the tow truck) into frame for the
  misdirection→payoff, then the `PUNCHIN` snaps on the karma device doing its work.
- **Locked prop scale.** The camera never re-scales a prop for framing convenience; a prop's
  [size ratio to its owner is locked](PROP_LIBRARY.md#interaction-rules) at every distance.
- **Readable interaction.** Frame a [pose + prop](POSE_LIBRARY.md#prompt-standards) so the contact reads
  outside the body silhouette (the grip, the stamp, the point).

---

## Shot Descriptor Notation

A **shot is a per-video composition** of a [location](ENVIRONMENT_BIBLE.md) + [cast](CHARACTER_BIBLE.md) +
[pose](POSE_LIBRARY.md) + [expression](EXPRESSION_LIBRARY.md) + [props](PROP_LIBRARY.md) — **not** a
reusable stored asset. It therefore does **not** get a `_v#` asset ID (that would compete with the
[asset namespaces](VISUAL_IDENTITY_LOCK.md#asset-id-naming)). Instead, storyboards and prompts describe a
shot with a compact **descriptor** built from this Bible's tokens:

```
SHOT <n> = <FRAMING>.<ANGLE>.<MOVEMENT>
           BG:<location BG_ id + time/weather>
           CAST:<CHAR + pose + expr (+ intensity)>
           PROPS:<PROP_ ids>
           BEAT:<sequencing beat>   CONTINUITY:<seed / loop note>
```

**Worked example (A1 shot 5 — the flex):**
```
SHOT 5 = FULL.LOW.PUSHIN
         BG: BG_parkinglot_v1 (afternoon, clear)
         CAST: CHAR_CHIEF_v1 pose=victory_l3 expr=triumphant_l3
         PROPS: PROP_stamp_v1 (raised), PROP_podium_v1 ; FX_sparkle_v1
         BEAT: Anticipation (ego peak, silent beat)   CONTINUITY: seed (chief scooter) held lower-right
```

**Notation rules**
- **Tokens only** from the [Camera](#camera-taxonomy) / [Movement](#camera-movement-taxonomy) taxonomies
  and the other libraries' canonical IDs — never invented framing words.
- The **finished video** is named `PTP_[####]_[premise]_[platform]_v#` per
  [Stage 2](../../docs/12-stage-2-channel-operating-system.md); individual shots are numbered *within*
  that video (`SHOT 1..n`), not globally versioned.
- Default omitted fields = `EYE` angle and `STATIC` movement.
- This notation is the machine-selectable backbone of [storyboard/shot generation](#future-integration).

---

## Prompt Standards

The **prompt architecture** for shot/camera assets. This section defines structure only; it does **not**
restate the style prefix or the paste-ready scaffolds — those live in the
[visual-prompt template](../templates/visual-prompt-template.md) (style prefix + `FRAMING` slot) and the
worked per-shot prompts in the [A1 storyboard](../A1-first-video/03-storyboard.md) and
[V1 image prompts](../../V1/04-image-prompts.md). Every shot prompt **must**:

- **prepend the locked style prefix + palette** from the [visual-prompt template](../templates/visual-prompt-template.md);
- **name the [shot descriptor](#shot-descriptor-notation)** (framing.angle.movement) + the asset IDs it composes;
- request **"9:16 vertical, flat-2D, no depth-of-field blur, no lens distortion, subject centered/thumb-safe"**.

| Prompt type | Purpose | Structure (beyond style prefix) | Reference scaffold |
|---|---|---|---|
| **Single shot** | One storyboard frame | shot descriptor + `BG_`/`CHAR_`/pose/expr/`PROP_` IDs + framing note | [A1 storyboard](../A1-first-video/03-storyboard.md) |
| **Camera sheet** | The shot-type vocabulary for a character/location (reference) | "same subject in `WIDE / MED / CU`, `EYE / LOW / HIGH`, flat-2D, consistent design" | [Camera Taxonomy](#camera-taxonomy) |
| **Camera movement** | The intent of a within-shot move for the motion tool | shot still + "`<PUSHIN/PUNCHIN/REVEAL>`, minimal camera move, keep design" *(timing = Animation Language)* | [V1 video prompts](../../V1/05-video-prompts.md) |
| **Character shot** | Frame a character beat | framing.angle + character ref + [pose+expr](POSE_LIBRARY.md#prompt-standards) | [Pose Library prompt standards](POSE_LIBRARY.md#prompt-standards) |
| **Environment shot** | Frame a location | framing.angle + `BG_` id + time/weather, no characters | [Environment prompt standards](ENVIRONMENT_BIBLE.md#prompt-standards) |
| **Prop shot** | Frame a hero prop as an anchor | framing (often `CU`/`LOW`) + prop id + `BRAND_YELLOW` focal hit | [Prop Library prompt standards](PROP_LIBRARY.md#prompt-standards) |
| **Storyboard shot** | A full beat in the video | the complete [shot descriptor](#shot-descriptor-notation) block | [A1 storyboard](../A1-first-video/03-storyboard.md) |

**One shot per prompt.** Keep one clear subject and key action; request no DOF blur, no lens distortion,
no readable text (unless the beat specifies it).

---

## Production Workflow

Shots are **planned and laid out**, not stored as versioned assets (the assets they compose are).

1. **Planning.** From the approved [script/storyboard](../A1-first-video/03-storyboard.md), assign each
   beat a [shot descriptor](#shot-descriptor-notation) covering the [sequencing arc](#shot-sequencing).
2. **Layout.** Block the composition per the [Composition Standards](#composition-standards) — subject
   scale, angle-for-status, thumb-safe framing, seed position, loop-seam plate.
3. **Review.** Run the [Quality Checklist](#quality-checklist) plus the
   [Visual Identity Lock quality checklist](VISUAL_IDENTITY_LOCK.md#quality-checklist). Off-brief →
   re-frame, never settle.
4. **Approval.** The beat, subject, and status must read muted at thumbnail size; the coverage must hit
   the arc; framing stays advertiser-safe.
5. **Versioning.** Shots are numbered *within* a video (`SHOT 1..n`); they are **not** globally
   versioned. The shot-type/movement **vocabulary** is versioned here (this doc). The finished video is
   `PTP_[####]…` per [Stage 2](../../docs/12-stage-2-channel-operating-system.md).
6. **Reuse.** Reuse **framing recipes** (the beat→coverage table) across videos, not per-shot files — a
   new video re-applies the same [sequencing](#shot-sequencing) to new situations. This is the coverage
   cost-moat: consistent, machine-selectable framing.

---

## Quality Checklist

Run before approving **any** shot/storyboard frame (in addition to the
[Visual Identity Lock quality checklist](VISUAL_IDENTITY_LOCK.md#quality-checklist)). One failure =
re-frame and regenerate.

- [ ] **One clear subject + one key action** read instantly, muted, at thumbnail size.
- [ ] **Correct shot type + angle** from the [taxonomy](#camera-taxonomy); angle carries the intended
      status (LOW=power, HIGH/small=vulnerable, EYE=neutral).
- [ ] **≤1 purposeful move** (`STATIC` default); no handheld, no orbit/rotation; the move earns the beat.
- [ ] **9:16 + thumb-safe** — subject and key action clear of the top ~15% / bottom ~20% UI zones; good
      headroom; look/lead room in the direction of gaze/motion.
- [ ] **Flat depth** — no DOF blur, no lens distortion, no perspective gradient; depth via plane + scale.
- [ ] **Environment quieter than the cast**; consistent ground line and locked prop scale.
- [ ] **Seed in frame** at hook/payoff, in its fixed position; **loop-seam plate** matches the opener.
- [ ] **Coverage** — the shot fits its [sequencing beat](#shot-sequencing); the arc stays legible.
- [ ] **Advertiser-safe** framing — no distressing/horror/disorienting camerawork.
- [ ] **Described in the [shot descriptor notation](#shot-descriptor-notation)** with canonical tokens +
      asset IDs (no invented framing words).

---

## Future Integration

This Bible is a **parent/sibling** to the remaining motion-, art-, and pipeline-level documents. Each
must describe framing in this Bible's [shot vocabulary](#camera-taxonomy) rather than inventing it.

| Consumer (future doc / stage) | How it uses this Bible |
|---|---|
| **[Animation Language & Motion System](ANIMATION_LANGUAGE_MOTION_SYSTEM.md)** ✅ | Executes the **timing/easing** of the camera moves this Bible names (how fast the `PUSHIN`, the snap+settle of the `PUNCHIN`, the hold on the flex); this Bible owns the shot vocabulary + intent, Animation Language owns the motion. |
| **[Production Prompt Framework & Runtime Orchestration](PRODUCTION_PROMPT_FRAMEWORK_RUNTIME_ORCHESTRATION.md)** ✅ (incl. wallpaper prompts) | Selects a **hero framing** (a `CU`/`LOW` on the hero pose+expression+prop, or a `WIDE` key-art) for channel art, thumbnails, and wallpapers per the [thumbnail spec](../templates/thumbnail-spec.md). |
| **Shot Generation** | Emits the [shot descriptor](#shot-descriptor-notation) per beat, driving the [visual-prompt template](../templates/visual-prompt-template.md) `FRAMING` slot with canonical tokens + asset IDs. |
| **Storyboard generation** | The [storyboard](../A1-first-video/03-storyboard.md) framing column is expressed in this Bible's tokens, making coverage reusable and machine-selectable. |
| **Editing workflow** | Consumes the shot list; owns the **cuts, freezes, speed-ramps, and captions between shots** (the [A1 editing spec](../A1-first-video/07-editing-spec.md) / [Stage 6](../../docs/15-stage-6-production-compiler.md)); this Bible owns the within-shot framing/move. |
| **Video production pipeline** | The [Stage 6 production compiler](../../docs/15-stage-6-production-compiler.md) assembles shots from **framing + location + cast + pose + expression + prop**, hitting the sub-30-minute reuse target. |

---

## Repository Integration

Additive one-line pointers are added in this branch at the highest-traffic entry points; deeper links
are recommendations to avoid over-editing locked docs.

| Document | Relationship | Action |
|---|---|---|
| [`production/design/README.md`](README.md) | Design/identity folder index | Add the Camera & Cinematography Bible + update planned-children note (done) |
| [`production/design/CHARACTER_BIBLE.md`](CHARACTER_BIBLE.md) | Frames its characters | Link the "Camera Language" future-doc row to this now-existing doc (done) |
| [`production/design/ENVIRONMENT_BIBLE.md`](ENVIRONMENT_BIBLE.md) | Provides the space this frames | Point its "Camera Language" future-integration row here (done) |
| [`production/design/PROP_LIBRARY.md`](PROP_LIBRARY.md) | Provides the props this frames | Point its "Camera Language" future-integration row here (done) |
| [`production/design/BRAND_BIBLE.md`](BRAND_BIBLE.md) | Its recognition row promised this doc | Update the "to be formalized" camera-language note to link here (done) |
| [`docs/00-index.md`](../../docs/00-index.md) | Master doc map | List the Camera & Cinematography Bible under Design standards (done) |
| [`production/README.md`](../README.md) | Production folder map | Add to the `design/` tree + a traceability row (done) |
| [`production/A1-first-video/03-storyboard.md`](../A1-first-video/03-storyboard.md) | The worked shot list | Point its framing at this Bible's grammar (done) |

**Anti-duplication (ownership map).** Where a requested topic is already owned elsewhere, this Bible
**references and extends** rather than competing:
- **9:16 framing, negative space, thumb-safe, one-key-action, centered subjects, continuity, loop seam**
  → owned by the [Visual Identity Lock Composition Rules](VISUAL_IDENTITY_LOCK.md#composition-rules); this
  Bible extends only rule-of-thirds/headroom/look-lead-room/eye-line/depth-staging.
- **Flat rendering, no DOF/gradient/blur** → owned by the [Lighting](VISUAL_IDENTITY_LOCK.md#lighting-rules)/[Rendering](VISUAL_IDENTITY_LOCK.md#rendering-rules)
  rules; this Bible's [Lens Language](#lens-language) is compositional, not optical.
- **The story beat arc, silent beat, tone** → owned by the [Brand Bible](BRAND_BIBLE.md) and
  [Library 6](../../intelligence/06-narrative-pattern-library.md); this Bible owns the *camera coverage*.
- **Cuts, transitions, freezes, speed-ramps, captions** → owned by the
  [Editing workflow](../A1-first-video/07-editing-spec.md) / [Stage 6](../../docs/15-stage-6-production-compiler.md).
- **Move timing/easing & all motion** → future **Animation Language**.
- **What is in the frame** (characters, expressions, poses, props, locations) → their respective
  libraries.

This Bible owns only the **shot taxonomy, camera-movement taxonomy, cinematographic composition
extensions, lens (compositional) language, shot sequencing/coverage, camera-to-subject framing rules,
and the shot-descriptor notation**.

---

## Change Control

A **locked** document, governed like the [Locked Roadmap](../../docs/03-locked-roadmap.md) and
[Decision Log](../../docs/21-decision-log.md).

- **Editorial changes** (clarifications, a new AVAILABLE shot/move token, examples, cross-links) may be
  made freely; **no version bump**.
- **Substantive changes** (adding/removing a shot-type or movement category, changing a
  framing-for-status rule, the DISALLOWED list, or the shot-descriptor notation) require: (1) a rationale
  in the [Decision Log](../../docs/21-decision-log.md), (2) a pass through the
  [Stage 2 5-Gate test](../../docs/12-stage-2-channel-operating-system.md), and (3) confirmation that no
  [locked decision](../../docs/03-locked-roadmap.md) or root document is contradicted.
- **New shot/movement tokens** must be added to the [taxonomies](#camera-taxonomy) here **before** they
  appear in any storyboard, prompt, or shot descriptor — this is what keeps framing from being invented
  ad hoc.

> **The camera is the storyteller's hand.** When in doubt, choose the framing whose single, clear read
> lands the beat and the status with the sound off — and cover the arc the same way every time.
