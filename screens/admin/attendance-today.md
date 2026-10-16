# Attendance Today (Admin) — approved

- **Status:** Approved pattern (Oct 2026). Previously "Composed pattern — pending design approval".
- **Figma:** [Light](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=497-14593) · [Dark](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=497-14900) (Screens page)
- **Platform:** Admin web app, desktop 1440×900, `br-app-shell` App=Admin, page title "Attendance Today" (no tabs, no primary button)
- **Content component:** `br-content-attendance-today` ([497:4887](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=497-4887), Toolkit page)
- **Starter:** `starter/admin-attendance-today.html` · **Sample data:** `fixtures/admin.json` → `attendance`

## Purpose
Who is working, late or absent today, with each person's roster for the day.

## Layout (content 1144 wide, padding 16, gap 16, bg `--br-contrast`)
1. **Summary row:** date "Thu 8 Oct 2026" (Roboto Medium 16) + 3 `br-m-status-pill` with counts: "Working 3", "Late 1", "Absent 2".
2. **Legend:** `br-m-legend` (Shift · Tasks · Overtime · Planned overtime · Leave).
3. **`br-table`** (r8, 1px `--br-component-border`): header row of `br-table-header-cell` (EMPLOYEE 120 · POSITION 90 · SHIFT 160 · TIME 140 · STATUS 110 · roster hours 5 AM–7 PM every 2 h). Rows 52 tall, 1px `--br-divider`: `br-table-cell` Text (employee), Text secondary (position, shift, time), status pill, roster track.
4. **Roster track:** 14 h × 32 px, `br-m-event-block` 36 tall, all 5 event types; overflow rule from My Schedule Day (title ellipsis, time hidden under 120 px or at 1 h).

## Status pills
| Status | Pill variant | Token | Icon |
|---|---|---|---|
| Working | Approved | `--br-semantic1` | check_circle |
| Late | Pending | `--br-semantic3` | schedule |
| Absent | Rejected | `--br-semantic2` | cancel |

## States
- Designed: Default (Light, Dark). Not designed: loading, error, empty, filters, row tap detail (TBD).
