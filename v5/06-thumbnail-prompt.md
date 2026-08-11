# v5 — Thumbnail Generation Prompt (LONG FORM ONLY)

> High-CTR thumbnail package for `IPPA_0005_pie_longform_v1`. Long-form videos live or die on the
> thumbnail + title pair, so this file gives **three competing concepts** (ranked), the exact generation
> prompts, title pairings, and a pass/fail checklist. Shorts don't need this file — they're discovered by
> feed autoplay, not by click.

**Spec:** 1280×720 px, 16:9, <2 MB, JPG/PNG. Must remain legible at **320×180** (mobile feed size) and as
small as **120×68** (sidebar). Design at full size, then **zoom out to 15% and re-check** — if the emotion
and the subject don't survive that, it fails.

---

## The CTR strategy for this video

The video's engine is a **curiosity gap**: CHIEF is loudly accusing the wrong suspect while the answer sits
behind him. The thumbnail should hand the viewer that gap directly — **let them see the pie in the evidence
box that CHIEF can't see.** The viewer becomes the only one who knows, and clicking is how they watch the
idiot find out.

That is a stronger click driver than hiding the answer, because it converts curiosity into *superiority* —
the viewer already feels smart before the video starts.

**Three ingredients, every concept:**
1. **One huge readable emotion** (CHIEF's face — accusatory or horrified).
2. **One clear conflict** (finger pointing at tiny, innocent PIP).
3. **One curiosity object** (the pie visibly in the box, unnoticed).

---

## Concept A — "The Wrong Suspect" ⭐ RECOMMENDED

CHIEF fills the left two-thirds, mid-accusation, pointing off-frame-right at tiny PIP who is cowering
bottom-right with crumbs on his scarf. Behind CHIEF's shoulder, clearly visible to us, sits the open
evidence box **with the pie in it**. A `BRAND_YELLOW` arc or halo isolates the pie so the eye finds it
second, after the face.

**Why it wins:** it tells the entire premise in one image without text, creates the "he's behind you!"
reflex, and the eye path is clean — face → finger → victim → pie.

```
Thumbnail illustration, flat-color 2D cartoon, thick uniform black outlines, no gradients, high
contrast, clean vector look, 16:9 horizontal composition, designed to be legible at very small size.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3.
LEFT TWO-THIRDS: a pompous rotund cartoon detective CHIEF — POP_TEAL jacket, oversized peaked cap with
a badge, diagonal BRAND_YELLOW medal sash, tiny mustache, bushy brows — face LARGE and filling the
upper left, mouth open in an enormous theatrical accusing shout, eyes wide, one oversized white glove
pointing dramatically toward the right of frame. An oversized magnifying glass in his other hand.
BOTTOM RIGHT: tiny PIP, a small round underdog with a POP_TEAL scarf and huge worried teary eyes,
cowering, small crumbs on his scarf, hands up innocently.
BEHIND CHIEF'S SHOULDER, clearly visible to the viewer: an open wooden evidence box sitting on the
ground with a whole golden pie inside it, subtly haloed by a BRAND_YELLOW glow arc so the eye lands on
it second. A faint trail of pie filling leads toward the box.
Bright flat SKY background, simple market awning shapes, heavily desaturated so the figures pop.
Strong silhouette separation between all three elements. NO TEXT IN THE IMAGE.
```

---

## Concept B — "The Horrified Realisation"

A single enormous close-up of CHIEF's face at the moment of the reveal — eyes blown wide, mouth open in
horror, sweat bead, cap slipping. Bottom-right corner: a small inset of the pie sitting in the evidence
box. Highest emotional contrast, weakest premise clarity.

**Use if:** Concept A tests poorly, or you want a face-forward thumbnail that matches the channel's other
episodes for a consistent grid.

```
Thumbnail illustration, flat-color 2D cartoon, thick uniform black outlines, no gradients, high
contrast, clean vector look, 16:9 horizontal, legible at very small size.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3.
EXTREME CLOSE-UP filling almost the whole frame: the face of a pompous rotund cartoon detective CHIEF
in an oversized peaked cap with a badge and a BRAND_YELLOW medal sash — eyes blown enormously wide in
comic horror, brows shot up, mouth wide open, a single large sweat bead on his temple, cap tipping off
his head, tiny mustache. Pure shock and mortification.
BOTTOM RIGHT CORNER, small and clearly separated: an open wooden evidence box with a whole golden pie
sitting inside it, outlined in a thin BRAND_YELLOW keyline so it reads at small size.
Flat ALERT_RED radiating comic shock lines behind his head for contrast. NO TEXT IN THE IMAGE.
```

---

## Concept C — "Split Verdict" (A/B test challenger)

A hard vertical split. **Left:** CHIEF pointing furiously at PIP (the accusation). **Right:** the pie
sitting in the evidence box. A thin `INK` divider between them and a `BRAND_YELLOW` question-mark shape
straddling the line.

**Use if:** you want the most explicit "spot the contradiction" framing. Slightly busier, but very clear
at tiny sizes because each half has one subject.

```
Thumbnail illustration, flat-color 2D cartoon, thick uniform black outlines, no gradients, high
contrast, clean vector look, 16:9 horizontal, legible at very small size. Split into two halves by a
thick vertical INK divider line.
Palette: INK #1A1A1A, BRAND_YELLOW #FFD400, PAPER #FFF7E0, SKY #BFE3F2, ASPHALT #6E7076,
ALERT_RED #E4322B, POP_TEAL #2FB6A3.
LEFT HALF: pompous rotund cartoon detective CHIEF in a POP_TEAL jacket, oversized peaked cap with badge
and BRAND_YELLOW medal sash, shouting furiously and pointing an oversized white glove at a tiny cowering
round underdog PIP with a POP_TEAL scarf and huge teary eyes.
RIGHT HALF: a clean, well-lit open wooden evidence box with a whole golden pie sitting inside it, a
faint trail of filling leading into it, on a plain PAPER background.
STRADDLING THE DIVIDER: one bold BRAND_YELLOW question-mark shape with a thick INK outline.
NO TEXT IN THE IMAGE.
```

---

## Text overlay (added after generation, not baked into the render)

Generate the art **text-free**, then overlay type in your editor so you can A/B test copy without
re-rendering.

- **Max 3–4 words.** Long titles are unreadable at 320px.
- Style: `INK` text with a `PAPER` outline, or `PAPER` text with an `INK` outline — whichever contrasts
  with that corner of the art. Heavy geometric sans, all caps, slight upward tilt.
- Placement: **top-left or bottom-left**, never bottom-right (YouTube's duration badge sits there) and
  never over a face.
- Keep the words and the title **different** — the thumbnail should add information, not repeat it.

| Overlay option | Pairs with |
|---|---|
| **"IT'S BEHIND YOU"** | Concept A — leans into the reflex |
| **"WRONG GUY."** | Concept A or C — short, confident, funny |
| **"HE DID IT"** *(with the arrow pointing at CHIEF)* | Concept B — ironic |
| *(no text at all)* | Concept A — the image is self-explanatory; worth testing, since text-free often wins on mobile |

---

## Title pairings (thumbnail + title must not duplicate each other)

| # | Title | Best thumbnail | Why |
|---|---|---|---|
| 1 | **He Investigated The Crime He Committed** | A (no text) | States the irony without naming the object; the thumbnail supplies the pie |
| 2 | **The Detective Was The Thief (He Didn't Know)** | A + "IT'S BEHIND YOU" | Parenthetical creates the curiosity gap |
| 3 | **Everyone Knew Except Him** | B + "WRONG GUY." | Pure superiority hook, works with the horror face |
| 4 | **Who Stole The Pie? 🥧** | C | Poses the question the thumbnail half-answers — highest curiosity, lowest specificity |

**Recommended launch pair:** Concept **A with no text overlay** + title **"He Investigated The Crime He
Committed."** The image carries the premise, the title carries the irony, and neither repeats the other.

---

## Pass/fail checklist
- [ ] Legible at **320×180**; subject and emotion still readable at **120×68**.
- [ ] **One** clear focal face with a big, unambiguous expression.
- [ ] Eye path is deliberate: face → pointing finger → victim → pie (max 3 stops).
- [ ] The curiosity object (pie in the box) is visible but **second** in the hierarchy, not competing with the face.
- [ ] Bottom-right corner kept clear of anything important (duration badge).
- [ ] No text baked into the generated art; overlay added separately, ≤4 words, not over a face.
- [ ] On-palette; **`BRAND_YELLOW` used only as the pie/halo accent** so it acts as the eye magnet.
- [ ] Cast on-model: CHIEF's cap + sash + medals, PIP's teal scarf.
- [ ] Thumbnail is **honest** — every element shown genuinely appears in the video. No clickbait that the video doesn't pay off.
- [ ] Sits distinctly next to v1–v4 thumbnails in the channel grid (different colour balance and composition).
- [ ] Advertiser-safe: comic shock only, no distress, no gore.
