# Architecture Diagram

The complete layered architecture of C-Cloning, from foundations to published video and the analytics feedback loop.

```mermaid
flowchart TB
    subgraph FOUND[Foundations]
        direction LR
        S1[Stage 1<br/>Competitor Intel]
        S15[Stage 1.5<br/>Business Decisions]
        S2[Stage 2<br/>Operating System]
        S1 --> S15 --> S2
    end

    subgraph KNOW[Knowledge Layer - Libraries 1-6]
        direction LR
        L1[L1 Formula]
        L2[L2 Comedy]
        L3[L3 Twist]
        L4[L4 Scenario]
        L5[L5 Psychology]
        L6[L6 Pattern]
        L1 --> L2 --> L3 --> L4 --> L5 --> L6
    end

    subgraph INTEL[Intelligence + Computation]
        direction LR
        L7[L7 Virality DB<br/>VID-Graph]
        L8[L8 Content Matrix<br/>Funnel-Select]
        L7 --> L8
    end

    subgraph GENPROD[Generation + Production]
        direction LR
        S4[S4 Idea Generator]
        S5[S5 Script Compiler]
        S6[S6 Production Compiler]
        S4 --> S5 --> S6
    end

    FOUND --> KNOW --> INTEL --> GENPROD --> OUT[Published Short]
    OUT -. analytics update scores + confidence .-> L7

    classDef y fill:#FFD400,stroke:#1A1A1A,color:#1A1A1A;
    classDef c fill:#FF4D4D,stroke:#1A1A1A,color:#FAF7F0;
    classDef t fill:#00C2A8,stroke:#1A1A1A,color:#1A1A1A;
    class S1,S15,S2 y
    class L1,L2,L3,L4,L5,L6 t
    class L7,L8 c
    class S4,S5,S6 y
```

## Reading the diagram
- **Foundations** decide what to build and how to operate.
- **Knowledge Layer** encodes why viral comedy works.
- **Intelligence + Computation** store and combine that knowledge.
- **Generation + Production** compile combinations into videos.
- The dotted arrow is the **self-improving feedback loop**: real analytics upgrade the graph's scores and confidence.

See also: [System Architecture](../docs/04-system-architecture.md).
