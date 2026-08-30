# v22 — Video & Animation Prompt ("The Shortcut") · **SHORTS 9:16**

> Compact-package file 2: per-shot image prompts **and** motion/camera/FX. Locks to `01-video-script.md`.

**Render spec:** 1080×1920 · 30 fps · ~32 s · flat-2D house style · hard cuts only *(one exception: C6's continuous pull-back)* · no camera rotation · no blur/glow/gradients · loop seam (final frame == C1b).

## 0. Style prefix
```
Flat-color 2D cartoon, thick uniform INK #1A1A1A outlines (never pure #000000), no gradients,
minimal single-tone shading, high-contrast clean vector look, 9:16 vertical, mobile-legible.
Proportions: chunky 2-2.5 head heights — PIP ~2, CHIEF ~2.5.
Palette ONLY: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text. Advertiser-safe, no gore.
```

**Cast:** `CHAR_CHIEF_v1` (rotund warden, `POP_TEAL` jacket, `BRAND_YELLOW` buttons + medal sash, peaked cap with badge, `PAPER` gloves, `smug`) · `CHAR_PIP_v1` (tiny, `PAPER` body, `POP_TEAL` scarf every shot) · `CROWD_parkanimals_v1` (assorted small animals lounging like people — **desaturated, silhouette-level, no individual faces**, never out-competing the leads). **Cap + sash + medals never leave CHIEF, including on his knees.**

**Environment** `BG_park_paths_v1`
```
BG_park_paths_v1: flat-2D public park, composed for 9:16. A PAPER signpost stands centre-frame on
ASPHALT ground with two INK arrows. Two ASPHALT paths lead away — one short and curving, one long. At the
short path's end: a SHALLOW GROUND-LEVEL ASPHALT trough. At the long path's end: a TALL ASPHALT drinking
fountain at chest height. POP_TEAL foliage masses, desaturated silhouette animals lounging like people,
flat SKY strip above. Quiet, lower-contrast than the cast, no text.
```
**Continuity locks:** the signpost's screen position and the **paw symbol's** size and placement are identical in C1b, C2 and C8. Both fountains exist in the layout from the start and never move — only the framing changes. C8 settles to the exact C1b framing.

---

## Per-shot prompts + direction

### C1 — 0:00–0:01.5 · ECU.EYE.STATIC · cold payoff
```
{style prefix} Extreme close-up, 9:16: the face and cap brim of CHIEF (oversized peaked cap with badge,
tiny mustache) ALREADY CROUCHED AND LEANING DOWN toward the rim of a shallow ground-level ASPHALT trough
of flat SKY water, one PAPER glove braced on the ground. At the frame edge, one desaturated duck
silhouette mid-blink. No park, no signpost, no context, no character entering frame. Tight, high contrast.
```
- 45 frames, static, motion underway on frame 1. **No music.**

### C1b — 0:01.5–0:02 · MED.FLAT.STATIC · goal diagram
```
{style prefix} Flat dead-centre schematic, 9:16: a PAPER signpost with two INK arrows from one post. The
upper arrow is SHORT and ends in a small fountain pictogram with a TINY PAW SYMBOL beside it. The lower
arrow is LONG and ends in a TALLER fountain pictogram. Plain PAPER background, no characters, no text.
Schematic and readable — but the paw symbol is rendered SMALL and unemphasised, not highlighted.
```
- Nothing moves, 15 frames. Music **enters**. One flat sparkle on the arrows — **not on the paw.**

### C2 — 0:02–0:06 · MED.EYE.PUSHIN · rewind/setup
```
{style prefix} Medium 9:16 in a flat park. The PAPER signpost stands centre on ASPHALT ground with its two
INK arrows. Tiny PIP (PAPER body, POP_TEAL scarf, neutral) is setting off down the LONG path without
comment. Beside the post CHIEF (POP_TEAL jacket, BRAND_YELLOW medal sash, peaked cap with badge, gloating)
is TAPPING THE SHORT ARROW with one PAPER glove and sneering at PIP's choice. POP_TEAL foliage and
desaturated silhouette animals lounging like people in the background. The tiny paw symbol is in frame,
unemphasised.
```
- Motion: PIP walks off; CHIEF two glove taps (3 frames each). Camera: push-in 100%→110% ending on the signpost. **No FX on the paw.**

### C3 — 0:06–0:11 · MED.EYE.STATIC ×2 · escalation 1 (intercut)
```
A) {style prefix} Medium 9:16: CHIEF striding briskly along a short curving ASPHALT path, chest out,
gloating, passing desaturated silhouette animals lounging like people who turn to watch him go by.
POP_TEAL foliage. No fountain visible yet.

B) {style prefix} Medium 9:16: tiny PIP walking unhurried along a long straight ASPHALT path between
POP_TEAL foliage masses, determined, POP_TEAL scarf. No fountain visible yet.
```
- Two beats each, hard cuts between. **Neither shot shows a fountain** — the intercut is the scoreboard, not the reveal.

### C4 — 0:11–0:16 · MED-WIDE.EYE.PUSHIN(slight) · escalation 2
```
{style prefix} Medium-wide 9:16. CHIEF has picked up pace, glancing back and gesturing dismissively down
the path behind him toward PIP, triumphant. More desaturated silhouette animals are gathering at the edge
of frame ahead of him, forming a patient line — but they are kept at the frame edge and the thing they are
queuing for is NOT in shot. POP_TEAL foliage, ASPHALT path.
```
- Motion: fast stride; 3-frame hold on the backward gesture. **Framing keeps the queue's destination out of shot.**

### C5 — 0:16–0:22 · MCU.LOW.PUSHIN → HOLD · full commit
```
{style prefix} Low hero angle, TIGHT medium-close, 9:16. CHIEF plants an enormous triumphant pose with one
PAPER glove raised, chest out, chin high, medals catching, FX_sparkle accents — he has arrived first. A rim
of ASPHALT stone and a sliver of flat SKY water is visible at the very bottom of frame. CRITICAL: the
framing is deliberately TIGHT and must EXCLUDE the fountain's height, the waiting animals, and everything
else in the park. The viewer must not yet be able to tell how low the water is.
```
- The pose **freezes** ~1.5 s. Music **cuts mid-phrase at 0:16**. Camera: low push-in settling into the hold.

### C6 — 0:22–0:27 · WIDE.EYE.PULLOUT · pattern break (the reveal begins)
```
{style prefix} 9:16, quiet. A slow continuous PULL-BACK from the tight shot. To reach the flat SKY water
CHIEF has to CROUCH, then KNEEL — his triumphant pose degrading in stages as the frame widens and the
ASPHALT trough is revealed to be at ANKLE HEIGHT. Desaturated duck silhouettes enter frame around him,
waiting patiently, closer with each stage. His expression moves from smug to confused to worried. POP_TEAL
foliage. The tall fountain is still just outside frame.
```
- Motion: **three discrete posture stages** (~1.4 s apart): triumphant → crouch → kneel. **Camera: one continuous PULLOUT — do not cut into this.**

### C7 — 0:27–0:31 · WIDE.EYE.PUNCHIN → SETTLE · perspective shift
```
{style prefix} Full-width 9:16 showing the WHOLE layout in one frame. On the left, CHIEF is on his knees
at the shallow ground-level ASPHALT trough, ringed by patient desaturated duck silhouettes, face shocked
and panicked, cap and sash and medals all still on. On the right, at the long path's end, stands the TALL
ASPHALT drinking fountain with tiny PIP drinking from it comfortably UPRIGHT, gleeful, its flat SKY water
arcing. Between them the PAPER signpost with both INK arrows clearly legible. Flat FX_impact_star at the
tall fountain. Nothing has changed except what is in frame.
```
- Motion: three-stage face snap; eyeline trough → fountain → sign. Camera: punch-in on the tall fountain, settle wide; **0.5 s freeze on the full three-element geometry.**

### C8 — 0:31–0:32 · WIDE → MED (== C1b) · payoff/loop
```
{style prefix} 9:16. CHIEF kneeling among patient desaturated duck silhouettes beside the low ASPHALT
trough, cap still on, sheepish. Tiny PIP has filled a small PAPER cup at the tall fountain, walked over and
SET IT DOWN within CHIEF's reach — plainly, no smirk — and gives a small friendly wave to camera, relieved.
Framing then settles into the EXACT C1b schematic composition of the PAPER signpost, both INK arrows and
the tiny paw symbol.
```
- Motion: cup set down (5 frames), PIP wave, one duck shuffle. **No sparkle on PIP.** Settle to C1b framing as the final frame.

---

## Transitions & cut map
| Between | Type |
|---|---|
| C1→C1b | hard cut (payoff → rule) |
| C1b→C2 | hard cut (rewind) |
| C2→C3 | hard cut · **C3 internal:** hard cuts A/B/A/B (the scoreboard) |
| C3→C4 | hard cut |
| **C5 internal 0:16** | **music cut only, no visual cut** |
| **C5→C6** | **NO CUT — continuous PULLOUT.** The reveal is the camera move |
| C6→C7 | hard cut into punch-in |
| **C7 internal** | 0.5 s freeze on the full geometry |
| C7→C8 | hard cut |
| C8→loop | hard cut, seam to C1 |

No dissolves, fades, wipes, glitch, zoom-blur or camera rotation.

> **The integrity rule for this episode:** nothing may be *hidden by cheating*, only by **framing**. Both
> fountains, both arrows and the paw symbol exist in the layout from frame 1 and never move. If any element
> of the reveal is added late or contradicts the sign, this stops being a Perspective Shift and becomes a
> rug pull — which the retention research names as the highest-severity failure available.

---

## Handoff checklist
- [ ] 9:16 / 1080×1920, ≈32 s, timecodes exact.
- [ ] C1 tight, mid-motion, no entrance.
- [ ] **Paw symbol present in C1b, C2 and C8 at identical small scale, never highlighted.** Test on a cold viewer: findable on rewatch, missable first time.
- [ ] Signpost screen position identical in C1b, C2, C8.
- [ ] **Both fountains exist in the layout throughout; neither ever moves.** Only framing changes.
- [ ] C3's intercut shows **no fountain** in either shot.
- [ ] **C5 framing genuinely excludes the fountain height and the animals.**
- [ ] **C5→C6 is one continuous pull-back, not a cut.**
- [ ] Posture degradation monotonic in C6 (triumphant → crouch → kneel), never rebounding.
- [ ] C7 holds trough + signpost + tall fountain in **one frame**.
- [ ] CHIEF keeps cap + sash + medals throughout, including kneeling.
- [ ] Animals are **Crowd class** — desaturated silhouettes, no individual faces, patient and calm. **None harmed, herded or startled.**
- [ ] Colour tokens only — foliage `POP_TEAL`, stone/paths `ASPHALT`, water `SKY`, sign/cup `PAPER`. **No "green", no "brown", no "grey".**
- [ ] Zero baked text; the sign is pictograms only.
- [ ] Final frame matches C1b.
