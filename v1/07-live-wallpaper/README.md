# v1 — Live Wallpaper ("The Wrong Scooter") · 9:16

A self-contained animated **9:16 live wallpaper** (1080×1920, 32 s seamless loop) that implements the
master timeline in [`../01-video-script.md`](../01-video-script.md) and the motion / camera /
transition / FX spec in [`../04-video-generation-prompt.md`](../04-video-generation-prompt.md).

**One file: `index.html`.** No build step, no dependencies, no network requests. All artwork is
hand-authored inline SVG generated at runtime, so it stays crisp at any resolution.

## Run it

| Target | How |
|---|---|
| Browser | Open `index.html` |
| Lively Wallpaper (Windows) | Add wallpaper → browse → select `index.html` |
| Wallpaper Engine (Windows) | Create wallpaper → Web → point at `index.html` |
| Android (KLWP/Web-based LWP) | Serve the folder and point the web wallpaper at it |
| macOS (Plash / Übersicht) | Add `file://…/index.html` as the web source |

## What it implements

| Clip | Time | Camera (file 04) | Beat |
|---|---|---|---|
| C1 | 0:00–0:02 | `WIDE.EYE.STATIC` | Hook + seed — CHIEF struts in, PIP fumbles coins, CHIEF's Vespa sits in the red zone |
| C2 | 0:02–0:06 | `MED.EYE.PUSHIN` 100→110% | Setup — draws the stamp + ticket pad, points at PIP's tyre |
| C3 | 0:06–0:11 | `MED.EYE.STATIC` + impact hold | Escalation 1 — ticket slapped on, yellow boot clamped |
| C4 | 0:11–0:16 | `MED-WIDE.PUSHIN` 100→104% | Escalation 2 — ticket mountain, medal polish |
| C5 | 0:16–0:22 | `FULL.LOW.PUSHIN` → hold | Anticipation — podium, flag, stamp to the sky |
| C6 | 0:22–0:27 | `WIDE.EYE.STATIC` | Pattern break — tow truck rolls in, hook aligns, PIP hopes |
| C7 | 0:27–0:31 | `WIDE.EYE.PUNCHIN` + 0.5 s freeze | **Twist** — his own scooter towed, his own stamp slams "TOWED" |
| C8 | 0:31–0:32 | `WIDE.EYE.STATIC` (== C1 plate) | Payoff — CHIEF hauled off, boot pops, PIP waves |

Hard cuts only — no dissolves, fades, wipes, glitch or zoom-blur. No camera rotation, orbit or
handheld. Both freezes from file 04 §B are in place (C5 hero hold, C7 "TOWED").

## URL parameters (review / QA only)

| Param | Effect |
|---|---|
| `?t=18.5` | Seek to a timecode and pause on that exact frame |
| `?captions=1` | Enable the two optional captions from file 04 §A (off by default — see below) |
| `?grid=1` | Overlay the wallpaper safe zones (top 15% / subject band / bottom 18%) |
| `?fit=cover` | Fill the screen instead of letterboxing |
| `?raw=1` | Lay out at native 1080×1920 with no scaling (for full-resolution captures) |

## Deliberate decisions worth knowing

- **Captions default to OFF.** File 04 §A offers two optional captions, but file 01's compliance
  checklist says the only on-frame text is the "TOWED" stamp. Off by default satisfies the gate;
  `?captions=1` restores them.
- **"NO PARKING" and "PARKING TICKET" are present**, matching the approved renders. This does
  contradict file 01's on-frame-text checkbox — see the divergence log in
  [`../06-wallpaper-prompt-pack.md`](../06-wallpaper-prompt-pack.md) §7 item 8.
- **The loop seam is framing-identical, not frame-identical.** Files 01 and 04 both ask for
  "last frame == first frame", which is impossible: C1 has CHIEF striding in and PIP fumbling coins,
  C8 has CHIEF hauled away and PIP waving. C8 reuses C1's exact plate — horizon, ground line, meter,
  parking lines and red-zone position — so the cut back to C1 is seamless.
- **C5 holds for ~4 s, not 1.5 s.** C5 spans 0:16–0:22 and the pose completes around 0:18, so file
  04's "~1.5 s proud hold" leaves ~4 s unaccounted for. The full remainder is held.
- **PIP's scooter is ticket-free in C8**, resolving the unstated question of what happens to the C4
  ticket mountain before the loop returns to the clean C1 plate.
- **Audio is not included.** The wallpaper is mute-first by design (file 01). The timeline matches
  [`../05-audio-bgm-sfx-reference.md`](../05-audio-bgm-sfx-reference.md) exactly, so a BGM/SFX layer
  can be dropped onto the same timecodes — including the 0:16–0:27 silence and the ~0:29 punch.

## Known limitation

The artwork is hand-authored vector, not AI-rendered. It is on-model for palette, silhouette,
costume and staging (CHIEF's cap + sash + medals, PIP's teal scarf, the locked seed position of the
Vespa), but it is **simpler and flatter than the approved reference renders** — no cel shading, no
grain, and less facial nuance. Treat it as a faithful, editable motion reference for the timeline
rather than a substitute for final rendered art.
