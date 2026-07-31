# Runtime Architecture (v1.0)

## Purpose

The Master Runtime architecture defines the **fixed module chain** that executes the
C-Cloning pipeline. Version 1.0 established the module model, the execution order, and the
fail-closed lifecycle. (The context-loading strategy was later refined in
[v1.1](Runtime_Architecture_v1.1.md).)

## Architectural model

The runtime is a **linear chain of single-responsibility modules**. Each module validates
its inputs, performs exactly one job, produces a contracted output, and transfers control
forward only on success.

```mermaid
flowchart TD
    INV[Runtime Invocation] --> M1[Module 1<br/>Runtime Initialization]
    M1 -->|READY| M2[Module 2<br/>Repository Context Loader]
    M2 -->|Context Package| M3[Module 3<br/>Decision Engine]
    M3 -->|Execution Objective| MG[Generation / Compilation Modules]
    MG --> OUT[Runtime Output]

    M1 -. failure .-> HALT[Halt + Report]
    M2 -. failure .-> HALT
    M3 -. failure .-> HALT

    classDef built fill:#FFD400,stroke:#1A1A1A,color:#1A1A1A;
    classDef planned fill:#EEE,stroke:#999,color:#555,stroke-dasharray: 4 3;
    class M1 built
    class M2,M3,MG planned
```

## Responsibilities of the runtime as a whole

- Validate and initialize the execution environment.
- Prepare the runtime context from authoritative repository documentation.
- Determine the execution objective (Decision Engine).
- Orchestrate the locked pipeline stages in the correct order.
- Halt on any failure and return a report.
- Preserve determinism and traceability end to end.

## Dependencies

The runtime depends on the **locked project architecture** as its authoritative knowledge
base. It does not function without a verified repository, a documentation branch/root, and
the locked roadmap and architecture documents.

```mermaid
flowchart LR
    RT[Master Runtime] --> REPO[Verified Repository]
    RT --> DOCS[Documentation Root]
    RT --> ROADMAP[Locked Roadmap]
    RT --> ARCH[Locked System Architecture]
```

## Execution order (v1.0)

| Order | Module | Responsibility | Output |
|---|---|---|---|
| 1 | Runtime Initialization | Validate environment, initialize state | Initialization Report → `READY` |
| 2 | Repository Context Loader | Load required knowledge for the execution | Runtime Context Package |
| 3 | Decision Engine | Determine the execution objective | Selected objective |
| 4+ | Generation / Compilation | Execute the locked pipeline stage | Pipeline output |

## Module contracts (summary)

Each module obeys a common contract shape: **Inputs → Validation → Single Responsibility →
Contracted Output → Control Transfer (on success only)**. Full per-module contracts are in
the [Runtime Module Overview](Runtime_Module_Overview.md).

## Failure philosophy

The runtime is **fail-closed**. Any module that fails validation terminates execution
immediately and returns a failure report. It does not attempt recovery, does not substitute
missing inputs, and does not pass partial results forward. A partially initialized runtime
is treated as a failed runtime.

## Repository philosophy

Repository documentation is the **single source of truth**. The runtime reads authoritative
documents, preserves their terminology, and never rewrites or overrides them. Locked
decisions are immutable; only intelligence-layer scores/confidence may change, and only from
real analytics.

## Runtime lifecycle (v1.0)

```mermaid
stateDiagram-v2
    [*] --> INITIALIZING
    INITIALIZING --> READY: validation passed
    INITIALIZING --> FAILED: validation failed
    READY --> CONTEXT_LOADED: context prepared
    CONTEXT_LOADED --> DECIDED: objective selected
    DECIDED --> EXECUTING: pipeline running
    EXECUTING --> COMPLETE: output produced
    FAILED --> [*]
    COMPLETE --> [*]
```

## Runtime data flow

See [Runtime Data Flow](Runtime_Data_Flow.md) for the detailed context and control-flow
diagrams.

## Version note

v1.0 required an execution objective early in the chain. This created a circular dependency
between initialization and objective selection. The refined
[Architecture v1.1](Runtime_Architecture_v1.1.md) resolves this by separating **permanent
context loading** from **task-specific context expansion**.
