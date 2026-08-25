# Placeholder Migration — *Plot Twist Pals* → IPPA

The rename is **mechanical and non-substantive**: a placeholder becomes a real name. No locked
decision changes. Every edit below is applied on this branch.

## Rename rules

| Old | New |
|---|---|
| `Plot Twist Pals` (brand name) | `IPPA` |
| `"Plot Twist Pals Promise"` | `"The IPPA Promise"` |
| `"Plot Twist Pals — Shorts"` (playlist) | `"IPPA — All Shorts"` |
| `PTP_[####]_[premise]_[platform]_v#` (video ID) | `IPPA_[####]_[premise]_[platform]_v#` |

The asset namespaces `CHAR_ / PROP_ / BG_ / UI_ / FX_ / MUS_ / SFX_` are **unchanged** — they are
asset-class prefixes, not brand prefixes, and the
[RC report](../production/RELEASE_CERTIFICATION_REPORT.md) scored that namespace discipline 10/10.
Only the video-level brand prefix moves.

## Brand name references

| File | Line | Change |
|---|---|---|
| [`docs/11-stage-1_5-business-decisions.md`](../docs/11-stage-1_5-business-decisions.md) | 40 | Channel DNA row: placeholder → locked name |
| [`docs/40-glossary.md`](../docs/40-glossary.md) | 77 | Glossary entry rewritten for IPPA |
| [`docs/41-faq.md`](../docs/41-faq.md) | 7 | "working name" → locked name |
| [`production/design/BRAND_BIBLE.md`](../production/design/BRAND_BIBLE.md) | 34 | Working-brand banner → locked |
| [`production/design/BRAND_BIBLE.md`](../production/design/BRAND_BIBLE.md) | 89 | "Plot Twist Pals Promise" → "The IPPA Promise" |
| [`production/templates/metadata-template.md`](../production/templates/metadata-template.md) | 34 | Playlist name |
| [`production/A1-first-video/08-publish-package.md`](../production/A1-first-video/08-publish-package.md) | 49 | Playlist name |
| [`production/RELEASE_CERTIFICATION_REPORT.md`](../production/RELEASE_CERTIFICATION_REPORT.md) | 110, 135 | Open action #1 marked resolved |

## Video-ID prefix references

| File | Occurrences |
|---|---|
| [`docs/12-stage-2-channel-operating-system.md`](../docs/12-stage-2-channel-operating-system.md) | 1 |
| [`production/RELEASE_CERTIFICATION_REPORT.md`](../production/RELEASE_CERTIFICATION_REPORT.md) | 1 |
| [`production/design/ANIMATION_LANGUAGE_MOTION_SYSTEM.md`](../production/design/ANIMATION_LANGUAGE_MOTION_SYSTEM.md) | 2 |
| [`production/design/CAMERA_CINEMATOGRAPHY_BIBLE.md`](../production/design/CAMERA_CINEMATOGRAPHY_BIBLE.md) | 2 |
| [`production/design/PRODUCTION_PROMPT_FRAMEWORK_RUNTIME_ORCHESTRATION.md`](../production/design/PRODUCTION_PROMPT_FRAMEWORK_RUNTIME_ORCHESTRATION.md) | 1 |
| [`production/design/VISUAL_IDENTITY_LOCK.md`](../production/design/VISUAL_IDENTITY_LOCK.md) | 1 |

## Branches not touched by this migration

The rename is applied on a branch cut from `feature/production-foundation-docs` (the superset). These
other branches carry their own copies of the same placeholder text and will need the same rename if
and when they're merged:

| Branch | Needs rename |
|---|---|
| `docs/project-architecture` | `docs/` copies |
| `feat/first-video-a1-artifacts` | `docs/` + `production/` copies |
| `feature/visual-production-system` | `docs/` copies |
| `feature/master-runtime` | `repository_map.yaml` path reference only — no brand text |
| `Execution`, `live-wallpaper` | No brand-name references (checked) |

`feature/master-runtime`, `feature/master-runtime-implementation`, and `feature/production-tool-stack`
use the word "channel" only in the software sense (reporting channel, release channel). **No changes
needed there** — don't let a find-and-replace touch them.

## Verification

```bash
# Should return nothing on this branch:
git grep -in "Plot Twist Pals"
git grep -n "PTP_"
```
