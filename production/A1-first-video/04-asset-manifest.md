# A1 — Asset Manifest (Stage 6 output)

Every asset needed to render A1, tagged **reuse** (already in the library) vs **new** (created for
A1, then added to the library). IDs follow the [Stage 2](../../docs/12-stage-2-channel-operating-system.md)
convention. Target: ~70% reusable at scale; for the *first* build most assets are new-but-additive.

## Characters
| Asset | ID | Status | Notes |
|---|---|---|---|
| CHIEF (+ expression pack) | `CHAR_CHIEF_v1` | new (launch cast) | [model sheet](../characters/chief.md) |
| PIP (+ expression pack) | `CHAR_PIP_v1` | new (launch cast) | [model sheet](../characters/pip.md) |

## Expressions used (from the packs)
`CHAR_CHIEF_expr_smug · _gloating · _shocked · _panicked` · `CHAR_PIP_expr_worried · _teary · _hopeful · _relieved · _wave`

## Props
| Asset | ID | Status | Scenes |
|---|---|---|---|
| Oversized ticket pad | `PROP_ticketpad_v1` | new | 2,4 |
| Giant rubber stamp | `PROP_stamp_v1` | new | 2,3,4,5,7 |
| Wheel boot / immobilizer | `PROP_boot_v1` | new | 3,8 |
| CHIEF's scooter (seed) | `PROP_chief_scooter_v1` | new | 1,6,7 |
| PIP's scooter | `PROP_pip_scooter_v1` | new | 1,3,8 |
| PIP's coin purse | `PROP_pip_coins_v1` | new | 1 |
| Tow truck | `PROP_towtruck_v1` | new | 6,7 |
| Ticket sheet | `PROP_ticket_v1` | new | 3,4 |
| Podium + tiny flag | `PROP_podium_v1` | new | 5 |
| Medals (on sash) | part of `CHAR_CHIEF_v1` | new | all |

## Backgrounds
| Asset | ID | Status | Scenes |
|---|---|---|---|
| Parking-lot wide | `BG_parkinglot_v1` | new | 1,6,7,8 |
| Parking-lot medium (meter area) | `BG_parkinglot_meter_v1` | new | 2,3,4 |
| No-parking zone marking | `BG_noparking_zone_v1` | new | 1,6,7 |

## UI / on-frame text
| Asset | ID | Status | Scenes |
|---|---|---|---|
| "TOWED" stamp mark | `UI_towed_stamp_v1` | new | 7 |

## Effects
| Asset | ID | Status | Scenes |
|---|---|---|---|
| Comedy impact star-burst | `FX_impact_star_v1` | reuse (generic) | 7 |
| Sparkle/gleam | `FX_sparkle_v1` | reuse (generic) | 5 |
| Motion lines | `FX_motionlines_v1` | reuse (generic) | 3,7 |

## Audio (see [06-audio-package](06-audio-package.md))
| Asset | ID | Status |
|---|---|---|
| Comedy music bed | `MUS_comedy_bed_v1` | new (cleared/owned) |
| Stamp thunk | `SFX_stamp_v1` | new |
| Boot clamp | `SFX_clamp_v1` | new |
| Truck rumble | `SFX_truck_v1` | new |
| Impact/anvil punch | `SFX_punch_v1` | reuse (generic) |
| Record-scratch reversal | `SFX_scratch_v1` | reuse (generic) |
| Button ding / pop | `SFX_button_v1` | reuse (generic) |

## Transitions
Hard cuts only (per [editing spec](07-editing-spec.md)); no dissolves. Transition asset: none.

## Reuse economics
- **This build:** ~30 new assets (launch cast + first parking-lot pack). All are **library-additive**.
- **Next videos:** CHIEF, PIP, expression packs, boot/stamp/ticket props, comedy SFX, and music
  become **reuse** — collapsing per-video asset work toward the sub-45-min ([later sub-30-min](../../docs/12-stage-2-channel-operating-system.md)) target.
