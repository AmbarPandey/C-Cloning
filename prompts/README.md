# Prompt Contracts

Reusable **input/output contracts** for the stages that are run repeatedly (the generation and production loop). These are not the original design prompts — they are the distilled, permanent interfaces each stage exposes, so the pipeline can be operated (or automated) consistently.

| Contract | Stage | Purpose |
|---|---|---|
| [idea-generation.md](idea-generation.md) | [Stage 4](../docs/13-stage-4-idea-generator.md) | Goal → ranked idea briefs |
| [script-compilation.md](script-compilation.md) | [Stage 5](../docs/14-stage-5-script-compiler.md) | Idea brief → production-ready script |
| [production-compilation.md](production-compilation.md) | [Stage 6](../docs/15-stage-6-production-compiler.md) | Script → production package |

## Contract rules (apply to all)
- Inputs from locked stages are **immutable**; report issues, never silently fix.
- Every output must be **traceable** to Libraries 1–8 with evidence + confidence.
- Never re-open a [locked decision](../docs/03-locked-roadmap.md).
- Never brainstorm; always query the intelligence system.
