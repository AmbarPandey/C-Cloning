# System Architecture

C-Cloning is a **layered pipeline**. Each layer transforms the output of the previous one, moving from raw competitor intelligence to a published video. The defining property is **determinism**: given the same inputs, the system produces the same outputs, and every output is traceable back to evidence.

## The four macro-layers

```mermaid
flowchart LR
    subgraph FOUND[Foundations]
      S1[Stage 1<br/>Competitor Intel]
      S15[Stage 1.5<br/>Business Decisions]
      S2[Stage 2<br/>Operating System]
    end
    subgraph KNOW[Knowledge Layer]
      L1[L1 Formula]
      L2[L2 Comedy]
      L3[L3 Twist]
      L4[L4 Scenario]
      L5[L5 Psychology]
      L6[L6 Pattern]
    end
    subgraph INTEL[Intelligence + Computation]
      L7[L7 Virality DB]
      L8[L8 Content Matrix]
    end
    subgraph PROD[Generation + Production]
      S4[S4 Idea Generator]
      S5[S5 Script Compiler]
      S6[S6 Production Compiler]
    end

    FOUND --> KNOW --> INTEL --> PROD --> OUT[Published Short]
    OUT -. analytics .-> L7
```

## Layer responsibilities

| Layer | Answers the question | Key documents |
|---|---|---|
| **Foundations** | What are competitors doing, what should we build, and how do we operate? | [Stage 1](10-stage-1-competitor-intelligence.md), [1.5](11-stage-1_5-business-decisions.md), [2](12-stage-2-channel-operating-system.md) |
| **Knowledge** | *Why* does viral animated comedy work? | [Libraries 1–6](../intelligence/) |
| **Intelligence + Computation** | How is that knowledge stored, connected, scored, and combined? | [Library 7](../intelligence/07-virality-intelligence-database.md), [Library 8](../intelligence/08-content-matrix.md) |
| **Generation + Production** | How do we compile knowledge into ideas → scripts → assets? | [Stages 4](13-stage-4-idea-generator.md), [5](14-stage-5-script-compiler.md), [6](15-stage-6-production-compiler.md) |

## Data flow (end to end)

```mermaid
flowchart TD
    G[Business Goal] --> M[Content Matrix query]
    M --> IDEA[Ranked Idea Brief<br/>Goal→Behavior→Pattern→Scenario→Comedy→Twist→Formula]
    IDEA --> SCRIPT[Compiled Script<br/>beat sheet + scene table]
    SCRIPT --> PKG[Production Package<br/>storyboard + assets + audio + edit spec]
    PKG --> RENDER[AI-assisted render + human QC]
    RENDER --> PUBLISH[Publish Short]
    PUBLISH --> DATA[Analytics]
    DATA --> UPDATE[Update scores + confidence in Library 7]
    UPDATE --> M
```

## Design principles

1. **Separation of knowledge and computation.** Libraries 1–6 hold *knowledge*; Library 7 *organizes* it; Library 8 *computes* with it. This keeps knowledge stable while generation evolves.
2. **Determinism with traceability.** Every idea carries its full decision path, compatibility scores, confidence, and evidence tags.
3. **Constraint enforcement.** Known failure modes are encoded as hard constraints so the system cannot repeat mistakes.
4. **Confidence as a first-class value.** Uncertainty is never hidden; it is a multiplier that ranks unproven combinations lower and flags them for validation.
5. **Feedback convergence.** Real analytics upgrade inferred assumptions toward observed truth over time.

## The dependency graph

See [`diagrams/dependency-graph.md`](../diagrams/dependency-graph.md) for the full node/edge dependency graph, and [`diagrams/architecture.md`](../diagrams/architecture.md) for the layered architecture diagram.

## Layer deep-dives
- [Knowledge Layer](05-knowledge-layer.md)
- [Generation Layer](06-generation-layer.md)
- [Production Layer](07-production-layer.md)
