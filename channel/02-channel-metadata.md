# Channel Metadata — copy-paste ready

Everything that goes into the text fields of the channel. Inherits voice rules from the
[Brand Bible](../production/design/BRAND_BIBLE.md) and the title/description/hashtag formulas from
the [metadata template](../production/templates/metadata-template.md).

---

## Channel name field

```
IPPA
```

## Handle

See [handle candidates](01-CHANNEL-IDENTITY-LOCK.md#handle-candidates). Claim the highest available.

---

## Channel description (the "About" box)

YouTube allows up to 1,000 characters. This draft is ~700, which leaves room to add links later.
The first ~100 characters are what surface in search and on mobile previews, so the hook is front-loaded.

```
IPPA makes tiny animated comedies where arrogance meets instant karma.

Every episode is under 40 seconds, works perfectly with the sound off, and ends on a twist that was hiding in the very first frame.

MEET THE PALS
PIP — small, round, kind, teal scarf. The underdog. Never the aggressor.
CHIEF — peaked cap, medal sash, giant stamp. His own ego is always his downfall.

THE IPPA PROMISE
1. Every video ends with a real twist.
2. Karma is fair and bloodless. It lands on whoever earned it.
3. It works muted, anywhere on Earth. No language needed.
4. The same pals are back tomorrow.
5. Your time is respected. Hard cut on the reveal.

New twist every day.
Watch the first second again. The clue was always there. 👀
```

**Why it's built this way:** it states the format in line 1 (so a stranger self-selects instantly),
introduces the cast as *characters* rather than assets (the loyalty engine, per
[D-02](../docs/21-decision-log.md)), and publishes the five-point promise verbatim from the
[Brand Bible](../production/design/BRAND_BIBLE.md) so the public contract and the internal contract
are identical. It closes on the replay nudge that points at the seed.

---

## Channel keywords

YouTube Studio → Settings → Channel → Basic info → Keywords. Comma-separated. Wrap multi-word
phrases in quotes so they aren't split.

```
IPPA, "animated shorts", "plot twist", "instant karma", "twist ending", cartoon, comedy, animation, "funny animation", "silent comedy", "no dialogue", satisfying, toon, "wholesome comedy", "karma animation"
```

> Channel keywords are a weak ranking signal — fill them once and move on. Your titles, the first
> frame, and retention do the real work.

---

## Contact and links

| Field | Value |
|---|---|
| Business email | Use a dedicated address, e.g. `hello@` or `business@` your domain — **not** your personal Gmail |
| Country | Set to your actual country of residence (affects monetization and tax setup) |
| Links | Leave empty at launch. Add TikTok/Instagram once you're actually cross-posting. |

Set the business email **before** launch. Sponsorship enquiries arriving at a personal address get
lost, and the address is public — you don't want that to be the one tied to your Google identity.

---

## Playlists

Create these on day 0. Playlists on a Shorts channel matter less for discovery than for the
**channel page** — they make a new visitor understand the format in one glance, which converts
browse traffic into subscribers.

| Playlist | Contents | Maps to |
|---|---|---|
| **IPPA — All Shorts** | Every episode, oldest→newest | Full catalogue |
| **PIP & CHIEF** | The flagship cast series | The recurring-cast loyalty engine |
| **Instant Karma** | Arrogance abuses power → immediate payback | Pillar NP1 Comeuppance |
| **Underdog Wins** | The little guy quietly comes out on top | Pillar NP2 Underdog Reversal |
| **Ego Collapse** | Greed/ego escalates until it topples itself | Pillar NP3 Overreach Collapse |
| **Wait… What?** | Reframes and misdirects — the rewatchable tier | Pillars NP4 Hidden Truth + NP7 Bait-and-Switch |
| **Best of IPPA** | Manually curated top performers | Conversion surface for new visitors |

Pillar definitions come from the [Brand Bible content pillars](../production/design/BRAND_BIBLE.md)
and [Library 6](../intelligence/06-narrative-pattern-library.md).

> **Update needed:** the [A1 publish package](../production/A1-first-video/08-publish-package.md) and
> the [metadata template](../production/templates/metadata-template.md) both name the playlist
> `"Plot Twist Pals — Shorts"`. That becomes `"IPPA — All Shorts"`. Tracked in
> [placeholder migration](06-placeholder-migration.md).

---

## Per-video metadata (unchanged formulas, new playlist name)

**Title:** `<curiosity hook implying a twist, no spoiler> <1 emoji> #shorts` — ≤ ~60 chars, exactly
one emoji, never reveal *how* the twist lands.

**Canonical hashtag set** — reuse on every video, per
[metadata template](../production/templates/metadata-template.md):

```
#shorts #animation #cartoon #comedy #plottwist #karma #funny #instantkarma #satisfying #toon
```

**Channel line for descriptions** — the fixed sentence that goes in the CTA block of every video:

```
New twist every day on IPPA. Who deserves the next one? 👇
```

This replaces the generic `<channel line>` slot in the description formula.

---

## Channel trailer

Two slots exist: **for new visitors** (non-subscribers) and **for returning subscribers**.

- **For new visitors:** your single best-performing Short. Do **not** cut a bespoke "welcome to my
  channel" trailer — it violates *respect the viewer's time* and a strong episode demonstrates the
  format better than any explanation. Swap it monthly as better episodes land.
- **For returning subscribers:** your most recent upload.

At launch you have no performance data, so use the episode whose twist you're most confident in
(currently [A1 — *The Wrong Scooter*](../production/A1-first-video/README.md)), then replace it as
soon as real retention data exists.
