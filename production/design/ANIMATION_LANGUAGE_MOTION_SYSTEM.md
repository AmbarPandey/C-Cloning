# Animation Language & Motion System

> **Status:** Locked · **Applies to:** every movement in every C-Cloning video and live wallpaper —
> character motion, camera-move timing, prop motion, environment motion, transitions, loops · **Owner
> role:** Lead Animation Director / Motion Designer / Runtime Animation Architect / AI Video Generation
> Specialist
>
> **This is the canonical motion language of the C-Cloning universe.** It defines how everything
> *moves* — the timing, holds, snaps, easing, loops, and runtime motion vocabulary — and it is the
> **motion specification for future AI video-generation and live-wallpaper systems.** Every future
> motion prompt, video prompt, and wallpaper prompt must inherit from this document.
>
> The other design docs define the **still frame**; this document defines the **change between
> frames.** The [Pose Library](POSE_LIBRARY.md) gives the keyframes, the
> [Camera Bible](CAMERA_CINEMATOGRAPHY_BIBLE.md) gives the shot — **this document gives the motion that
> connects them.**

> **Motion is storytelling, not decoration.** Every movement here communicates *emotion, status, comedy,
> and timing*; if a motion doesn't serve the beat, it isn't animated.

## Inheritance banner — the convergence point

This document is a **child of the Identity Core** and the **convergence of all eight foundation
documents**: each one defined a *static* layer and explicitly deferred its *motion* here. This document
never overrides them:

- **Render law** → the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md). Flat-2D, **no motion blur, no
  depth-of-field, no bloom, no gradients, no rotation** ([Lighting](VISUAL_IDENTITY_LOCK.md#lighting-rules)/[Rendering](VISUAL_IDENTITY_LOCK.md#rendering-rules)),
  FX motion-lines only as `INK`/`BRAND_YELLOW` strokes ([Line System](VISUAL_IDENTITY_LOCK.md#line-system)),
  and the **loop seam** (first frame = last frame, [Composition](VISUAL_IDENTITY_LOCK.md#composition-rules)).
  Motion adds *timing*, not new visual law. On a visual question, the Lock wins.
- **Pacing & tone** → the [Brand Bible](BRAND_BIBLE.md). "Brisk and snappy, pose-to-pose, escalating,
  with one deliberate silent beat before the turn — never frantic, never sluggish"
  ([personality](BRAND_BIBLE.md#brand-personality)); motion stays **advertiser-safe** (comic, benign).
- **Keyframes** → the [Pose Library](POSE_LIBRARY.md) (static poses this system moves *between*) and the
  [Expression Library](EXPRESSION_LIBRARY.md) (the [intensity holds](EXPRESSION_LIBRARY.md#expression-intensity),
  the **3-stage snap**, and the **no-lip-sync / expression-only mouth** rule — all consumed here).
- **The things that move** → the [Prop Library](PROP_LIBRARY.md) (prop motion), the
  [Environment Bible](ENVIRONMENT_BIBLE.md) (ambient/weather/time motion), and the
  [Character Bible](CHARACTER_BIBLE.md) (per-character movement personality).
- **The shot the motion lives in** → the [Camera & Cinematography Bible](CAMERA_CINEMATOGRAPHY_BIBLE.md).
  This system executes the **timing/easing** of the camera moves it names (`PUSHIN`/`PUNCHIN`/`REVEAL`);
  the Camera Bible owns the shot vocabulary + framing intent.

It also **defers to** (references, never restates):
- Naming & reuse → [Stage 2](../../docs/12-stage-2-channel-operating-system.md) and the
  [Visual Identity Lock asset-ID table](VISUAL_IDENTITY_LOCK.md#asset-id-naming).
- The worked motion spec → the [A1 animation spec](../A1-first-video/05-animation-spec.md) and
  [V1 video prompts](../../V1/05-video-prompts.md).

> **Ownership boundaries (important).**
> - **Motion vs. the still frame.** This system owns the *movement*; the **static pose/object/location/
>   face/framing** belong to the Pose, Prop, Environment, Expression, and Camera docs respectively.
> - **Motion vs. the edit.** This system owns motion **within a clip** (and the loop-seam motion match).
>   **Cuts, freezes, speed-ramps, captions, and transitions *between* clips** belong to the **Editing
>   workflow** ([A1 editing spec](../A1-first-video/07-editing-spec.md) / [Stage 6](../../docs/15-stage-6-production-compiler.md)).
> - **Motion vs. audio.** This system *syncs to* the [audio package](../A1-first-video/06-audio-package.md)
>   (the silent beat, the music slam on the twist) but does not own sound.
> - **Motion is not a stored `_v#` asset.** Motion is applied at generation time (image→video) via the
>   [runtime vocabulary](#runtime-semantics) and the [motion descriptor](#runtime-semantics); the
>   finished video is named `PTP_[####]…` per [Stage 2](../../docs/12-stage-2-channel-operating-system.md).

---

## Table of contents

1. [Purpose](#purpose)
2. [Motion Philosophy](#motion-philosophy)
3. [Animation Principles](#animation-principles)
4. [Motion Taxonomy](#motion-taxonomy)
5. [Motion Timing](#motion-timing)
6. [Character Motion](#character-motion)
7. [Camera Motion](#camera-motion)
8. [Prop Motion](#prop-motion)
9. [Environment Motion](#environment-motion)
10. [Transition Language](#transition-language)
11. [Wallpaper Motion System](#wallpaper-motion-system)
12. [Runtime Semantics](#runtime-semantics)
13. [Prompt Standards](#prompt-standards)
14. [Production Workflow](#production-workflow)
15. [Quality Checklist](#quality-checklist)
16. [Future Integration](#future-integration)
17. [Repository Integration](#repository-integration)
18. [Change Control](#change-control)

---

## Purpose

Consistent motion is what makes the channel *feel* the same in motion, the way the palette makes it
*look* the same still. A viewer recognizes the **snap of the twist**, the **held ego-flex**, the
**silent beat**, and the **seamless loop** as much as they recognize PIP's scarf. And because the
channel is produced by **AI image→video tools** at scale, a locked motion spec is what stops those
tools from morphing, over-animating, or drifting off-model.

Consistent motion matters because:

- **It is recognizable storytelling.** The [Brand Bible](BRAND_BIBLE.md#brand-recognition-system) lists
  "snappy pose-to-pose cuts" and "one deliberate silence before the turn" as recognition signals; motion
  rhythm is part of the brand.
- **Timing is the comedy.** The **hold** before the turn and the **punch-in snap** on the twist are the
  jokes' delivery ([Expression Library intensity](EXPRESSION_LIBRARY.md#expression-intensity)); mistimed
  motion kills the beat.
- **The loop compounds watch time.** A frame-matched loop (frame 960 = frame 1) is engineered replay
  ([Visual Identity Lock](VISUAL_IDENTITY_LOCK.md#composition-rules)); motion must land the seam.
- **It is the reuse/scale engine.** A shared motion vocabulary lets shots be generated by *applying named
  motions to reusable poses* rather than hand-animating ([Stage 2 reuse economics](../../docs/12-stage-2-channel-operating-system.md)).
- **Runtime automation needs a closed vocabulary.** AI video and live-wallpaper generators must select
  from a finite, named motion set — never invent ad-hoc movement — so output stays on-model
  ([runtime requirement](#runtime-semantics)).

> **Rule of thumb:** if a motion doesn't advance the beat, or if it makes the design morph/drift, it is
> wrong — prefer a **hold + a snap** over a busy in-between.

---

## Motion Philosophy

The principles every movement obeys. These apply the roots to *motion*; they do not restate them.

- **Clarity.** Motion makes the beat *clearer*, never busier. One clear movement at a time — the motion
  equivalent of [one key action per frame](VISUAL_IDENTITY_LOCK.md#composition-rules).
- **Appeal.** Movement is charming and snappy, inheriting the design's appeal
  ([Visual Identity Lock](VISUAL_IDENTITY_LOCK.md#core-visual-principles)); never floaty, never
  mechanical.
- **Simplicity.** **Pose-to-pose with limited in-betweens** ([A1 animation spec](../A1-first-video/05-animation-spec.md)):
  hold a clear pose, snap to the next. This is both the house style *and* the safest path for AI video
  tools.
- **Readability.** Every movement reads muted, at thumbnail size; if the motion is ambiguous at a glance,
  simplify it.
- **Mobile-first motion.** Big, legible movements for a small vertical screen; no subtle motion that
  vanishes on a phone, no frantic motion that blurs.
- **Advertiser-safe acting.** Physical comedy stays benign ([Brand Bible](BRAND_BIBLE.md#content-pillars)) —
  a flail or a fall is *comic*, never painful; nothing distressing.
- **Animation exaggeration via pose, not smear.** Exaggeration lives in the extreme *poses*
  ([Pose Library intensity](POSE_LIBRARY.md#pose-intensity)) and the *timing*, **not** in squash/stretch
  smears or motion blur (forbidden by the [Lock](VISUAL_IDENTITY_LOCK.md#rendering-rules) and prone to AI
  morphing).
- **Emotional clarity.** Motion carries the same beat and intensity as the face and body
  ([pose+expression pairing](POSE_LIBRARY.md#pose--expression-pairing)); a mismatched motion is off-model.
- **Loopability.** Every video (and every wallpaper) is built to **loop seamlessly** — motion must
  resolve to its start ([loop logic](#motion-timing)).

---

## Animation Principles

The classical animation principles, **adapted for the flat-2D house style *and* the constraints of
AI-generated video**. In this system the balance always favors **holds + snaps** over rich
interpolation, because (a) flat-2D reads as pose-to-pose and (b) image→video tools morph and drift when
asked for complex in-betweens.

| Principle | C-Cloning adaptation | AI-generation guardrail |
|---|---|---|
| **Anticipation** | A brief **held pose** (or tiny wind-up) before a snap — the `PUSHIN`/hold before the twist. | Express as a held frame, not a big wind-up arc the tool must invent. |
| **Follow-through / Overlap** | **Minimal, signature secondary settle** only — the scarf sway, the medal jiggle, a hat tilt after a stop. | Keep tiny; over-asking causes morphing. Prefer one small settle over layered overlap. |
| **Ease-in / Ease-out** | **Snappy** eases — fast in, quick settle. Not linear, not slow/soft. | "snappy pose-to-pose" in the prompt; avoid slow morph windows. |
| **Secondary motion** | One accent element moves (scarf/medals/flag), the rest holds. | Name the *one* secondary element; forbid extra motion. |
| **Staging** | Owned by the [Camera Bible](CAMERA_CINEMATOGRAPHY_BIBLE.md) framing + [Pose](POSE_LIBRARY.md) silhouette; motion keeps the staged read. | — |
| **Timing** | Governed by [Motion Timing](#motion-timing) — holds measured in frames; the silent beat; the punch. | Specify clip length + hold; keep within 2–4s shots. |
| **Spacing** | Big spacing on the snap (fast), zero spacing on the holds (still). | "hold, then snap" — avoid even in-between spacing that reads floaty. |
| **Exaggeration** | Via the **extreme pose** and the **timing**, never via smear/warp. | Reference the L3 pose; forbid distortion/morph. |
| **Appeal** | Inherited from the locked design; motion never distorts the character. | "keep the character design and colors identical." |
| **Weight** | Read via **hold + settle** (a heavy stamp lands and holds; a light coin bounces). | Convey with an impact hold, not physics simulation. |
| **Squash & stretch** | **Minimized** — a slight comic squash on an impact is OK as a *held* extreme; no rubbery smears. | Off by default; smears/morphs are a reject. |

**The AI-video prime directive** (from [V1 video prompts](../../V1/05-video-prompts.md)): *2D cartoon
animation, snappy pose-to-pose motion, minimal camera movement, keep the design and colors identical, no
morphing, no extra characters, no text overlays.* If a tool over-animates, re-prompt with **"subtle
animation, keep style"**; if an action is too complex, **split it into two simpler motions**.

---

## Motion Taxonomy

The canonical **motion categories** and the controlled vocabulary a prompt selects from. Each motion
**moves between [Pose Library](POSE_LIBRARY.md#pose-taxonomy) keyframes** — the pose is the static shape,
the motion is the change. (Mirrors the IN USE / AVAILABLE model of the sibling libraries.)

- **IN USE** = appears in the shipped [A1/V1](../A1-first-video/05-animation-spec.md) work.
- **AVAILABLE** = reserved; use when a beat first needs it.
- **DISALLOWED** = off-brand; never use.

### Character motions

| Motion | Moves between poses | Status |
|---|---|---|
| **Idle** (loop) | holds `idle`/`stand` with a `micro movement` (breath, sway) | **IN USE** (PIP coin-fumble loop) |
| **Strut cycle** | `strut` walk cycle, proud bounce | **IN USE** (CHIEF entrance) |
| **Walk / Run** | `walk` / `run` cycles | AVAILABLE |
| **Jump** | `stand`→`jump`→`celebrate` | AVAILABLE |
| **Turn** | re-face; a **quick snap**, never a 3D rotation | AVAILABLE |
| **Reach** | `idle`→`reach`/`leanin` | **IN USE** (PIP hopeful) |
| **Wave** | `relaxed`+`wave` (the mascot button) | **IN USE** (PIP close) |
| **Celebrate** | `idle`→`celebrate` (glee) | **IN USE** (PIP payoff) |
| **Point / Flourish** | `stand`→`point`/`hold` (draw-weapon flourish) | **IN USE** (CHIEF stamp) |
| **Shrink / Cower** | `idle`→`shrink` | **IN USE** (PIP flinch) |
| **Fall / Yank** | off-balance → `flail` | **IN USE** (CHIEF twist) |
| **Recover** | `flail`/`slump`→`stand` (settle) | AVAILABLE |
| **Look around** | head-turn; eyes lead (`micro movement`) | **IN USE** (PIP head-turn S6) |
| **React** | snap to a reaction pose+expression (the [3-stage snap](EXPRESSION_LIBRARY.md#expression-system)) | **IN USE** (CHIEF smug→shocked→panicked) |

### World motions

| Motion | What moves | Status |
|---|---|---|
| **Vehicle motion** | a [prop](PROP_LIBRARY.md) vehicle travels the ground line (scooter, tow-truck drive-in + hook swing) | **IN USE** |
| **Object motion** | prop action — stamp slam, boot clamp/snap, ticket pop-in, boot pop-off | **IN USE** |
| **Environmental motion** | ambient world motion — cloud drift, rain fall, wind sway | AVAILABLE |
| **Background motion** | distant/parallax layer drift (kept minimal, quieter than cast) | AVAILABLE |
| **Camera motion** | the [Camera Bible](CAMERA_CINEMATOGRAPHY_BIBLE.md#camera-movement-taxonomy) moves, timed here | **IN USE** (`PUSHIN`, `PUNCHIN`, `REVEAL`) |

**Taxonomy rules**
- **One name per motion.** Reuse these terms; a new need adds a category here first via
  [Change Control](#change-control).
- **Motion pairs with a pose + expression at matching intensity** ([pairing](POSE_LIBRARY.md#pose--expression-pairing));
  the antagonist is the *big mover*, the underdog the *small mover* ([Character Motion](#character-motion)).
- **No `Turn`/`Orbit` as 3D rotation** — a "turn" is a flat re-face snap ([Lock](VISUAL_IDENTITY_LOCK.md#rendering-rules)).

---

## Motion Timing

The channel runs at **1080×1920, 30 fps**, ~25–40 s per Short (A1 ≈ 32 s / 960 frames), within the
[Stage 2 timing framework](../../docs/12-stage-2-channel-operating-system.md) (shot 2–4 s, hook 0–2 s,
twist 27–36 s). Timing is measured in **frames and holds**, not eased curves.

| Timing element | Rule (from the [A1 animation spec](../A1-first-video/05-animation-spec.md)) |
|---|---|
| **Beats** | The video is a sequence of story beats ([Camera sequencing](CAMERA_CINEMATOGRAPHY_BIBLE.md#shot-sequencing)); each beat gets one clear motion. |
| **Holds** | Stillness sells the pose. Establishing/seed hold ≈ **6 frames**; impact hold ≈ **4 frames**; the ego-flex **long hold ≈ 1.5 s**; the twist **punch hold ≈ 0.5 s**. |
| **Anticipation timing** | A short held pose (or the silent beat) *before* the turn — build, don't rush. |
| **Reaction timing** | The [3-stage snap](EXPRESSION_LIBRARY.md#expression-system) (smug→shocked→panicked) reads as quick discrete steps, then a hold. |
| **Comedic timing** | Hold → **quick snap** → hold. The pause before the punch and the snap on it are the joke. |
| **Dramatic timing** | The **silent beat** (music drop, [audio](../A1-first-video/06-audio-package.md) 0:16–0:27) is covered by a held pose to build anticipation. |
| **Transition timing** | Pose-to-pose snaps *within* a clip; the *cut between* clips is a hard cut ([Editing](../A1-first-video/07-editing-spec.md)). |
| **Wallpaper timing** | Longer, calmer **seamless loops** (~3–8 s) of ambient motion only (see [Wallpaper Motion](#wallpaper-motion-system)). |
| **Loop timing** | The final frame must equal frame 1 (verify by overlay); hard cut **≤1 s after the button** ([Visual Identity Lock](VISUAL_IDENTITY_LOCK.md#composition-rules)). |

> **Sync to audio, don't lead it.** The twist motion lands *exactly* when the music slams back
> (~0:28); the hold covers the silence. Audio is owned by the
> [audio package](../A1-first-video/06-audio-package.md).

---

## Character Motion

Each character has a **movement personality** — the motion half of the profile in the
[Character Bible](CHARACTER_BIBLE.md). Motion must match the character's band and reuse the
[Pose Library](POSE_LIBRARY.md) keyframes.

| Character | Speed | Energy | Weight | Rhythm |
|---|---|---|---|---|
| **PIP** (underdog/mascot) | slow–moderate, **low-amplitude** | gentle, timid | light (small bounces, quick fidgets) | soft; small moves + gentle holds; the *small mover* ([Character Bible → PIP](CHARACTER_BIBLE.md#pip)) |
| **CHIEF** (antagonist) | brisk, **large-amplitude** | puffed, showy | heavy/stiff (planted struts, big flourishes) | the *big mover*; escalating flourishes → the frozen flex → the collapse |
| **Future characters** | declared per character | per [taxonomy class](CHARACTER_BIBLE.md#character-taxonomy) | — | reuse this system's vocabulary; heroes small, authority big |

**Character-motion rules**
- **Amplitude carries status:** the antagonist moves big and takes the frame; the underdog moves small.
  Never let PIP out-move CHIEF (it breaks the status read).
- **Reuse pose keyframes** — motion moves *between* the character's [pose set](POSE_LIBRARY.md#character-overrides);
  never invent an off-model body.
- **Signature secondary motion** only: PIP's scarf sway, CHIEF's medal jiggle / cap tilt — one accent,
  kept tiny.
- **Mouths animate for expression only** — **no lip-sync** (mute-first, [A1 animation spec](../A1-first-video/05-animation-spec.md)).
- **In-character motion:** PIP never moves aggressively; CHIEF's own big motion triggers his fall
  ([behavior rules](CHARACTER_BIBLE.md#pip)).

---

## Camera Motion

The [Camera Bible](CAMERA_CINEMATOGRAPHY_BIBLE.md) owns the **shot vocabulary and framing intent**; this
system owns the **timing and execution** of each move. It does not restate framing.

| Camera move | Timing / execution |
|---|---|
| **Push-in** (`PUSHIN`) | **Slow**, steady, small travel — builds over the beat (A1 S2/S5); never a fast lurch. |
| **Punch-in** (`PUNCHIN`) | **Fast snap in + small settle**, with a tiny screen shake, on the twist (A1 S7); the signature comedic camera move. |
| **Reveal** (`REVEAL`) | A slow bring-in of an incoming element (tow truck) + a slight zoom to the key point (the hook). |
| **Tracking / Pan / Tilt** | Steady, motivated by a moving subject; ease gently, keep the subject framed. |

**Movement limits (for cinematic readability + AI safety)**
- **≤1 camera move per shot**; most shots are **static** ([Camera Bible](CAMERA_CINEMATOGRAPHY_BIBLE.md#camera-movement-taxonomy)).
- **No handheld, no orbit/rotation** (also a [Lock](VISUAL_IDENTITY_LOCK.md#rendering-rules) rule).
- **"minimal camera movement"** in every AI video prompt — the tool should move the camera barely, and
  never at the cost of morphing the subject.
- Camera motion **never fights the loop seam** — the closing plate returns to the opening framing.

---

## Prop Motion

The [Prop Library](PROP_LIBRARY.md) owns the static objects; this system owns their **movement**. Physics
is **cartoon-snappy, not realistic**.

- **Vehicles** (`PROP_pip_scooter_v1`, `PROP_towtruck_v1`): travel along the location ground line at
  locked scale; drive-ins/exits use the [environment planes](ENVIRONMENT_BIBLE.md#background-standards);
  the tow-truck **hook swing** is a simple arc into position.
- **Coins / small objects** (`PROP_pip_coins_v1`): light **gentle bounce**, quick settle.
- **Doors / hinged objects**: a snap open/close with a small **overshoot** + settle (no slow swing).
- **Interactive props** (stamp, boot, ticket): the functional beat is a **quick snap + impact hold** —
  the **stamp slam** (4-frame impact hold), the **boot clamp**, the **ticket pop-in ×3**, the **boot
  pop-off**.
- **Physics style:** no gravity simulation, no realistic momentum, **no motion blur**; weight is shown
  by the **impact hold + settle**, arcs are simple, and a thrown object's path is a clean arc (the
  *object* is the Prop Library's, the *arc* is this system's).

**Prop-motion rules:** locked scale at every frame; the **seed prop holds its screen position**;
`FX_motionlines_v1` / `FX_impact_star_v1` (flat, `INK`/`BRAND_YELLOW`) accent an impact — never a blur.

---

## Environment Motion

The [Environment Bible](ENVIRONMENT_BIBLE.md) owns the static location and the *flat expression* of
weather/time; this system owns the **motion** of those elements — kept **minimal, flat, looping, and
quieter than the cast**.

| Element | Motion | Rule |
|---|---|---|
| **Wind** | soft **ambient sway** of flat elements + drifting flat leaves/paper | subtle; `FX_motionlines_v1` optional |
| **Rain** | flat streak shapes **fall** on a loop, behind the cast | low-contrast; never obscures the cast |
| **Clouds** | **slow drift** across the flat `SKY` | very slow; loops seamlessly |
| **Trees / foliage** | gentle **ambient sway** | tiny amplitude |
| **Traffic / distant life** | slow lateral drift in the bg plane | quiet, non-distracting |
| **Ambient / parallax** | bg/mg/fg planes drift at slightly different rates on a camera move | subtle depth cue; **never** a 3D parallax that warps |
| **Mood-shadow creep** | the single flat cool shadow slides in for the pre-twist beat, then clears by the seam ([Environment time rules](ENVIRONMENT_BIBLE.md#time-system)) | flat shape, not a light sim |

**Environment-motion rules:** flat and **no gradient/blur**; **loops seamlessly**; **always quieter and
slower than the cast** so it never competes; **one weather state per video** ([Environment weather](ENVIRONMENT_BIBLE.md#weather-system)).

---

## Transition Language

How motion connects beats. This system owns **motion-level** transitions; the **cut between clips**
(hard cut / freeze / speed-ramp / captions) is the [Editing workflow](../A1-first-video/07-editing-spec.md)'s.

| Transition | Motion rule |
|---|---|
| **Scene changes** | Between clips the default is a **hard cut** (Editing owns it); this system ensures each clip *starts and ends on a clear pose* so the cut reads clean — no mid-motion cuts. |
| **Action transitions** | Within a clip, **pose-to-pose snap**: hold pose A → quick snap → hold pose B. No morphing between them. |
| **Reaction transitions** | Action → **reaction** handoff: the cause completes and holds, then the witness snaps to their reaction ([3-stage snap](EXPRESSION_LIBRARY.md#expression-system)); read the beat, then react. |
| **Loop transitions** | The closing motion **settles exactly onto the opening frame** (frame 960 = frame 1) so the video loops seamlessly ([loop timing](#motion-timing)). |
| **Wallpaper transitions** | Ambient loops have **frame-matched loop points** with no visible seam (see [Wallpaper Motion](#wallpaper-motion-system)). |

**Transition rules:** never cut mid-motion; every clip resolves to a hold; the loop match is a hard
requirement, verified by overlay.

---

## Wallpaper Motion System

Live wallpapers are a **runtime deliverable**: a **seamless, continuously-looping ambient animation** of
the cast, for channel art / device wallpapers / idle loops. They inherit everything here and add these
rules. (Selection of the hero framing/pose/expression is the
[Camera](CAMERA_CINEMATOGRAPHY_BIBLE.md#future-integration)/[Pose](POSE_LIBRARY.md#future-integration)
docs'; this section owns the *motion*.)

- **Continuous animation:** **ambient only** — `micro movement`, `ambient sway`, `slow drift`, a
  `gentle bounce`. **No story beat, no big action, no twist** — the character rests in a held **hero
  pose** and breathes/sways.
- **Loop points:** the clip is a **perfect loop** — the last frame equals the first (frame-matched), so
  it can play forever **without a visible seam**. Design the motion to return to its start (a sway out
  and back, a cloud that exits and re-enters).
- **Camera movement:** **static or a very slow drift that returns** to start; never a one-way move that
  breaks the loop.
- **Background activity:** subtle [environment motion](#environment-motion) (a drifting cloud, a gentle
  sway) — kept quiet and looping, always behind the cast.
- **Timing:** **~3–8 s** loops (longer/calmer than a Short); slow, restful pacing — the anti-frantic end
  of the [brand energy](BRAND_BIBLE.md#brand-personality) range.
- **Runtime target:** wallpaper prompts are generated with the [motion-prompt scaffold](#prompt-standards)
  + a **"perfect seamless loop, ambient motion only, keep design identical, minimal/looping camera"**
  instruction. Every future wallpaper prompt **inherits from this document**.

---

## Runtime Semantics

The **controlled motion vocabulary** — standardized terms every motion/video/wallpaper prompt must use
instead of ad-hoc words. This is the runtime interface for AI video generation (parallel to the
[Expression](EXPRESSION_LIBRARY.md#expression-taxonomy) / [Pose](POSE_LIBRARY.md#pose-taxonomy) / [Camera](CAMERA_CINEMATOGRAPHY_BIBLE.md#camera-taxonomy)
vocabularies).

| Term | Meaning | Typical use |
|---|---|---|
| **`hold`** | A beat of stillness on a clear pose (measured in frames). | Sell a pose; the ego-flex; before a snap. |
| **`quick snap`** | A fast pose-to-pose change (big spacing, minimal in-betweens). | The twist; a reaction; a stamp slam. |
| **`soft anticipation`** | A small held wind-up before a snap. | Before the punch; before an action. |
| **`comic pause`** | A deliberate extra beat of stillness for comedic timing. | The silent beat before the turn. |
| **`overshoot`** | A slight past-the-target then **`settle`** back — comic, small. | Doors, props, a proud pose landing. |
| **`settle`** | The small resolve after a snap/overshoot into the final hold. | End of most motions; the loop return. |
| **`micro movement`** | Tiny life (breath, blink, faint sway) on an otherwise held pose. | Idle loops; wallpaper; keeping a hold alive. |
| **`ambient sway`** | Slow, small, looping side-to-side of soft/world elements. | Scarf, foliage, wind; wallpaper background. |
| **`slow drift`** | A very slow one-directional travel (that loops/returns). | Clouds; a wallpaper camera; traffic. |
| **`gentle bounce`** | A small, soft up-down with quick settle. | PIP's steps; coins; a happy idle. |
| **`pose-to-pose snap`** | The default motion connector: `hold` → `quick snap` → `hold`. | The house motion grammar everywhere. |
| **`loop-match`** | Resolve motion so the last frame equals the first. | Every video and wallpaper loop. |

**Motion descriptor (extends the [Camera shot descriptor](CAMERA_CINEMATOGRAPHY_BIBLE.md#shot-descriptor-notation)).**
A shot's motion is written by adding a `MOTION:` line using these terms + the
[motion taxonomy](#motion-taxonomy):

```
SHOT 5 = FULL.LOW.PUSHIN
         CAST: CHAR_CHIEF_v1 pose=victory_l3 expr=triumphant_l3
         MOTION: soft anticipation → pose-to-pose snap into victory → long hold (~1.5s) ;
                 secondary: medal jiggle + flag ambient sway ; camera: slow PUSHIN ; sync: silence begins
```

**Semantics rules:** use **only** these terms (or a term added here via [Change Control](#change-control));
they are the words AI motion prompts are built from — never improvise a synonym.

---

## Prompt Standards

The **prompt architecture** for motion. This section defines structure only; it does **not** restate the
scaffolds — the canonical **motion-prompt prefix** is the [V1 video-prompts](../../V1/05-video-prompts.md)
"general settings" line, and stills come from the [visual-prompt template](../templates/visual-prompt-template.md).
Every motion prompt **must**:

- **start from an approved still** (the shot image composed of locked [pose](POSE_LIBRARY.md) + [expression](EXPRESSION_LIBRARY.md) + [prop](PROP_LIBRARY.md) + [BG](ENVIRONMENT_BIBLE.md));
- **use the [runtime-semantics](#runtime-semantics) vocabulary** + the [motion taxonomy](#motion-taxonomy) + the [Camera](CAMERA_CINEMATOGRAPHY_BIBLE.md) move;
- **carry the AI prime directive** — *snappy pose-to-pose, minimal camera, keep design/colors identical, no morphing, no extra characters, no text overlays* ([V1 video prompts](../../V1/05-video-prompts.md));
- **state the clip length** and any `hold`/`loop-match`.

| Prompt type | Purpose | Structure (beyond the prime directive) | Reference scaffold |
|---|---|---|---|
| **Animation prompt** | A full shot's motion | still + `MOTION:` descriptor + clip length + holds | [V1 video prompts](../../V1/05-video-prompts.md) |
| **Motion prompt** | One named motion on a subject | still + one [motion taxonomy](#motion-taxonomy) term + runtime-semantics timing | [A1 animation spec](../A1-first-video/05-animation-spec.md) |
| **Wallpaper prompt** | A seamless ambient loop | hero still + "perfect seamless loop, ambient only (`micro movement`/`ambient sway`), `loop-match`, static/slow-return camera" | [Wallpaper Motion](#wallpaper-motion-system) |
| **Loop prompt** | A looping video/segment | still(s) + "last frame equals first, `loop-match`, no residual motion/FX" | [loop timing](#motion-timing) |
| **Camera movement prompt** | A within-shot camera move | still + the [Camera move](CAMERA_CINEMATOGRAPHY_BIBLE.md#camera-movement-taxonomy) + its timing ("slow `PUSHIN`" / "fast `PUNCHIN` + `settle`") | [V1 video prompts](../../V1/05-video-prompts.md) |

**Fallbacks (AI tools):** if the tool over-animates → re-prompt **"subtle animation, keep style"**; if the
action is too complex → **split into two simpler motions** and hard-cut them ([V1 video prompts](../../V1/05-video-prompts.md)).
**One motion (or one clear sequence) per prompt.**

---

## Production Workflow

Motion is **planned and applied at generation**, not stored as a versioned asset (the poses/props/BGs it
moves are).

1. **Planning.** From the [shot list](CAMERA_CINEMATOGRAPHY_BIBLE.md#shot-sequencing), write each beat's
   **motion descriptor** (motion taxonomy + runtime semantics + camera-move timing), covering the arc and
   the [holds](#motion-timing).
2. **Blocking.** Confirm the start/end **poses** ([Pose Library](POSE_LIBRARY.md)) and the **timing**
   (holds, snap, silent beat, loop seam) before generating.
3. **Review.** Run the [Quality Checklist](#quality-checklist) plus the
   [Visual Identity Lock quality checklist](VISUAL_IDENTITY_LOCK.md#quality-checklist). Morphing/drift/
   blur → regenerate (or split the motion), never settle.
4. **Approval.** Motion reads muted at thumbnail size, matches the beat's band/intensity, syncs to the
   audio, and lands the loop seam; it stays advertiser-safe.
5. **Versioning.** Motion is **not** globally versioned; the **motion vocabulary** is versioned here (this
   doc). The finished video is `PTP_[####]…` per [Stage 2](../../docs/12-stage-2-channel-operating-system.md).
6. **Reuse.** Reuse **motion recipes** (named motions + timing patterns) across videos — a new video
   re-applies the same motion grammar to new poses/situations. This is the motion cost-moat.

---

## Quality Checklist

Run before approving **any** animated clip or wallpaper loop (in addition to the
[Visual Identity Lock quality checklist](VISUAL_IDENTITY_LOCK.md#quality-checklist)). One failure =
regenerate or split the motion.

- [ ] **On-model throughout** — no morphing, warping, or design/color drift across frames.
- [ ] **Pose-to-pose + holds** — clear start/end poses with a `hold`; not floaty or over-animated.
- [ ] **Snappy timing** — brisk, never frantic or sluggish; holds hit the frame counts.
- [ ] **One motion per beat** — one clear movement; secondary motion is one small accent (scarf/medals).
- [ ] **Amplitude matches status** — antagonist big, underdog small; motion band fits the character.
- [ ] **Matches face + body** — motion, pose, and expression share the beat and intensity.
- [ ] **No forbidden motion** — no motion blur, no DOF, no rotation/orbit, no handheld, no lip-sync.
- [ ] **Camera ≤1 move**, minimal, timed per the Camera Bible; never fights the subject or the loop.
- [ ] **Environment quieter/slower than the cast**; ambient motion subtle and looping.
- [ ] **Audio sync** — the twist lands on the music return; the hold covers the silent beat.
- [ ] **Loop-match** — last frame equals first (overlay-verified); hard cut ≤1 s after the button.
- [ ] **Runtime vocabulary** — the motion is described in [runtime-semantics](#runtime-semantics) terms
      (no invented motion words); wallpaper loops are seamless.

---

## Future Integration

This system is consumed by the runtime/automation layers — it is the **last design document before
generation**, and every motion-producing tool inherits from it.

| Consumer (future doc / stage) | How it uses this system |
|---|---|
| **[Production Prompt Framework & Runtime Orchestration](PRODUCTION_PROMPT_FRAMEWORK_RUNTIME_ORCHESTRATION.md)** ✅ | Encodes the [runtime semantics](#runtime-semantics) + [motion descriptor](#runtime-semantics) into reusable motion/video generation contracts, alongside the visual/character/camera vocabularies. |
| **Wallpaper prompts** (via the framework) | Inherit the [Wallpaper Motion System](#wallpaper-motion-system) — seamless ambient loops, `loop-match`, calm timing — for live wallpapers and channel art. |
| **Video generation** (image→video) | Applies the [prompt standards](#prompt-standards) + AI prime directive to turn approved stills into on-model clips; the [Anijam](../tools/anijam-usage.md) / image→video tools consume this spec. |
| **Future automation** | The [Stage 2 automation roadmap](../../docs/12-stage-2-channel-operating-system.md) (animation assembly) selects named motions per beat — no ad-hoc movement — so scaled output stays on-model. |
| **Future runtime systems** | This document is the **motion specification** for any future runtime/AI video system; motion terms and timing here are the contract those systems implement. |
| **Video production pipeline** | The [Stage 6 production compiler](../../docs/15-stage-6-production-compiler.md) turns the shot list into a [motion descriptor](#runtime-semantics) per beat and hands stills+motion to the video tool, hitting the sub-30-minute reuse target. |

---

## Repository Integration

Additive one-line pointers are added in this branch at the highest-traffic entry points; deeper links
are recommendations to avoid over-editing locked docs.

| Document | Relationship | Action |
|---|---|---|
| [`production/design/README.md`](README.md) | Design/identity folder index | Add the Animation Language & Motion System + update planned-children note (done) |
| [`production/design/CHARACTER_BIBLE.md`](CHARACTER_BIBLE.md) | Movement personality per character | Link the "Animation Language" future-doc row here (done) |
| [`production/design/EXPRESSION_LIBRARY.md`](EXPRESSION_LIBRARY.md) | Holds / 3-stage snap / no-lip-sync | Link its "Animation Language" row here (done) |
| [`production/design/POSE_LIBRARY.md`](POSE_LIBRARY.md) | Keyframes this moves between | Link its "Animation Language" row here (done) |
| [`production/design/PROP_LIBRARY.md`](PROP_LIBRARY.md) | Prop motion | Link its "Animation Language" row here (done) |
| [`production/design/ENVIRONMENT_BIBLE.md`](ENVIRONMENT_BIBLE.md) | Ambient/weather motion | Link its "Animation Language" row here (done) |
| [`production/design/CAMERA_CINEMATOGRAPHY_BIBLE.md`](CAMERA_CINEMATOGRAPHY_BIBLE.md) | Camera-move timing | Link its "Animation Language" row here (done) |
| [`production/design/BRAND_BIBLE.md`](BRAND_BIBLE.md) | Names Animation Language as a future child | Link its future-children row here (done) |
| [`docs/00-index.md`](../../docs/00-index.md) | Master doc map | List the Animation Language & Motion System (done) |
| [`production/README.md`](../README.md) | Production folder map | Add to the `design/` tree + a traceability row (done) |
| [`production/A1-first-video/05-animation-spec.md`](../A1-first-video/05-animation-spec.md) | The worked motion spec | Point it at this Bible's motion grammar (done) |

**Anti-duplication (ownership map).** Where a requested topic is already owned elsewhere, this system
**references and extends** rather than competing:
- **Static poses / keyframes** → [Pose Library](POSE_LIBRARY.md). **Static objects** → [Prop Library](PROP_LIBRARY.md).
  **Static locations + flat weather/time expression** → [Environment Bible](ENVIRONMENT_BIBLE.md).
  **Faces / holds authored** → [Expression Library](EXPRESSION_LIBRARY.md).
- **Shot vocabulary + framing intent** → [Camera & Cinematography Bible](CAMERA_CINEMATOGRAPHY_BIBLE.md);
  this system owns the **move timing/easing**.
- **Cuts / freezes / speed-ramps / captions / transitions between clips** → the
  [Editing workflow](../A1-first-video/07-editing-spec.md) / [Stage 6](../../docs/15-stage-6-production-compiler.md).
- **Audio / music / silence** → the [audio package](../A1-first-video/06-audio-package.md); this system
  *syncs to* it.
- **Render law (no blur/gradient/rotation), loop-seam continuity** → the [Visual Identity Lock](VISUAL_IDENTITY_LOCK.md).
  **Pacing/tone stance** → the [Brand Bible](BRAND_BIBLE.md).

This system owns only the **motion philosophy & principles, motion taxonomy, motion timing/holds/loop
logic, per-domain motion (character/camera/prop/environment), transition (motion-level) language, the
wallpaper motion system, and the runtime motion vocabulary**.

---

## Change Control

A **locked** document, governed like the [Locked Roadmap](../../docs/03-locked-roadmap.md) and
[Decision Log](../../docs/21-decision-log.md).

- **Editorial changes** (clarifications, a new AVAILABLE motion or runtime-semantics term, examples,
  cross-links) may be made freely; **no version bump**.
- **Substantive changes** (adding/removing a motion category or a runtime-semantics term, changing the
  timing/hold rules, the DISALLOWED list, the loop logic, or the wallpaper motion rules) require: (1) a
  rationale in the [Decision Log](../../docs/21-decision-log.md), (2) a pass through the
  [Stage 2 5-Gate test](../../docs/12-stage-2-channel-operating-system.md), and (3) confirmation that no
  [locked decision](../../docs/03-locked-roadmap.md) or root document is contradicted.
- **New motion or runtime terms** must be added to the [taxonomy](#motion-taxonomy) /
  [runtime semantics](#runtime-semantics) here **before** they appear in any prompt — this is what keeps
  AI generation from inventing motion.

> **Motion is the change between frames — keep it snappy, keep it on-model, and land the loop.** When in
> doubt, choose a **hold and a snap** over a busy in-between.
