# My Schedule · Day

- **Platform:** Employee app · Mobile (390; tablet 768 where noted)
- **Shell:** `br-m-app-bar` + `br-m-nav-drawer`

## Components
br-m-date-nav, br-m-hour-row, br-m-event-block, br-m-legend

## Designed states / frames
- **My Schedule · Day**: [Light](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=372-5392) 390×844 · [Dark](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=372-6394) 390×844

## Not designed yet
Loading, error, skeleton. Do not invent them silently; flag in the PR and follow README gaps.

## Detailed anatomy (top to bottom, 390×844)

Read with `tokens/events.md`, `tokens/typography.md`, `patterns/formats.md`, `patterns/calendar-layout.md`. Starter markup: `starter/`. Sample data: `fixtures/schedule.json`.

| # | Block | Component | Size | Padding t/r/b/l · gap | Contents and alignment | Fixed / scroll |
|---|---|---|---|---|---|---|
| 1 | App bar | `br-m-app-bar` | 390×57 | row 56: 0/8/0/4 · bottom divider 1px `--br-component-border` | **Left:** menu icon button 48×48 (`menu`, 24, `--br-neutral-darkest`). **Centre:** `br-logo` Isotype 32×34 at x 153. **Right:** notifications 48×48 with badge (17×18, r9, `--br-primary`, count Roboto Bold 11) + account 48×48 with 32px initials avatar (`--br-neutral-light`, "JM" Roboto Medium 13). Bg `--br-contrast`. | fixed (outside Body) |
| 2 | Body | frame | 390 wide | 16/16/32/16 · gap 16 | Holds rows 3–6. Bg `--br-contrast`. | scrolls |
| 3 | Page header | `br-m-page-header` | 358×85 | gap 8 | Title "My Schedule" Roboto Bold 24 (28 tall), left. Tabs strip 48 + 1px divider: 3 equal `br-page-tab` (≈119 wide, padding 0 16, gap 8, icon 24 + label Roboto Medium 15). Active: `--br-primary-dark` text/icon + 2px bottom border; default `--br-text-label`. | in flow (sticky TBD) |
| 4 | Legend | `br-m-legend` | 358×14 | gap 12 between items, 4 dot→label | Shift · Tasks · Overtime · Planned overtime · Leave; 8px dots; Roboto Regular 12 `--br-text-label`. Left aligned. | in flow |
| 5 | Date nav | `br-m-date-nav` | 358×40 | 0/0/0/4 · gap 4 | **Left:** label Roboto Medium 14 (fills width). **Right:** `chevron_left` 24 · **Today** pill (padding 6/10, 1px `--br-component-border`, r16, Roboto Medium 13) · `chevron_right` 24. | in flow |
| 6 | Timeline | frame of `br-m-hour-row` | 358×576 | — | 12 rows × 48 (5 AM → 4 PM). Each row: 40px right-aligned label (Roboto Regular 11 `--br-text-label`) + gap 8 + 310×1 line `--br-divider`; label and line at the row top. Events absolutely positioned from x 48: **Shift** (48, 52) 150×472 `--br-event-shift-neutral`, **Task** (204, 52) 150×472 `--br-event-shift`, side by side, 6px gap. | scrolls with Body |

Body content height is 811 (16 + 85 + 16 + 14 + 16 + 40 + 16 + 576 + 32), taller than the 787 px under the app bar.

## Event overflow (approved)

Applies when 3 or more events overlap in the Day timeline (width per column = (310 − 4 − 6·(n−1)) / n).

- **Title:** one line, ellipsis (`white-space: nowrap; overflow: hidden; text-overflow: ellipsis`).
- **Time line:** hidden when the column is under 120 px wide (3 columns = 98 px) or the event lasts 1 h (40 px tall). Class `is-compact`.
- **4+ overlapping:** show 3 columns; the rest collapse into a `+N` pill (`br-m-event-more`, 20 tall, r10, padding 0 6, Roboto Medium 11, bg `--br-neutral-darkest`, text `--br-contrast`) at the top-right of the 3rd column. Tapping it opens the day agenda (TBD).

## Visual reference

Exported from Figma (mobile at 2x, desktop/admin at 1x). Match these pixel-for-pixel before anything else.

**My Schedule · Day**

![My Schedule · Day · Light](img/my-schedule-day-light.png) ![My Schedule · Day · Dark](img/my-schedule-day-dark.png)

## Anatomy (extracted from the Light frame)

Order is top to bottom as in the Figma layer tree. x,y are relative to the parent. Paddings are top/right/bottom/left in px. Tokens are the variables bound in Figma. Full trimmed tree: see `json/`.

### My Schedule · Day (`372:5392`)

| Layer | Component / type | x,y | Size | Layout · tokens |
|---|---|---|---|---|
| App bar | `br-m-app-bar` | 0,0 | 390×57 | vertical, gap 0, padding 0/0/0/0; bg br/contrast |
| ↳ Row | `fram` | 0,0 | 390×56 | horizontal, gap 0, padding 0/8/0/4 |
| ↳ Divider | `rect` | 0,56 | 390×1 | bg br/component-border |
| Body | `fram` | 0,57 | 390×811 | vertical, gap 16, padding 16/16/32/16 |
| ↳ Page header | `br-m-page-header` | 16,16 | 358×85 | vertical, gap 8, padding 0/0/0/0 |
| ↳ Legend | `br-m-legend` | 16,117 | 358×14 | horizontal, gap 12, padding 0/0/0/0 |
| ↳ Date nav | `br-m-date-nav` | 16,147 | 358×40 | horizontal, gap 4, padding 0/0/0/4 |
| ↳ Timeline | `fram` | 16,203 | 358×576 |  |

Node tree: [`json/my-schedule-day.json`](json/my-schedule-day.json)

