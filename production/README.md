# Production — First-Video Artifacts

This folder contains the **concrete, executable production artifacts** for the first
Short. Where [`docs/`](../docs/) defines the *method* and [`prompts/`](../prompts/)
defines the *contracts*, this folder is the *filled output* — everything an operator
needs to actually build, review, and publish **Idea A1**.

> **Scope & governance.** These artifacts *instantiate* the locked design; they do not
> change it. Every artifact traces 1:1 back to the locked stages/libraries. Nothing here
> re-opens a locked decision (see [Locked Roadmap](../docs/03-locked-roadmap.md)).

## Layout

```
production/
├── README.md                     ← you are here
├── design/                       ← channel-wide visual standards (single source of truth)
│   ├── README.md
│   └── VISUAL_IDENTITY_LOCK.md   ← the locked visual language every asset must obey
├── characters/                   ← model sheets for the fixed cast + style guide  (fills F2)
│   ├── README.md
│   ├── cast-style-guide.md
│   ├── chief.md
│   └── pip.md
├── A1-first-video/               ← the complete, filled production package for Idea A1  (fills F7)
│   ├── README.md
│   ├── 01-idea-brief.md          ← the exact Stage 4 brief
│   ├── 02-script.md              ← the full Stage 5 script (8 scenes, scene table)
│   ├── 03-storyboard.md          ← the filled Stage 6 storyboard + per-shot render prompts
│   ├── 04-asset-manifest.md      ← every asset, tagged reusable vs new, with IDs
│   ├── 05-animation-spec.md      ← motion, camera, timing, loop spec
│   ├── 06-audio-package.md       ← VO/SFX/music/silence map + ElevenLabs settings
│   ├── 07-editing-spec.md        ← timeline, cuts, captions, loop seam
│   ├── 08-publish-package.md     ← title / description / hashtags / thumbnail  (fills F6)
│   ├── 09-scoring-worksheet.md   ← reproduces FinalScore 9.2 from the formula  (fills F1, scoped)
│   └── 10-production-checklist.md← filled 11-point Publish Gate + ordered build steps
├── templates/                    ← reusable, blank templates for every future video
│   ├── README.md
│   ├── visual-prompt-template.md ← (fills F3)
│   ├── thumbnail-spec.md         ← (fills F6)
│   ├── metadata-template.md      ← title / description / hashtag formulas  (fills F6)
│   ├── editing-timeline-template.md
│   └── publish-gate-checklist.md ← fillable 11-point gate
└── tools/                        ← how to drive the locked tool stack  (fills F4)
    ├── README.md
    ├── anijam-usage.md
    ├── elevenlabs-usage.md
    ├── image-generator-usage.md
    └── n8n-publishing.md
```

## How to produce the first video (operator quickstart)

1. Read the [Visual Identity Lock](design/VISUAL_IDENTITY_LOCK.md) (the master visual standard), then
   the [cast style guide](characters/cast-style-guide.md) and the two model sheets.
2. Generate the character + background assets using the
   [image generator guide](tools/image-generator-usage.md) and the prompts in the
   [storyboard](A1-first-video/03-storyboard.md).
3. Render the 8 scenes in [Anijam](tools/anijam-usage.md) using the
   [animation spec](A1-first-video/05-animation-spec.md).
4. Generate SFX/music (no VO for A1 — it is mute-first) per the
   [audio package](A1-first-video/06-audio-package.md) and
   [ElevenLabs guide](tools/elevenlabs-usage.md).
5. Assemble/caption/export per the [editing spec](A1-first-video/07-editing-spec.md).
6. Run the [filled Publish Gate](A1-first-video/10-production-checklist.md); fix any single
   failing item.
7. Publish using the [publish package](A1-first-video/08-publish-package.md) and the
   [n8n publishing guide](tools/n8n-publishing.md).

## Traceability

| Artifact | Locked source it instantiates |
|---|---|
| Idea brief | [Stage 4](../docs/13-stage-4-idea-generator.md) + [Idea-Generation contract](../prompts/idea-generation.md) |
| Script | [Stage 5](../docs/14-stage-5-script-compiler.md) + [Script-Compilation contract](../prompts/script-compilation.md) |
| Storyboard → editing | [Stage 6](../docs/15-stage-6-production-compiler.md) + [Production-Compilation contract](../prompts/production-compilation.md) |
| Visual style (all assets) | [Visual Identity Lock](design/VISUAL_IDENTITY_LOCK.md) → derived from [Stage 1.5 art direction](../docs/11-stage-1_5-business-decisions.md) |
| Asset IDs / reuse | [Stage 2 asset library](../docs/12-stage-2-channel-operating-system.md) |
| Publish gate | [Stage 2 Publish Gate](../docs/12-stage-2-channel-operating-system.md) |
| Tool choices | [Stage 1.5 tool stack](../docs/11-stage-1_5-business-decisions.md) · [D-20](../docs/21-decision-log.md) |
| Scoring | [Library 7](../intelligence/07-virality-intelligence-database.md) · [Library 8](../intelligence/08-content-matrix.md) |
