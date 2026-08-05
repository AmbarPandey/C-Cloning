# v2 — Voice-Over Storytelling Script ("The Victory Lap")

> A narrator VO layer synced to the master timeline in `01-video-script.md`. As in v1, the video is
> designed **mute-first** (it reads perfectly with no sound), so VO is an *amplifier*, not a crutch.
> The narration deliberately vacates the **silence beat (0:19–0:27)** so the pattern break lands.
> Total spoken ≈ 15 s across a 33 s video.

**Voice direction:** identical narrator to v1 — warm, dry, storyteller cadence, slightly amused,
never shouty. This is a **series voice**: reuse the same cloned voice for every episode so returning
viewers recognise it. (ElevenLabs: mid-range friendly narrator, stability ~0.45, similarity ~0.8,
style/exaggeration low.)

---

## Timed narration script

| # | In–Out | Line | Delivery | Leaves room for |
|---|---|---|---|---|
| VO1 | 0:00–0:03 | "The champion brought a rocket." | easy, setting the scene | strut boings, engine idle |
| VO2 | 0:03–0:07 | "The challenger brought… roller skates." | dry, land the pause | flick "pfft", aha sting |
| VO3 | 0:07–0:12 | "It went about how you'd expect." | matter-of-fact | booster #1 + doppler |
| VO4 | 0:12–0:17 | "But winning wasn't enough. He wanted a *margin*." | amused, lean on "margin" | boosters #2–#4 |
| VO5 | 0:17–0:19 | "So he went faster." | drop to near-whisper, then STOP | the music cut at 0:19 |
| — | 0:19–0:27 | **(SILENCE — no VO)** | let the fading whine + tape flutter carry it | the whole pattern break |
| VO6 | 0:27–0:30 | "He forgot one thing. You have to cross the line." | the payoff — calm, satisfying | tape SNAP + confetti + scratch |
| VO7 | 0:31–0:33 | "Slow and steady. **Every time.**" | soft button, smile in the voice | booster deflate, button ding |

**Total spoken ≈ 15 s.** Everything from 0:19–0:27 is intentionally VO-free.

> **Series signature:** VO7 closes on **"Every time."** — the same button as v1. Keep this as the
> channel's spoken sign-off on every episode; it builds the recognition loop (Character Loyalty).

---

## Sync rules (so VO, video & audio lock together — see files 04 & 05)
1. **Never talk over the twist impact.** VO6 finishes just as (or a beat before) the tape SNAP at ~0:29; the SFX owns the hit.
2. **Protect the silence.** No VO between 0:19–0:27, except optionally a single breathed *"…all of it."* at ~0:26 (≤0.6 s). Otherwise leave it clean.
3. **The "margin" line is the setup for the whole twist** — VO4 must land clearly, because it names CHIEF's fatal motive (greed for a bigger win). Do not rush it.
4. **Duck the BGM** ~4–6 dB during VO1–VO5, then release. There is nothing to duck during the silence.
5. **Mute-first guarantee:** removing the VO entirely must leave the video fully readable. VO adds voice and shareable lines, never essential plot.
6. **Loudness:** VO peaks ≈ -12 to -10 dBFS, sitting ~3 dB above the ducked bed; mix target -14 LUFS integrated, true-peak ≤ -1 dBTP (matches file 05).

---

## Optional on-screen captions (comment-bait)
The render itself carries **zero baked-in text** (a v2 rule). If you add captions in the edit:
- Style: `INK` text on a `PAPER` pill, bottom-center, never over faces or over the finish tape, ≤3 words.
- **0:01:** "watch the tape 👀" — plants Seed A → replay bait.
- **0:31:** "he never crossed it 💀" — the comment-driver; invites the "wait, rewatch it" reply.

---

## Alternate VO variants (A/B test — pick one per upload)
- **Variant B (punchier / TikTok-style):** VO1 "POV: you brought a rocket to a race…" · VO6 "…and forgot the finish line." · VO7 "skates win. every time."
- **Variant C (pure mute-first, no VO):** ship with music + SFX only. Highest global reach, zero localization barrier, and it fully preserves the language-free delivery constraint from Library 1. Use this for non-English audiences.
- **Variant D (question hook, comment-farming):** replace VO7 with "Would you have noticed the tape?" to drive replies. Use sparingly — it slightly weakens the series sign-off.
