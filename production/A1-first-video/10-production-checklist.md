# A1 — Production Checklist + Publish Gate (filled)

Ordered build steps plus the **11-point Publish Gate** from
[Stage 2](../../docs/12-stage-2-channel-operating-system.md), filled for A1. A blank, reusable
version is in [templates/publish-gate-checklist](../templates/publish-gate-checklist.md).

## Ordered build steps (with effort estimates)

| # | Step | Artifact | Tool | First-build | At scale |
|---|---|---|---|---|---|
| 1 | Approve idea brief | [01](01-idea-brief.md) | — | 2 min | 1 min |
| 2 | Approve script + QA | [02](02-script.md) | — | 10 min | 5 min |
| 3 | Generate character assets (CHIEF, PIP + expressions) | [manifest](04-asset-manifest.md), [chief](../characters/chief.md), [pip](../characters/pip.md) | [Image gen](../tools/image-generator-usage.md) | 25 min | reuse |
| 4 | Generate backgrounds + props | [manifest](04-asset-manifest.md) | Image gen | 15 min | ~5 min |
| 5 | Render 8 shots | [storyboard](03-storyboard.md), [anim spec](05-animation-spec.md) | [Anijam](../tools/anijam-usage.md) | 20 min | 12 min |
| 6 | Add music + SFX + silence | [audio](06-audio-package.md) | Music/SFX lib | 8 min | 4 min |
| 7 | Assemble, caption(optional), verify loop seam | [editing spec](07-editing-spec.md) | Editor | 8 min | 5 min |
| 8 | Run Publish Gate (below) | this doc | — | 4 min | 3 min |
| 9 | Metadata + thumbnail | [publish package](08-publish-package.md) | Image gen / [n8n](../tools/n8n-publishing.md) | 6 min | 3 min |
| 10 | Schedule / publish | [publish package](08-publish-package.md) | [n8n](../tools/n8n-publishing.md) | 2 min | 1 min |

**First-build total ≈ 100 min** (front-loaded by new launch assets) → **~35–40 min at scale** once
CHIEF/PIP/props/SFX become reuse — consistent with the [Stage 2](../../docs/12-stage-2-channel-operating-system.md) target.

## Batch opportunities
Steps 3–4 (asset gen), 6 (audio), and 9 (metadata) are batchable across the weekly slate per the
[daily workflow](../../docs/30-daily-workflow.md) assembly-line rule.

## 11-Point Publish Gate (A1)

| # | Gate | Criterion | Status |
|---|---|---|---|
| 1 | Script | Every beat serves a traceable objective; QA 10/10 | ✅ |
| 2 | Comedy | CM-C2 Overconfidence present, dominant, lands | ✅ |
| 3 | Animation | Style-guide consistent; snappy; readable silhouettes | ⬜ verify on render |
| 4 | Timing | 25–40 s ✔ (~32 s); hook 0–2 s ✔; twist 27–31 s ✔ | ✅ |
| 5 | Visual clarity | Mute-readable; seed visible but not obvious | ✅ |
| 6 | Brand consistency | CHIEF/PIP match model sheets; palette exact | ⬜ verify on render |
| 7 | Voice | N/A (0 spoken words) — intentionally mute-first | ✅ (N/A) |
| 8 | Audio | Bed + silence + slam-back mixed to spec; ~-14 LUFS | ⬜ verify on mix |
| 9 | Retention | Proj. 3 s ≥70%, completion ≥45%; silence holds to twist | ✅ (design) |
| 10 | Metadata | Title/desc/hashtags/thumbnail ready + advertiser-safe | ✅ |
| 11 | Originality/Safety | Original assets, no lifted IP/music, no gore | ✅ |

**Rule:** one failure blocks publishing. Items marked ⬜ are the three that can only be confirmed on
the actual render/mix — they are the [two human roles'](../../docs/30-daily-workflow.md) sign-off
(**animation QC** → gates 3 & 6; **punchline editor** already cleared gates 1–2).

## Sign-off
- [ ] Punchline editor approves the twist beat (gate 1–2).
- [ ] Animation QC approves consistency + loop seam (gates 3, 6).
- [ ] Audio pass approved (gate 8).
- [ ] Gate 11/11 → **PUBLISH**.
