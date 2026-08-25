# Characters — Fixed Cast

> **Governed by the [Character Bible](../design/CHARACTER_BIBLE.md).** That document defines the
> channel-wide character *system* (taxonomy, lifecycle, asset/naming/prompt standards, validation) and
> holds each character's full narrative profile. The model sheets in this folder are its
> **implementations** — the exact locked visual spec per character. On a character-system question, the
> Character Bible wins; the model sheets own the precise hexes/measurements.

Model sheets and the shared visual grammar for the recurring cast. These artifacts fill the
gap where [Stage 2](../../docs/12-stage-2-channel-operating-system.md) mandated character
*consistency* and a versioning convention but no visual reference existed.

> **Consistency is the brand.** Per [Stage 1](../../docs/10-stage-1-competitor-intelligence.md),
> a recurring, lovable cast is one of the four proven engines. Every video reuses these exact
> designs; do not redraw them per video — reuse the locked reference art.

## Cast roster (Phase 1)

| ID | Name | Role archetype | First appearance |
|---|---|---|---|
| `CHAR_CHIEF_v1` | **CHIEF** | Pompous authority figure (antagonist) | [Idea A1](../A1-first-video/README.md) |
| `CHAR_PIP_v1` | **PIP** | Small, kind underdog (protagonist) | [Idea A1](../A1-first-video/README.md) |

Two more fixed cast members (a neutral bystander and a rival) are reserved for later videos and
are **not** required for the first video.

## Files
- [Cast style guide](cast-style-guide.md) — the shared art rules every character obeys.
- [CHIEF model sheet](chief.md)
- [PIP model sheet](pip.md)

## Naming & versioning
Follows the [Stage 2](../../docs/12-stage-2-channel-operating-system.md) convention:
`CHAR_[NAME]_v#` for the character; expression packs are `CHAR_[NAME]_expr_[name]`;
turnaround poses are `CHAR_[NAME]_pose_[name]`. Bump the version **only** if the locked
silhouette changes (it should not in Phase 1).
