# Runtime Data Flow

## Purpose

This document describes how **context** and **control** move through the Master Runtime, and
how runtime execution connects to the locked C-Cloning pipeline data flow.

## Two flows: control and context

The runtime has two intertwined flows:

- **Control flow** — which module is active, and when control transfers.
- **Context flow** — what knowledge is loaded, and when it is loaded.

```mermaid
flowchart TD
    subgraph CONTROL[Control Flow]
      I[Invocation] --> M1[Module 1: Initialization]
      M1 --> M2[Module 2.1: Context Loader]
      M2 --> M3[Module 3: Decision Engine]
      M3 --> MG[Generation / Compilation]
    end

    subgraph CONTEXT[Context Flow]
      BASE[Base Runtime Context<br/>vision, roadmap, index, architecture, config]
      EXP[Expanded Context<br/>stage docs, libraries, briefs, scripts]
    end

    M2 -. builds .-> BASE
    M3 -. triggers .-> EXP
    BASE --> MG
    EXP --> MG

    classDef planned fill:#EEE,stroke:#999,color:#555,stroke-dasharray: 4 3;
    class M3,MG,EXP planned
```

## Control transfer contract

Control moves forward **only** when the active module completes successfully and emits its
contracted output. Any failure diverts to a terminal failure report.

```mermaid
sequenceDiagram
    participant INV as Invocation
    participant M1 as Module 1
    participant M2 as Module 2.1
    participant M3 as Decision Engine
    INV->>M1: Runtime State, Project ID, Repo Connection
    M1-->>M2: Initialization Report (READY)
    M2-->>M3: Base Runtime Context + Expansion Plan
    Note over M3: selects Execution Objective
    M3-->>M3: execute Context Expansion Plan
    Note over M1,M3: any validation failure => Halt + Failure Report
```

## Context loading data flow (v1.1)

```mermaid
flowchart LR
    CFG[Runtime Configuration] --> LOAD[Load permanent context]
    LOAD --> BASE[Base Runtime Context]
    BASE --> PLAN[Context Expansion Plan]
    PLAN -->|deferred| DECIDE{Objective chosen?}
    DECIDE -- yes --> PULL[Pull only required docs]
    DECIDE -- no --> WAIT[Remain deferred]
```

## Connection to the locked pipeline data flow

Once context is prepared and an objective is chosen, the runtime drives the **locked**
C-Cloning data flow. The runtime orchestrates this flow; it does not alter it.

```mermaid
flowchart TD
    G[Business Goal] --> M[Content Matrix query]
    M --> IDEA[Ranked Idea Brief]
    IDEA --> SCRIPT[Compiled Script]
    SCRIPT --> PKG[Production Package]
    PKG --> RENDER[AI-assisted render + human QC]
    RENDER --> PUBLISH[Publish Short]
    PUBLISH --> DATA[Analytics]
    DATA --> UPDATE[Update scores + confidence in Library 7]
    UPDATE --> M
```

> The feedback edge (analytics → Library 7 scores/confidence) is the **only** mechanism by
> which the runtime's execution influences the knowledge base — and it changes scores and
> confidence only, never locked frameworks.

## Data artifacts by module

| Module | Consumes | Produces |
|---|---|---|
| Runtime Initialization | Runtime invocation, project ID, repo connection | Initialization Report, `READY` state |
| Repository Context Loader | Runtime configuration, repository connection | Base Runtime Context, Context Expansion Plan |
| Decision Engine | Base Runtime Context | Selected Execution Objective |
| Generation / Compilation | Expanded context + prior stage output | Idea Brief / Script / Production Package |

## Related reading
- [Runtime Architecture v1.1](Runtime_Architecture_v1.1.md)
- [Runtime Module Overview](Runtime_Module_Overview.md)
- [System Architecture data flow (knowledge base)](../../docs/04-system-architecture.md)
