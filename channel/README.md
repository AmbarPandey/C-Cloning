# IPPA — Channel Setup

Everything needed to stand up the actual YouTube channel. This folder is the **operational bridge**
between the locked strategy in [`docs/`](../docs/00-index.md) + [`production/`](../production/README.md)
and a live, publishing channel.

> **Channel name:** **IPPA** · pronounced *IP-puh* · tagline **"The jerk always gets it."**
> Locked in [01-CHANNEL-IDENTITY-LOCK.md](01-CHANNEL-IDENTITY-LOCK.md), recorded as
> [D-21](../docs/21-decision-log.md).

## Read in this order

| # | Document | What it gives you |
|---|---|---|
| 1 | [Channel Identity Lock](01-CHANNEL-IDENTITY-LOCK.md) | The name, pronunciation, tagline, logo concept, handle candidates, D-21 entry |
| 2 | [Channel Metadata](02-channel-metadata.md) | Copy-paste description, keywords, playlists, trailer strategy |
| 3 | [Brand Art Specs](03-brand-art-specs.md) | Icon / banner / wordmark / watermark specs + ready-to-run generation prompts |
| 4 | [YouTube Studio Setup](04-youtube-studio-setup.md) | Step-by-step account and settings walkthrough |
| 5 | [Launch Checklist](05-launch-checklist.md) | Day 0 → Day 90 sequence, and the **YPP math problem** you need to decide on |
| 6 | [Placeholder Migration](06-placeholder-migration.md) | The *Plot Twist Pals* → IPPA rename map |

## What this folder does not contain

- **Image files.** [Brand Art Specs](03-brand-art-specs.md) contains the specs and the generation
  prompts; the actual PNG/SVG exports go in `channel/assets/` once you've run them.
- **Any change to locked strategy.** The name changed; nothing else did. Every decision in the
  [Decision Log](../docs/21-decision-log.md) stands.

## Open decisions

Two things are waiting on you, both flagged in place:

1. **The YPP path** — the Shorts-only route to monetization requires 10M Shorts views in 90 days,
   which doesn't line up with the stated Day-90 target. Three options, with a recommendation, in
   [Launch Checklist](05-launch-checklist.md#the-ypp-math-problem).
2. **Made-for-kids and synthetic-content disclosures** — compliance settings only you can set. Factors
   laid out in [YouTube Studio Setup](04-youtube-studio-setup.md#step-9--two-disclosures-you-must-set-yourself).

## Where this sits

```
docs/           strategy, locked decisions, stage definitions   (WHY + WHAT)
intelligence/   the viral/comedy/twist/pattern libraries        (THE MECHANICS)
production/     design bibles, templates, per-video packages    (HOW TO MAKE IT)
channel/        the live channel: identity, art, settings       (WHERE IT SHIPS)  ← you are here
V1/             the first finished video package
```
