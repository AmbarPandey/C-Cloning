# Prop Library

> **Status:** Locked · **Applies to:** every reusable object / prop asset generated for any C-Cloning
> video · **Owner role:** Lead Prop Designer / Production Designer / Asset System Architect
>
> **This is the canonical object system of the cast's world.** It defines how every reusable
> object is created, classified, scaled, named, versioned, interacted with, and maintained — so
> every recurring object originates here and is reused, never reinvented. **Future image generation
> must pick a prop from this library (or mint one through it) rather than inventing objects ad hoc.**
>
> The [Expression Library](EXPRESSION_LIBRARY.md) explains the face, the
> [Pose Library](POSE_LIBRARY.md) explains the body — **this document explains the objects the body
> holds and the world it acts on.**

## Inheritance banner

This document is a **child of the character system** and inherits from all five foundation documents;
it never overrides them:

- **Appearance** → the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md). Shape language ("props are
  scaled for comedy and readability, not realism"; rounded default, sharp = authority/threat accent),
  the [Color System](VISUAL_IDENTITY_LOCK.md#color-system) (`BRAND_YELLOW` = hero props like the boot),
  the line system, and all flat rendering law are inherited. This library adds *object-design* rules,
  not new visual law. On a visual question, the Lock wins.
- **Meaning / story role** → the [Brand Bible](BRAND_BIBLE.md). Props serve the
  [content pillars](BRAND_BIBLE.md#content-pillars) as **seeds** and **karma devices** (the stamp that
  gets used *on* CHIEF; the scooter parked in the no-parking zone in frame 1); they stay
  **advertiser-safe** (no weapons-as-weapons, no harm).
- **Character system** → the [Character Bible](CHARACTER_BIBLE.md). Signature props are declared per
  character ([Asset Standards](CHARACTER_BIBLE.md#character-asset-standards)); this library is the
  canonical **catalog** those declarations point to, and it obeys the
  [naming standards](CHARACTER_BIBLE.md#character-naming-standards).
- **Physical acting** → the [Pose Library](POSE_LIBRARY.md). A character using a prop is a
  **pose + prop composite** (`CHAR_CHIEF_pose_hold` + `PROP_stamp_v1`); this library owns the object
  and the [interaction rules](#interaction-rules), the Pose Library owns the body.

It also **defers to** (references, never restates):
- Naming & reuse → [Stage 2](../../docs/12-stage-2-channel-operating-system.md) and the
  [Visual Identity Lock asset-ID table](VISUAL_IDENTITY_LOCK.md#asset-id-naming).
- The worked object list → the [A1 asset manifest](../A1-first-video/04-asset-manifest.md) and
  [storyboard](../A1-first-video/03-storyboard.md).

> **Two ownership boundaries (important).**
> 1. **Prop vs. costume.** A **prop** is a *discrete, separable object* a character interacts with. A
>    character's *worn signature accessories* — CHIEF's cap + sash + **medals** + gloves, PIP's scarf —
>    are **costume, part of the character** (`part of CHAR_[NAME]_v#`, owned by the
>    [Character Bible](CHARACTER_BIBLE.md) / model sheet), **not props**. The
>    [A1 manifest](../A1-first-video/04-asset-manifest.md) already lists medals as "part of
>    `CHAR_CHIEF_v1`."
> 2. **Prop vs. environment.** This library owns **discrete, movable, interactable objects** (and small
>    movable furniture a character uses). **Fixed architectural set dressing** that *locates* the scene
>    (walls, the parking-lot ground, the sky, the no-parking zone marking) belongs to the future
>    **Environment Bible** and lives in the `BG_[name]_v#` namespace. Likewise, **on-frame text** (the
>    "TOWED" mark, `UI_towed_stamp_v1`) is the `UI_` namespace, and **prop *motion*** (a thrown arc, the
>    tow-hook swing) belongs to the future **Animation Language**. This library owns the *static object
>    + how it is held/scaled*.

---

## Table of contents

1. [Purpose](#purpose)
2. [Prop Philosophy](#prop-philosophy)
3. [Prop Taxonomy](#prop-taxonomy)
4. [Prop Classification](#prop-classification)
5. [Prop Standards](#prop-standards)
6. [Character Ownership](#character-ownership)
7. [Interaction Rules](#interaction-rules)
8. [Prop Asset Naming](#prop-asset-naming)
9. [Prompt Standards](#prompt-standards)
10. [Production Workflow](#production-workflow)
11. [Quality Checklist](#quality-checklist)
12. [Future Integration](#future-integration)
13. [Repository Integration](#repository-integration)
14. [Change Control](#change-control)

---

## Purpose

Objects are not set dressing on this channel — they are **story machinery**. The
[twist engine](../../intelligence/03-narrative-twist-library.md) runs on *seeds* and *karma devices*
that are almost always **props**: CHIEF's scooter parked in the red zone in frame 1 (the seed), and
his own giant stamp turned against him at the twist (the karma device). A recurring, reusable object
system is therefore both a storytelling asset and a production-speed asset.

Recurring props matter because:

- **They carry the story.** A seed prop planted in the hook and paid off at the twist is the mechanism
  of the [Seeded Reversal Framework](../../intelligence/03-narrative-twist-library.md); if the object
  isn't consistent and readable, the seed→payoff link breaks.
- **They build recognition.** CHIEF's giant stamp and the `BRAND_YELLOW` boot are recognizable channel
  motifs, part of the [brand recognition system](BRAND_BIBLE.md#brand-recognition-system). A viewer
  learns "the stamp = his power object."
- **They are the reuse engine.** The [Stage 2 reuse economics](../../docs/12-stage-2-channel-operating-system.md)
  (~70% reuse, sub-30-minute videos) depend on a shared prop catalog — the stamp, boot, ticket pad, and
  scooters become **reuse** across every future video.
- **Automation needs a closed catalog.** Prompt frameworks and shot generation must select props from a
  finite, named library — never invent new objects per shot — so the world stays consistent at scale.

> **Rule of thumb:** if an object appears in more than one shot or could appear in a future video, it is
> a **library prop** with an ID — not a one-off drawing.

---

## Prop Philosophy

The design principles every prop obeys. These apply the roots to *objects*; they do not restate them.

- **Simplicity.** A prop is a few big, flat shapes from the
  [shape kit](VISUAL_IDENTITY_LOCK.md#shape-language) (circle, rounded rect, capsule). No mechanical
  detail, no fine parts. If a detail doesn't help the gag or the read, delete it.
- **Recognizability.** A prop has **one iconic read** — "giant stamp," "yellow boot," "tiny scooter."
  It should be nameable instantly and identical every time it recurs.
- **Silhouette readability.** Every prop reads filled 100% black ([Shape Language](VISUAL_IDENTITY_LOCK.md#shape-language)),
  including in a character's hand — the object must not disappear into the body silhouette.
- **Visual hierarchy.** A prop's prominence matches its story job
  ([Composition](VISUAL_IDENTITY_LOCK.md#composition-rules)): the **hero prop** of a beat is large and
  can take the frame's single `BRAND_YELLOW` focal hit; background/utility props stay quiet and never
  out-compete the cast or the beat.
- **Mobile readability.** Props are **scaled for comedy and readability, not realism**
  ([Visual Identity Lock](VISUAL_IDENTITY_LOCK.md#shape-language)) — a "giant" stamp/ticket pad — so
  they read at thumbnail size on a muted vertical screen.
- **Advertiser-safe design.** No real weapons, gore, or unsafe objects. "Threat" objects are comic and
  benign (a boot immobilizer, a stamp), and karma devices punish the arrogant without harm
  ([Brand Bible](BRAND_BIBLE.md#content-pillars)).
- **Emotional storytelling through objects.** A prop can carry status and story on its own: the
  over-decorated stamp = CHIEF's ego; the tiny scooter = PIP's smallness; the tow truck = impartial
  justice arriving. Design each prop to *say* something that supports the beat.

---

## Prop Taxonomy

The canonical **prop categories** and the **controlled catalog** of prop names. A prop may carry a
**primary category** plus a story tag (e.g. a Vehicle that is also a Story Device / seed).

- **IN USE** = the prop exists in the shipped [A1/V1](../A1-first-video/04-asset-manifest.md) work.
- **AVAILABLE** = a reserved category to fill *when a story first needs it* (mint the object through
  this library, then it becomes IN USE).

| Category | Definition | Example (status) |
|---|---|---|
| **Signature** | A prop that *belongs to* a specific character and helps define them | `PROP_stamp_v1`, `PROP_ticketpad_v1` (CHIEF) — IN USE |
| **Personal** | A small personal-effect owned/carried by a character | `PROP_pip_coins_v1` (PIP coin purse) — IN USE |
| **Vehicle** | A rideable/driveable object | `PROP_pip_scooter_v1`, `PROP_chief_scooter_v1`, `PROP_towtruck_v1` — IN USE |
| **Utility** | A functional tool used to act on the world | `PROP_boot_v1` (immobilizer), `PROP_ticketpad_v1` — IN USE |
| **Reward** | A prize / trophy / prop that marks a win | (AVAILABLE — e.g. a trophy for a future flex) |
| **Furniture** | A small **movable** seat/stand/table a character uses | `PROP_podium_v1` (podium + flag) — IN USE |
| **Interactive** | A generic object built to be picked up, pressed, or handled | (AVAILABLE) |
| **Consumable** | A prop used up or produced in quantity within a video | `PROP_ticket_v1` (ticket sheet) — IN USE |
| **Collectible** | A repeated small item that stacks/accumulates for a gag | ticket pile (uses `PROP_ticket_v1`) — IN USE |
| **Story Device** | A prop whose *job is the plot* — a **seed** or a **karma device** | `PROP_chief_scooter_v1` (seed), `PROP_stamp_v1` (karma device) — IN USE |
| **Background prop** | A small movable object that dresses a shot without interaction | (AVAILABLE — must stay quiet; large fixed set → Environment Bible) |

**Taxonomy rules**
- **One name per object.** If a video needs "a clamp," that is `PROP_boot_v1` — do not mint a synonym.
- **Story tags are additive.** `Story Device` (seed / karma device) is a *tag* layered on a base
  category; the same scooter is a **Vehicle** and the **seed**.
- **Costume is not a prop** ([boundary](#inheritance-banner)): medals, cap, sash, scarf, gloves belong
  to the character asset, not this catalog.
- **Fixed set dressing is not a prop**: it belongs to the future **Environment Bible** (`BG_` namespace).

---

## Prop Classification

Independent of category, every prop is classified by **persistence** — how long it lives and how much it
is reused. This drives review depth and library placement.

| Class | Definition | Examples |
|---|---|---|
| **Hero prop** | Carries the beat; large, can take the frame's `BRAND_YELLOW` focal hit; often the karma device | `PROP_stamp_v1`, `PROP_boot_v1` |
| **Supporting prop** | Helps the beat but isn't the focus | `PROP_ticketpad_v1`, `PROP_podium_v1`, `PROP_pip_coins_v1` |
| **Background prop** | Set dressing; stays quiet, never out-competes the cast | (small movable dressing; fixed set → Environment Bible) |
| **Persistent prop** | Recurs across many videos; core reusable catalog | CHIEF's kit (stamp, boot, ticket pad); PIP's scooter/coins |
| **Single-use prop** | Built for one video's premise, not expected to recur | (a premise-specific object) |
| **Episode-exclusive prop** | Tied to one video's setting; may or may not return | `PROP_podium_v1`, `PROP_towtruck_v1` (A1-specific; promote to persistent if reused) |

> A prop can hold one **persistence** class and one **hero/supporting/background** role. Persistent hero
> props (the stamp, the boot) get the deepest review because they define the channel.

---

## Prop Standards

The object-design rules every prop obeys, extending the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md).

- **Size relationships.** Prop scale is **locked relative to the cast** and **comedy-scaled, not
  realistic** — the "giant" stamp/ticket pad read as oversized against CHIEF, and PIP's scooter reads
  tiny. A prop's size ratio to its owner must stay identical across all shots
  ([scale consistency](#interaction-rules)).
- **Proportions.** Built from the [shape kit](VISUAL_IDENTITY_LOCK.md#shape-language); chunky and bold,
  with oversized functional parts (a big stamp head, a chunky boot clamp) for readability.
- **Visual complexity.** Minimal — a prop resolves to 2–4 flat shapes. No gears, screws, fine mechanical
  or decorative detail. If it needs explaining, it's too complex.
- **Line treatment.** Uniform thick `INK` outline at the same weight as the cast in-frame
  ([Line System](VISUAL_IDENTITY_LOCK.md#line-system)); rounded corners by default. **Sharp/angular
  outline is a deliberate authority/threat accent** (the hard rubber stamp, a hazard chevron) — used
  sparingly.
- **Color usage.** Palette-only ([Color System](VISUAL_IDENTITY_LOCK.md#color-system)). **`BRAND_YELLOW`
  is reserved for hero props / the karma device** (the boot, stamp highlights) — one yellow focal hit
  per frame. Utility/background props use quieter palette tokens so they don't compete.
- **Wear rules.** The world is clean and flat — **no grime, rust, scuffs, or texture**
  ([Rendering Rules](VISUAL_IDENTITY_LOCK.md#rendering-rules)). "Well-used" is implied by *shape*, not
  texture.
- **Damage rules.** Damage is shown as a **flat shape change**, never texture: a dent is a flat notch, a
  crack is a single `INK` line, "broken" is a clean shape break. A damaged/altered state that recurs is
  a **variant asset** (see [naming](#prop-asset-naming)), never an ad-hoc redraw. Damage stays
  advertiser-safe (comic, bloodless).
- **Reuse rules.** **Reuse-first** ([Stage 2](../../docs/12-stage-2-channel-operating-system.md)): pull
  the locked prop from the catalog; never redraw it per video. A prop is designed once, locked, and
  swapped into shots via [interaction](#interaction-rules) + [pose](POSE_LIBRARY.md) composites.

---

## Character Ownership

Signature/personal props are **owned by a character** and are declared on that character's model sheet;
this library is the catalog those declarations point to. Shared/world props are owned by the library.

### PIP (the underdog / mascot) — [model sheet](../characters/pip.md)
| Prop | ID | Category / class |
|---|---|---|
| Tiny scooter | `PROP_pip_scooter_v1` | Vehicle · supporting (the thing unjustly booted) |
| Coin purse | `PROP_pip_coins_v1` | Personal · supporting (innocence beat in the hook) |

> PIP's props are **small, soft, and sympathetic** — they reinforce smallness. PIP owns **no** weapon,
> tool-of-authority, or karma device (PIP never causes the twist — [Character Bible](CHARACTER_BIBLE.md#pip)).

### CHIEF (the antagonist) — [model sheet](../characters/chief.md)
| Prop | ID | Category / class |
|---|---|---|
| Giant rubber stamp | `PROP_stamp_v1` | Signature · **hero** · Story Device (power object → karma device used *on* him) |
| Wheel boot / immobilizer | `PROP_boot_v1` | Utility · **hero** · `BRAND_YELLOW` karma device |
| Oversized ticket pad | `PROP_ticketpad_v1` | Signature · supporting |
| CHIEF's scooter | `PROP_chief_scooter_v1` | Vehicle · Story Device (**the seed** in frame 1) |

> CHIEF's props are **oversized, over-decorated tools of petty authority** — they broadcast ego and set
> up the karma. His stamp and boot are the recurring "power objects."

### Shared / world props (owned by the library)
| Prop | ID | Category / class |
|---|---|---|
| Tow truck | `PROP_towtruck_v1` | Vehicle · Story Device (impartial justice arriving) |
| Podium + tiny flag | `PROP_podium_v1` | Furniture · episode-exclusive |
| Ticket sheet | `PROP_ticket_v1` | Consumable / collectible (stacks into the ticket pile) |

### Rules for assigning future character props
1. **Justify by story.** A new prop must serve a [content pillar](BRAND_BIBLE.md#content-pillars) beat
   (a seed, a karma device, a status object), not novelty.
2. **Assign ownership explicitly.** Signature/personal → owner-prefixed ID + listed on that model sheet;
   world object → bare ID + listed here.
3. **Match the owner's band.** Underdog props stay small/soft/harmless; antagonist props stay
   oversized/authoritative. The prop must reinforce the character's [status read](POSE_LIBRARY.md).
4. **Keep it a prop, not costume** — if it is *worn* and defines the silhouette, it belongs on the
   character asset instead.
5. **Reuse before minting.** If an existing catalog prop can play the role, reuse it.

---

## Interaction Rules

How characters physically engage props. This library owns the **object + contact rules**; the
**body pose** is owned by the [Pose Library](POSE_LIBRARY.md) (a `pose + prop` composite) and the
**motion** by the future Animation Language.

| Interaction | Rule |
|---|---|
| **Holding** | The prop sits **in the oversized hand/glove**, reading fully **outside the body silhouette**. One clear grip; the object is never ambiguous. |
| **Carrying** | Prop held against the body still clears the silhouette; scale to the owner stays locked. |
| **Throwing** | This library defines the *held* and *released* object; the **arc/motion** is Animation Language. Throws stay comic and safe (nothing weaponized at a character). |
| **Placing** | Prop set on a surface reads as resting (flat contact shadow per the [Lighting Rules](VISUAL_IDENTITY_LOCK.md#lighting-rules)); position is continuity-locked if it is a seed. |
| **Dropping** | A drop is a placement + a reaction pose; the falling motion is Animation Language. |
| **Using** | The functional beat (stamping, clamping the boot, tearing a ticket) — one **key action per shot**, mute-readable, paired with a `hold`/`point` pose. |
| **Pointing** | A prop can extend a point (the stamp brandished); the arm + prop read as one clear diagonal outside the silhouette. |
| **Driving** | Vehicles (`scooter`, `towtruck`) seat the character at locked scale; the character reads *on* the vehicle, both silhouettes preserved. |
| **Touching** | Light contact (a hand on a prop) keeps both the hand and prop legible; no overlap that muddies either silhouette. |
| **Hand placement** | Grip is on the prop's obvious handle/mass; the [oversized gloves/hands](../characters/cast-style-guide.md) make the contact clear. Never hide the interaction behind the body. |
| **Scale consistency** | A prop's **size ratio to its owner is locked** — the giant stamp is *always* giant; PIP's scooter is *always* tiny. Never resize a prop per shot for convenience. |
| **Pose compatibility** | Each prop declares which [poses](POSE_LIBRARY.md#pose-taxonomy) it pairs with (e.g. stamp → `hold`/`point`/`victory`; scooter → `driving`/`idle`). A prop must not be forced into an incompatible pose. |

**Interaction invariants:** one key action per shot; the interaction is **mute-readable** (the object's
job is clear with sound off); both the character's and the prop's silhouettes stay intact; and any
seed/loop prop keeps its **fixed screen position** ([Composition continuity](VISUAL_IDENTITY_LOCK.md#composition-rules)).

---

## Prop Asset Naming

Extends the locked convention in the [Visual Identity Lock asset-ID table](VISUAL_IDENTITY_LOCK.md#asset-id-naming)
and [Character Bible naming standards](CHARACTER_BIBLE.md#character-naming-standards). No base rule is
redefined; this **formalizes the owner-prefix pattern already used** in the
[A1 manifest](../A1-first-video/04-asset-manifest.md).

| Thing | Convention | Example |
|---|---|---|
| World / generic prop | `PROP_[name]_v#` | `PROP_stamp_v1`, `PROP_towtruck_v1` |
| Owner-scoped prop | `PROP_[owner]_[name]_v#` | `PROP_pip_scooter_v1`, `PROP_chief_scooter_v1` |
| Prop variant / altered state | `PROP_[name]_[variant]_v#` | `PROP_boot_clamped_v1` |

**Naming rules (extensions):**
- Use the **owner prefix** (`PROP_[owner]_[name]`) when the same object type exists for more than one
  character (both own a *scooter*) or for a clearly **personal** item (`PROP_pip_coins_v1`). Otherwise
  use the **bare** `PROP_[name]_v#` for single-instance world/signature objects (`PROP_stamp_v1`).
- `[name]` and `[variant]` are **lowercase, hyphen-free, single concept**
  ([Character Bible](CHARACTER_BIBLE.md#character-naming-standards)); never a synonym for an existing prop.
- **Bump `_v#` only** when the prop's locked design genuinely changes (it should not in Phase 1). A
  recurring *altered state* (clamped, torn, stacked) is a **variant asset**, not a version bump.
- **Namespace discipline** — props are `PROP_`; backgrounds/set dressing are `BG_` (Environment Bible),
  on-frame text is `UI_`, effects are `FX_`. Do not file a prop under another namespace.

---

## Prompt Standards

The **prompt architecture** for prop assets. This section defines structure only; it does **not**
restate the style prefix or the paste-ready scaffolds — those live in the
[visual-prompt template](../templates/visual-prompt-template.md) (style prefix + slots incl. `PROPS`)
and the worked list in the [A1 asset manifest](../A1-first-video/04-asset-manifest.md) and
[storyboard](../A1-first-video/03-storyboard.md). Every prop prompt **must**:

- **prepend the locked style prefix + palette** from the [visual-prompt template](../templates/visual-prompt-template.md);
- for a recurring prop, **attach the approved prop reference** (reference image / fixed seed) so it stays identical;
- **name the target asset ID**, category, and locked scale.

| Prompt type | Purpose | Structure (beyond style prefix) | Reference scaffold |
|---|---|---|---|
| **Single prop** | One object asset | "flat-2D `<prop>`, `<2–4 shape description>`, `<palette token>`, chunky, thick `INK` outline, plain background, no character" | [visual-prompt template](../templates/visual-prompt-template.md) |
| **Prop turnaround** | Front / 3/4 / side of one prop | "`<prop>` turnaround: front, 3/4, side; identical proportions across views" | [visual-prompt template §4](../templates/visual-prompt-template.md) |
| **Prop sheet** | A set/kit at once | "prop sheet: `<list prop names>` (e.g. CHIEF's kit: stamp, boot, ticket pad), consistent scale + line weight" | [A1 asset manifest](../A1-first-video/04-asset-manifest.md) |
| **Character + prop** | Owner holding/using their prop | character reference sheet + prop asset ID + one [interaction](#interaction-rules) | [Character Bible — prop interaction](CHARACTER_BIBLE.md#character-prompt-standards) |
| **Pose + prop** | A full acting beat with an object | [pose](POSE_LIBRARY.md#prompt-standards) + prop asset ID + key action, locked scale | [Pose Library prompt standards](POSE_LIBRARY.md#prompt-standards) |
| **Environment + prop** | A prop placed in a set | prop asset ID + `BG_` set reference + placement/continuity note *(set dressing owned by Environment Bible)* | [A1 storyboard](../A1-first-video/03-storyboard.md) |

**One prop (or one clear kit) per prompt.** Keep it to 2–4 flat shapes; request the hero-prop
`BRAND_YELLOW` hit only where the beat calls for it.

---

## Production Workflow

Props follow the reuse-first lifecycle in [Stage 2](../../docs/12-stage-2-channel-operating-system.md)
and the [Character Bible lifecycle](CHARACTER_BIBLE.md#character-lifecycle) model.

1. **Creation.** Confirm the prop is justified by a story beat ([assignment rules](#character-ownership));
   pick its [category](#prop-taxonomy), [class](#prop-classification), and owner; generate with the
   [prompt standards](#prompt-standards).
2. **Review.** Run the [Quality Checklist](#quality-checklist) plus the
   [Visual Identity Lock quality checklist](VISUAL_IDENTITY_LOCK.md#quality-checklist). Off-model →
   regenerate, never settle.
3. **Approval.** The object must read as its one iconic thing at thumbnail size, hold locked scale to its
   owner, and stay advertiser-safe.
4. **Versioning.** File as `PROP_[name]_v1` (or owner-scoped / variant per [naming](#prop-asset-naming)),
   and — if a signature/personal prop — list it on the owner's model sheet. Adding a prop is **editorial**;
   only a locked-design change bumps `_v#`.
5. **Reuse.** Shots **select** an existing prop and compose it with a [pose](POSE_LIBRARY.md); they do
   **not** generate new objects unless a genuinely new object is needed. This is the cost moat.
6. **Retirement.** Retire a prop only by a logged decision
   ([Decision Log](../../docs/21-decision-log.md)); mark it `deprecated`, keep the asset (published
   videos reference it), and stop using it in new videos. A replacement gets a **new name/ID**, never a
   silent redefinition.

---

## Quality Checklist

Run before accepting **any** prop asset (in addition to the
[Visual Identity Lock quality checklist](VISUAL_IDENTITY_LOCK.md#quality-checklist)). One failure =
reject and regenerate.

- [ ] **One iconic read** — the object is instantly nameable and identical to its catalog reference.
- [ ] **Silhouette reads** — recognizable filled 100% black, including when held (clears the body).
- [ ] **2–4 flat shapes** — no mechanical/fine detail; built from the shape kit.
- [ ] **Uniform `INK` outline** at the in-frame weight; rounded default; sharp only as an authority accent.
- [ ] **Palette-only color** — `BRAND_YELLOW` reserved for hero prop / karma device; one yellow focal hit.
- [ ] **Flat rendering** — no gradients, textures, grime, or realistic materials; ≤1 flat shadow tone.
- [ ] **Locked scale** — size ratio to the owner matches every other appearance.
- [ ] **Correct hierarchy** — hero prop prominent; supporting/background props stay quiet.
- [ ] **Advertiser-safe** — no real weapon/gore; damage is a flat, bloodless shape change.
- [ ] **Right namespace + owner** — `PROP_` (not `BG_`/`UI_`/`FX_`); owner-prefix applied per the rules; not costume.
- [ ] **Correct ID** — named per [naming standards](#prop-asset-naming) and filed; signature props also on the model sheet.

---

## Future Integration

This library is a **parent/sibling** to the remaining world-, shot-, and motion-level documents. Each
must reference a prop by its canonical ID rather than describing an object from scratch.

| Consumer (future doc / stage) | How it uses this library |
|---|---|
| **Environment Bible** | Consumes the **prop vs. environment boundary**: props are movable objects; fixed set dressing (`BG_`) is the Environment Bible's. It places catalog props into locked sets. |
| **Camera Language** | Frames hero props (the low hero angle on the raised stamp; the punch-in on the karma device) and keeps seed props in their continuity position. |
| **Animation Language** | Owns **prop motion** (throw arcs, the tow-hook swing, a stamp slam, stacking tickets) using this library's static objects as the things it moves. |
| **Wallpaper Prompt Framework** | Selects a **hero prop** (stamp / boot) alongside the hero pose + expression for channel art and thumbnails per the [thumbnail spec](../templates/thumbnail-spec.md). |
| **Shot Generation** | Each shot names the props present by ID, driving the [visual-prompt template](../templates/visual-prompt-template.md) `PROPS` slot; seed props flagged for continuity. |
| **Storyboard generation** | The [storyboard](../A1-first-video/03-storyboard.md) prop column is expressed as canonical `PROP_` IDs, making set-ups reusable and machine-selectable. |
| **Video production pipeline** | The [Stage 6 production compiler](../../docs/15-stage-6-production-compiler.md) assembles shots from reusable **cast + pose + expression + prop**, hitting the sub-30-minute reuse target; the [asset manifest](../A1-first-video/04-asset-manifest.md) tags each prop reuse-vs-new. |

---

## Repository Integration

Additive one-line pointers are added in this branch at the highest-traffic entry points; deeper links
are recommendations to avoid over-editing locked docs.

| Document | Relationship | Action |
|---|---|---|
| [`production/design/README.md`](README.md) | Design/identity folder index | Add the Prop Library + update planned-children note (done) |
| [`production/design/CHARACTER_BIBLE.md`](CHARACTER_BIBLE.md) | Parent (character system) | Link the "Prop Library" future-doc row to this now-existing doc (done) |
| [`production/design/POSE_LIBRARY.md`](POSE_LIBRARY.md) | Sibling (the body) | Point its "pose + prop" prompt row at this catalog (done) |
| [`docs/00-index.md`](../../docs/00-index.md) | Master doc map | List the Prop Library under Design standards (done) |
| [`production/README.md`](../README.md) | Production folder map | Add to the `design/` tree + a traceability row (done) |
| [`production/characters/pip.md`](../characters/pip.md) · [`chief.md`](../characters/chief.md) | Signature-prop tables | Point each "Signature props" section at this catalog (done) |
| [`production/A1-first-video/04-asset-manifest.md`](../A1-first-video/04-asset-manifest.md) | The worked prop list | Recommend a "catalog: Prop Library" pointer (follow-up) |

**Anti-duplication (ownership map).** Where a requested topic is already owned elsewhere, this library
**references and extends** rather than competing:
- **Rendering, color, shape, silhouette** → owned by the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md);
  this library applies them to *objects* only.
- **Props-as-story (seeds, karma devices, pillar service)** → owned by the [Brand Bible](BRAND_BIBLE.md)
  and the [twist](../../intelligence/03-narrative-twist-library.md)/[pattern](../../intelligence/06-narrative-pattern-library.md)
  libraries; referenced.
- **The body holding the prop** → owned by the [Pose Library](POSE_LIBRARY.md) (pose + prop composite).
- **Prop motion / timing** → will be owned by the future **Animation Language**.
- **Fixed set dressing / backgrounds** → will be owned by the future **Environment Bible** (`BG_`).
- **On-frame text** (`UI_`) and **worn costume** (part of `CHAR_`) → owned by the
  [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md#rendering-rules) / [Character Bible](CHARACTER_BIBLE.md).
- **Character build, lifecycle, naming base** → owned by the [Character Bible](CHARACTER_BIBLE.md).

This library owns only the **object catalog, prop taxonomy/classification, object-design standards,
character ownership of objects, and interaction rules**.

---

## Change Control

A **locked** document, governed like the [Locked Roadmap](../../docs/03-locked-roadmap.md) and
[Decision Log](../../docs/21-decision-log.md).

- **Editorial changes** (adding a prop, a variant, a new AVAILABLE category slot, clarifications,
  cross-links) may be made freely; **no version bump**.
- **Substantive changes** (changing a locked prop's design, adding/removing a **prop category** or
  classification, changing the interaction rules or the prop/costume or prop/environment boundary)
  require: (1) a rationale in the [Decision Log](../../docs/21-decision-log.md), (2) a pass through the
  [Stage 2 5-Gate test](../../docs/12-stage-2-channel-operating-system.md), and (3) confirmation that no
  [locked decision](../../docs/03-locked-roadmap.md) or root document is contradicted.
- **New props** must be filed in this catalog (with an ID, category, class, and owner) **before** they
  appear in any prompt or shot — this is what keeps generation from inventing objects.

> **Objects are story machinery.** When in doubt, choose the prop whose one iconic read makes the seed
> and the karma unmistakable with the sound off — and reuse it, never redraw it.
