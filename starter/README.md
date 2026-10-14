# starter/ — plain HTML/CSS for mockups

For **static mockups only** (Claude, Figma Make, quick prototypes outside Angular). Production code uses the Angular `br-*` components from Storybook (see `AGENTS.md`).

| File | What |
|---|---|
| `br-m.css` | Classes for the mobile components: `br-m-app-bar`, `br-m-page-header` + `br-page-tab`, `br-m-legend`, `br-m-date-nav`, `br-m-hour-row` + timeline, `br-m-event-block` (5 types), `br-m-week-day`, `br-m-month-cell`, agenda, `br-m-status-pill`, cards (`br-m-request-card`, `br-overtime-card`, `br-m-balance-card`, `br-chip`), `br-filter-button`, `br-m-filter-bar`, `br-filter-dialog` (Mobile), `br-select-field`. Imports `../tokens/tokens.css`; colors only via `var(--br-*)`. |
| `components.html` | Gallery with copy-paste markup for every snippet. `?theme=dark` for Dark. |
| `my-schedule-day.html` | Full My Schedule · Day page assembled from the snippets, with the timeline geometry from `patterns/calendar-layout.md`. |
| `_verify/compare-light.png`, `compare-dark.png` | Side by side: Figma export (left) vs headless Chrome render of `my-schedule-day.html` (right), 390×844 @2x. Mean pixel difference ≈ 2/255. |

Fonts: Roboto (400/500/700) and Material Icons Outlined from Google Fonts. Logo: `../assets/br-logo-isotype-{light,dark}.svg`.
Keep the folder structure (`starter/`, `tokens/`, `assets/` side by side) so relative paths work.

## admin-attendance-today.html
Admin "who is absent / who is working today" view, mobile 390. **Composed pattern — pending design approval** (no Figma frame yet). Built from my-schedule-day pieces; placeholder names only. Renders: `_verify/admin-attendance-today-{light,dark}.png`.
