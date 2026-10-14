# Calendar layout rules (My Schedule, mobile)

Measured from Figma frames 372:5392 (Day), 372:5508 (Week), 372:5618 (Month), all 390×844. See the PNGs in `screens/employee-mobile/img/`.

## Page frame (all three views)
1. `br-m-app-bar` — 390×57 (56 row + 1px divider `--br-component-border`). Sibling **above** Body, not inside it.
2. **Body** — vertical auto layout, padding **16 / 16 / 32 / 16**, gap **16** between blocks:
   1. `br-m-page-header` 358×85 (title 28 + gap 8 + tabs 49)
   2. `br-m-legend` 358×14
   3. `br-m-date-nav` 358×40
   4. view content (Day timeline / Week strip + agenda / Month grid + agenda)

Vertical positions inside Body: header y=16, legend y=117, date nav y=147, content y=203.

## Day view: timeline
- Container 358 wide; one `br-m-hour-row` per hour, **48px per hour** (row height 48, so 1 px = 1.25 min).
- Hour row: label column **40px** (right-aligned text) + gap **8** + line 310×1 (`--br-divider`: transparent in Light, `#ffffff1f` in Dark). Label and line both sit at the **top** of the row.
- Events area starts at **x = 48** and spans 310px.
- **Event geometry:** `top = (start − firstHour) × 48 + 4`, `height = duration_h × 48 − 8` (4px inset top and bottom). Example: 6:00–16:00 with first hour 5 AM → top 52, height 472.
- **Overlapping events go side by side in equal columns**, never stacked: with 2 overlapping events each column is **150px** wide with a **6px** gap (x 48–198 and 204–354), leaving 4px on the right. General rule derived from that: `colWidth = (310 − 4 − 6 × (n − 1)) / n`. Layout for 3+ overlaps is not drawn in Figma (TBD — ask).
- Column order in the design: **Shift first (left), then Task**.
- Event block internals: padding 6/8, gap 2, radius 4, title wraps, time on its own line.

## Week view
- Week strip 358×71: 7 × `br-m-week-day` (48×71), horizontal, space-between (≈3–4px gaps). Day item: padding 6/0/6/0, gap 4; weekday 11px; day circle 32×32 radius 16; dot row (5px dots, gap 3) under it. States: Default, **Today** (circle `--br-primary`, number `--br-on-primary`), **Selected** (whole item bg `--br-primary-lightest`, radius 8).
- Agenda below (y=290): vertical, gap **14** between days. Each day: heading (Roboto Medium 13, `--br-text-label`) + gap 6 + full-width (358) event blocks stacked with gap 6. Here blocks are 41px tall (not time-scaled).

## Month view
- Weekday initials row 13px tall, 7 equal columns (≈51px), centred.
- Grid: 6 week rows × **52px**; cells 51×52 with a **1px top border** (`--br-divider`), padding-top 4, gap 4: day circle 26×26 radius 13, then a dot row. Outside-month days use `--br-component-disabled`. Today: circle `--br-primary`. Selected: cell bg `--br-primary-lightest`.
- After the grid (gap 16): agenda of the selected day, same structure as the Week agenda.

## Scroll and sticky
- What Figma shows: the app bar is outside Body; Body content in Day is 811px tall in an 844 frame (787 below the app bar), so Body scrolls under a fixed app bar.
- Overtime has an explicit scrolled state (341:677 "Sticky filters"): app bar + a collapsed filter bar stay pinned, cards scroll. Use the same idea for calendars: **app bar fixed**.
- Whether page header/tabs, legend and date nav stick on My Schedule is **not designed** — keep them in the scroll flow and flag it (TBD).

## Implementation
- Production calendars use Mobiscroll (`br-mobiscroll-*`) per AGENTS.md; apply these measurements through its theme. For static mockups use `starter/`.
