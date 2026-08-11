# v5 — "The Case of the Missing Pie" (production package) · **LONG FORM**

The first **long-form** IPPA episode: **1:30**, **16:9 horizontal**, 16 shots across 5 acts.
**Video ID:** `IPPA_0005_pie_longform_v1`.

Computed from the Content Matrix as **Mode B — Exploration B1**: Goal *Replay* → *B2 Replay* →
**NP4 Hidden Truth** → **SC6 Crime & Justice (bloodless)** → **CM-A2 Misdirection** →
**TW5 Hidden Cause + TM3 Seed Callback** → FM. **FinalScore 5.5**, Confidence Medium.

Cast: **CHIEF** (self-appointed detective) · **PIP** (falsely accused) · **BUD** (Animal, proposed) ·
**MITTENS** the market cat (Guest, proposed) · market crowd (Crowd class).

| # | File | What it's for |
|---|---|---|
| 1 | [`01-video-script.md`](01-video-script.md) | Beats, master timeline, **retention architecture**, scene script, seeds, compliance checklist |
| 2 | [`02-image-generation-reference.md`](02-image-generation-reference.md) | Characters, reactions, surroundings, props + a paste-ready image prompt per shot |
| 3 | [`03-voiceover-script.md`](03-voiceover-script.md) | Timed narration (deadpan case-file register), sync rules, chapter cards, variants |
| 4 | [`04-video-generation-prompt.md`](04-video-generation-prompt.md) | Motion, camera angles, transitions, cut/freeze timing, FX per shot + one-shot master prompt |
| 5 | [`05-audio-bgm-sfx-reference.md`](05-audio-bgm-sfx-reference.md) | **Exact cue sheet** — every BGM/SFX layer at every timecode |
| 6 | [`06-thumbnail-prompt.md`](06-thumbnail-prompt.md) | **NEW (long form only)** — 3 high-CTR thumbnail concepts + title pairings |

**Story in one line:** a pie vanishes from a market stall; CHIEF appoints himself detective, clears the
dog, clears the cat, and builds an absurd case against tiny PIP — but there was never a thief. He propped
his own ledger against the stall leg in the opening seconds, tilting the table, and the pie slid into
**his own evidence box**, where it sat for the entire investigation.

**The seeds (both his, both visible by 0:07):** the **ledger** against the table leg, and the **open
evidence box** on the ground.

---

## ⚠️ Read this before you upload
Any **vertical or square** video up to **3 minutes** is auto-classified as a **Short** by YouTube
([YouTube Help](https://support.google.com/youtube/answer/15424877)). A 1:00–2:00 vertical video would land
in the Shorts feed, not as long form. **v5 is therefore specced 16:9 horizontal** — this is the first
episode that is *not* 9:16, and every shot is composed for horizontal, not letterboxed from vertical.
*Content rephrased from the source for licensing compliance.*

---

## What's new in v5

**Format**
- First long form: 1:30, 16:9, 16 shots, 5 acts. The 8-clip/32 s Shorts skeleton does not apply.
- First **thumbnail file** (`06`) — three ranked concepts, generation prompts, overlay copy, title pairings, and a small-size legibility checklist.
- Silence beat scaled to **10 s (1:08–1:18)** and placed immediately before the reveal.

**Retention design (per your instruction — now applies to Shorts too)**
- Cold open on the empty plate with **one second of no music at all**, then a gasp. No logo, no title card.
- An **open loop** planted at 0:07 and unresolved until 1:18.
- A **micro-payoff every ≤15 s**, with two deliberately unnarrated laugh windows (0:23–0:28, 0:39–0:44).
- **Pattern interrupts at ~0:28 and ~0:56** — exactly the two known drop-off points.
- **Three subliminal seed glimpses** (0:26 elbow-occluded, 0:41 crate-occluded, 0:58 reflected in the stamp) — unease on first watch, obvious on replay.
- Ends on the **opening frame** so the rewatch hunts for the ledger.

**Audio (per your instruction — now applies to Shorts too)**
- `05` is now a **prescriptive cue sheet**: a 14-row table giving the exact layer stack (`SFX only` / `BGM+SFX+VO+AMB` / `SILENCE`) for every time range, plus a complete hit list of all 40 SFX with timecodes and mix levels.
- The standout cue: from **1:02–1:08 the music un-builds**, dropping one instrument per character who turns to look — brass, then snare, then bass, then woodblock — so the arrangement collapses in sync with the on-screen turn, straight into the 10-second silence.

**Craft note — the signature-sound inversion**
v1 = the stamp · v2 = the booster · v3 = the block clack · v4 = the panel slam. v5's signature is the
**discovery sting**, escalating four times (S/M/L/XL at 0:01, 0:13, 0:29, 0:47). It's then inverted by
**absence**: at the real moment of discovery there is no sting at all, because the discovery isn't his.

---

## ⚠️ Needs your approval
- **BUD** (Animal class) appears for a second time, which under the Character Bible pushes him toward recurring status and a full model sheet.
- **MITTENS** is proposed as **Guest** class (one-off sheet only).
- Neither is locked. Suspect 2 could instead be a pigeon built from existing Crowd shapes, or Act 3 could be cut entirely, bringing the runtime to ~1:14.

Series conventions are recorded in [`.kiro/steering/video-generation-standards.md`](../.kiro/steering/video-generation-standards.md).
Reusable style/character vocabulary: [`IMAGE-GEN-REFERENCE.md`](../IMAGE-GEN-REFERENCE.md).
Previous episodes: [`../v1`](../v1) · [`../v2`](../v2) · [`../v3`](../v3) · [`../v4`](../v4).
