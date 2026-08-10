# v4 — Voice-Over Storytelling Script ("The Wrong Side of the Fence")

> A narrator VO layer synced to the master timeline in `01-video-script.md`. **Important:** the
> video is designed **mute-first** (it reads perfectly with no sound), so this VO is an *amplifier*,
> not a crutch — it adds a storytelling voice and comment-bait without ever covering the twist SFX.
> The narration deliberately leaves the **silence beat (0:16–0:27)** almost empty so the pattern
> break lands. Total spoken time ≈ 13 s across a 32 s video (lots of breathing room).

**Voice direction:** identical narrator to v1–v3 — warm, dry, storyteller cadence, like narrating a
fable. Slightly amused. Never shouty. This is a **series voice**: reuse the same cloned voice on every
IPPA episode so returning viewers recognise it. (ElevenLabs: a mid-range friendly male/neutral
narrator, stability ~0.45, similarity ~0.8, style/exaggeration low.)

---

## Timed narration script

| # | In–Out | Line | Delivery | Leaves room for |
|---|---|---|---|---|
| VO1 | 0:00–0:02 | "There was one good spot in the whole park." | easy, setting-the-scene | strut boings, water trickle, cicadas |
| VO2 | 0:02–0:04 | "And someone decided it should be his." | dry | the first panel SLAM |
| VO3 | 0:04–0:06 | "So he started building." | matter-of-fact | slams, dust puffs |
| VO4 | 0:06–0:09 | "Panel by panel." | flat, patient | the rhythmic slam combo |
| VO5 | 0:11–0:15 | "Taller than it needed to be. With a lock, obviously." | amused, dry on "obviously" | padlock clink, glove claps |
| VO6 | 0:16–0:18 | "He thought of everything." | confident, full stop, then STOP | — |
| — | 0:18–0:27 | **(SILENCE — no VO)** | let the rising cicada buzz carry it | the whole pattern break |
| VO7 | 0:27–0:30 | "He'd built it from the outside." | the payoff — calm, almost sympathetic | the padlock CLICK + fence rattle |
| VO8 | 0:31–0:32 | "Every time." | soft button; a tiny smile in the voice | cicada buzz, button ding |

**Total spoken ≈ 13 s.** Everything from 0:18–0:27 is intentionally VO-free.

> **Do not let VO6 leak the twist.** "He thought of everything." must land as *agreement* with CHIEF —
> the narrator is on his side for one beat. If the delivery winks, or if the line becomes anything like
> "…except which side he was on," the reveal in C6 is spoiled and the irony collapses. The narrator finds
> out at the same moment the audience does.

> **Series signature:** VO8 closes on **"Every time."** — the same button as v1, v2 and v3. Keep this as
> the channel's spoken sign-off on every IPPA episode; it builds the recognition loop.

---

## Sync rules (so VO, video & audio lock together — see files 04 & 05)
1. **Never talk over the twist.** VO7 must finish before or land into the **padlock CLICK** at ~0:29. That click is a tiny sound doing enormous work — it cannot be masked by narration.
2. **Protect the silence.** No VO between 0:18–0:27 except, optionally, a single breathed *"…oh."* at ~0:26 (≤0.6 s). That one syllable is very effective here because it lets the narrator realise it a half-beat before the audience.
3. **VO5 and VO6 must be played straight.** They are the misdirection — the narrator is admiring the wall along with CHIEF. Sincerity here is what buys the reversal.
4. **Duck the BGM under VO** by ~4–6 dB during VO1–VO5, then release. During the 0:16–0:27 silence there is nothing to duck — but never duck the **cicada buzz**, which is doing the storytelling.
5. **Mute-first guarantee:** if VO is removed entirely, the video still reads — the irony is pure geometry. VO adds voice + shareable lines, never essential plot.
6. **Loudness:** VO peaks ≈ -12 to -10 dBFS, sitting ~3 dB above the ducked BGM; overall mix target -14 LUFS integrated, true-peak ≤ -1 dBTP (matches file 05).

---

## Optional on-screen text (comment-bait, only if you want captions)
The render itself carries **zero baked-in text** (a v4 rule). If you add captions in the edit:
- Style: `INK` text on a `PAPER` pill, bottom-center, never over faces, the padlock, or the shade edge, ≤3 words.
- **Caption at 0:01:** "watch where he's standing 👀" (plants the seed → replay bait; this is the single best caption in the series so far because the twist is genuinely visible from frame 1)
- **Caption at 0:31:** "he locked himself out 💀" (the comment-driver)

---

## Alternate VO variants (A/B test for virality — pick one per upload)
- **Variant B (punchier / TikTok-style):** VO1 "POV: you build a wall to keep one guy out…" · VO6 "Perfect." · VO7 "…from the outside." · VO8 "measure twice. every time."
- **Variant C (pure narrator, no VO):** ship mute-first with music+SFX only — highest global reach, zero localization barrier. **Strong option for v4**, because the sun/shade split and the padlock click tell the whole story with no language at all.
- **Variant D (question hook, comment-farming):** replace VO8 with "How early did you spot it?" — unusually well-suited to v4, since the answer is genuinely "frame one." Use sparingly; it slightly weakens the series sign-off.
