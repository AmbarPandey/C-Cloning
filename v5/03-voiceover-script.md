# v5 — Voice-Over Storytelling Script ("The Case of the Missing Pie") · **LONG FORM**

> A narrator VO layer synced to the master timeline in `01-video-script.md`. As always the video is
> **mute-first** — it reads with sound off — so VO is an *amplifier*, not a crutch. But long form leans on
> narration harder than Shorts do: at 90 seconds the narrator is the thread that holds four separate
> comedy cycles into one story, and the deadpan case-file voice is a large part of the entertainment.
> Total spoken ≈ **34 s across 90 s** (38% speech density — roughly double the Shorts ratio, still leaving
> more than half the runtime for visual comedy and the silence).

**Voice direction:** the same narrator as v1–v4 — warm, dry, storyteller cadence, slightly amused, never
shouty. For v5 he adopts a **deadpan police-report register**: clipped, factual, faintly bureaucratic,
delivering absurd details with a completely straight face. The comedy comes from treating a missing pie
with the gravity of a homicide. He is **never** in on the joke and **never** ahead of CHIEF.
(ElevenLabs: mid-range friendly male/neutral narrator, stability ~0.50 (slightly higher than Shorts for the
flatter register), similarity ~0.8, style/exaggeration low.)

---

## Timed narration script

| # | In–Out | Line | Delivery | Leaves room for |
|---|---|---|---|---|
| VO1 | 0:01–0:03 | "At eleven o'clock this morning, a crime was committed." | flat, official, ominous | the gasp sting at 0:01 |
| VO2 | 0:03–0:07 | "The victim: one pie. The scene: the market square." | clipped case-file listing | **the two seed sounds at 0:05–0:06** |
| VO3 | 0:07–0:12 | "And in the absence of anyone qualified… he appointed himself." | dry, the first real joke | lens whoosh, notebook flick |
| VO4 | 0:13–0:17 | "Suspect one. Motive: obvious." | brisk, confident | the accusation sting, dog snore |
| VO5 | 0:18–0:23 | "Muzzle: clean. Lead: three feet. Table: nine." | pure deadpan list — do not smile | lens ting, lead twang, deflate |
| — | 0:23–0:28 | **(no VO — micro-payoff 1)** | let BUD's yawn play | the laugh |
| VO6 | 0:29–0:33 | "Suspect two. Silent. Watchful. Suspiciously clean." | building, faintly ridiculous | the bigger sting, one meow |
| VO7 | 0:34–0:39 | "Suspect two is four inches tall. The pie was nine." | flat, defeated by arithmetic | tape zip and snap |
| — | 0:39–0:44 | **(no VO — micro-payoff 2)** | let the cat's indifference play | the laugh, the 0:41 seed drip |
| VO8 | 0:45–0:50 | "And then — a break in the case." | a genuine lift; the narrator believes it | the XL gasp at 0:47 |
| VO9 | 0:51–0:56 | "He had crumbs. He had proximity. He had, and I quote, 'a look about him.'" | build the list, land "a look about him" | three pin thunks, brass stab |
| VO10 | 0:57–1:00 | "Case closed." | absolute, final, satisfied | the stamp whoosh, crowd inhale |
| — | 1:02–1:08 | **(no VO — the turn)** | let the music un-build | every character turning to look |
| — | **1:08–1:18** | **(SILENCE — no VO)** | the 10-second dread beat | creak at 1:12, drip at 1:15 |
| VO11 | 1:19–1:24 | "There was no thief. There was a man who put his ledger down." | quiet, almost gentle — the payoff | the stinger, the stamp thud at 1:20 |
| VO12 | 1:28–1:30 | "Every time." | soft button; a tiny smile at last | applause, button ding |

**Total spoken ≈ 34 s.** Four deliberate VO-free windows: 0:23–0:28, 0:39–0:44, 1:02–1:08, **1:08–1:18**.

---

## The four rules that make this script work

1. **The narrator is not smarter than CHIEF.** He reports the investigation as credible right up to VO10
   ("Case closed."). If he winks, hedges, or foreshadows, the reveal has nothing to overturn. He is
   surprised at 1:19 too.
2. **VO5 and VO7 are the comic engine.** Both are flat factual lists whose humour comes entirely from the
   arithmetic being stated without comment ("Table: nine." / "The pie was nine."). Do not add inflection,
   do not add a punchline beat — the flatness *is* the joke.
3. **The two unnarrated payoff windows are non-negotiable.** At 0:23–0:28 and 0:39–0:44 the visual gag
   (BUD's yawn, the cat's indifference) must play with no voice over it. Narrating a deadpan animal
   reaction kills it.
4. **VO11 names the cause, not the culprit.** "A man who put his ledger down" is the whole thesis of the
   episode — no crime, just carelessness. It must land *after* the visual reveal, never before.

> **Series signature:** VO12 closes on **"Every time."** — same as v1–v4. Non-negotiable channel sign-off.

---

## Sync rules (so VO, video & audio lock together — see files 04 & 05)
1. **Protect the 10-second silence (1:08–1:18) absolutely.** No VO, except optionally a single breathed *"…oh no."* at ~1:16 (≤0.7 s). Nothing may cover the 1:12 creak or the 1:15 drip.
2. **VO2 must not talk over the seeds.** The seed sounds land at 0:05–0:06 (ledger clunk, table creak, box thud). Phrase VO2 so there is a natural gap across those two beats — the audience should *hear* the cause being created even while the narrator lists the case details.
3. **VO11 starts at 1:19, one second after the reveal frame at 1:18.** The image lands first, the explanation second. Never the reverse.
4. **Duck BGM ~5 dB under all VO**, release fully in the four VO-free windows.
5. **VO10 "Case closed." must sound completely sincere.** It is the last line before the collapse, and its confidence is what makes the silence that follows unbearable.
6. **Mute-first guarantee:** strip all VO and the video still reads — ledger → tilt → trail → box is pure geometry. VO adds voice, jokes and shareable lines, never essential plot.
7. **Loudness:** VO peaks ≈ -12 to -10 dBFS, ~3 dB above the ducked bed; mix target -14 LUFS integrated, true-peak ≤ -1 dBTP (matches file 05).

---

## Optional on-screen text (added in the edit — the render is text-free)
Long form supports slightly more on-screen text than Shorts, and a case-file motif suits it:
- Style: `INK` text on a `PAPER` card, upper-left, heavy geometric sans, ≤4 words. Never over a face, never over the corkboard, never over the evidence box.
- **0:12 "SUSPECT 1"** · **0:28 "SUSPECT 2"** · **0:44 "SUSPECT 3"** — chapter cards that reinforce the case-file structure and give the viewer a sense of progress (a real retention device in long form: it signals "there's more coming").
- **Do not** add a card at 1:08. The silence must arrive unannounced.
- Optional closing card **1:26 "CASE CLOSED"** with the word struck through.

---

## Alternate VO variants (A/B test — pick one per upload)
- **Variant B (mock true-crime):** lean the register further into documentary parody — "The market square. Eleven a.m. A community, shattered." Higher comedy ceiling, slightly narrower international appeal because it parodies a specific genre.
- **Variant C (pure mute-first, no VO):** music + SFX only. **Not recommended for v5.** Unlike v1–v4, this episode's four-cycle structure genuinely benefits from a narrator to bind it; without VO the middle section (0:12–0:44) risks reading as repetitive. Use the "SUSPECT 1/2/3" cards if you go this route.
- **Variant D (PIP's perspective):** re-voice as PIP's quiet retelling ("I was just eating a biscuit"). Warmer and more parasocial, drives Subscribe over Share — worth testing later, but it weakens the deadpan-report comedy that is v5's main engine.
