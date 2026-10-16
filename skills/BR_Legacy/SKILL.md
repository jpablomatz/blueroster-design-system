---
name: BR_Legacy
description: Design or build any Blue Roster screen in the Blue Roster Legacy style (Figma "Design System Legacy"). Use when the request says @BR_Legacy, Blue Roster, Blue Roster Legacy or BR.
---

# @BR_Legacy — Blue Roster Legacy skill

Invoke with `@BR_Legacy <simple request>`, e.g. `@BR_Legacy agenda para que el admin vea quién faltó y quién trabaja hoy`.
Repo: https://github.com/jpablomatz/blueroster-design-system · Raw base: `https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/`
Full context in one file: `llms-full.txt`.

## Cheat sheet (memorize before starting)

| Event | Token | Light | Dark | Text on it |
|---|---|---|---|---|
| Shift | `--br-event-shift-neutral` | #d1d5db | #373c4b | normal text |
| Tasks | `--br-event-shift` | #1e75f6 | #6ea3ff | white |
| Overtime | `--br-event-overtime` | #1c9646 | #1c9646 | white |
| Planned overtime | `--br-special-4` | #5a2ead | #5a2ead | white |
| Leave / absent | `--br-event-leave` | #ef4444 | #ef4444 | white |

- Hex values are for reading only. In code use the CSS variables from `tokens/tokens.css`.
- Time: 12h (`6:00 am - 4:00 pm`, hour labels `5 AM`). Dates: `Thu 8 Oct 2026`. Default day range is 5 AM–4 PM.
- Calendar geometry: 48px per hour; overlapping events sit in equal side-by-side columns (`patterns/calendar-layout.md`).
- Type: Roboto (some legacy components use Inter, a known inconsistency, so do not copy it). Icons: Material Icons Outlined (`<span class="mi">name</span>`). The filter icon is `filter_alt`.
- Filters: 1–3 inline; 4 or more go in one `br-filter-dialog` opened by `br-filter-button`.
- Mobile first: 390 → 768 → desktop. Light (`:root`) and Dark (`[data-theme="dark"]`).
- Employee shell: `br-app-shell` with `App=Employee`. Admin specs are drawn at 1440×900.
- **Light and Dark side by side:** event tokens such as `--br-event-shift-neutral` are aliases (`var(--br-neutral-light)`). An alias resolves where it is declared, so if it only lived on `:root`, a `<div data-theme="dark">` inside a Light page kept the Light event colors. `tokens/tokens.css` now re-declares all 74 alias tokens on `[data-theme="light"], [data-theme="dark"]`, so `data-theme` works on any container out of the box. If you copy tokens into another file, keep that alias block (or use one iframe per theme).
- Day sample (`fixtures/schedule.json`, Thu 8 Oct 2026) now has all 5 event types: Shift, Tasks, Planned overtime 5–6 am, Leave 12–2 pm, Overtime 5–7 pm (placeholders reusing existing fixture text; range extended to 7 PM). Overlapping events go side by side in columns.

## Workflow

### 1. Find the closest screen
Open the keyword → spec table in `llms.txt` (or `AGENTS.md` → Playbook) and match the request words. Name the spec you picked and why. If two match, pick one and say so.

### 2. Start from what exists, never from scratch
For the chosen spec, load:
- the spec `screens/<group>/<name>.md` (read its **Anatomy** section),
- the PNGs `screens/<group>/img/<name>-light.png` and `-dark.png`,
- the node tree `screens/<group>/json/`,
- the closest starter in `starter/` (`my-schedule-day.html`, `admin-attendance-today.html`, `components.html`) with `starter/br-m.css`.
Copy the starter and edit it. Keep its classes, spacing and structure.

### 3. Use only Blue Roster tokens and formats
- Colors: `br/*` tokens only (`--br-…`), events per the cheat sheet (`tokens/events.md`).
- Spacing, radius and type: `--spacing`, `--radius-*`, `--text-*`, `--font-weight-*`.
- Formats per `patterns/formats.md`. No hard-coded hex, rgb or px where a token exists.

### 4. Reuse components
Use only what is documented in `components/` and shown in `starter/components.html`: `br-m-app-bar`, `br-m-page-header`, `br-page-tab`, `br-m-legend`, `br-m-date-nav`, `br-m-timeline`, `br-m-event-block`, `br-m-status-pill`, `br-m-avatar`, `br-chip`, `br-button`, `br-filter-button`, `br-filter-dialog`, `br-table` and Mobiscroll (`br-mobiscroll-*`) for calendars. Do not redraw a component in raw HTML.

### 5. Missing pattern? Compose it and flag it
If no spec covers the request (for example a multi-employee admin calendar or attendance view):
1. Compose it from existing pieces: schedule and timeline (`my-schedule-day`), event blocks, legend, date nav, avatars, status pills and filters.
2. Label it in the output: **"Composed pattern — pending design approval"**.
3. Write an **Assumptions** list (layout, states, colors chosen, copy, data) and a **Questions** list for the designer.
4. Never invent new tokens, components, business rules, prices or legal text. Unknown items stay `TBD`.
5. Use sample data only from `fixtures/schedule.json`, or neutral placeholders such as "Employee 1". No real-looking names.

### 6. Self-check before you answer
- [ ] I named the spec and starter I followed.
- [ ] Every color is a `--br-*` variable, and the event colors match the cheat sheet.
- [ ] Times are 12h, dates look like `Thu 8 Oct 2026`, hours run 5 AM–4 PM unless the spec says otherwise.
- [ ] Roboto plus Material Icons Outlined; no Inter, no other icon sets.
- [ ] Filters: 1–3 inline, 4+ in `br-filter-dialog` with `filter_alt`.
- [ ] Only existing components; no new ones were invented.
- [ ] Mobile 390 first; Light and Dark both work (`?theme=dark`).
- [ ] Composed patterns are labeled, with Assumptions and Questions listed.
- [ ] Placeholder data only, and gaps are marked `TBD`.
- [ ] One view delivered; I am asking for review before the next one.

## Output format
1. **Based on:** spec + starter.
2. The code (HTML/CSS or framework requested) or the Figma frame.
3. **Assumptions** and **Questions** (always, even if short).
4. The checklist result.
