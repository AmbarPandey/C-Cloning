# Documentation Index

Complete map of every document in the C-Cloning repository.

## Project foundations
| # | Document | Purpose |
|---|---|---|
| 01 | [Project Vision](01-project-vision.md) | Why the project exists; mission & vision |
| 02 | [Objectives](02-objectives.md) | Concrete, measurable goals |
| 03 | [Locked Roadmap](03-locked-roadmap.md) | The immutable execution order |

## Architecture
| # | Document | Purpose |
|---|---|---|
| 04 | [System Architecture](04-system-architecture.md) | End-to-end technical design |
| 05 | [Knowledge Layer](05-knowledge-layer.md) | How discovered knowledge is structured |
| 06 | [Generation Layer](06-generation-layer.md) | How ideas → scripts are produced |
| 07 | [Production Layer](07-production-layer.md) | How scripts → assets are produced |

## Stage documentation
| # | Document | Purpose |
|---|---|---|
| 10 | [Stage 1 — Competitor Intelligence](10-stage-1-competitor-intelligence.md) | Reverse engineering |
| 11 | [Stage 1.5 — Business Decisions](11-stage-1_5-business-decisions.md) | Founder-level strategy |
| 12 | [Stage 2 — Channel Operating System](12-stage-2-channel-operating-system.md) | Daily SOPs |
| 13 | [Stage 4 — Infinite Idea Generator](13-stage-4-idea-generator.md) | Deterministic idea pipeline |
| 14 | [Stage 5 — Script Compiler](14-stage-5-script-compiler.md) | Idea → script |
| 15 | [Stage 6 — Production Compiler](15-stage-6-production-compiler.md) | Script → production package |

## Intelligence libraries
See [`intelligence/README.md`](../intelligence/README.md) for the full library index (Libraries 1–8).

## Business & governance
| # | Document | Purpose |
|---|---|---|
| 20 | [Business Strategy](20-business-strategy.md) | Model, positioning, monetization |
| 21 | [Decision Log](21-decision-log.md) | Every major decision + rationale |

## Operations
| # | Document | Purpose |
|---|---|---|
| 30 | [Daily Workflow](30-daily-workflow.md) | How to operate the system today |
| 31 | [Future Runtime Workflow](31-future-runtime-workflow.md) | The automated future pipeline |
| 32 | [Future Expansion](32-future-expansion.md) | Scaling roadmap (Phase 2+) |

## Reference
| # | Document | Purpose |
|---|---|---|
| 40 | [Glossary](40-glossary.md) | Definitions of every term |
| 41 | [FAQ](41-faq.md) | Common questions |

## Diagrams
See [`diagrams/README.md`](../diagrams/README.md) for all architecture and dependency diagrams.

## Prompts
See [`prompts/README.md`](../prompts/README.md) for the reusable stage prompt contracts.

## Production (first-video artifacts)
See [`production/README.md`](../production/README.md) for the concrete, filled production
artifacts — character model sheets, the complete [Idea A1 package](../production/A1-first-video/README.md)
(script → storyboard → assets → audio → edit → publish), reusable templates, and tool usage guides.

## Design standards — the Identity Core
The **Identity Core** lives in [`production/design/`](../production/design/README.md) — two locked root
documents every creative asset inherits from:
- [`BRAND_BIBLE.md`](../production/design/BRAND_BIBLE.md) — *who the channel is*: purpose, mission,
  vision, values, personality, audience, emotional design, storytelling philosophy, content pillars,
  brand recognition, voice, and the creative decision framework.
- [`VISUAL_IDENTITY_LOCK.md`](../production/design/VISUAL_IDENTITY_LOCK.md) — *how everything looks*:
  the locked visual language (shape, line, color, lighting, composition, rendering, brand-recognition
  and consistency rules + a pre-approval quality checklist).

Nothing visual is created without the Lock; nothing strategic without the Bible.

Built on the Identity Core:
- [`CHARACTER_BIBLE.md`](../production/design/CHARACTER_BIBLE.md) — the permanent **character system**
  (taxonomy, lifecycle, asset/naming/prompt standards, validation) + the full **PIP** profile and a
  reusable future-character template. Implemented by the model sheets in
  [`production/characters/`](../production/characters/README.md).
- [`EXPRESSION_LIBRARY.md`](../production/design/EXPRESSION_LIBRARY.md) — the canonical **emotional
  language**: emotion taxonomy + expression-name vocabulary, three intensity levels, facial-acting
  standards, per-character overrides, and expression asset IDs. Generation picks an expression from
  here instead of inventing one.
- [`POSE_LIBRARY.md`](../production/design/POSE_LIBRARY.md) — the canonical **body-language system**:
  pose taxonomy + pose-name vocabulary, three intensity levels, universal body-language rules,
  pose+expression pairing, per-character overrides, and pose asset IDs. The Expression Library explains
  the face; the Pose Library explains the body.
- [`PROP_LIBRARY.md`](../production/design/PROP_LIBRARY.md) — the canonical **object system**: prop
  taxonomy + classification, object-design standards, character ownership of objects, interaction rules,
  and prop asset IDs. Generation picks a prop from here instead of inventing objects.
- [`ENVIRONMENT_BIBLE.md`](../production/design/ENVIRONMENT_BIBLE.md) — the canonical **world system**:
  environment taxonomy + classification, depth-layering, `BG_` assets, the weather & time systems,
  environmental storytelling, and a worked Parking Lot location profile. Every recurring location is a
  reusable asset; scenes pick a location from here instead of inventing a background.
- [`CAMERA_CINEMATOGRAPHY_BIBLE.md`](../production/design/CAMERA_CINEMATOGRAPHY_BIBLE.md) — the canonical
  **visual storytelling language**: shot-type + camera-movement taxonomies, composition extensions, a
  compositional lens language, shot sequencing/coverage, camera-to-subject framing, and a shot-descriptor
  notation. Storyboards and shot prompts describe framing in its vocabulary instead of inventing it.

See [`production/design/README.md`](../production/design/README.md) for the full index and dependency graph.
