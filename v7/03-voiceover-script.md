# v7 — Voice-Over Storytelling Script ("The Big One") · **SHORTS**

> A narrator VO layer synced to the master timeline in `01-video-script.md`. **Important:** the
> video is designed **mute-first** (it reads perfectly with no sound), so this VO is an *amplifier*,
> not a crutch — it adds a storytelling voice and comment-bait without ever covering the twist SFX.
> The narration deliberately leaves the **silence beat (0:16–0:27)** almost empty so the pattern
> break lands. Total spoken time ≈ 12 s across a 32 s video (the sparsest script in the series).

**Voice direction:** the same narrator as v1–v6 — warm, dry, storyteller cadence, slightly amused, never
shouty. This is a **series voice**: reuse the same cloned voice on every IPPA episode so returning
viewers recognise it. (ElevenLabs: mid-range friendly male/neutral narrator, stability ~0.45,
similarity ~0.8, style/exaggeration low.)

**Why v7's script is the sparsest yet:** this episode runs on **dramatic irony** — the audience can see
the canopy filling and the character can't. Narration is the enemy of dramatic irony, because every word
risks either stating the obvious or tipping the character off. The narrator must stay as oblivious as
CHIEF, and mostly stay quiet.

---

## Timed narration script

| # | In–Out | Line | Delivery | Leaves room for |
|---|---|---|---|---|
| VO1 | 0:00–0:02 | "It started to rain." | flat, plain, scene-setting | **the 0:01 gutter drip** |
| VO2 | 0:02–0:04 | "There were two umbrellas." | simple statement of fact | the big umbrella *fwoomp* |
| VO3 | 0:04–0:06 | "He took the big one." | dry, no comment | PIP's modest little *pop* |
| VO4 | 0:06–0:09 | "Obviously." | one word, perfectly flat — the first real laugh | the trickle beginning |
| VO5 | 0:11–0:15 | "And he found the best spot to enjoy it from." | sincere, admiring — **no irony in the voice** | the pour, the fabric strain |
| VO6 | 0:16–0:18 | "**Dry as a bone.**" | confident, satisfied, final — then STOP | the music cut |
| — | 0:18–0:27 | **(SILENCE — no VO)** | let the pour and the straining fabric do everything | the whole pattern break |
| VO7 | 0:27–0:30 | "Then he pointed." | the payoff — quiet, almost apologetic | the SPLASH |
| VO8 | 0:31–0:32 | "Every time." | soft button; a tiny smile in the voice | the last drip, button ding |

**Total spoken ≈ 12 s.** Everything from 0:18–0:27 is intentionally VO-free.

> **VO5 is the most important line to get right.** "He found the best spot" must be delivered as a genuine
> compliment. The narrator agrees with CHIEF. If there is a knowing lilt on "best," the audience is told the
> spot is a trap and the dramatic irony collapses into a smug joke. Play it straight and let the *picture*
> be ironic.

> **VO7 names the cause in three words.** "Then he pointed." is the entire mechanism — no external agent, no
> wind, no accident. His own gloating gesture emptied the bucket. Do not extend this line; do not explain it.
> The brevity is what makes it land.

> **Series signature:** VO8 closes on **"Every time."** — the same button as v1–v6. Non-negotiable sign-off.

---

## Sync rules (so VO, video & audio lock together — see files 04 & 05)
1. **Never talk over the SPLASH.** VO7 begins at 0:27 on the tipping canopy and must be **finished or nearly finished before the splash lands at 0:29.** The splash is the loudest sound in the video and must arrive uncontested.
2. **Protect the 0:01 drip.** VO1 is only three words for exactly this reason — phrase it so the single gutter drip is clearly audible around it. If the audience can't hear the seed, the fair-play contract breaks.
3. **Protect the silence.** No VO between 0:18–0:27 except, optionally, a single breathed *"…he tried to say something."* at ~0:24 (≤0.8 s). Nothing may cover **PIP's step back at 0:25**.
4. **Duck the BGM under VO** by ~4–6 dB during VO1–VO6, then release. **Never duck the pour** — it is doing the storytelling from 0:12 onward.
5. **VO4 ("Obviously.") needs air on both sides.** Give it ~0.4 s of silence before and after. A one-word line only works if it's isolated.
6. **Mute-first guarantee:** strip all VO and the video still reads — a bowl, a pouring gutter and gravity need no language. VO adds voice and shareable lines, never essential plot.
7. **Loudness:** VO peaks ≈ -12 to -10 dBFS, sitting ~3 dB above the ducked BGM; mix target -14 LUFS integrated, true-peak ≤ -1 dBTP (matches file 05).

---

## Optional on-screen text (comment-bait, only if you want captions)
The render itself carries **zero baked-in text**. If you add captions in the edit:
- Style: `INK` text on a `PAPER` pill, bottom-centre, never over faces, the gutter or the canopy, ≤3 words.
- **Caption at 0:01:** "check the gutter 👆" (plants Seed A → replay bait; the upward arrow is a nice touch here because *looking up* is exactly what CHIEF fails to do)
- **Caption at 0:31:** "he pointed. 💀" (the comment-driver — the flatness invites replies)

---

## Alternate VO variants (A/B test for virality — pick one per upload)
- **Variant B (punchier / TikTok-style):** VO1 "POV: you took the big umbrella…" · VO6 "Not a drop on him." · VO7 "…and then he pointed." · VO8 "look up. every time."
- **Variant C (pure mute-first, no VO):** music + SFX only. **Strongest option in the series for this route** — the four water stages (`drip → trickle → pour → splash`) narrate the entire story in sound design alone, with zero language. Best choice for non-English audiences, and arguably the better version outright.
- **Variant D (PIP's perspective, one line):** keep the script silent except a single line at 0:31 in PIP's voice — *"I did try."* Very warm, strong Subscribe driver, and it pays off his attempted warning at 0:22. Worth testing; the only risk is that it breaks the narrator convention.
