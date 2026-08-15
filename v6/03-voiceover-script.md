# v6 — Voice-Over Storytelling Script ("One Sweet, One Coin") · **SHORTS**

> A narrator VO layer synced to the master timeline in `01-video-script.md`. **Important:** the
> video is designed **mute-first** (it reads perfectly with no sound), so this VO is an *amplifier*,
> not a crutch — it adds a storytelling voice and comment-bait without ever covering the twist SFX.
> The narration deliberately leaves the **silence beat (0:16–0:27)** almost empty so the pattern
> break lands. Total spoken time ≈ 13 s across a 32 s video (lots of breathing room).

**Voice direction:** the same narrator as v1–v5 — warm, dry, storyteller cadence, slightly amused, never
shouty. This is a **series voice**: reuse the same cloned voice on every IPPA episode so returning
viewers recognise it. (ElevenLabs: mid-range friendly male/neutral narrator, stability ~0.45,
similarity ~0.8, style/exaggeration low.)

---

## Timed narration script

| # | In–Out | Line | Delivery | Leaves room for |
|---|---|---|---|---|
| VO1 | 0:00–0:02 | "The rate was posted. One sweet, one coin." | flat, factual — establish the rule | purse thud, cup clack |
| VO2 | 0:02–0:04 | "He didn't read it." | dry | the scoops |
| VO3 | 0:04–0:06 | "He didn't need to. He was rich." | delivered as **fact**, not irony | **the 0:04 purse rattle** |
| VO4 | 0:06–0:09 | "Or so the purse suggested." | the first raised eyebrow — small, quick | scoop clatters |
| VO5 | 0:11–0:15 | "He wanted the biggest cup anyone had ever seen." | building, a little grand | the two-handed shovelling |
| VO6 | 0:16–0:18 | "**He got it.**" | flat, final, satisfied — then STOP | the slam and the music cut |
| — | 0:18–0:27 | **(SILENCE — no VO)** | let the scale groan and the coin land | the whole pattern break |
| VO7 | 0:27–0:30 | "Then he paid for it." | the payoff — quiet, almost kind | the reverse clatter + balance ting |
| VO8 | 0:31–0:32 | "Every time." | soft button; a tiny smile in the voice | BUD's munch, button ding |

**Total spoken ≈ 13 s.** Everything from 0:18–0:27 is intentionally VO-free.

> **The joke is the gap.** VO6 (**"He got it."**) and VO7 (**"Then he paid for it."**) are one thought split
> across 11 seconds of silence. The whole episode's punchline is the *turn* on the word "paid" — he pays in
> the literal sense, and the price is everything he was gloating about. Do not merge these lines, do not
> shorten the silence, and do not let VO7 arrive early.

> **VO3 must be played completely straight.** "He was rich" has to sound like the narrator believes it —
> it's the misdirection. If it's delivered as sarcasm, the purse reveal has nothing to overturn. The
> narrator finds out at 0:23 along with everyone else.

> **Series signature:** VO8 closes on **"Every time."** — the same button as v1–v5. Non-negotiable sign-off.

---

## Sync rules (so VO, video & audio lock together — see files 04 & 05)
1. **Never talk over the two protected sounds.** The **0:23 coin tink** and the **0:30 balance ting** are the two sounds carrying the twist. VO7 begins at 0:27 and must be clear of 0:30 — phrase it so "paid for it" lands *just before* the ting, letting the ting be the full stop.
2. **Protect the silence.** No VO between 0:18–0:27 except, optionally, a single breathed *"…one."* at ~0:25 (≤0.5 s). That one word is very effective here because it states the arithmetic without explaining it.
3. **VO3 must not step on the 0:04 purse rattle.** Phrase it with a natural gap so the thin, sparse coin sound is audible underneath the claim that he's rich — the audio contradicts the narration in real time, which is the best joke in the mix.
4. **Duck the BGM under VO** by ~4–6 dB during VO1–VO6, then release. During the 0:16–0:27 silence there is nothing to duck.
5. **Mute-first guarantee:** strip all VO and the video still reads — a balance scale, a pile and one coin is pure arithmetic. VO adds voice and shareable lines, never essential plot.
6. **Loudness:** VO peaks ≈ -12 to -10 dBFS, sitting ~3 dB above the ducked BGM; mix target -14 LUFS integrated, true-peak ≤ -1 dBTP (matches file 05).

---

## Optional on-screen text (comment-bait, only if you want captions)
The render itself carries **zero baked-in text** (a v6 rule — the pictogram rate is what makes this episode
work in every language). If you add captions in the edit:
- Style: `INK` text on a `PAPER` pill, bottom-centre, never over faces, the rate sign, the purse or the scale, ≤3 words.
- **Caption at 0:01:** "watch the purse 👀" (plants Seed B → replay bait)
- **Caption at 0:31:** "one. sweet. 💀" (the comment-driver — the flat arithmetic of it invites replies)

---

## Alternate VO variants (A/B test for virality — pick one per upload)
- **Variant B (punchier / TikTok-style):** VO1 "POV: you didn't check the price…" · VO6 "He got it all." · VO7 "…then the scale got involved." · VO8 "check the sign. every time."
- **Variant C (pure mute-first, no VO):** music + SFX only. **Strong option for v6** — the balance scale, the pictogram and the single coin tell the entire story with no language at all, making this one of the most exportable episodes in the series. Best choice if you're targeting non-English audiences.
- **Variant D (question hook, comment-farming):** replace VO8 with "Did you see how much was in the purse?" to drive replies about the 0:04 seed. Use sparingly — it slightly weakens the series sign-off.
