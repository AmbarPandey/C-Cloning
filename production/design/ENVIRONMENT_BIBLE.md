# Environment Bible

> **Status:** Locked · **Applies to:** every location, background, set element, atmosphere, weather,
> and time-of-day asset generated for any C-Cloning video · **Owner role:** Lead Environment Artist /
> World Builder / Production Designer / Cinematic Layout Director
>
> **This is the canonical world system of the C-Cloning universe.** It defines every reusable
> location, environmental asset, atmosphere, weather condition, lighting context, and world-building
> rule — and it treats **every recurring location as a reusable production asset**, not a throwaway
> background. **Future scenes must place the cast into a location from this Bible (or mint one through
> it) rather than inventing a background ad hoc.**
>
> The [Expression Library](EXPRESSION_LIBRARY.md) explains the face, the
> [Pose Library](POSE_LIBRARY.md) explains the body, the [Prop Library](PROP_LIBRARY.md) explains the
> objects — **this document explains the world they all live in.**

## Inheritance banner

This document is a **child of the Identity Core** and inherits from all six foundation documents; it
never overrides them:

- **Appearance & background law** → the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md). The
  [Background Rules](VISUAL_IDENTITY_LOCK.md#background-rules) (complexity limits, allowed detail, color
  hierarchy, distraction avoidance), the [Composition Rules](VISUAL_IDENTITY_LOCK.md#composition-rules)
  (negative space, thumb-safe zones, seed continuity, loop seam), the
  [Lighting Rules](VISUAL_IDENTITY_LOCK.md#lighting-rules) (flat ambient, no light source, one flat
  shadow tone, **no gradients**), and the [Color System](VISUAL_IDENTITY_LOCK.md#color-system)
  (the `SKY`/`ASPHALT` Environment palette + the rule that new setting tokens register **there** first)
  are all inherited. This Bible adds *world-building* rules, not new visual law. On a visual question,
  the Lock wins.
- **Meaning / setting role** → the [Brand Bible](BRAND_BIBLE.md). Settings are **variables** — only the
  situation and twist change between videos while the cast/format stay constant
  ([content pillars](BRAND_BIBLE.md#content-pillars), [V1 Series Bible](../../V1/08-series-bible.md)).
  Worlds stay **advertiser-safe**, **global / non-region-locked**, and serve the status-gap /
  comeuppance story.
- **Who lives in the world** → the [Character Bible](CHARACTER_BIBLE.md),
  [Expression Library](EXPRESSION_LIBRARY.md), [Pose Library](POSE_LIBRARY.md), and
  [Prop Library](PROP_LIBRARY.md). The environment must stay **quieter than the cast** and never
  out-compete the beat's subject ([visual hierarchy](VISUAL_IDENTITY_LOCK.md#core-visual-principles)).

It also **defers to** (references, never restates):
- Naming & reuse → [Stage 2](../../docs/12-stage-2-channel-operating-system.md) and the
  [Visual Identity Lock asset-ID table](VISUAL_IDENTITY_LOCK.md#asset-id-naming).
- The worked background list → the [A1 asset manifest](../A1-first-video/04-asset-manifest.md) and
  [storyboard](../A1-first-video/03-storyboard.md).

> **Ownership boundaries (important).**
> - **Environment vs. prop.** This Bible owns **fixed set dressing** — the ground, sky, walls,
>   architecture, and painted markings that *locate* a scene (the `BG_` namespace). **Discrete, movable,
>   interactable objects** (the stamp, boot, scooters, tow truck) are the
>   [Prop Library](PROP_LIBRARY.md)'s (`PROP_`). This mirrors the boundary the Prop Library already set.
> - **Space vs. camera.** This Bible owns the *space* and its layout; **how the camera frames and moves
>   through it** (shot grammar, angles) belongs to the future **Camera Language**.
> - **Static world vs. motion.** This Bible owns the *static* location and its atmospheric *state*;
>   **ambient motion, parallax, and weather animation** belong to the future **Animation Language**.
> - **Palette registry.** New Environment palette tokens are **registered in the
>   [Visual Identity Lock Color System](VISUAL_IDENTITY_LOCK.md#color-system)** via
>   [Change Control](#change-control); this Bible *documents which tokens each location uses* and
>   *proposes* new ones — it does not keep a competing palette.

---

## Table of contents

1. [Purpose](#purpose)
2. [World Philosophy](#world-philosophy)
3. [Environment Taxonomy](#environment-taxonomy)
4. [Location Classification](#location-classification)
5. [Background Standards](#background-standards)
6. [Environmental Assets](#environmental-assets)
7. [Weather System](#weather-system)
8. [Time System](#time-system)
9. [Environmental Storytelling](#environmental-storytelling)
10. [Character Interaction](#character-interaction)
11. [Prompt Standards](#prompt-standards)
12. [Production Workflow](#production-workflow)
13. [Quality Checklist](#quality-checklist)
14. [Location Profile — Parking Lot (first implementation)](#location-profile--parking-lot)
15. [Future Location Template](#future-location-template)
16. [Future Integration](#future-integration)
17. [Repository Integration](#repository-integration)
18. [Change Control](#change-control)

---

## Purpose

A recurring, reusable world is a storytelling asset *and* a production-speed asset. The
[Brand Bible](BRAND_BIBLE.md#content-pillars) locks that **settings are variables** — the channel will
visit a parking lot, a beach, an office, a zoo, a gym — but each of those worlds must be built **once**,
consistently, and reused, or the channel loses both its recognizable look and its cost advantage.

Environmental consistency matters because:

- **Immersion & tone.** A coherent, on-brand world makes each Short feel like it belongs to the same
  universe; a mismatched or noisy background breaks the spell and the recognition.
- **Storytelling.** Locations silently establish the **status gap** (an authority's turf vs. a little
  guy's spot) and can *carry the seed* of the twist (the `ALERT_RED` no-parking zone). A location does
  narrative work before a character moves ([Environmental Storytelling](#environmental-storytelling)).
- **Production speed.** The [Stage 2 reuse economics](../../docs/12-stage-2-channel-operating-system.md)
  (~70% reuse, sub-30-minute videos) depend on a shared **location catalog** — a built location is
  reused across many videos with only a swapped situation.
- **Brand recognition.** A signature world palette and layout are part of the
  [brand recognition system](BRAND_BIBLE.md#brand-recognition-system); the world must always stay
  *quieter* than the cast so the recognizable characters pop.
- **Automation needs a closed catalog.** Prompt frameworks and shot generation must select a location
  from a finite, named library — never invent a background per shot — so the world stays consistent at
  scale.

> **Rule of thumb:** if a background appears in more than one shot or could appear in a future video, it
> is a **catalogued location asset** with an ID — not a one-off drawing. And it must never be the
> loudest thing in the frame.

---

## World Philosophy

The principles every location obeys. These apply the roots to *environments*; they do not restate them.

- **Simplicity.** A location is a few large flat shapes — a ground plane, a backdrop, and 1–3 set
  pieces ([Background Rules](VISUAL_IDENTITY_LOCK.md#background-rules)). Suggest a place with the
  *minimum* iconic elements (a meter + lines = "parking lot"); never render a detailed environment.
- **Readability.** The setting must be identifiable in **under a second** from its silhouette and its
  1–2 iconic elements, muted, at thumbnail size.
- **Visual hierarchy.** The world is **background** — it is always quieter, lower-contrast, and more
  desaturated than the cast and hero props, and it never competes for the eye
  ([visual hierarchy](VISUAL_IDENTITY_LOCK.md#core-visual-principles)).
- **Mobile-first readability.** Built for a vertical 9:16 muted feed: keep the horizon and key set
  pieces clear of the [thumb-safe zones](VISUAL_IDENTITY_LOCK.md#composition-rules) and leave generous
  negative space for the cast.
- **Advertiser-safe environments.** Clean, wholesome, non-threatening places. No hazardous, scary,
  graphic, real-brand, political, or region-locked settings ([Brand Bible](BRAND_BIBLE.md#content-pillars)).
- **Environmental storytelling.** Every location is designed to *say something* that supports the beat
  (status, conflict, tone) without a word ([Environmental Storytelling](#environmental-storytelling)).
- **World consistency.** A given location looks identical every time it recurs — same layout, palette
  tokens, and set pieces — so it is a recognizable, reusable asset.
- **Recognizable locations.** Recurring worlds become part of the brand ("the parking lot where CHIEF
  rules") — designed with a memorable, repeatable identity.
- **Global by default.** Language-free and culturally neutral — no readable signage text, no
  region-specific architecture that wouldn't travel ([Brand Bible audience](BRAND_BIBLE.md#audience-definition)).

---

## Environment Taxonomy

The canonical **location categories** and the **controlled catalog** of location names. A location has
one **primary category** and an **Indoor/Outdoor** attribute.

- **IN USE** = the location exists in the shipped [A1/V1](../A1-first-video/04-asset-manifest.md) work.
- **AVAILABLE** = a reserved category to fill *when a story first needs it* (build the location through
  this Bible, then it becomes IN USE).

| Category | Definition | In/Out | Example location | Status |
|---|---|---|---|---|
| **Parking / Roads** | Lots, streets, kerbs, transit lanes | Outdoor | **Parking Lot** (`BG_parkinglot`) | **IN USE** |
| **Urban** | City streets, plazas, storefronts (façades only) | Outdoor | city block | AVAILABLE |
| **Commercial / Retail** | Shops, counters, queues | Indoor | shop interior | AVAILABLE |
| **Workplace / Institutional** | Office, DMV, reception — "petty authority" turf | Indoor | office | AVAILABLE |
| **School** | Classroom, hallway, yard | Both | classroom | AVAILABLE |
| **Residential / Domestic** | Home, apartment, front stoop | Both | living room | AVAILABLE |
| **Parks / Nature** | Park, garden, forest, mountain, sky | Outdoor | park | AVAILABLE |
| **Recreation** | Beach, gym, zoo, pool, fair (per [V1 Series Bible](../../V1/08-series-bible.md)) | Both | beach · gym · zoo | AVAILABLE |
| **Transit** | Bus/train interior, station, stop | Both | bus interior | AVAILABLE |
| **Public Space** | Plaza, waiting area, civic space | Both | town square | AVAILABLE |
| **Abstract / Void** | A plain `PAPER` limbo for pure character beats, thumbnails, wallpapers | N/A | studio void (`BG_void`) | AVAILABLE |

**Taxonomy rules**
- **One name per location.** A specific place is built once and reused; do not mint a synonym for an
  existing location.
- **Category drives the token set & mood** (see [Environmental Storytelling](#environmental-storytelling)):
  authority/institutional settings lean rigid and symmetrical; recreation/nature settings lean open and
  soft.
- **Abstract void** is the deliberate "no environment" setting — a flat `PAPER` field used for
  reaction close-ups, [wallpapers, and channel art](#future-integration); it still obeys the
  [Background Rules](VISUAL_IDENTITY_LOCK.md#background-rules).

---

## Location Classification

Independent of category, every location is classified by **persistence** — how central and how reused it
is. This drives design depth and catalog placement.

| Class | Definition | Example |
|---|---|---|
| **Hero location** | Central to a video's premise; the stage the beats play out on | **Parking Lot** (A1) |
| **Recurring location** | Reused across many videos; core catalog | Parking Lot (recurs), future office/beach |
| **Supporting location** | A secondary space within/around a video | a kerbside, an entrance |
| **Background-only location** | A distant backdrop never entered (a skyline behind the set) | far city silhouette |
| **Episode-exclusive location** | Built for one premise, not expected to recur | a one-off themed set |
| **Future-expansion location** | Reserved for the [franchise roadmap](../../docs/32-future-expansion.md) (new niches/languages) | genre worlds for cloned channels |

> A location holds one persistence class. A **hero + recurring** location (the Parking Lot) gets the
> deepest design and a full [location profile](#location-profile--parking-lot).

---

## Background Standards

The [Visual Identity Lock Background Rules](VISUAL_IDENTITY_LOCK.md#background-rules) **already own**
background complexity limits, allowed detail, color hierarchy, and distraction avoidance — those are
inherited, not restated. This Bible adds the **spatial / depth-layering** standard that turns a flat
backdrop into a reusable, characters-can-stand-in-it *set*.

**Depth layers (every location is built in three flat planes):**

| Plane | What it holds | Rules |
|---|---|---|
| **Foreground (fg)** | Optional framing element the cast passes in front of/behind; the ground the cast stands on | Sparse; never blocks the beat; a hero seed prop may live here (owned by [Prop Library](PROP_LIBRARY.md)) |
| **Midground (mg)** | The **stage** — where the cast, poses, and interactions happen; the key set pieces (meter, podium spot) | The clearest, most negative-space-rich band; the cast lives here at a consistent ground line |
| **Background (bg)** | The backdrop/sky and distant silhouettes that name the place | Most desaturated, lowest contrast, no detail that competes; flat `SKY`/backdrop token |

**Depth & layering standards**
- **Flat, layered — never perspectival rendering.** Depth is implied by **stacking flat planes** and
  scale, not by realistic perspective, vanishing-point detail, or gradients.
- **A consistent ground line / horizon** per location so the cast always "sits" in the space at the
  correct scale across shots.
- **Detail decreases with depth:** fg may carry the one framing element; mg carries the stage; bg is
  nearly empty. The **subject band (mg) keeps the most negative space**.
- **Depth cueing without gradients:** use **flat value/desaturation steps** between planes (bg lighter
  & flatter than mg) — never atmospheric gradient haze.
- **Visual balance & negative space** follow the [Composition Rules](VISUAL_IDENTITY_LOCK.md#composition-rules):
  balance set pieces against open space; keep the mg subject zone and any on-frame text clear of the
  top ~15% / bottom ~20% UI zones.
- **Mobile readability:** the location must read at thumbnail size; if a set piece disappears when
  small, enlarge or drop it.

---

## Environmental Assets

Every location is a set of versioned `BG_` assets. IDs extend the
[Visual Identity Lock asset-ID table](VISUAL_IDENTITY_LOCK.md#asset-id-naming) (`BG_[name]_v#`); this
section **formalizes the variant pattern already used** in the
[A1 manifest](../A1-first-video/04-asset-manifest.md) (`BG_parkinglot_v1`, `BG_parkinglot_meter_v1`,
`BG_noparking_zone_v1`).

| Asset kind | Convention | Example |
|---|---|---|
| **Base location** (establishing wide) | `BG_[location]_v#` | `BG_parkinglot_v1` |
| **Sub-area / framing variant** | `BG_[location]_[area]_v#` | `BG_parkinglot_meter_v1` |
| **Set element / marking** (fixed dressing overlay) | `BG_[element]_v#` (often `_zone`) | `BG_noparking_zone_v1` |
| **Time-of-day variant** | `BG_[location]_[time]_v#` | `BG_parkinglot_night_v1` |
| **Weather variant** | `BG_[location]_[weather]_v#` | `BG_parkinglot_rain_v1` |
| **Season variant** | `BG_[location]_[season]_v#` | `BG_beach_winter_v1` |
| **Event variant** | `BG_[location]_[event]_v#` | `BG_parkinglot_fair_v1` |

**Environmental-asset rules**
- **Namespace discipline** — locations/set dressing are `BG_`; movable objects are `PROP_`
  ([Prop Library](PROP_LIBRARY.md)); on-frame text is `UI_`; effects are `FX_`; characters are
  `CHAR_`. Never file a background under another namespace, or a prop under `BG_`.
- `[location]`, `[area]`, `[time]`, `[weather]`, `[season]`, `[event]` are **lowercase, hyphen-free,
  single concept** ([Character Bible naming standards](CHARACTER_BIBLE.md#character-naming-standards)).
- **Variants share the base location's layout & identity** — a time/weather/area variant only changes
  the atmospheric state or framing, never the location's identity. A different *place* is a new base
  location, not a variant.
- **Day/night, weather, season, event are variant axes**, applied via
  [Time](#time-system)/[Weather](#weather-system); they are generated only when a story needs them.
- **Bump `_v#` only** when the location's locked design genuinely changes; a new atmospheric state is a
  **variant**, not a version bump.
- **New palette tokens** a location needs (e.g. `SAND`, `OFFICE_WALL`, a night-sky token) are
  **registered in the [Visual Identity Lock Color System](VISUAL_IDENTITY_LOCK.md#color-system)** first
  via [Change Control](#change-control); this Bible then records which tokens the location uses.

---

## Weather System

Weather is a **variable atmospheric state** applied to a location. Because the channel is a **flat,
no-gradient** world ([Lighting Rules](VISUAL_IDENTITY_LOCK.md#lighting-rules)), weather is expressed
with **palette-token swaps + flat overlay shapes + at most one flat mood-shadow** — **never** gradients,
soft haze, bloom, or realistic lighting.

| Condition | Flat expression | Usage rule |
|---|---|---|
| **Clear** (default) | Flat `SKY` fill, bright even ambient | The default; used unless a beat needs otherwise |
| **Cloudy** | 1–3 flat rounded cloud shapes on `SKY`; slightly desaturated ground | Gentle, calm; safe for any comedy |
| **Overcast** | Swap `SKY` for a flatter grey-blue token; drop overall contrast a step | Mild melancholy / "before the turn" tone |
| **Rain** | Flat evenly-spaced diagonal `INK`/desaturated streak shapes (behind the cast) + a flat cloud shape + optional flat puddle shapes | Streaks stay low-contrast so the cast reads; benign, never stormy-scary |
| **Wind** | Static **lean** of soft elements + `FX_motionlines_v1`; leaves/paper as flat shapes | The *motion* itself is [Animation Language](#future-integration); this owns the static lean read |
| **Fog** | A single flat, semi-opaque `PAPER`/pale overlay shape over the **bg only**, reducing bg detail | Never over the cast; used to simplify/mysterious a bg, still mute-readable |
| **Snow** | Swap ground token for a pale flat token + flat round snow dots; simple flat flakes | Wholesome/seasonal; keep the cast high-contrast against it |
| **Storm** | Cloudy + rain + one flat `BRAND_YELLOW` angular lightning shape as a *comedic accent* | **Advertiser-safe only** — comic, never frightening; use sparingly |
| **Special (sparkle air, heat shimmer-as-flat-lines, petals)** | Flat decorative shapes as a mood accent | Must stay quiet and on-palette; register any new element here |

**Weather rules**
- **Default is clear.** Weather is chosen deliberately for tone, like the setting.
- **Weather never reduces cast readability** — overlays sit **behind** the cast (or on the bg only) and
  stay low-contrast; the cast and hero prop remain the most vivid things on screen.
- **One weather state per video**, held across all shots (a deliberate shift is allowed only as a
  documented tension beat, and must return for the [loop seam](VISUAL_IDENTITY_LOCK.md#composition-rules)).
- **Advertiser-safe ceiling** — weather is atmosphere/comedy, never threat or disaster.
- **No gradients, ever** — every weather element is a flat shape or a token swap.

---

## Time System

Time-of-day is also a **variable atmospheric state**, expressed by **swapping the sky/ground palette
tokens and adding flat sky elements** — never a gradient sky. New time tokens register in the
[Visual Identity Lock Color System](VISUAL_IDENTITY_LOCK.md#color-system).

| Time | Flat expression |
|---|---|
| **Morning** | Default bright `SKY`; crisp, cheerful; long-side flat contact shadows |
| **Afternoon** (default) | Full-bright flat `SKY`, even ambient — the A1 default ("bright, flat midday") |
| **Golden hour** | Swap to a warm flat sky token + a warm flat wash on set pieces (flat, not graded) |
| **Sunset** | Warm flat sky token + a few flat cloud shapes; darker flat ground token |
| **Overcast** | Flat grey-blue sky token; reduced contrast (shared with [Weather](#weather-system)) |
| **Night** | Swap `SKY` for a dark flat night token + flat stars/moon shapes; cast stays high-contrast; a single flat cool mood-shadow allowed |

**Time / lighting-continuity rules**
- **One time-of-day per video.** Pick it up front; keep the sky/ground tokens and shadow direction
  identical across every shot.
- **Loop-seam match.** The first and last frames must share the *same* time-of-day and lighting so the
  [loop](VISUAL_IDENTITY_LOCK.md#composition-rules) is seamless (A1 returns to the bright shot-1 state).
- **Lighting stays flat.** Time is a *palette + flat-element* change, not modeled lighting; obey the
  [Lighting Rules](VISUAL_IDENTITY_LOCK.md#lighting-rules) (one flat shadow tone, no gradients, no
  rim/volumetric light).
- **Tension shift exception.** A single flat cool mood-shadow may "creep in" for the pre-twist beat
  (as in [V1 shot 6](../../V1/01-script.md)) — it is a flat shape, not a lighting simulation, and it
  clears by the loop seam.

---

## Environmental Storytelling

How a location silently communicates — **without dialogue** — in service of the
[Brand storytelling philosophy](BRAND_BIBLE.md#storytelling-philosophy). The environment does narrative
work *before and beneath* the cast's performance.

| It communicates… | …through the environment |
|---|---|
| **Status** | Turf and elevation: an authority's domain (rigid, symmetrical, sign-and-rule-heavy) vs. the little guy's small spot; a raised platform/podium spot = power (CHIEF), a low kerb/meter = the underdog. |
| **Conflict** | The **seed** lives in the set: the `ALERT_RED` [no-parking zone](#location-profile--parking-lot) planted in frame 1 is the environmental seed the twist pays off. Hazard/rule markings signal the coming clash. |
| **Emotion** | Palette & openness: open sky + `PAPER` space = safety/relief; a closed, rigid, grey space = pressure; [weather](#weather-system)/[time](#time-system) set the mood (overcast before the turn, bright at the warm button). |
| **Resolution** | The world returns to calm and bright at the payoff/loop seam — order restored, fair and clean. |
| **Comedy** | Comedic scale and framing: an over-official, over-signed environment makes petty authority absurd; a tiny subject in a big empty lot reads as sympathetic. |
| **Tone** | Consistently warm, clean, benign — the world is a *fair* place where karma lands ([Brand Bible personality](BRAND_BIBLE.md#brand-personality)). Never grim, threatening, or cynical. |

**Storytelling rules**
- The environment **supports** the beat; it never steals it — status/conflict cues are quiet and
  low-contrast so the cast still leads.
- **Seeds placed in the set** obey [seed continuity](VISUAL_IDENTITY_LOCK.md#composition-rules) (fixed
  screen position across the video); the seed *object* is a [prop](PROP_LIBRARY.md), the *place* it sits
  (the zone) is a `BG_` set element.
- Staging the **status gap** in space (high vs. low, big turf vs. small spot) is the environment's
  primary job in the [NP1 Comeuppance](../../intelligence/06-narrative-pattern-library.md) engine.

---

## Character Interaction

How the cast, props, vehicles, and background elements coexist in a location. The environment is the
stage; this section owns the **stage-contact rules** (poses are the [Pose Library](POSE_LIBRARY.md)'s,
motion is the future Animation Language's).

| Element | Interaction rule |
|---|---|
| **Characters** | Composited into the **midground** at a consistent ground line and locked scale; grounded by a flat contact shadow ([Lighting Rules](VISUAL_IDENTITY_LOCK.md#lighting-rules)). The cast is always higher-contrast than the world; the bg never overlaps or camouflages a character. |
| **Props** | Placed in the set per the [Prop Library interaction rules](PROP_LIBRARY.md#interaction-rules) at locked scale; a **seed/loop prop** keeps its fixed screen position within the location across shots. |
| **Vehicles** | Driveable [props](PROP_LIBRARY.md) (scooter, tow truck) travel *through* the location on the ground line; entrances/exits use the location's fg/bg planes without breaking scale. |
| **Background elements (fixed set dressing)** | Stay in the bg/fg planes, quiet and low-contrast; never move independently (that would be [Animation Language](#future-integration)); never carry readable text or compete with the cast. |

**Interaction invariants:** a consistent ground line and scale per location; the cast reads clearly
against the world at all times; seeds hold position; nothing in the environment out-contrasts the
subject; the location's identity (layout + tokens + set pieces) is identical every time it recurs.

---

## Prompt Standards

The **prompt architecture** for environment assets. This section defines structure only; it does **not**
restate the style prefix or the paste-ready scaffolds — those live in the
[visual-prompt template](../templates/visual-prompt-template.md) (style prefix + the `BACKGROUND` slot)
and the worked scene prompts in the [A1 storyboard](../A1-first-video/03-storyboard.md) and
[V1 image prompts](../../V1/04-image-prompts.md). Every environment prompt **must**:

- **prepend the locked style prefix + palette** from the [visual-prompt template](../templates/visual-prompt-template.md);
- **name the target `BG_` asset ID**, the location, and its [time](#time-system)/[weather](#weather-system) state;
- request **"flat layered background, desaturated, no characters, generous negative space, quieter than
  the subject"** (the background read).

| Prompt type | Purpose | Structure (beyond style prefix) | Reference scaffold |
|---|---|---|---|
| **Single location** | One base location | "wide flat-2D `<location>`, ground + backdrop + 1–3 set pieces, `<tokens>`, `<time/weather>`, no characters, mobile-legible" | [visual-prompt template](../templates/visual-prompt-template.md) |
| **Location sheet** | A location + its sub-areas | "location sheet: `<location>` wide + `<area>` views, consistent layout/tokens" | [A1 asset manifest](../A1-first-video/04-asset-manifest.md) |
| **Environment overview** | A key-art / establishing wide of the world | wide establishing, empty stage, generous negative space | [A1 storyboard](../A1-first-video/03-storyboard.md) |
| **Location + characters** | The stage with the cast composited | `BG_` id + character reference sheets + [poses](POSE_LIBRARY.md) at the ground line | [Pose Library prompt standards](POSE_LIBRARY.md#prompt-standards) |
| **Location + props** | Set with placed props / set elements | `BG_` id + prop asset IDs + placement/continuity note | [Prop Library prompt standards](PROP_LIBRARY.md#prompt-standards) |
| **Weather variant** | A location in a weather state | base `BG_` + the [weather](#weather-system) flat expression + "no gradient" | [Weather System](#weather-system) |
| **Time-of-day variant** | A location at a time | base `BG_` + the [time](#time-system) token swap + flat sky elements | [Time System](#time-system) |

**One location (or one clear variant) per prompt.** Keep it to a few flat shapes and always quieter than
the cast; request no readable text and no incidental characters.

---

## Production Workflow

Locations follow the reuse-first lifecycle in [Stage 2](../../docs/12-stage-2-channel-operating-system.md)
and the [Character Bible lifecycle](CHARACTER_BIBLE.md#character-lifecycle) model.

1. **Creation.** Confirm the location is justified by a premise ([settings-as-variables](BRAND_BIBLE.md#content-pillars));
   fill a [Location Profile](#future-location-template) (category, class, identity, tokens, layers);
   register any new palette tokens in the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md#color-system).
2. **Review.** Run the [Quality Checklist](#quality-checklist) plus the
   [Visual Identity Lock quality checklist](VISUAL_IDENTITY_LOCK.md#quality-checklist). Off-model →
   regenerate, never settle.
3. **Approval.** The place must read in under a second, stay quieter than the cast, and be
   advertiser-safe, global, and text-free.
4. **Versioning.** File the base `BG_[location]_v1` + any variants; log the location and its tokens.
   Adding a variant is **editorial**; only a locked-design change bumps `_v#`.
5. **Reuse.** Shots **select** an existing location + variant and composite the cast/props into it; they
   do **not** generate new backgrounds unless a genuinely new place is needed. This is the cost moat.
6. **Retirement.** Retire a location only by a logged decision
   ([Decision Log](../../docs/21-decision-log.md)); mark it `deprecated`, keep the asset (published
   videos reference it), and stop using it in new videos. A replacement gets a **new name/ID**.

---

## Quality Checklist

Run before accepting **any** environment asset (in addition to the
[Visual Identity Lock quality checklist](VISUAL_IDENTITY_LOCK.md#quality-checklist)). One failure =
reject and regenerate.

- [ ] **Reads in <1s** — the place is identifiable from its silhouette + 1–2 iconic elements, muted, at thumbnail size.
- [ ] **Quieter than the cast** — more desaturated, lower-contrast; never competes with the subject or hero prop.
- [ ] **Layered depth** — clear fg/mg/bg planes; consistent ground line; detail decreases with depth.
- [ ] **Generous negative space** in the midground subject band; key elements clear of the top ~15% / bottom ~20% UI zones.
- [ ] **Flat & no-gradient** — token fills + flat shapes only; time/weather via token swap + flat overlays; ≤1 flat mood-shadow.
- [ ] **On-palette** — uses registered Environment tokens; any new token was added to the [Color System](VISUAL_IDENTITY_LOCK.md#color-system) first.
- [ ] **No readable text, no incidental characters, no busy patterns** ([Background Rules](VISUAL_IDENTITY_LOCK.md#background-rules)).
- [ ] **Advertiser-safe & global** — clean, non-threatening, culturally neutral.
- [ ] **Continuity** — recurring location matches its catalog layout; seeds hold position; loop-seam time/weather matches.
- [ ] **Right namespace** — `BG_` (not `PROP_`/`UI_`/`FX_`); fixed set dressing, not a movable object.
- [ ] **Correct ID** — named per [environmental-asset naming](#environmental-assets) and catalogued in its Location Profile.

---

## Location Profile — Parking Lot

The **first complete implementation** of the world system — the worked example every future location
follows (as PIP is for characters). The exact render prompt lives in the
[A1 storyboard](../A1-first-video/03-storyboard.md); this is the location's canonical profile.

- **Location ID:** `BG_parkinglot_v1` · **Category:** Parking / Roads (Outdoor) ·
  **Classification:** Hero + Recurring.
- **First appearance:** [Idea A1 — "Wrong Scooter"](../A1-first-video/README.md) / [V1](../../V1/README.md).

**Identity.** An open, orderly public parking lot — asphalt ground, open sky, a parking meter, painted
lines, and a marked no-parking zone. Deliberately plain and rule-governed so it reads instantly and
frames "petty authority's turf."

**Purpose.** The stage for the A1 comeuppance and a reusable everyday-authority setting the channel can
return to.

**Emotional role.** Orderly, rule-bound, mildly official — it legitimizes CHIEF's petty power and makes
his overreach absurd; the wide open space isolates the tiny sympathetic underdog. It resolves to bright
and calm at the payoff.

**Palette tokens.** `ASPHALT` (ground) · `SKY` (backdrop) · `PAPER` (negative space/markings base) ·
`ALERT_RED` (the no-parking zone seed) · `INK` (outlines/lines). All per the
[Color System](VISUAL_IDENTITY_LOCK.md#color-system).

**Depth layers.**
- **fg:** the `ALERT_RED` no-parking zone (`BG_noparking_zone_v1`) in the lower-right, holding CHIEF's
  scooter seed ([prop](PROP_LIBRARY.md)); the ground plane.
- **mg:** the stage — parking meter, painted lines, the cast and their poses; the podium spot for the
  victory beat.
- **bg:** flat `SKY`, empty and calm.

**Set elements (fixed dressing, `BG_`):** parking meter, painted parking lines, the
`BG_noparking_zone_v1` marking. *(Movable objects in the lot — scooters, tow truck, boot, stamp — are
[props](PROP_LIBRARY.md), not part of this location.)*

**Assets in the catalog.**
- `BG_parkinglot_v1` — establishing wide (A1 shots 1, 6, 7, 8).
- `BG_parkinglot_meter_v1` — meter-area sub-view (A1 shots 2, 3, 4).
- `BG_noparking_zone_v1` — the seed-carrying set-element marking (A1 shots 1, 6, 7).

**Continuity notes.** The no-parking zone stays in the **same lower-right screen position** across shots
1, 6, 7 (seed continuity); shot 8 uses the **identical framing/lighting of shot 1** for the loop seam.

**Time / weather.** A1 default = **afternoon, clear** (bright flat midday). A single flat cool
mood-shadow creeps in for the pre-twist beat and clears by the loop seam.

**Future scalability.** New variants can extend it without a redesign: `BG_parkinglot_night_v1`,
`BG_parkinglot_rain_v1`, `BG_parkinglot_meter_v2` sub-areas, etc. — same layout and tokens, swapped
atmospheric state. The **Parking / Roads** category and this profile are the template for sibling
authority-turf locations (an office, a DMV) that play the same status role.

---

## Future Location Template

Copy this block to create any new location. Fill every field; leave nothing blank. This is the input to
the [Production Workflow](#production-workflow).

```
# Location Profile — <LOCATION>
- Location ID:         BG_<location>_v1
- Category (taxonomy): <Parking/Roads | Urban | Commercial/Retail | Workplace/Institutional | School |
                        Residential | Parks/Nature | Recreation | Transit | Public Space | Abstract> + Indoor/Outdoor
- Classification:      <hero | recurring | supporting | background-only | episode-exclusive | future-expansion>
- First appearance:    <video ID / idea>

## World & story
- Identity:            <the place in one line; its 1–2 iconic elements>
- Purpose:             <why this location exists — the premise/status role it serves>
- Emotional role:      <what it silently communicates (status/tone)>
- Story hooks:         <where a seed can sit in the set; the status-gap staging>

## Visual (defer render law to the Visual Identity Lock)
- Palette tokens:      <which Environment tokens; register any NEW token in the Color System first>
- Depth layers:        fg: <…>  ·  mg (stage): <…>  ·  bg: <…>
- Set elements (BG_):  <fixed dressing: meter, lines, walls, signage-shapes…>
- Negative space:      <where the cast sits; thumb-safe zones kept clear>

## Atmosphere
- Default time:        <morning | afternoon | golden hour | sunset | overcast | night>
- Default weather:     <clear | cloudy | overcast | rain | wind | fog | snow | storm>
- Continuity:          <seed position; loop-seam match; any tension mood-shadow>

## Assets & production
- Base + variants:     BG_<location>_v1 · BG_<location>_<area>_v1 · BG_<location>_<time>_v1 · …
- Hosts:               <which cast/props/vehicles appear here>
- Reuse note:          <how it recurs; which sibling locations it templates>
- Future scalability:  <variants that may be added editorially vs. what is locked>
```

---

## Future Integration

This Bible is a **parent/sibling** to the remaining shot-, motion-, and channel-art documents. Each must
reference a location by its canonical `BG_` ID rather than describing a background from scratch.

| Consumer (future doc / stage) | How it uses this Bible |
|---|---|
| **[Camera & Cinematography Bible](CAMERA_CINEMATOGRAPHY_BIBLE.md)** ✅ | Frames and moves *through* the locations this Bible builds (the low hero angle on the podium spot; the punch-in that keeps the seed in frame); this Bible owns the space, the Camera Bible owns the shot grammar. |
| **[Animation Language & Motion System](ANIMATION_LANGUAGE_MOTION_SYSTEM.md)** ✅ | Owns **ambient motion, parallax, and weather/time animation** (drifting clouds, falling rain, the mood-shadow creep) using this Bible's static locations and states as the things it animates. |
| **[Production Prompt Framework & Runtime Orchestration](PRODUCTION_PROMPT_FRAMEWORK_RUNTIME_ORCHESTRATION.md)** ✅ (incl. wallpaper prompts) | Selects a location (or the [Abstract void](#environment-taxonomy)) + hero cast/pose/prop for channel art, thumbnails, and wallpapers per the [thumbnail spec](../templates/thumbnail-spec.md). |
| **Shot Generation** | Each shot names the `BG_` location + time/weather state, driving the [visual-prompt template](../templates/visual-prompt-template.md) `BACKGROUND` slot; seed set-elements flagged for continuity. |
| **Storyboard generation** | The [storyboard](../A1-first-video/03-storyboard.md) location column is expressed as canonical `BG_` IDs, making sets reusable and machine-selectable. |
| **Video production pipeline** | The [Stage 6 production compiler](../../docs/15-stage-6-production-compiler.md) assembles shots from reusable **location + cast + pose + expression + prop**, hitting the sub-30-minute reuse target; the [asset manifest](../A1-first-video/04-asset-manifest.md) tags each `BG_` reuse-vs-new. |

---

## Repository Integration

Additive one-line pointers are added in this branch at the highest-traffic entry points; deeper links
are recommendations to avoid over-editing locked docs.

| Document | Relationship | Action |
|---|---|---|
| [`production/design/README.md`](README.md) | Design/identity folder index | Add the Environment Bible + update planned-children note (done) |
| [`production/design/CHARACTER_BIBLE.md`](CHARACTER_BIBLE.md) | Parent (character system) | Link the "Environment Bible" future-doc row to this now-existing doc (done) |
| [`production/design/PROP_LIBRARY.md`](PROP_LIBRARY.md) | Sibling (defers set dressing here) | Point its "Environment Bible" future-integration row here (done) |
| [`production/design/VISUAL_IDENTITY_LOCK.md`](VISUAL_IDENTITY_LOCK.md) | Root (owns the palette registry) | Note in the Color System Environment-set that per-location token usage is documented here (done) |
| [`docs/00-index.md`](../../docs/00-index.md) | Master doc map | List the Environment Bible under Design standards (done) |
| [`production/README.md`](../README.md) | Production folder map | Add to the `design/` tree + a traceability row (done) |
| [`production/A1-first-video/04-asset-manifest.md`](../A1-first-video/04-asset-manifest.md) | The worked `BG_` list | Point its Backgrounds section at this catalog (done) |

**Anti-duplication (ownership map).** Where a requested topic is already owned elsewhere, this Bible
**references and extends** rather than competing:
- **Background complexity / allowed detail / color hierarchy / distraction** → owned by the
  [Visual Identity Lock Background Rules](VISUAL_IDENTITY_LOCK.md#background-rules); this Bible adds only
  *depth layering* and the *location-as-asset* system.
- **Composition / negative space / thumb-safe / continuity / loop seam** → owned by the
  [Composition Rules](VISUAL_IDENTITY_LOCK.md#composition-rules).
- **Lighting law (flat, no gradient, one shadow tone)** → owned by the
  [Lighting Rules](VISUAL_IDENTITY_LOCK.md#lighting-rules); this Bible owns *time/weather expressed
  within* that law.
- **The palette token registry** → owned by the [Color System](VISUAL_IDENTITY_LOCK.md#color-system);
  this Bible documents per-location usage and proposes new tokens through Change Control.
- **Camera framing/angles** → future **Camera Language**. **Ambient/weather motion & parallax** →
  future **Animation Language**.
- **Movable objects** → [Prop Library](PROP_LIBRARY.md). **Characters** → [Character Bible](CHARACTER_BIBLE.md).
- **Settings-as-variables / seeds / tone** → [Brand Bible](BRAND_BIBLE.md) and the
  [twist library](../../intelligence/03-narrative-twist-library.md).

This Bible owns only the **location catalog, environment taxonomy/classification, depth-layering
standard, weather & time systems, environmental storytelling, and environment interaction rules**.

---

## Change Control

A **locked** document, governed like the [Locked Roadmap](../../docs/03-locked-roadmap.md) and
[Decision Log](../../docs/21-decision-log.md).

- **Editorial changes** (adding a location, a variant, a new AVAILABLE category slot, a weather/time
  state, clarifications, cross-links) may be made freely; **no version bump**.
- **Substantive changes** (changing a locked location's design, adding/removing a **category** or
  classification, changing the weather/time model, the depth-layering standard, or the
  environment/prop or environment/camera boundary) require: (1) a rationale in the
  [Decision Log](../../docs/21-decision-log.md), (2) a pass through the
  [Stage 2 5-Gate test](../../docs/12-stage-2-channel-operating-system.md), and (3) confirmation that no
  [locked decision](../../docs/03-locked-roadmap.md) or root document is contradicted.
- **New palette tokens** must be added to the [Visual Identity Lock Color System](VISUAL_IDENTITY_LOCK.md#color-system)
  **before** a location uses them. **New locations** must be filed here (ID, category, class, profile)
  **before** they appear in any prompt or shot — this is what keeps generation from inventing worlds.

> **The world is a reusable asset, never a throwaway background.** When in doubt, choose the location
> whose one-second read frames the status gap — keep it quieter than the cast, and reuse it, never
> redraw it.
