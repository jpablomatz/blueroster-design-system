# <Screen name>

- **Figma:** [Light](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=<id>) · [Dark](…?node-id=<id>) · <W>×<H>
- **Platform:** Employee mobile 390 | Tablet 768 | Desktop 1440 | Admin 1440×900
- **Shell:** `br-m-app-bar` + `br-m-nav-drawer` | `br-app-shell` App=Employee/Admin
- **Content component:** `br-content-<section>-<tab>`

## Purpose
One or two sentences. No invented business rules; unknowns are TBD.

## Visual reference
![<state> · Light](img/<spec>-light.png) ![<state> · Dark](img/<spec>-dark.png)

Export PNGs from Figma (mobile 2x, desktop 1x) into `img/`. One pair per designed state.

## Anatomy (top to bottom)
| # | Block | Component | Size (w×h) | Padding (t/r/b/l) | Gap | Alignment / position | Fixed or scrolls |
|---|---|---|---|---|---|---|---|
| 1 | App bar | `br-m-app-bar` | 390×57 | 0/8/0/4 | 0 | logo centred, actions right | fixed |
| 2 | … | | | | | | |

## Tokens on this screen
| Element | Background | Text | Border | Light hex | Dark hex |
|---|---|---|---|---|---|
| … | `--br-…` | `--br-…` | `--br-…` | | |

## Typography
| Element | Family / weight | Size / line height | Color token |
|---|---|---|---|

## Formats and copy
Dates, times (12h AM/PM?), plurals, units, empty-state copy. Link `patterns/formats.md` and list only what differs.

## Layout rules
Grid, px per hour, overlap behaviour, scroll, sticky. Link `patterns/` when shared.

## Sample data
Which part of `fixtures/*.json` this screen uses.

## States
- Designed: …
- Not designed yet: loading, error, skeleton (flag, do not invent).

## Node tree
`json/<spec>.json` (trimmed export: names, layout, sizes, token bindings).
