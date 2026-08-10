# v3 — Voice-Over Storytelling Script ("One Block Too Many")

> A narrator VO layer synced to the master timeline in `01-video-script.md`. **Important:** the
> video is designed **mute-first** (it reads perfectly with no sound), so this VO is an *amplifier*,
> not a crutch — it adds a storytelling voice and comment-bait without ever covering the twist SFX.
> The narration deliberately leaves the **silence beat (0:16–0:27)** almost empty so the pattern
> break lands. Total spoken time ≈ 13 s across a 32 s video (lots of breathing room).

**Voice direction:** identical narrator to v1 and v2 — warm, dry, storyteller cadence, like narrating
a fable. Slightly amused. Never shouty. This is a **series voice**: reuse the same cloned voice on
every episode so returning viewers recognise it. (ElevenLabs: a mid-range friendly male/neutral
narrator, stability ~0.45, similarity ~0.8, style/exaggeration low.)

---

## Timed narration script

| # | In–Out | Line | Delivery | Leaves room for |
|---|---|---|---|---|
| VO1 | 0:00–0:02 | "The rules were simple. Reach the line." | easy, setting-the-scene | strut boings, block clack |
| VO2 | 0:02–0:04 | "One of them listened." | dry | careful clacks, crooked-block creak |
| VO3 | 0:04–0:06 | "The other one had a better idea." | wry | careless double-slams |
| VO4 | 0:06–0:09 | "Higher. Always higher." | flat, a little sing-song | stacking combo, wooden groans |
| VO5 | 0:11–0:15 | "And for one perfect moment, he had everything he wanted." | warm, almost sincere — sell it | wobble creaks, fanfare |
| VO6 | 0:16–0:18 | "**He'd won.**" | confident, full stop, then STOP | — |
| — | 0:18–0:27 | **(SILENCE — no VO)** | let the creaking carry it | the whole pattern break |
| VO7 | 0:27–0:30 | "…for about ten seconds." | the payoff — dry, perfectly timed | the CRASH + trophy "ting" |
| VO8 | 0:31–0:32 | "Every time." | soft button; a tiny smile in the voice | final block clack, button ding |

**Total spoken ≈ 13 s.** Everything from 0:18–0:27 is intentionally VO-free.

> **The joke is the gap.** VO6 ("He'd won.") and VO7 ("…for about ten seconds.") are one sentence split
> across the silence — the ~11 seconds of quiet *is* the punchline's timing. Do not shorten the silence
> to fit more narration, and do not merge these two lines.

> **Series signature:** VO8 closes on **"Every time."** — the same button as v1 and v2. Keep this as the
> channel's spoken sign-off on every IPPA episode; it builds the recognition loop.

---

## Sync rules (so VO, video & audio lock together — see files 04 & 05)
1. **Never talk over the twist impact.** VO7 lands just before or into the top of the CRASH at ~0:29; the SFX owns the hit and the trophy "ting" must be heard clean.
2. **Protect the silence.** No VO between 0:18–0:27 except, optionally, a single breathed *"…mostly."* at ~0:26 (≤0.6 s) — otherwise leave it clean so the creaks do the work.
3. **VO5 must be played straight.** It is the only sincere line in the script; if the narrator winks here, the false victory doesn't land and the reversal loses its drop.
4. **Duck the BGM under VO** by ~4–6 dB during VO1–VO5, then release. During the 0:16–0:27 silence there is nothing to duck — but do **not** duck the creaks under the optional whisper.
5. **Mute-first guarantee:** if VO is removed entirely, the video still reads. VO adds voice + shareable lines, never essential plot.
6. **Loudness:** VO peaks ≈ -12 to -10 dBFS, sitting ~3 dB above the ducked BGM; overall mix target -14 LUFS integrated, true-peak ≤ -1 dBTP (matches file 05).

---

## Optional on-screen text (comment-bait, only if you want captions)
The render itself carries **zero baked-in text** (a v3 rule). If you add captions in the edit:
- Style: `INK` text on a `PAPER` pill, bottom-center, never over faces, the red band, or the crooked block, ≤3 words.
- **Caption at 0:03:** "watch the bottom block 👀" (plants the callback seed → replay bait)
- **Caption at 0:31:** "he had it. briefly. 💀" (the comment-driver — invites the "rewatch the base" reply)

---

## Alternate VO variants (A/B test for virality — pick one per upload)
- **Variant B (punchier / TikTok-style):** VO1 "POV: 'good enough' wasn't good enough…" · VO6 "He won." · VO7 "…for ten whole seconds." · VO8 "stack smarter. every time."
- **Variant C (pure narrator, no VO):** ship mute-first with music+SFX only — highest global reach, zero localization barrier. **Recommended for v3**, because the creak-then-crash sound design carries the whole twist without a single word.
- **Variant D (question hook, comment-farming):** replace VO8 with "Did you spot it at the start?" to drive replies about the crooked block. Use sparingly — it slightly weakens the series sign-off.
