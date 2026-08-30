# ElevenLabs — Usage Guide

Voice generation for the fixed cast. ElevenLabs is the locked voice tool
([Stage 1.5](../../docs/11-stage-1_5-business-decisions.md), [D-20](../../docs/21-decision-log.md)):
"best quality + API scale; clone fixed cast voices."

> **A1 uses no voice** (0 spoken words, mute-first). This guide readies the pipeline for **future
> dialogue videos** so voice is a one-time setup, then reuse.

## One-time setup (per cast member)
1. Create/clone a **fixed voice** for each speaking character; record the **voice ID**.
2. Lock voice settings (stability, similarity, style) so the character sounds identical across videos.
3. Store voice IDs in the cast reference (add to each [model sheet](../characters/README.md)) and the
   automation secret store — **never** commit API keys.

## Per-video workflow (dialogue videos only)
1. Extract the dialogue/narration lines from the [script](../A1-first-video/02-script.md) `DLG`/`VO` fields.
2. Batch-generate each line with the character's locked voice ID.
3. Keep lines **minimal and visual-led** (per [Stage 1.5](../../docs/11-stage-1_5-business-decisions.md));
   the video must still be mute-readable.
4. Hand VO tracks to [Anijam](anijam-usage.md) for optional lip-sync, then to the editor.

## Loudness
- Normalize VO to sit under the music bed; overall mix ~ -14 LUFS (see [audio package](../A1-first-video/06-audio-package.md)).

## Retry / fallback
| Symptom | Action |
|---|---|
| Voice inconsistent between videos | Reuse the exact locked voice ID + settings; never re-clone per video |
| Line too long / breaks pacing | Trim to the Stage 2 words/sec target; prefer visual over dialogue |
| Mispronunciation | Use phonetic spelling / SSML for that word |

## Output
Batch VO audio files (dialogue videos) — or **nothing for mute-first videos like A1**.
