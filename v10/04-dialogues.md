# v10 — Dialogues ("The Printer") · **talking-head speech**

> Who says what, when, in `IPPA_0010_printer_shorts_v1`. Locks to the 8-clip master timeline in
> [`01-video-script.md`](01-video-script.md) and sits alongside the SFX/BGM cue sheet in
> [`03-audio-bgm-sfx-reference.md`](03-audio-bgm-sfx-reference.md).
>
> **Total spoken content: 29 words across 32 seconds.** CHIEF has 23 of them. PIP has 4.

---

## ⚠️ Read this first — what talking heads change

The cast has never spoken in this series. Three locked things are affected, and you should decide
knowingly rather than discover it in the edit:

| Locked rule | Where | What talking heads do to it |
|---|---|---|
| *"Eyes carry ~70% of the read. **Mouth (secondary). Supports, never leads (mute-first). Kept small by default**… the mouth animates for expression only."* | [Expression Library](../production/design/EXPRESSION_LIBRARY.md) | **Directly inverted.** A speaking mouth leads and must animate continuously. This is the biggest change — it needs a mouth/viseme asset set that does not currently exist (§5). |
| *"Mute-first: the story must read with sound off. VO is an amplifier, never load-bearing."* | [standards](../.kiro/steering/video-generation-standards.md) | **Survivable, and I have preserved it.** Every line below is written so that removing all dialogue costs the viewer nothing. |
| *"No language dependency… consistent with the locked global/mute-first mandate."* | [Channel Identity Lock](../channel/01-CHANNEL-IDENTITY-LOCK.md) (reason #3 the name IPPA was chosen) | **Genuinely reduced.** Speech introduces a language the video did not previously have. Mitigations in §7. |

**My recommendation:** keep the dialogue exactly this sparse. At 29 words it is an *amplifier* — it adds
personality and two real story beats without ever becoming the thing that carries the video. Shorts are
swipe-decided with sound off, so anything load-bearing in speech is spent on an audience that cannot hear it.

---

## 1. Voice direction

**CHIEF** — pompous, institutional, self-congratulating. Speaks in short declarative bursts, never long
sentences. Talks *over* people without noticing. Mid-range, slightly nasal, over-articulated like a man who
enjoys the sound of his own announcements. **Never shouts, never swears.** He is the only character who
speaks unprompted.

**PIP** — soft, polite, quiet. Two lines in the entire video and both are useful: one correct warning that
is ignored, and one thank-you. Slightly higher register, unhurried, no whine. **PIP never argues, never
gloats, never says "I told you so"** — that would break the Hero/Underdog rule that he is vindicated *by the
twist*, never by his own retaliation.

**NARRATOR** — the existing series voice, now reduced to the sign-off only (see §4).

---

## 2. The dialogue script

| # | Time | Clip | Speaker | Line | Words | Delivery |
|---|---|---|---|---|---|---|
| D1 | 0:01 | C1 | **CHIEF** | "Coming through." | 2 | Brisk, not angry — an announcement, as he shoves past |
| D2 | 0:03 | C2 | **CHIEF** | "Nine ninety-nine." | 2 | Reading his own counter with relish |
| D3 | 0:05 | C2 | **CHIEF** | "You'll wait." | 2 | Flat, over the shoulder, finger wagging |
| D4 | 0:07 | C3 | **CHIEF** | "Look at that." | 3 | Admiring his own printed face |
| D5 | 0:09 | C3 | **CHIEF** | "Every single month." | 3 | Proud, as though it were an achievement |
| D6 | 0:12 | C4 | **CHIEF** | "One for every desk." | 4 | Grand, expansive, knee-deep in paper |
| **D7** | **0:14** | **C4** | **PIP** | **"That's too many."** | **3** | **Quiet, polite, and completely correct** |
| D8 | 0:15 | C4 | **CHIEF** | "It's fine." | 2 | Dismissive, *without looking* — he talks over D7's tail |
| D9 | 0:16 | C5 | **CHIEF** | "Perfect." | 1 | Satisfied, landing **just before** the CLUNK |
| — | **0:17–0:27** | **C5–C6** | — | **NO DIALOGUE** | 0 | **The protected silence beat.** See §3 |
| D10 | 0:28 | C7 | **CHIEF** | "Queue zero?" | 2 | Reading the screen, disbelief, rising |
| D11 | 0:29 | C7 | **CHIEF** | "Where's mine?" | 2 | Small, deflating |
| **D12** | **0:30** | **C7** | **PIP** | **"Thanks."** | **1** | **Even, sincere, unhurried. Not smug** |
| D13 | 0:32 | C8 | *NARRATOR* | "Every time." | 2 | The locked series button, unchanged |

### The two lines that matter
- **D7 "That's too many."** — PIP diagnoses the actual cause (the copy count, `SEED B`) out loud, and is talked over. It makes CHIEF's collapse verbally self-inflicted as well as mechanically self-inflicted, and it mirrors the beat in v7 where PIP tries to warn the man who shoved him.
- **D12 "Thanks."** — PIP's only substantive word, arriving after ~29 seconds of silence from him. One word, placed at the payoff, lands harder than a speech. He is thanking the printer, not taunting CHIEF, which keeps him inside the Hero class.

### Word balance is the design, not an accident
| Speaker | Words | Share |
|---|---|---|
| CHIEF | 23 | 79% |
| PIP | 4 | 14% |
| Narrator | 2 | 7% |

This mirrors the motion design already specified in
[`02-video-animation-prompt.md`](02-video-animation-prompt.md) — *"CHIEF: big theatrical gestures… PIP:
nearly motionless… his stillness is the contrast."* PIP's near-silence is the audible version of his
stillness. **Do not give PIP more lines**; the ratio is the joke.

---

## 3. The protected silence beat (0:17–0:27) — do not put dialogue here

`03-audio-bgm-sfx-reference.md` cuts the music on the CLUNK at 0:17 and leaves 11 seconds carried by the
blinking-light click, the paper rip, the panel clacks and one desperate slap. **That window stays
dialogue-free.**

- CHIEF is frantic for five straight seconds **in silence**, which is far funnier than a man narrating his
  own panic — and it is the single highest-tension stretch in the episode.
- **Effort noises are not dialogue.** Grunts, strained breaths and the slap are SFX and belong in file 03,
  not here. Keep them there so this window remains *musically silent and speech-free*.
- **One optional exception:** a breathed, half-swallowed **"…no."** from CHIEF at ~0:19, ≤0.4 s, at
  **-22 dB**. It is cuttable and the beat is fine without it. If in doubt, cut it.

---

## 4. Reconciling with the existing narrator VO

`01-video-script.md` currently carries **eight** narrator lines. If those stay *and* the cast speaks, 32
seconds becomes crowded and the two layers fight. Recommended resolution — **the narrator stands down to the
sign-off**, because the character lines now do the same job better:

| Old narrator line | Status | Replaced by |
|---|---|---|
| "One printer. One problem." | **cut** | D1 "Coming through." *(also retires the banned `"One ___. One ___."` cadence flagged in the retention analysis)* |
| "Nine hundred and ninety-nine copies." | **cut** | D2 "Nine ninety-nine." — better in his own mouth |
| "His best angle. Obviously." | **cut** | D4 + D5 |
| "Still printing." | **cut** | D6 |
| "Uh oh." | **cut** | D9 "Perfect." — irony instead of commentary |
| *(whisper)* "…it wasn't coming back." | **cut** | nothing. Protects the silence beat |
| "One page. First in queue." | **cut** | D10 + D11 + D12 |
| **"Every time."** | **KEEP** | — locked series sign-off, non-negotiable |

> **Alternative if you want the narrator retained:** keep only *"Every time."* plus one mid-video line, and
> drop D4/D5/D6 to make room. Do **not** run all eight narrator lines and all twelve character lines — the
> audio has ~14 seconds of usable speech space once the silence beat and the twist SFX are protected.

---

## 5. ⚠️ New asset required — mouth / viseme set (proposed, **not locked**)

Neither character has a speaking mouth. The Character Bible gives PIP a *"tiny mouth"* and describes CHIEF
as *"carried by strut, gloat, and the final open-mouthed shock"* — both fixed features, because the
Expression Library keeps mouths small on purpose. Talking heads need a new asset, which per the Character
Bible lifecycle requires a model sheet and your approval before it becomes canon.

**Proposed minimal set — 4 shapes per character** (`CHAR_CHIEF_mouth_v1`, `CHAR_PIP_mouth_v1`):

| ID | Shape | Used for |
|---|---|---|
| `M0` REST | The character's existing expression mouth | All non-speaking frames — the default |
| `M1` SMALL | Slightly open, flat oval | most consonants and short vowels |
| `M2` WIDE | Open, taller than wide | "ah", stressed syllables, D9 "Perfect" |
| `M3` ROUND | Narrow, rounded | "oo"/"o" — D10 "Queue zero?" |

**Lip-sync rules for this house style (30 fps, flat 2D):**
- Animate **per syllable, not per phoneme.** 29 words is roughly 40 syllables in the whole video.
- **Minimum 2 frames per viseme**; never a 1-frame flicker.
- **Return to `M0` between lines**, and hold `M0` through every non-speaking beat.
- Mouth shapes are flat `INK`-outlined shapes on the existing head — **no new head angles, no jaw rig, no teeth or tongue detail.**
- **The eyes and brows still lead.** Keep the Expression Library's `L1/L2/L3` intensity on eyes and brows exactly as `01-video-script.md` specifies, and let the mouth ride underneath. This is how the 70/30 hierarchy survives speech.
- **PIP's mouth stays small even when speaking** — `M1` is his ceiling except for `M2` on "Thanks." His tiny mouth is a silhouette signature.

---

## 6. Audio placement

Slots into the file 03 cue sheet without disturbing it. Dialogue is a **new layer**, `DLG`:

| Time range | Layers | Note |
|---|---|---|
| 0:00–0:16 | `BGM + SFX + DLG` | **Duck BGM ~5 dB under every line.** Dialogue sits above the bed |
| **0:17–0:27** | `SFX only` | **No DLG, no BGM.** The protected beat |
| 0:27–0:32 | `BGM + SFX + DLG` | D10–D12, then the narrator button |

- Dialogue peaks **≈ -12 to -10 dBFS**, ~3 dB above the ducked bed — same target as the narrator VO.
- **D8 "It's fine." overlaps the tail of D7** by ~0.2 s. That overlap is deliberate: he is talking over the correct answer. It is the only intentional overlap in the video.
- **Protect these SFX from dialogue:** the **CLUNK at 0:17**, the **reboot chime at 0:27**, the **clean page `shk` at 0:28** and the **output `ding`**. D10 lands *after* the chime, not on it.
- **D12 "Thanks." must sit in clear space** at 0:30 — it is one word and it is the emotional payoff. Duck everything ~3 dB for 400 ms around it.

---

## 7. Localization — the cost, and how to keep it small

The channel name was chosen partly for having **no language dependency**, and speech spends some of that.
Kept manageable by design:

- **29 words is a cheap dub.** A full-cast re-record per language is minutes of studio time.
- **Nothing plot-critical is spoken.** Strip all dialogue and the video still reads: a paper tower, a
  counter at 999, an overheating machine, a jam, a reboot, one clean page. Verified in §8.
- **Ship a captions track** rather than baking text — the standards forbid baked-in on-frame text, and
  captions are the existing carve-out for the hook overlay.
- **If a market tests badly with speech,** publish the mute-first cut: drop the `DLG` layer entirely,
  restore the narrator's *"Every time."*, and nothing else changes.

---

## 8. Mute-first verification (run this before shipping)
- [ ] Mute the whole dialogue layer and watch it once. **The story must still be completely clear.** If anything is now confusing, that beat was load-bearing and must be moved back into the picture.
- [ ] No line explains something the frame does not already show.
- [ ] D7 is a *warning*, not an *explanation* — the 999 counter already told the audience; PIP only confirms it.
- [ ] The 0:17–0:27 window contains **no dialogue** (the optional "…no." at 0:19 is cut or ≤0.4 s at -22 dB).
- [ ] PIP speaks **twice**, totalling 4 words, and never gloats or says "I told you so."
- [ ] CHIEF never shouts, never swears, and his last line is small rather than loud.
- [ ] The narrator's **"Every time."** survives as the final line.
- [ ] Mouths return to `M0` in every non-speaking frame; eyes and brows still lead the read.
- [ ] Cap + sash + medals on CHIEF and the scarf on PIP in every frame, unchanged.

---

## 9. Things I noticed in v10 while reading — flagged, not changed

These are pre-existing and sit outside this file's scope, but they affect anyone working in v10 next. Per
the base audit's convention, creative content is **flagged rather than silently edited**:

1. **`SC4` is mislabelled.** The header declares `SC4 Workplace/Office`, but `SC4` is **Family/Domestic** in the Scenario Library. An office is `SC1 Authority` or `SC8 Everyday Friction`. Already recorded in [`BASE-AUDIT.md`](../BASE-AUDIT.md).
2. **Comedy core = twist core.** The header declares `CM-C4 Own Tool Backfire → TW4 False Victory`, but `CM-C4` **is** False Victory — one core named twice, which silently fails the Rule of One.
3. **Off-palette colour words reach the renderer.** `01` and `02` both say *"the big **green** PRINT button"*, and `02` specifies *"flat **white** confetti bits"*; `01` has *"screen flashes **white**"*. Per the standards these should be tokens: the button → `POP_TEAL`, the confetti and flash → `PAPER`. **I have used no English colour words anywhere in this file.**
4. **Non-canonical emotion names.** v10's timeline uses `aggressive`, `patient`, `content`, `observant`, `kind` and `defeated`, none of which exist in the Expression Library. `curious` is the only valid one. Nearest canonical substitutes: `aggressive`→`gloating`, `patient`/`content`/`observant`→`neutral`, `kind`→`relieved`, `defeated`→`sheepish`. **This file references only canonical names.**

---

*Naming note: filed as `04-dialogues.md` so it sorts with the numbered package files and is discoverable
next to the script it depends on.*
