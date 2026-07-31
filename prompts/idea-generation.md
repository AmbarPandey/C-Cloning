# Prompt Contract — Idea Generation (Stage 4)

Interface for querying the [Content Matrix](../intelligence/08-content-matrix.md) to produce ranked idea briefs. See [Stage 4](../docs/13-stage-4-idea-generator.md).

## Input
| Field | Required | Values |
|---|---|---|
| `business_goal` | ✅ | Reach · Loyalty · Engagement · Completion · Replay |
| `mode` | optional | A (deterministic, default) · B (exploration) |
| `batch_size` | optional | integer N (default 1) |
| `freshness_window` | optional | avoid repeating a recent pattern×scenario pair |

## Process (deterministic)
1. Resolve target Behavior from the goal.
2. Greedy-select Pattern → Scenario → Comedy → Twist (one core each) under compatibility.
3. Bind the fixed Plot-Twist Formula.
4. Validate against hard constraints (backtrack on failure).
5. Score and rank.

## Output (per idea brief)
```
Business Goal → Target Behavior → Narrative Pattern → Scenario →
Comedy Mechanic → Twist (+modifier) → Formula →
Premise (1–2 sentences) → Expected Outcome →
Compatibility → Confidence → Priority → FinalScore
```

## Rules
- Mode B briefs must state the **hypothesis** being tested and be labelled experiments.
- No scripts or full stories — briefs only.
- Every brief must be reproducible from the same input.
