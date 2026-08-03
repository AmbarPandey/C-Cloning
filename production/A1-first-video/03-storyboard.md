# A1 — Storyboard + Render Prompts (Stage 6 output)

Compiled 1:1 from [02-script](02-script.md). Each shot lists framing, staging, and a **ready-to-paste
image/scene prompt** built on the [visual-prompt template](../templates/visual-prompt-template.md)
and the [cast style guide](../characters/cast-style-guide.md). Frame: **1080×1920 (9:16)**.

> Shot framing and camera moves follow the [Camera & Cinematography Bible](../design/CAMERA_CINEMATOGRAPHY_BIBLE.md)
> (shot-type + movement taxonomies and the [shot-descriptor notation](../design/CAMERA_CINEMATOGRAPHY_BIBLE.md#shot-descriptor-notation)).

## Global style prefix (prepend to every prompt)
```
Flat-color 2D cartoon, thick uniform black outlines, no gradients, minimal single-tone shading,
chunky 2.5-head proportions, high-contrast, clean vector look, 9:16 vertical, mobile-legible.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3. No text unless specified. Advertiser-safe, no gore.
```

## Storyboard table

| Shot | Time | Framing | Positions | Key action | Emotion |
|---|---|---|---|---|---|
| 1 | 0–2 s | Wide establishing | CHIEF enters L; PIP at meter C; **CHIEF's scooter in NO-PARKING zone R-fg** | Strut in / seed planted | smug / worried |
| 2 | 2–6 s | Medium two-shot | CHIEF L over PIP's tire R | Spots infraction, draws stamp | gloating / worried |
| 3 | 6–11 s | Medium | CHIEF R, PIP's scooter L | Stamp ticket + clamp boot | smug / teary |
| 4 | 11–16 s | Medium-wide | CHIEF C on paper pile | Pile-on + medal polish | peak-gloat / defeated |
| 5 | 16–22 s | Low-angle hero | CHIEF on podium C | Victory pose, stamp to sky | triumphant |
| 6 | 22–27 s | Wide (depth) | CHIEF C-fg posing; tow truck enters bg-R toward no-parking zone | Truck arrives unseen | oblivious / hopeful |
| 7 | 27–31 s | Punch-in wide | Truck + CHIEF's scooter R; CHIEF yanked from podium C | Own scooter towed + "TOWED" stamp | panicked / gleeful |
| 8 | 31–32 s | Wide (== shot 1) | CHIEF shrinking R-bg; PIP C waves | Boot pops off; PIP waves; loop | relieved |

## Per-shot render prompts

**Shot 1 (Hook + seed):**
```
{style prefix} Wide vertical parking lot, ASPHALT ground, SKY top. A parking meter left with
tiny PIP (small round cartoon, PAPER body, POP_TEAL scarf, big worried eyes) fumbling coins.
A pompous round warden CHIEF (POP_TEAL jacket, oversized peaked cap with badge, diagonal
BRAND_YELLOW medal sash, tiny mustache, smug) strutting in from left, chest out.
Lower-right foreground: an ALERT_RED "NO PARKING" painted zone containing a parked scooter.
Composition balanced and calm. This exact framing repeats at the end.
```

**Shot 2 (Setup):**
```
{style prefix} Medium two-shot. CHIEF grinning, pulling an oversized ticket pad and a giant
rubber stamp from his jacket, pointing at PIP's tiny scooter tire slightly over a white line.
PIP shrinking, worried.
```

**Shot 3 (Escalation 1):**
```
{style prefix} CHIEF slapping a paper ticket onto PIP's tiny scooter and clamping a bright
BRAND_YELLOW wheel boot on its wheel with a flourish, blowing on the stamp like a gunslinger.
PIP teary. Motion lines on the stamp.
```

**Shot 4 (Escalation 2):**
```
{style prefix} Medium-wide. A comical mountain of paper tickets piled on PIP's little scooter.
CHIEF standing proud, polishing his BRAND_YELLOW medals, chin up. PIP slumped, defeated.
```

**Shot 5 (Anticipation / peak overconfidence):**
```
{style prefix} Low hero angle. CHIEF standing on a small podium, one tiny flag planted, striking
an over-the-top victory pose with the giant stamp raised triumphantly to the sky. Proud gleam,
sparkle accents. Dramatic emptiness around him.
```

**Shot 6 (Pattern break):**
```
{style prefix} Wide with depth. CHIEF frozen mid-pose in foreground-center, oblivious. In the
background-right a cartoon TOW TRUCK rolls in, its hook arm swinging toward the ALERT_RED
NO-PARKING zone (NOT toward PIP). PIP off to the side, eyes widening with hope.
```

**Shot 7 (Twist / instant karma):**
```
{style prefix} Punch-in wide. The tow truck's hook clamps CHIEF'S OWN scooter in the NO-PARKING
zone; the truck's arm wields CHIEF's own giant stamp to slam a huge ALERT_RED "TOWED" mark on it.
CHIEF yanked off the podium, face snapping to shocked/panicked, arms flailing. PIP gleeful.
Big comedic impact star-burst behind the stamp. (Only on-frame text: "TOWED".)
```

**Shot 8 (Payoff / loop seam):**
```
{style prefix} Wide composition IDENTICAL to shot 1 framing. CHIEF shrinking into the distance
right, hanging off his towed scooter, medals jangling. PIP center, calmly peeling the popped-off
boot from his scooter, giving a small friendly wave to camera, relieved smile. Calm resolved mood.
```

## Notes for the renderer
- Shots 1 and 8 **must** share the identical camera framing/composition for the loop seam.
- Keep the no-parking scooter in the same screen position in shots 1, 6, 7 (continuity of the seed).
- On-frame text is allowed **only** on the "TOWED" stamp in shot 7.
- See [Anijam usage](../tools/anijam-usage.md) for turning these stills into animated shots.
