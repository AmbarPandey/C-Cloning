# Model Sheet — CHIEF

> **This is CHIEF's locked visual spec.** The channel-wide character system that governs CHIEF (class,
> lifecycle, asset/naming standards, validation) lives in the
> [Character Bible](../design/CHARACTER_BIBLE.md); CHIEF is a **Bully / Antagonist** in its
> [taxonomy](../design/CHARACTER_BIBLE.md#character-taxonomy). This sheet owns the exact design values.

- **Asset ID:** `CHAR_CHIEF_v1`
- **Role archetype:** Pompous authority figure / antagonist (the "power-abuser" whose own
  overconfidence triggers his comeuppance).
- **Function in the system:** the recurring authority foil for [SC1 Authority](../../intelligence/04-scenario-intelligence-library.md) scenarios and [NP1 Comeuppance](../../intelligence/06-narrative-pattern-library.md) patterns.

## Silhouette & build
Short and round but puffed-up; struts with chest out and chin high. ~2.5 heads tall. Big head,
small legs, oversized white gloves for expressive gestures. Instantly readable as "self-important
official" even in black silhouette at thumbnail size.

## Design spec

| Feature | Spec |
|---|---|
| Body | Rotund; stiff, upright posture; heels-together strut |
| Uniform | `POP_TEAL` warden jacket, gold buttons, oversized peaked cap with a badge |
| Sash / medals | Diagonal `BRAND_YELLOW` sash covered in (unearned) medals — his vanity tell |
| Face | Bushy brows, tiny mustache, permanent smug half-smile; small eyes |
| Hands | Oversized white gloves (for stamp/point gestures) |
| Palette | Jacket `POP_TEAL` · sash/medals `BRAND_YELLOW` · trim `INK` · face `PAPER` |

## Signature props (reusable asset IDs)
| Prop | ID | Notes |
|---|---|---|
| Oversized ticket pad | `PROP_ticketpad_v1` | Comically large; tears sheets with a flourish |
| Giant rubber stamp | `PROP_stamp_v1` | His "power object"; used to stamp tickets — and, in the twist, used *on him* |
| Wheel boot / immobilizer | `PROP_boot_v1` | `BRAND_YELLOW`; clamps wheels |
| CHIEF's scooter | `PROP_chief_scooter_v1` | **Plot-critical:** it is parked in the no-parking zone in frame 1 (the seed) |

## Expression pack
`CHAR_CHIEF_expr_neutral · _smug · _gloating · _shocked · _panicked · _deadpan`
(default resting face = **smug**; adds `_triumphant` at the L3 peak). Canonical emotions, intensity
levels, and the pride ladder: [Expression Library → CHIEF](../design/EXPRESSION_LIBRARY.md#character-overrides).

## Personality (for pose/timing, not dialogue)
Vain, petty, drunk on small power, oblivious to his own hypocrisy. He never speaks in A1 — all
character is carried by strut, gloat, and the final open-mouthed shock.

## Consistency notes
- Cap + sash + medals must appear in **every** shot; they are his silhouette.
- Default expression is smug; he only breaks to **shocked → panicked** at the twist.
- Do not slim him down or remove medals between shots.
