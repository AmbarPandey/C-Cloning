# v2 — Voice-Over Storytelling Script ("The Victory Lap")

> A narrator VO layer synced to the master timeline in `01-video-script.md`. **Important:** the
> video is designed **mute-first** (it reads perfectly with no sound), so this VO is an *amplifier*,
> not a crutch — it adds a storytelling voice and comment-bait without ever covering the twist SFX.
> The narration deliberately leaves the **silence beat (0:16–0:27)** almost empty so the pattern
> break lands. Total spoken time ≈ 14 s across a 32 s video (lots of breathing room).

**Voice direction:** identical narrator to v1 — warm, dry, storyteller cadence, like narrating a
fable. Slightly amused. Never shouty. Confident downbeat on the payoff line. This is a **series
voice**: reuse the same cloned voice on every episode so returning viewers recognise it.
(ElevenLabs: a mid-range friendly male/neutral narrator, stability ~0.45, similarity ~0.8,
style/exaggeration low.)

---

## Timed narration script

| # | In–Out | Line | Delivery | Leaves room for |
|---|---|---|---|---|
| VO1 | 0:00–0:02 | "The champion brought a rocket." | easy, setting-the-scene | strut boings, engine idle |
| VO2 | 0:02–0:04 | "The challenger brought roller skates." | dry punch | trophy clunk, ribbon "pfft" |
| VO3 | 0:04–0:06 | "Nobody was betting on the skates." | wry | "aha" sting |
| VO4 | 0:06–0:09 | "And for a while, nobody had to." | matter-of-fact | flag whoosh, booster #1 |
| VO5 | 0:11–0:15 | "But winning wasn't enough. He wanted a *margin*." | amused, lean on "margin" | boosters #2–#4 |
| VO6 | 0:16–0:18 | "So he went faster." | drop to near-whisper, then STOP | — |
| — | 0:18–0:27 | **(SILENCE — no VO)** | let the fading whine + tape flutter carry it | the whole pattern break |
| VO7 | 0:27–0:30 | "He forgot one thing. You have to cross the line." | the payoff — calm, satisfying | tape SNAP + confetti + scratch |
| VO8 | 0:31–0:32 | "Every time." | soft button; a tiny smile in the voice | booster deflate, button ding |

**Total spoken ≈ 14 s.** Everything from 0:18–0:27 is intentionally VO-free.

> **Series signature:** VO8 closes on **"Every time."** — the same button as v1. Keep this as the
> channel's spoken sign-off on every episode; it builds the recognition loop.

---

## Sync rules (so VO, video & audio lock together — see files 04 & 05)
1. **Never talk over the twist impact.** VO7 finishes just as (or a beat before) the tape SNAP at ~0:29; the SFX owns the hit.
2. **Protect the silence.** No VO between 0:18–0:27 except, optionally, a single breathed *"…all of it."* at ~0:26 (≤0.6 s) — otherwise leave it clean.
3. **VO5 is the setup for the whole twist.** It names CHIEF's fatal motive (greed for a bigger margin), which is what lifts him over the tape. Do not rush it.
4. **Duck the BGM under VO** by ~4–6 dB during VO1–VO5, then release. During the 0:16–0:27 silence there is nothing to duck.
5. **Mute-first guarantee:** if VO is removed entirely, the video still reads. VO adds voice + shareable lines, never essential plot.
6. **Loudness:** VO peaks ≈ -12 to -10 dBFS, sitting ~3 dB above the ducked BGM; overall mix target -14 LUFS integrated, true-peak ≤ -1 dBTP (matches file 05).

---

## Optional on-screen text (comment-bait, only if you want captions)
The render itself carries **zero baked-in text** (a v2 rule). If you add captions in the edit:
- Style: `INK` text on a `PAPER` pill, bottom-center, never over faces or over the finish tape, ≤3 words.
- **Caption at 0:01:** "watch the tape 👀" (plants the seed → replay bait)
- **Caption at 0:31:** "he never crossed it 💀" (the comment-driver — invites the "wait, rewatch it" reply)

---

## Alternate VO variants (A/B test for virality — pick one per upload)
- **Variant B (punchier / TikTok-style):** VO1 "POV: you bring a rocket to a race…" · VO7 "…and forget the finish line." · VO8 "skates win. every time."
- **Variant C (pure narrator, no VO):** ship mute-first with music+SFX only — highest global reach, zero localization barrier. Use this if targeting non-English audiences.
- **Variant D (question hook, comment-farming):** replace VO8 with "Would you have noticed the tape?" to drive replies. Use sparingly — it slightly weakens the series sign-off.
