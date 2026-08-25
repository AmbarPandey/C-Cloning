# Library 9 — Freshness Log & Idea Ledger

## Purpose

The idea funnel in [Library 8](08-content-matrix.md) is **deterministic**: given the same goal it
returns the same top-ranked combination every time. That is a feature for quality and a hazard for
variety — left unchecked it will ship the same pattern with a new backdrop forever.

This log is the funnel's memory. It records what has already been spent so the constraint engine can
exclude it. Two hard rules depend on it:

> **F-1** A `pattern × scenario` pair may not be reused.
> **F-2** Scenario families and twist cores must rotate; no axis value may dominate a run of episodes.

**Update this file in the same commit as the package.** A package that does not appear here has not
been through the funnel, whatever its header claims.

---

## Idea ledger

Idea numbers are a **continuous sequence** and are deliberately *not* tied to video numbers — `v5`
was a Mode B exploration and took `B1`, which is why `v6` is `A5` and not `A6`.

| Video | Idea | Mode | Format | Title | Status |
|---|---|---|---|---|---|
| v1 | `A1` | A | Shorts | The Wrong Scooter | shipped |
| v2 | `A2` | A | Shorts | The Victory Lap | shipped |
| v3 | `A3` | A | Shorts | One Block Too Many | shipped |
| v4 | `A4` | A | Shorts | The Wrong Side of the Fence | shipped |
| v5 | `B1` | **B** | **Long form 1:30** | The Case of the Missing Pie | shipped |
| v6 | `A5` | A | Shorts | One Sweet, One Coin | shipped |
| v7 | `A6` | A | Shorts | The Big One | shipped |
| v8 | `A8` ⚠ | A | Shorts | The Smart Lock | shipped, metadata unverified |
| v9 | `A9` ⚠ | A | Shorts | The Last Slice | shipped, metadata unverified |
| v10 | `A10` ⚠ | A | Shorts | The Printer | shipped, metadata unverified |
| v11 | `A11` ⚠ | A | Shorts | The Express Lane | shipped, metadata unverified |
| v12 | `A12` ⚠ | A | Shorts | The Express Elevator | shipped, metadata unverified |
| v13 | `A13` ⚠ | A | Shorts | The Big Catch | shipped, metadata unverified |
| v14 | `A14` ⚠ | A | Shorts | The Sand Castle | shipped, metadata unverified |
| v15 | `A15` ⚠ | A | Shorts | The Last Dryer | shipped, metadata unverified |
| v16 | `A16` ⚠ | A | Shorts | The Book Tower | shipped, metadata unverified |
| v17 | `A17` ⚠ | A | Shorts | The Biggest Kite | shipped, metadata unverified |

⚠ **Ledger break:** `A7` was never issued. The `v8`–`v17` batch set `idea = video number`, which
skipped `A7` and destroyed the offset that `B1` created. Next Mode A idea is **`A18`**; `A7` stays
permanently unissued so the ledger and the git history keep agreeing.

**Next available:** Mode A → `A18` · Mode B → `B2`.

---

## Combination register (F-1)

Every `pattern × scenario` pair ever spent. A new package must not match a row here.

| Video | Pattern | Scenario | Comedy | Twist | Score | Verified |
|---|---|---|---|---|---|---|
| v1 | `NP1` Comeuppance | `SC1` Authority | `CM-C2` Overconfidence Collapse | `TW3` Instant Karma | 9.2 | ✅ |
| v2 | `NP2` Underdog Reversal | `SC3` Competition | `CM-E1` Escalation | `TW1` Role Reversal | 9.0 | ✅ |
| v3 | `NP3` Overreach Collapse | `SC3` Competition | `CM-C2` Overconfidence Collapse | `TW4` False Victory | 8.9 | ✅ |
| v4 | `NP1` Comeuppance | `SC10` Animals-as-People | `CM-B1` Irony | `TW2` Irony Reversal | 8.8 | ✅ |
| v5 | `NP4` Hidden Truth | `SC6` Crime & Justice | `CM-A2` Misdirection | `TW5` Hidden Cause + `TM3` | 5.5 | ✅ |
| v6 | `NP3` Overreach Collapse | `SC2` Service Exchange | `CM-E1` Escalation | `TW2` Irony Reversal | 8.7 | ✅ |
| v7 | `NP1` Comeuppance | `SC8` Everyday Friction | `CM-C3` Instant Karma | `TW3` Instant Karma | 8.6 | ⚠ core collapse |
| v8 | `NP3` Overreach Collapse | `SC9` Technology/Social | `CM-C4` (mislabelled) | `TW4` False Victory | 8.5 | ⚠ pair valid, core collapse |
| v9 | `NP2` Underdog Reversal | **misassigned** (`SC7` cited) | `CM-C2` (mislabelled) | `TW2` Irony Reversal | 8.4 | ❌ |
| v10 | `NP2` Underdog Reversal | **misassigned** (`SC4` cited) | `CM-C4` (mislabelled) | `TW4` False Victory | 8.5 | ❌ core collapse |
| v11 | `NP3` Overreach Collapse | **unresolved** | `CM-C3` (mislabelled) | `TW3` Instant Karma | 8.6 | ❌ |
| v12 | `NP1` Comeuppance | **unresolved** | `CM-C4` (mislabelled) | `TW2` Irony Reversal | 8.4 | ❌ |
| v13 | `NP3` Overreach Collapse | **unresolved** | `CM-C3` Instant Karma | `TW3` Instant Karma | 8.3 | ❌ core collapse |
| v14 | `NP3` Overreach Collapse | **unresolved** | `CM-C4` (mislabelled) | `TW2` Irony Reversal | 8.5 | ❌ |
| v15 | `NP3` Overreach Collapse | **unresolved** | `CM-C4` (mislabelled) | `TW3` Instant Karma | 8.4 | ❌ |
| v16 | `NP3` Overreach Collapse | **unresolved** | `CM-C4` (mislabelled) | `TW3` Instant Karma | 8.5 | ❌ |
| v17 | `NP3` Overreach Collapse | **unresolved** | `CM-C4` (mislabelled) | `TW3` Instant Karma | 8.6 | ❌ |

**unresolved** = the package cites a scenario ID that does not exist in
[Library 4](04-scenario-intelligence-library.md) at all (`SC11`, `SC13`, `SC16`, `SC17`, `SC19`,
`SC20`, `SC22`). **misassigned** = the ID exists but names a different family than the premise
actually belongs to — `v9` cites `SC7 Danger/Survival` for a restaurant scene, `v10` cites
`SC4 Family/Domestic` for an office scene. Either way the pair cannot be registered and F-1 cannot be
enforced against it. See [`BASE-AUDIT.md`](../BASE-AUDIT.md) for the proposed remapping.

> **The invented IDs were not a cosmetic error — they defeated F-1.** Because `SC11`, `SC13`, `SC16`,
> `SC17`, `SC19`, `SC20` and `SC22` are outside the register, every one of those pairs looked novel.
> Resolve them onto real families and collisions appear immediately: a laundromat, a library and a
> beach are all `SC8 Everyday Friction`, so `v15`, `v16` and `v14` all reduce to `NP3 × SC8` — the
> same pair, three times, in one batch.

---

## Rotation health (F-2)

Counted across all 17 shipped episodes.

**Narrative pattern**

| Pattern | Uses | Episodes |
|---|---|---|
| `NP3` Overreach Collapse | **9** | v3, v6, v8, v11, v13, v14, v15, v16, v17 |
| `NP1` Comeuppance | 4 | v1, v4, v7, v12 |
| `NP2` Underdog Reversal | 3 | v2, v9, v10 |
| `NP4` Hidden Truth | 1 | v5 |
| `NP5` Escalating Disaster | **0** | — |
| `NP6` Literal Trap | **0** | — |
| `NP7` Bait-and-Switch | **0** | — |
| `NP8` Ironic Backfire | **0** | — |

`NP3` carries 53% of the catalogue and 7 of the last 10 episodes. Half the pattern library has never
been used. `NP8 Ironic Backfire` is the notable gap — it is a daily-viable pattern and it is exactly
the shape most of the `v8`–`v17` premises were reaching for.

**Comedy mechanic**

| Mechanic | Uses |
|---|---|
| `CM-C4` False Victory | **7** (v8, v10, v12, v14, v15, v16, v17) |
| `CM-C2` Overconfidence Collapse | 3 (v1, v3, v9) |
| `CM-C3` Instant Karma | 3 (v7, v11, v13) |
| `CM-E1` Escalation | 2 (v2, v6) |
| `CM-A2` Misdirection · `CM-B1` Irony | 1 each (v5, v4) |
| Families A (except A2), B (except B1), D | **0** |

Family D (reaction amplifiers) has never been used, and `CM-A1 Expectation Violation` — which the
Comedy Stack marks **"Always"** — is not named in a single package.

**Twist core**

`TW3` Instant Karma **7** (v1, v7, v11, v13, v15, v16, v17) · `TW2` Irony Reversal 5 (v4, v6, v9,
v12, v14) · `TW4` False Victory 3 (v3, v8, v10) · `TW1` Role Reversal 1 (v2) · `TW5` Hidden Cause 1
(v5) · `TW6`–`TW10` **0**. `TM3 Seed Callback` is declared once (v5) despite every episode planting
seeds and closing on a loop.

**Goal / mode**

- Goal `Reach` → Behavior `Share`: **16 of 17**. Goal `Replay`: 1 (v5).
- Mode A: 16 · Mode B: 1. The rule is ~1 Mode B per 5 Mode A, so the catalogue is **short by
  roughly two explorations**.
- Format: Shorts 16 · Long form 1.

---

## Standing corrections for the next package

1. Take idea **`A18`** (or `B2` if this is the exploration slot — one is overdue).
2. Do **not** use `NP3`. Prefer `NP8 Ironic Backfire` or `NP5 Escalating Disaster`.
3. Do **not** use `CM-C4`. Name `CM-A1 Expectation Violation` as the mandatory deliver layer and pick
   a non-C-family core, or a C-family core that differs from the twist.
4. Avoid `TW3`. `TW7 Visual Transformation` and `TW8 Identity Reveal` are untouched.
5. If the premise plants a seed and loops, the goal is **`Replay`**, not `Reach` — say so, and attach
   `TM3` explicitly.
6. Verify the pair against the combination register above **before** writing a word of script.
