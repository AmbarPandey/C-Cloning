# Runtime Pipeline Diagram

The operational path from a business goal to a published, self-improving video.

```mermaid
sequenceDiagram
    participant OP as Operator
    participant M as Content Matrix (L8)
    participant G as Idea Generator (S4)
    participant SC as Script Compiler (S5)
    participant PC as Production Compiler (S6)
    participant AI as AI Render + Human QC
    participant YT as YouTube
    participant DB as Virality DB (L7)

    OP->>M: BusinessGoal
    M->>G: ranked valid combinations
    G-->>OP: ranked idea briefs (A/B modes)
    OP->>SC: approve top brief
    SC-->>OP: production-ready script (QA pass)
    OP->>PC: approve script
    PC-->>AI: production package (assets + specs)
    AI->>YT: publish (after Publish Gate)
    YT-->>DB: analytics (retention, replay, share, subs)
    DB->>M: update scores + confidence
    Note over M,DB: matrix re-ranks itself over time
```

## The loop's key property
The pipeline is a **closed loop**: outputs feed analytics, analytics update the intelligence graph, and the graph changes which ideas rank highest next — without altering any locked framework.

See also: [Future Runtime Workflow](../docs/31-future-runtime-workflow.md).
