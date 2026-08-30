# Dependency Graph

What each stage/library **depends on** (arrows point from a dependency to the thing that consumes it).

```mermaid
flowchart TD
    S1[Stage 1<br/>Competitor Intel]
    S15[Stage 1.5<br/>Business Decisions]
    S2[Stage 2<br/>Operating System]

    L1[L1 Formula]
    L2[L2 Comedy]
    L3[L3 Twist]
    L4[L4 Scenario]
    L5[L5 Psychology]
    L6[L6 Pattern]
    L7[L7 Virality DB]
    L8[L8 Content Matrix]

    S4[Stage 4 Ideas]
    S5[Stage 5 Script]
    S6[Stage 6 Production]

    S1 --> S15 --> S2
    S1 --> L1 & L2 & L3 & L4 & L5 & L6

    L1 --> L6
    L2 --> L3
    L2 --> L6
    L3 --> L6
    L4 --> L6
    L5 --> L6

    L1 --> L7
    L2 --> L7
    L3 --> L7
    L4 --> L7
    L5 --> L7
    L6 --> L7
    L7 --> L8

    S2 --> S4
    L8 --> S4 --> S5 --> S6
    S6 -. feedback .-> L7
```

## Dependency table

| Component | Depends on | Consumed by |
|---|---|---|
| Stage 1 | — | Stage 1.5, Libraries 1–6 |
| Stage 1.5 | Stage 1 | Stage 2 |
| Stage 2 | Stages 1, 1.5 | Stage 4 (operating rules) |
| Library 1 (Formula) | Stage 1 | L6, L7 |
| Library 2 (Comedy) | Stage 1 | L3, L6, L7 |
| Library 3 (Twist) | L2 | L6, L7 |
| Library 4 (Scenario) | Stage 1 | L6, L7 |
| Library 5 (Psychology) | Stage 1 | L6, L7 |
| Library 6 (Pattern) | L1–L5 | L7 |
| Library 7 (Virality DB) | L1–L6 | L8 |
| Library 8 (Content Matrix) | L7 | Stage 4 |
| Stage 4 (Ideas) | L8, Stage 2 | Stage 5 |
| Stage 5 (Script) | Stage 4, L1–L8 | Stage 6 |
| Stage 6 (Production) | Stage 5, Stage 2 | Publish → feedback to L7 |

See also: [Locked Roadmap](../docs/03-locked-roadmap.md).
