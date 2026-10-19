# AGENTS.md — Blue Roster Design System rules

> **Skill:** requests with `@BR_Legacy` follow `skills/BR_Legacy/SKILL.md` (see the end of this file).
> **Marketing (v6):** blueroster.com sections, the questionnaire landing and campaign banners follow `marketing/README.md` (section 11). They use the `mkt` layer (`tokens/marketing.css`, Inter), never the product `br-*` kit.

This file is the single source of rules for every AI coding agent (Cursor, Claude Code, Codex, others) building Blue Roster UI. `CLAUDE.md` and `.cursor/rules/blueroster.mdc` point here. `.cursor/rules/blueroster-build.mdc` repeats the Playbook. Read this file, then `tokens/` (including `tokens/events.md` and `tokens/typography.md`), `patterns/`, `components/` and the relevant `screens/` spec (with its PNGs in `img/` and node tree in `json/`) before writing UI code. Requests that say **Blue Roster**, **Blue Roster Legacy**, or **BR** follow the Playbook at the end of this file.

Figma source: **Design System Legacy** — https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy (fileKey `k05NWBKMjsvo5hEugQc2Tq`).

## 1. Reuse, never redraw
- Build every screen from existing components. Look up `components/` first; if a `br-*`, `br-m-*` or `ms-*` component covers the need, use it.
- **Storybook is the source of truth for code.** The Angular `br-*` components in Storybook are what you import. Figma names match Storybook names (`br-button`, `br-input`, `br-table`, ...).
- Never re-implement a component with raw HTML/CSS. If something is genuinely missing, say so in the PR and propose a new component instead of inlining a one-off.

## 2. Tokens, not hex
- Every color, spacing, radius and typography value comes from `tokens/tokens.css` (CSS variables) or `tokens/tokens.json`.
- Prefer semantic `br/*` tokens (`--br-...`, including `br/event-*` for schedule events) over raw `mat/*` palette tokens.
- No hard-coded hex, rgb or px values where a token exists.

## 3. Light and Dark
- Every screen and component must work in both themes. Themes switch with `[data-theme="dark"]` on a root element; Light is the default (`:root`).
- Verify both themes before finishing.
- **Light and Dark side by side:** event tokens such as `--br-event-shift-neutral` are aliases (`var(--br-neutral-light)`). An alias resolves where it is declared, so if it only lived on `:root`, a `<div data-theme="dark">` inside a Light page kept the Light event colors. `tokens/tokens.css` now re-declares all 74 alias tokens on `[data-theme="light"], [data-theme="dark"]`, so `data-theme` works on any container out of the box. If you copy tokens into another file, keep that alias block (or use one iframe per theme).
- **Event block overflow (My Schedule Day, 3+ overlapping):** the title stays on one line with an ellipsis; the time line is hidden when the column is under 120 px wide or the event lasts 1 h (40 px tall); with 4+ overlapping events show 3 columns plus a `+N` pill (`br-m-event-more`) for the rest. `starter/br-m.css` and `starter/my-schedule-day.html` implement it (`is-compact` class).
- **Proposals (new, not in Legacy):** coverage holes (`--br-event-hole`, `br-event-hole`, `br-coverage-warning`) and Shift swap request cards live in `proposals/` and Figma page "Proposals · not in Legacy". Use them only when the user asks for coverage holes or shift swap, and label output "Proposal — new, not in Legacy".

## 4. Icons
- Use **Material Icons Outlined** only. Do not mix icon sets.

## 5. Platforms and layout
- **Employee app is mobile first** (390 wide reference; tablet 768 reference exists for Overtime). Desktop (1440) uses `br-app-shell` with `App=Employee`.
- **Admin app** is desktop web (1440×900) with `br-app-shell` `App=Admin`.
- App shell variants: `br-app-shell` → `App=Admin | Employee`. Employee sidebar: My Schedule, Overtime, Time Off, Sick Time, Logout. Mobile uses `br-m-app-bar` + `br-m-nav-drawer`.
- Page content components are named `br-content-<section>-<tab>` (e.g. `br-content-rosters-assignment`, `br-content-roster-catalogs-shift`). Follow that naming for new screens.
- Page header + tabs: `br-page-header` with `br-page-tab`.

## 6. Filter pattern
- **1–3 filters:** inline. On desktop they sit in **one row**.
- **4+ filters:** collapse them into a single dialog (`br-filter-dialog`, `Device=Mobile|Desktop`) opened by `br-filter-button` (shows a badge with the active filter count). One dialog for all filters, not one dialog per filter.
- Mobile dialog: full screen with Clear all / Apply pinned at the bottom. Desktop dialog: centered, 560 wide.

## 7. Calendars and dates
- Use **Mobiscroll** (`br-mobiscroll` and `br-mobiscroll-*`) for calendars, timelines, agenda and schedulers. Date inputs use `br-single-datepicker`, `br-range-datepicker`, `br-inline-datepicker` and the `br-linear-*-selector` components.

## 8. Tables, empty states, services
- Tables: `br-table` (+ `br-table-row`, `br-table-cell`, `br-table-header-cell`, `br-paginator`). Responsive data: `br-responsive-table`.
- Empty states: `br-empty-state-panel` (desktop) / `br-m-empty-state` (mobile).
- Dialogs, drawers, toasts and confirmations go through the services on the Figma *Services* page (dialog, drawer, confirmationDialogService, result dialog, toast). Do not hand-build modals.

## 9. Data honesty
- Text and numbers in Figma frames are illustrative. Do not copy them as real data, API fields or business rules.
- **Mockups may use sample data from `fixtures/`** (copied verbatim from the Figma frames and labelled sample). Use it for visual prototypes and mockups only; label it as sample data and never treat it as an API contract. Do not invent other data; if `fixtures/` has nothing that fits, reuse the closest sample and say so.
- Specs in `screens/` must not contain invented data or behavior. If a requirement is unknown, write "TBD" and ask.

## 9b. Match the Figma reference
- Each spec embeds Light and Dark PNGs exported from Figma (`screens/<group>/img/`). Compare your result against them before finishing.
- Event colors come from `tokens/events.md` (Shift = neutral gray `--br-event-shift-neutral`, Tasks = solid `--br-event-shift` with white text, Overtime `--br-event-overtime`, Planned overtime `--br-special-4`, Leave `--br-event-leave`).
- Day sample (`fixtures/schedule.json`, Thu 8 Oct 2026) now has all 5 event types: Shift, Tasks, Planned overtime 5–6 am, Leave 12–2 pm, Overtime 5–7 pm (placeholders reusing existing fixture text; range extended to 7 PM). Overlapping events go side by side in columns.
- Type is **Roboto** (see `tokens/typography.md`); icons are Material Icons Outlined.
- Time/date formats and copy: `patterns/formats.md` (12-hour `6 AM` labels, `Thu 8 Oct 2026`). Calendar geometry: `patterns/calendar-layout.md` (48px per hour, overlapping events side by side).
- Logo and avatar/badge specs: `assets/`. Never redraw the logo.
- For non-Angular mockups (Claude, Figma Make, plain HTML) start from `starter/` (`br-m.css`, `components.html`, `my-schedule-day.html`).

## 10. Known gaps (do not silently invent)
Loading / error / skeleton states, formal breakpoints, avatar initials variant (see `assets/README.md` for how the app bar draws it), `br-textarea` variant in `br-input`, no `br/event-planned-overtime` alias (the design uses `br/special-4`, see `tokens/events.md`), accent palette update, sticky behaviour of page header/tabs on My Schedule, multi-employee mobile calendar, unpublished Figma library. See README. When you hit one, flag it in your PR.

## 11. Marketing layer (website, landing, banners)
Requests about **marketing, banners, posts, LinkedIn/Instagram/Story, campaigns, the questionnaire landing, Wix or blueroster.com** follow `marketing/` instead of sections 1–9:
- Read `marketing/README.md`, then `marketing/foundations.md` and `tokens/marketing.md`; code uses `tokens/marketing.css` (`--mkt-*`, `.mkt-*`). Do not mix `--br-*` tokens or `br-*` components into marketing pages; product screenshots inside a marketing piece keep their own look.
- Landing: `marketing/landing.md` (`mkt-button`, `mkt-text-field`, `mkt-progress`, `mkt-option-card`, `mkt-result-card`, `mkt-step`, `mkt-select`, `mkt-checkbox`, flow, copy, Wix notes). Banners: `marketing/banners.md`. Examples: `marketing/references/`.
- Inter only: Black for display/H1 (and banner headlines), H2–H4 Semi Bold. Light page; Navy `#002458` only as a band (`[data-mkt-band="navy"]`), no Dark pages.
- Buttons: `#064DB7` + White on light (Manufacturing too); White `#F9F9F9` + Navy text inside Navy bands. `#1E75F6` is a non-text accent only. Orange `#F66C1E` is an accent only: Navy text on it, never white, never a button.
- Text contrast ≥ 4.5:1. Banner minimum sizes (approved by István 2026-10-19): support/body ≥ 24 px, eyebrows and button text ≥ 20 px on 1080/1200 formats; Display ≥ 12 px. Story safe zone 250 px top and bottom.
- Approved stats only (per vertical, `marketing/banners.md`); never invent stats, quotes, testimonials, names or prices. Say "light version" (up to 50 users), never "free". Headlines verbatim from blueroster.com, sentence case + period. Links in the first comment. Market: US only.
- Unknowns stay `TBD`, exactly as for product work.

## Definition of done for UI work
- Uses existing components and tokens only (or flags the gap).
- Works in Light and Dark.
- Employee screens verified at 390 first, then desktop.
- Filter count follows the 1–3 / 4+ rule.
- Links the Figma node it implements in the PR description.

## Playbook

Follow this playbook when the request says **Blue Roster**, **Blue Roster Legacy**, or **BR**.

1. Read `AGENTS.md` and `tokens/` before writing UI (`tokens.css`, `tokens.json`, and the markdown tables).
2. Map the request to the closest spec in `screens/` and state which file you are following. Use the keyword table. If several rows match, pick one view and say why.
3. Build mobile first: **390**, then **768**, then **desktop**. Admin specs are drawn at 1440×900. If the chosen spec has no 390 or 768 frame, flag that gap instead of inventing a layout.
4. Colors use only `br/*` tokens, through the CSS variables in `tokens/tokens.css` (`--br-...`, slash becomes hyphen). Spacing, radius, and type use the variables in that same file (`--spacing`, `--radius-*`, `--text-*`, `--font-weight-*`). No hard-coded hex, rgb, or px where a token exists.
5. Use only components documented in `components/`. Calendars, timelines, agenda, and schedulers use Mobiscroll (`br-mobiscroll` and `br-mobiscroll-*`).
6. Filters: **1–3** stay inline (one row on desktop). **4+** go in one `br-filter-dialog`, opened by `br-filter-button`.
7. Deliver **Light and Dark**. Light is `:root`; Dark is `[data-theme="dark"]`.
8. Flag gaps instead of inventing components, tokens, states, copy, or behavior. Unknown items stay `TBD`.
9. Build **one view first** and ask for review before the next view.

### Keyword → spec

Keywords are request language. Each spec path is a file in `screens/`.

| Keywords | Spec |
|---|---|
| screen index, list of screens, qué pantallas | `screens/README.md` |
| marketing, mkt, website section, blueroster.com, Navy band | `marketing/foundations.md` + `tokens/marketing.css` (**marketing layer**, see section 11) |
| landing, questionnaire, cuestionario, Wix form, lead form | `marketing/landing.md` (**marketing layer**) |
| banner, post, LinkedIn, Instagram, Story, social, campaign, campaña, screen banner | `marketing/banners.md` + `marketing/references/` (**marketing layer**) |
| action center, action center live, centro de acción | `screens/admin/action-center.md` |
| action center requests, requests tab | `screens/admin/action-center-requests.md` |
| catalogs user, user catalog, usuarios | `screens/admin/catalogs-user.md` |
| gantt production, production schedule, producción | `screens/admin/gantt-production-schedule.md` |
| gantt, projection, gantt projection | `screens/admin/gantt.md` |
| history, assignment history, historial de asignaciones | `screens/admin/history-assignments.md` |
| roles, roles management | `screens/admin/roles.md` |
| base model, modelo base, roster catalogs base model | `screens/admin/roster-catalogs-base-model.md` |
| model catalog, roster catalogs model | `screens/admin/roster-catalogs-model.md` |
| pattern catalog, patrón, roster catalogs pattern | `screens/admin/roster-catalogs-pattern.md` |
| shift catalog, turno, roster catalogs shift | `screens/admin/roster-catalogs-shift.md` |
| rosters list, rosters tab | `screens/admin/rosters-rosters.md` |
| rosters assignment, assignment planning | `screens/admin/rosters.md` |
| sign in, login, iniciar sesión | `screens/admin/sign-in.md` |
| attendance, attendance today, asistencia, who is absent, quién faltó, ausencias hoy | `screens/admin/attendance-today.md` (approved, desktop 1440) |
| coverage hole, hueco, holes, cobertura | `proposals/coverage-holes.md` (**proposal**, not in Legacy) |
| shift swap, cambio de turno, intercambio de turno | `proposals/shift-swap.md` (**proposal**, not in Legacy) |
| workload engine | `screens/admin/workload-engine.md` |
| workload template, plantilla | `screens/admin/workload-template.md` |
| employee profile, perfil, profile desktop | `screens/employee-desktop/employee-profile-desktop.md` |
| my schedule desktop, agenda desktop, schedule desktop | `screens/employee-desktop/my-schedule-desktop-proposal.md` |
| overtime desktop, overtime filters desktop | `screens/employee-desktop/overtime-opportunities-desktop-filters.md` |
| avatar, language, notifications, nav drawer, idioma, notificaciones, menú | `screens/employee-mobile/global-overlays-avatar-menu-language-notifications-nav-drawer.md` |
| multi-employee calendar, team calendar on mobile, team schedule mobile, ver empleados en móvil, calendario de empleados móvil, calendario del equipo | **No spec yet. Stop and ask the user.** Offer `screens/admin/gantt.md` / `screens/admin/gantt-production-schedule.md` (desktop admin Gantt) as reference and the My Schedule mobile specs for styling; do not invent the layout. |
| agenda, schedule, my schedule, day, día, calendario | `screens/employee-mobile/my-schedule-day.md` |
| my schedule month, month, mes | `screens/employee-mobile/my-schedule-month.md` |
| my schedule week, week, semana | `screens/employee-mobile/my-schedule-week.md` |
| overtime approvals | `screens/employee-mobile/overtime-approvals.md` |
| overtime, overtime opportunities, horas extra | `screens/employee-mobile/overtime-opportunities.md` |
| sick time history, sick history | `screens/employee-mobile/sick-time-history.md` |
| sick time, sick request | `screens/employee-mobile/sick-time-request.md` |
| time off approvals | `screens/employee-mobile/time-off-approvals.md` |
| time off, time off request | `screens/employee-mobile/time-off-request.md` |

Marketing words (banner, post, landing, campaign, Wix, blueroster.com) win over product rows: "banner with My Schedule" maps to `marketing/banners.md`, not to the screen spec. Disambiguation: "agenda" or "my schedule" with no Day, Week, or Month, and no desktop, maps to `screens/employee-mobile/my-schedule-day.md`. "Overtime" with no Approvals maps to Opportunities. Desktop or Admin in the request wins over the mobile row. State the chosen spec before building.

"My schedule" means the signed-in employee's own calendar. A request to see **several employees** (team, crew, roster, empleados) on mobile has **no spec**: say so, ask, and offer the Gantt desktop spec as reference.

## @BR_Legacy skill (Codex and all agents)
When a request starts with **@BR_Legacy** (or says Blue Roster / BR), read and follow `skills/BR_Legacy/SKILL.md` before writing UI: closest spec → starter + PNG + spec → `--br-*` tokens and formats → reuse components → compose missing patterns with listed assumptions → self-check. Raw: https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/skills/BR_Legacy/SKILL.md

Marketing requests (banner, post, landing, campaign, Wix, blueroster.com), with or without @BR_Legacy, follow the **Marketing mode** in `skills/BR_Legacy/SKILL.md` and `marketing/README.md`.
