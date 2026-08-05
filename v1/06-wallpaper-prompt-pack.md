# v1 — Wallpaper Prompt Pack ("The Wrong Scooter")

> **Purpose:** Eight paste-ready **9:16 wallpaper** prompts (1080×1920), one per clip of the master
> timeline in [`01-video-script.md`](01-video-script.md), staged with the motion/camera/FX intent from
> [`04-video-generation-prompt.md`](04-video-generation-prompt.md) collapsed into a single held frame.
>
> **Style source:** calibrated to the **approved rendered reference images**, not to the older flat-vector
> text in `02` §0 / root `IMAGE-GEN-REFERENCE.md` §1. Those two describe a stricter style than what was
> actually shipped — see **§7 Divergence log** before you reconcile anything.
>
> **How to use:** prepend **§1 Style Prefix v2**, add the **cast** (§2) and **set** (§3), then paste the
> shot block from §5. Attach the approved reference image for each character as an image prompt / seed on
> every generation. Use the **§6 negative prompt** every time.

---

## 1. Style Prefix v2 — ALWAYS prepend (calibrated to the approved renders)

```
Semi-flat 2D cartoon illustration, bold dark charcoal outlines with slight weight variation, soft
two-tone cel shading, subtle fine paper-grain texture on ground planes, no photographic detail,
no lens blur. Clean saturated storybook-comic look, 9:16 vertical 1080x1920, mobile-legible,
one clear subject, generous negative space. Bright cheerful daytime mood. Advertiser-safe, no gore.
Palette: outlines charcoal #22201E; sky cyan #45BEEE; clouds warm cream #F6F1E4;
asphalt grey #4E4E4E with worn white painted lines #EDE7D8; hazard red #BB2E25 with faded cream
lettering; uniform teal #1F6B68; brass/gold #F0B21C; skin peach #F3C9A0; ivory #F7F1E3.
Saturated accents limited to teal, gold, and red. Backgrounds stay quieter than the cast.
```

---

## 2. Cast lock blocks (as rendered — reuse verbatim)

**CHIEF — smug warden / antagonist** (`CHAR_CHIEF_v2`)
```
Rotund pompous parking warden, ~3.5 heads tall, large head, barrel chest thrust out, short legs,
chin high. Deep teal military-cut warden jacket #1F6B68 with gold buttons and shoulder tabs, a wide
diagonal gold sash #F0B21C crossing the chest, a cluster of colorful ribbon medals and gold stars on
the left breast, oversized peaked cap in matching teal with a gold shield badge, oversized puffy
white gloves, black trousers and black shoes. Peach skin #F3C9A0, glossy black side-parted hair,
thick black eyebrows, curled black mustache, small half-lidded eyes, permanent smug half-smile.
Silhouette signature (NEVER omit): peaked cap + diagonal sash + medals. Default face: smug.
```

**PIP — tiny underdog / protagonist** (`CHAR_PIP_v2`)
```
Tiny baby-like underdog, ~2.5 heads tall, huge round head, soft ivory #F7F1E3 rounded body, white
diaper, tiny stub arms and legs, one small tuft of hair. Enormous glossy black eyes with large white
catchlights, pink blush cheeks, tiny mouth. A chunky knitted teal scarf #1F6B68 around the neck
(signature — present in EVERY image). Reads small, soft and harmless in silhouette.
Default face: worried, brows raised, eyes welling.
```

**Status rule:** in any shared frame CHIEF reads bigger / higher / more open; PIP smaller / lower / more closed. Karma always lands on CHIEF, never on PIP.

---

## 3. Set + prop lock blocks

**Parking lot plate** (`BG_parkinglot_v2`)
```
Open public parking lot on a bright clear day. Flat cyan sky #45BEEE with a few soft flat cream
puffy clouds. Mid-grey asphalt #4E4E4E with fine speckle grain and worn white painted parking lines.
A dark grey coin parking meter on a post at the left. In the lower-right foreground a bold hazard-red
#BB2E25 painted NO-PARKING zone: a thick red rectangle in perspective with a lighter red inner
border and large faded cream "NO PARKING" lettering. Plain, orderly, rule-governed. No incidental
characters. Ground and sky stay lower-contrast than the cast.
```

| Prop | Locked description |
|---|---|
| `PROP_chief_scooter_v2` | Teal vintage Vespa-style scooter, rounded body, gold shield emblem on the leg shield, black saddle, chrome mirrors and headlamp. **The seed** — parked inside the red zone. |
| `PROP_pip_scooter_v2` | Small teal two-wheel kick-scooter, slim deck, black handlebar grips, tiny wheels. |
| `PROP_boot_v2` | Chunky golden-yellow wheel-clamp immobilizer with bolt heads. |
| `PROP_stamp_v2` | Comically oversized rubber stamp, dark brown wooden body, polished brass handle with a star emblem. |
| `PROP_ticketpad_v2` | Oversized cream clipboard sheet reading "PARKING TICKET" with red "$$$" marks. |
| `PROP_towtruck_v2` | Chunky white-cab tow truck, yellow-and-black hazard-striped boom base, long black crane arm, chrome hook on cables, orange roof lightbar. |
| `PROP_podium_v2` | Cream stone two-step podium with a gold laurel wreath and gold "P" shield on the front. |
| `PROP_flag_v2` | Plain gold-yellow rectangular flag on a slim grey pole. |
| `UI_towed_v2` | Large tilted hazard-red distressed rubber-stamp mark: the word "TOWED" in heavy condensed caps inside a red double-line rectangular border. |
| FX | Small gold four-point sparkle stars; charcoal motion arcs; small white puff clouds; single blue sweat drop; radial gold burst lines. |

---

## 4. Wallpaper composition rules (these differ from the video stills)

A video frame and a phone wallpaper are not the same crop. Apply all four:

1. **Top safe zone — keep the upper 15% (0–288 px) free** of faces, props and text. Sky and clouds only. The clock/status bar sits here.
2. **Bottom safe zone — keep the lower 18% (1574–1920 px) visually calm.** In the approved renders the "NO PARKING" lettering sits in the bottom ~8%, where a lock-screen dock will cover it. For wallpapers, **pull the red zone and its lettering up so the text ends by ~1560 px**, or crop the lettering deliberately.
3. **Subject band:** place the primary read (CHIEF's face, the TOWED stamp, PIP's wave) between **25% and 70% of the height** (480–1345 px).
4. **Mute-first still holds:** the beat must read with no motion and no caption. Where `04` conveys the beat through movement (a strut cycle, a push-in, a punch-in), substitute a **static equivalent** — motion arcs, puff clouds, a tilted pose, radial burst lines. Each block below names its substitution.

---

## 5. The eight wallpaper prompts

Prepend §1, attach cast references. `{set}` = the §3 plate block.

### W1 — Hook + Seed (C1, 0:00–0:02) · WIDE.EYE.STATIC
```
{set} Wide establishing wallpaper. Left third: CHIEF mid-strut walking in from the left edge, chest
out, chin high, smug, one white-gloved fist swinging, small charcoal motion arcs behind his heels.
Center: tiny PIP standing at the parking meter, worried, holding a small brown coin purse in both
stub hands with one gold coin lifted toward the meter slot; his teal kick-scooter parked just behind
him. Lower-right foreground: the red NO-PARKING zone with CHIEF's teal Vespa parked squarely inside
it, clearly visible but not emphasized. Calm balanced composition, wide empty sky across the top.
MOTION SUBSTITUTION: strut conveyed by heel motion arcs + mid-stride pose, not blur.
```

### W2 — Setup (C2, 0:02–0:06) · MED.EYE.PUSHIN
```
{set} Medium two-shot wallpaper, tighter than W1. CHIEF dominating the left and center, gloating
grin, one gloved hand raising the oversized brown-and-brass rubber stamp, the other holding out the
cream "PARKING TICKET" clipboard, his free index finger pointing accusingly down at PIP's kick-scooter
front tire sitting a hair over a worn white line. PIP small at the right, shrunk in on himself,
worried, standing beside his scooter. The red NO-PARKING zone with CHIEF's Vespa still held in the
lower-right. MOTION SUBSTITUTION: the slow push-in becomes a tighter crop and a larger CHIEF; add
small charcoal shake arcs beside the raised stamp.
```

### W3 — Escalation 1 (C3, 0:06–0:11) · MED.EYE.STATIC
```
{set} Medium wallpaper. CHIEF at the right, smug, stamp raised high in his gloved fist with charcoal
shake arcs around it, ticket clipboard in the other hand. Center-left: PIP's teal kick-scooter now
wearing a chunky golden-yellow wheel boot clamped on its front wheel, with a single cream "PARKING
TICKET" sheet hanging from the handlebar. PIP at the far left, teary, both stub hands clutched at his
mouth, fat blue tear drops on his cheeks. The red NO-PARKING zone holds the lower-right.
MOTION SUBSTITUTION: the 4-frame clamp impact hold becomes a small white puff cloud at the boot.
```

### W4 — Escalation 2 (C4, 0:11–0:16) · MED-WIDE.EYE.PUSHIN
```
{set} Medium-wide wallpaper. Center: PIP's little kick-scooter buried under a comical overflowing
mountain of cream "PARKING TICKET" sheets with red "$$$" marks, tickets spilling and scattering
across the asphalt around it, the golden wheel boot just visible underneath. Right: CHIEF standing
proud and peak-gloating, chin up, one gloved hand raising the stamp with a small white puff of
self-satisfaction above it, the other holding a fresh ticket clipboard. Left: PIP slumped and teary.
The red NO-PARKING zone with CHIEF's Vespa in the lower-right. MOTION SUBSTITUTION: the staggered
ticket pop-ins become mid-air scattering sheets; one gold sparkle glints off a medal.
```

### W5 — Anticipation / peak overconfidence (C5, 0:16–0:22) · FULL.LOW.PUSHIN → HOLD
```
{set} Low hero-angle wallpaper — strongest hero composition of the set. Center: CHIEF standing atop
the cream stone podium with its gold laurel and "P" shield, in an over-the-top victory pose, chest
maximally out, chin high, triumphant, the giant brown-and-brass stamp thrust to the sky in his right
glove, left hand planted on his hip. A gold-yellow flag on a grey pole planted beside him. Radial
gold burst lines and gold four-point sparkle stars around the raised stamp. Right of the podium: tall
untidy stacks of parking tickets. Lower left: PIP tiny, low, teary, dwarfed by the podium. Wide empty
sky above CHIEF. Dramatic negative space, maximum status contrast. MOTION SUBSTITUTION: the camera
rise becomes a worm's-eye angle; the 1.5s freeze becomes the held pose itself.
```

### W6 — Pattern break (C6, 0:22–0:27) · WIDE.EYE.STATIC (deep flat focus)
```
{set} Wide tense wallpaper with flat layered depth. Foreground center-right: CHIEF oblivious,
mid-swagger, eyes closed in smug self-congratulation, one gloved index finger raised, small charcoal
music notes beside his head, and a large white thought bubble above him containing a miniature
CHIEF proudly presenting his teal Vespa with sparkles. Background right: the white tow truck rolling
in, black crane arm extended, chrome hook swinging low and aimed at the red NO-PARKING zone — NOT at
PIP's scooter. Left: PIP small, hands at his mouth, tears still on his cheeks but eyes widening with
dawning hope, a tiny charcoal "!" above his head. Lower-right: the red zone with CHIEF's Vespa,
golden boot now clamped on its wheel. Tense, quiet, suspended mood. MOTION SUBSTITUTION: the suspense
hold becomes the hook frozen mid-swing directly above the Vespa.
```

### W7 — Twist / instant karma (C7, 0:27–0:31) · WIDE.EYE.PUNCHIN
```
{set} Wide punch-in wallpaper — the punchline frame. Upper left: CHIEF's own teal Vespa hoisted into
the air on the tow truck's chrome hook and slings, tilted nose-down, small charcoal strain lines at
the cables. Center-right: the white tow truck with its hazard-striped boom. Center: CHIEF flung
backwards off the podium in mid-air, panicked — eyes blown wide, mouth open in a gasp, both gloved
hands splayed, legs kicking up, blue sweat drops flying, his peaked cap knocked off and tumbling
above him. Foreground center-right, overlapping the red zone: a huge tilted hazard-red distressed
"TOWED" rubber-stamp mark in heavy condensed caps inside a red double-line border. Lower left: PIP
gleeful, hands clasped at his chin, gold sparkle stars around him, happy tears. Keep the TOWED mark
fully inside the safe band, ending by 1560 px. Only on-frame text is "TOWED".
MOTION SUBSTITUTION: the punch-in and impact-star become the oversized tilted stamp plus radial burst.
```

### W8 — Payoff / loop seam (C8, 0:31–0:32) · WIDE.EYE.STATIC (== W1 framing)
```
{set} Wide wallpaper reusing the EXACT W1 framing and horizon. Upper center-right: CHIEF dangling
helplessly in mid-air from the tow truck's chrome hook, panicked, arms and legs flailing, medals
jangling, peaked cap knocked off and tumbling beside him, blue sweat drops, charcoal motion arcs;
the white tow truck at the right edge. Lower left: PIP standing free and delighted, wide happy grin,
one stub arm raised in a small friendly wave to camera, gold sparkle stars around him. Center-right
foreground: the red NO-PARKING zone with CHIEF's teal Vespa, the golden wheel boot now lying loose
beside it. PIP's kick-scooter clean, ticket-free, behind him. Warm resolved mood, no residual FX.
CONTINUITY: identical camera framing and ground line to W1 for the loop seam.
```

---

## 6. Negative prompt (use on every generation)

```
photorealistic, 3D render, CGI, photograph, painterly brush texture, watercolor, sketch lines,
heavy gradients, glow, bloom, lens flare, depth-of-field blur, motion blur, vignette, film grain,
neon colors, off-palette color, colored outlines, pure black #000000, pure white #FFFFFF,
extra characters, crowds, bystanders, human passersby, extra limbs, deformed hands, warped faces,
mismatched character proportions, missing teal scarf, missing peaked cap, missing medal sash,
readable signage or lettering other than "NO PARKING" / "PARKING TICKET" / "TOWED",
watermark, signature, logo, UI overlays, borders, letterboxing, horizontal composition,
gore, blood, cruelty, the small character being hurt or humiliated.
```

---

## 7. Divergence log — approved renders vs. the written bibles

The reference renders are **style v2** and contradict `02` §0 and root `IMAGE-GEN-REFERENCE.md` on eight
points. Nothing below is a defect in the art; it means the *text* is stale. Reconcile in one direction
before the next video, or the two will keep drifting.

| # | Written bible says | Approved renders actually do | Suggested resolution |
|---|---|---|---|
| 1 | "No gradients", "flat color", "minimal single-tone shading" | Soft two-tone cel shading, speckle grain on asphalt, worn texture on the red zone | Adopt v2 wording; update the bible |
| 2 | "No realistic skin tones", CHIEF face `PAPER #FFF7E0` | CHIEF has peach skin, black hair, black mustache | Adopt v2 |
| 3 | CHIEF "~2.5 heads tall" | CHIEF reads ~3.5 heads | Adopt v2; PIP/CHIEF contrast still works |
| 4 | PIP wears "a simple tee" | PIP is baby-styled: diaper, blush cheeks, hair tuft | Adopt v2 |
| 5 | `SKY #BFE3F2` (desaturated) | Bright saturated cyan sky | Adopt v2 |
| 6 | Palette is closed; `BRAND_YELLOW #FFD400`, `POP_TEAL #2FB6A3` | Deeper teal, brass/gold, plus off-palette orange lightbar, chrome, ribbon multicolor | Add a small "mechanical/chrome" token set to the palette |
| 7 | Stamp is the hero prop and "can take the `BRAND_YELLOW` hit" | Stamp is brown wood + brass; the **boot** carries the yellow | Reassign: boot = yellow hero prop |
| 8 | **`01` checklist: "Only on-frame text is the 'TOWED' stamp"** | Every render has "NO PARKING" painted on the ground; C3/C4 add "PARKING TICKET" + "$$$" | **Amend the checklist** to: *"Only narrative text is 'TOWED'; environmental signage (NO PARKING, PARKING TICKET) is permitted set dressing."* As written, every approved render fails the gate. |

Two further items carried over from the script review, both of which affect W8:

- **`01`/`04` claim "last frame == first frame" / "Final frame must equal Shot-1 frame 1."** C1 has CHIEF
  strutting in and PIP fumbling coins; C8 has CHIEF hauled away and PIP waving. Those frames cannot be
  identical. The achievable spec — and what W8 above implements — is *identical framing, ground line and
  set position*, not identical content.
- **The ticket mountain is never cleared.** C4 buries PIP's scooter; C8 addresses only the boot, yet is
  meant to match the C1 plate, which has no tickets. W8 above resolves this by explicitly returning
  PIP's scooter to clean/ticket-free — decide whether the tickets blow away on the twist, and if so add
  it to `04` Shot 7.
