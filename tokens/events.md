# Event tokens (schedule events)

Extracted from Figma (`br-m-event-block` 371:5384, `br-m-legend` 371:5362, `br-m-week-day` 371:5403, `br-m-month-cell` 371:5428) and from the My Schedule frames (372:5392 / 372:6394). Values are the variables **actually bound on screen**, resolved in the `s2d` collection for Light and Dark.

> Important: on screen, **Shift is neutral gray** and **Tasks is solid blue with white text**. The Task block is bound to `br/event-shift` (which aliases `br/primary`), not to `br/event-task`. Use the table below, not the token names, to decide colors.

## Event blocks (`br-m-event-block`, Type=…)

No border on any type. Radius 4px (no radius token for 4; use `calc(var(--spacing) * 1)`). Padding 6 top/bottom, 8 left/right, gap 2 between title and time.

| Event type (Figma variant) | Legend label | Background token | Bg Light | Bg Dark | Text token | Text Light | Text Dark | Border |
|---|---|---|---|---|---|---|---|---|
| Shift | Shift | `--br-event-shift-neutral` (→ `br/neutral-light`) | `#d1d5db` | `#373c4b` | `--br-neutral-darkest` | `#121212` | `#f5f6f8` | none |
| Task | Tasks | `--br-event-shift` (→ `br/primary`) | `#1e75f6` | `#6ea3ff` | `--br-on-primary` | `#ffffff` | `#ffffff` | none |
| Overtime | Overtime | `--br-event-overtime` (→ `br/semantic1`) | `#1c9646` | `#1c9646` | `--br-on-primary` | `#ffffff` | `#ffffff` | none |
| Planned overtime | Planned overtime | `--br-special-4` | `#5a2ead` | `#5a2ead` | `--br-on-primary` | `#ffffff` | `#ffffff` | none |
| Leave | Leave | `--br-event-leave` (→ `br/semantic2`) | `#ef4444` | `#ef4444` | `--br-on-primary` | `#ffffff` | `#ffffff` | none |

**Planned overtime gap resolved:** the design uses `br/special-4` (`#5a2ead`, same in Light and Dark) for the block, the legend dot and nothing else. There is still no `br/event-planned-overtime` alias; use `--br-special-4`.

Legend order in every My Schedule frame: **Shift · Tasks · Overtime · Planned overtime · Leave** (5 items; label "Tasks" is plural, the Figma variant is "Task").

## Dots (legend, week strip, month grid)

| Where | Size | Shift | Task | Overtime | Planned overtime | Leave |
|---|---|---|---|---|---|---|
| `br-m-legend` dot | 8×8 circle, 4px gap to label | `--br-event-shift-neutral` | `--br-event-shift` | `--br-event-overtime` | `--br-special-4` | `--br-event-leave` |
| `br-m-week-day` dots | 5×5, gap 3 | `--br-event-shift-neutral` | `--br-event-shift` | `--br-event-overtime` | — (no dot in component) | — (no dot in component) |
| `br-m-month-cell` dots | 5×5, gap 3 | `--br-event-shift-neutral` | `--br-event-shift` | `--br-event-overtime` | — (no dot in component) | `--br-event-leave` |

Legend label: Roboto Regular 12, `--br-text-label` (`#00000099` Light / `#ffffffb2` Dark).

## Unused / soft tokens (exist in tokens.css, not used on these screens)

`--br-event-task` (→ `br/primary-light`), `--br-event-shift-soft`, `--br-event-task-soft`, `--br-event-overtime-soft`, `--br-event-leave-soft`. Do not use them for My Schedule blocks unless a spec says so.

## Status pills (`br-m-status-pill`, for requests)

Outline pill, transparent fill, 1px border, radius 12, height 24, padding 0 10 0 8, gap 4, icon 14 + label Roboto Medium 12. Border, icon and label share one color:

| Status | Token | Light | Dark | Icon |
|---|---|---|---|---|
| Pending | `--br-semantic3` | `#f59e0b` | `#f59e0b` | `schedule` |
| Approved | `--br-semantic1` | `#1c9646` | `#1c9646` | `check_circle` |
| Rejected | `--br-semantic2` | `#ef4444` | `#ef4444` | `cancel` |
