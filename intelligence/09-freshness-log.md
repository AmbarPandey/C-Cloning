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
| v18 | `A18` | A | Shorts | The Last Drop | shipped |
| v19 | `A19` | A | Shorts | The Deep End | shipped |
| v20 | `A20` | A | Shorts | The Inspection | shipped |
| v21 | `A21` | A | Shorts | The Upgrade | shipped |
| v22 | `B2` | **B** | Shorts | The Shortcut | shipped |
| v23 | `B3` | **B** | Shorts | The Evidence | shipped |
| v24 | `A22` | A | Shorts | The Fast Lane | shipped |
| v25 | `A23` | A | Shorts | The Tie-Breaker | shipped |
| v26 | `A24` | A | Shorts | The Ferry | shipped |
| v27 | `A25` | A | Shorts | The Chock | shipped |

⚠ **Ledger break:** `A7` was never issued. The `v8`–`v17` batch set `idea = video number`, which
skipped `A7` and destroyed the offset that `B1` created. Next Mode A idea is **`A18`**; `A7` stays
permanently unissued so the ledger and the git history keep agreeing.

**Next available:** Mode A → `A26` · Mode B → `B4`.

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
| v18 | `NP5` Escalating Disaster | `SC4` Family/Domestic | `CM-A3` Delayed Realization | `TW10` Chain-Reaction Payoff | 7.2 | ✅ |
| v19 | `NP8` Ironic Backfire | `SC7` Danger/Survival | `CM-B3` Absurd Logic | `TW9` Literal Outcome | 6.1 | ✅ |
| v20 | `NP2` Underdog Reversal | `SC1` Authority | `CM-C1` Role Reversal | `TW4` False Victory | 8.1 | ✅ |
| v21 | `NP1` Comeuppance | `SC2` Service Exchange | `CM-C2` Overconfidence Collapse | `TW7` Visual Transformation | 7.9 | ✅ |
| v22 | `NP7` Bait-and-Switch | `SC10` Animals-as-People | `CM-A2` Misdirection | `TW6` Perspective Shift + `TM3` | 7.1 | ✅ |
| v23 | `NP5` Escalating Disaster | `SC6` Crime & Justice | `CM-B1` Irony | `TW5` Hidden Cause + `TM3` | 6.0 | ✅ |
| v24 | `NP2` Underdog Reversal | `SC8` Everyday Friction | `CM-E1` Escalation | `TW1` Role Reversal | 8.8 | ✅ |
| v25 | `NP1` Comeuppance | `SC3` Competition | `CM-E2` Chain Reaction | `TW2` Irony Reversal | 8.4 | ✅ |
| v26 | `NP8` Ironic Backfire | `SC10` Animals-as-People | `CM-C2` Overconfidence Collapse | `TW1` Role Reversal | 8.7 | ✅ |
| v27 | `NP2` Underdog Reversal | `SC2` Service Exchange | `CM-E1` Escalation | `TW4` False Victory | 9.0 | ✅ |

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


---

## Batch note — v18–v25 (added with those packages)

Eight packages were computed together to repair the rotation failure recorded above, where `NP3` held
**9 of 17** episodes and half the pattern library had never been used.

**Nodes opened for the first time in this batch:** `NP5` Escalating Disaster · `NP7` Bait-and-Switch ·
`NP8` Ironic Backfire · `SC4` Family/Domestic · `SC7` Danger/Survival · `CM-A3` Delayed Realization ·
`CM-B3` Absurd Logic · `CM-C1` Role Reversal · `CM-E2` Chain Reaction · `TW6` Perspective Shift ·
`TW7` Visual Transformation · `TW9` Literal Outcome · `TW10` Chain-Reaction Payoff. **Thirteen.**

**`NP3` was rested completely** — it appears in none of the eight.

**Scenario spread:** all eight use a **different** scenario (`SC4`, `SC7`, `SC1`, `SC2`, `SC10`, `SC6`,
`SC8`, `SC3`), so no `pattern × scenario` pair repeats inside the batch or against v1–v17.

**Twist spread:** all eight use a **different** twist core (`TW10`, `TW9`, `TW4`, `TW7`, `TW6`, `TW5`,
`TW1`, `TW2`).

**Mode B ratio restored.** The catalogue held 16 Mode A to 1 Mode B. Adding `B2` (v22) and `B3` (v23)
brings it to 22 A : 3 B — approximately the 1-in-5 the generator specifies. Both state a hypothesis and a
kill condition.

**Score profile, and why it is lower than v1–v17.** Opening unused regions of the matrix costs points
honestly, because the unproven tiers carry Medium confidence and higher difficulty:

| Video | Score | Confidence_avg |
|---|---|---|
| v24 | 8.8 | 1.000 |
| v25 | 8.4 | 0.925 |
| v20 | 8.1 | 0.925 |
| v21 | 7.9 | 0.925 |
| v18 | 7.2 | 0.850 |
| v22 | 7.1 | 0.850 |
| v19 | 6.1 | 0.775 |
| v23 | 6.0 | 0.775 |

No edge was rounded up to flatter a score. `v19`'s `CM-B3↔TW9` and `v23`'s `NP5↔SC6` are both recorded at
**4/5** because they are genuinely loose joins. `v24` is the full-confidence workhorse that funds the batch.

**Comedy core ≠ twist core** was verified on all eight — the defect found on `v7`, `v8`, `v10` and `v13`
does not recur.

**Ledger note:** `A7` remains permanently unissued. This batch continues the sequence from `A18`, and
because `v22` and `v23` took `B2` and `B3`, the video and idea numbers are offset again from `v24` onward —
which is the intended behaviour, not a fault.


---

## Batch note — v26–v27

Built to the v24/v25 profile after those two were identified as the strongest of the v18–v25 batch. Both are
**Confidence 1.00 with all four chain edges at 5/5** — the first time two consecutive episodes have achieved
that.

| Video | Pair | Score | Confidence | Weakest edge |
|---|---|---|---|---|
| v26 | `NP8 × SC10` | 8.7 | 1.00 | none (all 5/5) |
| v27 | `NP2 × SC2` | 9.0 | 1.00 | none (all 5/5) |

**v27's 9.0 is the highest score since v2**, from the least exotic combination available. That confirms the
v24 lesson: score comes from **proven nodes plus a legible mechanism**, not from novelty. v19 (6.1) and v23
(6.0) are the counter-evidence.

### ⚠ Structural finding — F-1 runway is exhausted on `NP1`

Measured against this register, **`NP1 Comeuppance` now has no unused pairing left against any
daily-or-support scenario** (`SC1`, `SC2`, `SC3`, `SC8`, `SC10` are all spent). Remaining
high-confidence fresh pairs after v27:

| Pattern | Free daily/support scenarios |
|---|---|
| `NP1` | **none — exhausted** |
| `NP2` | `SC10` |
| `NP3` | `SC1`, `SC8`, `SC10` *(but `NP3` holds 9 uses and is on rotation rest)* |
| `NP8` | `SC1`, `SC2`, `SC3`, `SC8` |

Everything else free is a Medium-confidence tier (`NP4`, `NP5`, `NP7`) or a Variety/Rare scenario
(`SC4`–`SC7`, `SC9`). **All ten twist cores are now used**, so twist reuse is unavoidable from here and
should be selected for *semantic distance from the mechanic* rather than for novelty.

**Recommendation for v28+:** either accept lower-confidence scenarios and be honest about the score, or
raise the question of amending the Scenario Library through `intelligence/04` as the standards allow —
**not** by minting IDs inside an episode package, which is what produced the v8–v17 drift.

### Corrections to earlier records

1. **`NP5` confidence was inconsistent in my own scoring.** v18 rated it `H(1.0)`; v23 rated it `M(0.7)`.
   Library 6 places `NP5 Escalating Disaster` in the **Variety** tier, so **`M(0.7)` is correct** and v18's
   figure was too generous. v18's honest score is therefore **≈6.7, not 7.2.** The package is otherwise
   sound; the header is optimistic by ~0.5 and this row is the authoritative record.
2. **`TW8 Identity Reveal` is formally parked, not pending.** It is the only twist core never used, and it
   was attempted twice during v20 and v22 design. With a **locked two-person cast** an identity reveal
   requires either a third character with a concealed role — which the recurring-cast rule resists — or a
   contrivance of the kind the base audit warns about. **Decision: `TW8` is reserved for long form**, where
   a Guest-class character can be established properly, and is excluded from the Shorts queue. It should not
   be counted as an outstanding freshness gap for Shorts.

### Near-collapse avoided in v26 — worth recording as a pattern
The intuitive container for `NP8 Ironic Backfire` is `TW2 Irony Reversal`, and that pairing is **one core
wearing two hats** — the same defect found on v7, v8, v10 and v13. v26 uses `TW1 Role Reversal` instead.
**Check for this whenever a pattern name and a twist name share a root word** (`Ironic`/`Irony`,
`Overreach`/`Collapse`, `Hidden`/`Hidden`); it passes the letter of the comedy-core check while failing its
intent, because the collision is between *pattern* and *twist* rather than *comedy* and *twist*.
