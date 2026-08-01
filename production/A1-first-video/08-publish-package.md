# A1 — Publish Package (Stage 6 output)

The final, copy-paste-ready publishing metadata for A1, plus the thumbnail brief. Built on the
reusable [metadata template](../templates/metadata-template.md) and
[thumbnail spec](../templates/thumbnail-spec.md). This is what feeds the
[n8n publishing flow](../tools/n8n-publishing.md).

## Title (primary)
```
He Booted the Wrong Scooter 😳 #shorts
```
Alternates (A/B): `The Parking Officer's Instant Karma 😅 #shorts` · `Karma Towed Him Away 🚛 #shorts`

Rules honored: ≤ ~60 chars, curiosity + payoff promise, no spoilers of *how*, one emoji, `#shorts`.

## Description
```
The parking officer picked on the little guy… until karma parked itself right behind him. 🚛😂
Watch the very first frame again — his scooter was in the no-parking zone the whole time. 👀

New twist-ending toons every day. Which pal deserves the next comeuppance? 👇

#shorts #animation #cartoon #comedy #plottwist #karma #funny #instantkarma #satisfying #toon
```
Rules honored: 1-line hook + replay nudge (drives the seed rewatch) + comment prompt + hashtag block.

## Hashtags (canonical set)
`#shorts #animation #cartoon #comedy #plottwist #karma #funny #instantkarma #satisfying #toon`
(10 tags: 1 format + 3 genre + 3 twist/payoff + 3 discovery. Reuse this set as the channel default.)

## Thumbnail brief
> Shorts autoplay, but a thumbnail is still set for the channel grid / browse. Follow the
> [thumbnail spec](../templates/thumbnail-spec.md).

- **Frame source:** a beat between Shot 5 and Shot 7 — CHIEF mid-victory-pose, tow hook just
  visible entering behind him (tension, not the full spoiler).
- **Composition:** CHIEF large left (smug), tow-truck hook peeking top-right, PIP tiny bottom-right.
- **Face:** CHIEF `smug` expression, oversized.
- **Text (optional, ≤3 words):** `WRONG MOVE` in `INK` on a `BRAND_YELLOW` pill, top area, not covering faces.
- **Contrast:** keep `ALERT_RED` no-parking zone visible as a subconscious clue.
- **Export:** 1080×1920 still + a 1280×720 center-safe crop for the grid.

## Publishing settings
| Field | Value |
|---|---|
| Category | Comedy / Film & Animation |
| Audience | Not made for kids (advertiser-safe general audience) — set per channel policy |
| Visibility | Scheduled (batch per [daily workflow](../../docs/30-daily-workflow.md)) |
| Playlist | "Plot Twist Pals — Shorts" |
| Language / captions | English (auto); manual SFX captions optional (see [editing spec](07-editing-spec.md)) |
| Cadence slot | Fills one slot of the 10–14/week schedule |

## Pre-publish dependency
Do **not** publish until the [Publish Gate](10-production-checklist.md) passes 11/11.
