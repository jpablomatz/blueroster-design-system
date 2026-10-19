---
name: BR_Legacy
description: Design or build Blue Roster screens in the Blue Roster Legacy style. Use when the user writes @BR_Legacy, Blue Roster, Blue Roster Legacy or BR. Also covers Blue Roster marketing (banners, questionnaire landing, blueroster.com) through Marketing mode.
---

# BR_Legacy (Claude Skill)

Before answering, fetch and follow these files. They are the source of truth:
1. Skill workflow: https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/skills/BR_Legacy/SKILL.md
2. Full context (rules, tokens, components, specs): https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/llms-full.txt
3. Starters: https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/starter/br-m.css, https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/starter/my-schedule-day.html, https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/starter/admin-attendance-today.html
4. Screen PNGs: https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/screens/<group>/img/<name>-light.png (and -dark.png)
5. Marketing (banners, landing): https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/marketing/README.md, https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/marketing/foundations.md, https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/marketing/landing.md, https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/marketing/banners.md, https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/tokens/marketing.css

If you cannot fetch them, use the copy below.


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
- **Event block overflow (My Schedule Day, 3+ overlapping):** the title stays on one line with an ellipsis; the time line is hidden when the column is under 120 px wide or the event lasts 1 h (40 px tall); with 4+ overlapping events show 3 columns plus a `+N` pill (`br-m-event-more`) for the rest. `starter/br-m.css` and `starter/my-schedule-day.html` implement it (`is-compact` class).
- **Proposals (new, not in Legacy):** coverage holes (`--br-event-hole`, `br-event-hole`, `br-coverage-warning`) and Shift swap request cards live in `proposals/` and Figma page "Proposals · not in Legacy". Use them only when the user asks for coverage holes or shift swap, and label output "Proposal — new, not in Legacy".
- Day sample (`fixtures/schedule.json`, Thu 8 Oct 2026) now has all 5 event types: Shift, Tasks, Planned overtime 5–6 am, Leave 12–2 pm, Overtime 5–7 pm (placeholders reusing existing fixture text; range extended to 7 PM). Overlapping events go side by side in columns.

## Workflow

### 1. Find the closest screen
Open the keyword → spec table in `llms.txt` (or `AGENTS.md` → Playbook) and match the request words. Name the spec you picked and why. If two match, pick one and say so.

### 2. Start from what exists, never from scratch
For the chosen spec, load:
- the spec `screens/<group>/<name>.md` (read its **Anatomy** section),
- the PNGs `screens/<group>/img/<name>-light.png` and `-dark.png`,
- the node tree `screens/<group>/json/`,
- the closest starter in `starter/` (`my-schedule-day.html`, `admin-attendance-today.html` (approved, desktop 1440), `components.html`) with `starter/br-m.css`.
Copy the starter and edit it. Keep its classes, spacing and structure.

### 3. Use only Blue Roster tokens and formats
- Colors: `br/*` tokens only (`--br-…`), events per the cheat sheet (`tokens/events.md`).
- Spacing, radius and type: `--spacing`, `--radius-*`, `--text-*`, `--font-weight-*`.
- Formats per `patterns/formats.md`. No hard-coded hex, rgb or px where a token exists.

### 4. Reuse components
Use only what is documented in `components/` and shown in `starter/components.html`: `br-m-app-bar`, `br-m-page-header`, `br-page-tab`, `br-m-legend`, `br-m-date-nav`, `br-m-timeline`, `br-m-event-block`, `br-m-status-pill`, `br-m-avatar`, `br-chip`, `br-button`, `br-filter-button`, `br-filter-dialog`, `br-table` and Mobiscroll (`br-mobiscroll-*`) for calendars. Do not redraw a component in raw HTML.

### 5. Missing pattern? Compose it and flag it
If no spec covers the request (for example a multi-employee mobile calendar):
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

## Marketing mode (banners, landing, blueroster.com)
Use this instead of steps 1–6 when the request is about a banner, post, LinkedIn/Instagram/Story, campaign, the questionnaire landing, Wix or a blueroster.com section.
1. Read `marketing/README.md`, then `marketing/foundations.md` (decisions, colors, 20 `mkt` text styles, grid, spacing) and `tokens/marketing.css` (`--mkt-*`).
2. Landing or form → `marketing/landing.md` (`mkt-*` components, flow, copy, Wix notes). Banner or post → `marketing/banners.md`. Match the PNGs in `marketing/references/`.
3. Inter only (Black for display/H1 and banner headlines; H2–H4 Semi Bold). Light page; Navy `#002458` only as a band. Buttons `#064DB7` + White on light, White `#F9F9F9` + Navy text on Navy. `#1E75F6` is never text. Orange `#F66C1E`: accent only, Navy text on it, never white, never a button.
4. Copy verbatim from blueroster.com or approved lines; headlines in sentence case + period. Approved stats only, per vertical. No quotes, testimonials, names, prices or "free" (say "light version", up to 50 users). Links in the first comment. Market: US only.
5. Screen banners: Attendance Today, My Schedule Day, Overtime cards, Light captures at 2x, role-based example data, current dates, no real names.
6. Self-check: text contrast ≥ 4.5:1; minimum sizes (support ≥ 24 px, eyebrow/button ≥ 20 px on 1080/1200, Display ≥ 12 px); Story safe zone 250 px top and bottom; every line has a source; gaps stay `TBD`. Output: **Based on** (file + reference PNG), the piece, Assumptions, Questions, checklist.

## Output format
1. **Based on:** spec + starter.
2. The code (HTML/CSS or framework requested) or the Figma frame.
3. **Assumptions** and **Questions** (always, even if short).
4. The checklist result.
