# Stage 4 — Infinite Idea Generator

## Purpose
Turn the intelligence system into a **ranked, unlimited pipeline of production-ready idea briefs** by querying the [Content Matrix](../intelligence/08-content-matrix.md). No brainstorming — every idea is computed and traceable.

## Inputs
- A **Business Goal** (Reach, Loyalty, Engagement, Completion, or Replay).
- The locked intelligence layer ([Libraries 7](../intelligence/07-virality-intelligence-database.md) & [8](../intelligence/08-content-matrix.md)).

## Outputs
- A ranked queue of idea briefs, each with its full decision path, compatibility, confidence, evidence, and priority.

## Two modes

| Mode | Combinations | Role |
|---|---|---|
| **A — Deterministic** | Highest-scoring, high-confidence | Default production queue |
| **B — Exploration** | Medium/low-confidence | Labelled experiments, each stating a hypothesis; ~1 per 5 Mode A |

## Brief structure
`Goal → Behavior → Pattern → Scenario → Comedy → Twist → Formula → Premise (1–2 sentences) → Expected Outcome → Compatibility → Confidence → Priority`

Briefs contain **no scripts or full stories** — only production-ready blueprints.

## Internal logic
Runs the Content Matrix funnel greedily with backtracking: resolve behavior from goal, then select one pattern → scenario → comedy → one twist core, bind the fixed formula, validate against constraints, and rank by Final Score.

## Demonstrated output (top of default queue)

| # | Goal | Pattern | Scenario | Comedy | Twist | Conf | Score |
|---|---|---|---|---|---|---|---|
| **A1** | Reach | NP1 Comeuppance | SC1 Authority | Overconfidence | Instant Karma | H | **9.2** |
| A2 | Reach | NP2 Underdog | SC3 Competition | Escalation | Role Reversal | H | 9.0 |
| A3 | Reach | NP3 Overreach | SC3 Competition | Overconfidence | False Victory | H | 8.9 |

*(A1–A12 deterministic + B1–B6 exploration were generated; A1 is the first production item.)*

## How it stays infinite
Change the input goal (and rotate scenarios, respecting a freshness log) → `matrix.select(goal)` returns the next-best untried valid combination. The goal × pattern × scenario × compatible comedy/twist space yields thousands of ranked, valid briefs.

## Dependencies
[Library 7](../intelligence/07-virality-intelligence-database.md), [Library 8](../intelligence/08-content-matrix.md); operates within [Stage 2](12-stage-2-channel-operating-system.md) rules.

## How it connects to other stages
The top-ranked brief is the immutable input to [Stage 5 — Script Compiler](14-stage-5-script-compiler.md).

## Expected deliverables
Ranked Mode A queue + labelled Mode B experiments + an operating guide.

## Success criteria
- Every idea traces to the Content Matrix.
- Another agent reproduces the same idea from the same inputs.
- No random brainstorming.
