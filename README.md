# blueroster-design-system

Source of truth for AI coding agents (Cursor, Claude Code, Codex) to build Blue Roster features consistently with the Figma **Design System Legacy** file (`k05NWBKMjsvo5hEugQc2Tq`).

## Structure
| Path | What it is |
|---|---|
| `AGENTS.md` | The rules every agent must follow (components, tokens, themes, icons, filters, shells, naming). |
| `CLAUDE.md` | Pointer for Claude Code → `AGENTS.md`. |
| `.cursor/rules/blueroster.mdc` | Always-on Cursor rule → `AGENTS.md`. |
| `.cursor/rules/blueroster-build.mdc` | Always-on build playbook. Triggers: Blue Roster, Blue Roster Legacy, BR. |
| `llms.txt` | llmstxt.org index: playbook, token summary, and raw links to every source file. |
| `llms-full.txt` | `AGENTS.md` plus every `tokens/*.md`, `components/*.md`, and `screens/**/*.md`, concatenated. |
| `tokens/tokens.json` | All 777 Figma variables from collection `s2d` with Light / Dark / Default values and aliases (plus resolved values). |
| `tokens/tokens.css` | Same tokens as CSS custom properties. Light on `:root`, Dark overrides on `[data-theme="dark"]`. |
| `tokens/*.md` | Readable tables: `semantic-br.md` (br/*), `typography.md`, `spacing.md`, `radius.md`. |
| `components/` | Inventory of Figma components per page (`br-*`, `br-m-*`, `ms-*`) with node links and props/variants. |
| `screens/` | One spec per screen: admin (desktop), employee mobile, employee desktop. Figma links, purpose, components, designed states. |
| `tokens/events.md` | Event type → background / text / border tokens and hex, Light and Dark, as used on screen. |
| `patterns/formats.md` | Date, time and copy formats as drawn (12h `6 AM`, `Thu 8 Oct 2026`, plurals). |
| `patterns/calendar-layout.md` | Calendar geometry: 48px/hour, side-by-side overlaps, week strip, month grid, scroll. |
| `screens/*/img/` | Light and Dark PNG of every frame referenced by a spec (embedded in the spec). |
| `screens/*/json/` | Trimmed Figma node tree per frame (names, layout, sizes, token bindings). |
| `screens/_TEMPLATE.md` | Template for new specs (anatomy, token table, formats, images). |
| `assets/` | `br-logo` SVGs (isotype + full, Light/Dark/tokens), avatar-initials and badge specs, reference PNGs. |
| `fixtures/schedule.json` | Sample shifts, tasks, overtime cards copied from the Figma mockups. Mockups only. |
| `marketing/` | **Marketing design system (v6):** `foundations.md` (mkt colors, type, grid, spacing, decisions), `landing.md` (questionnaire landing + Wix notes), `banners.md` (campaign banners), `references/` (approved PNGs). |
| `tokens/marketing.css` / `tokens/marketing.md` | Marketing `--mkt-*` tokens v0.5 (Inter, Light page + Navy band, orange `#F66C1E` with Navy on-color). Marketing pages only. |
| `.cursor/rules/br-marketing.mdc` | Cursor rule for banners, landing and blueroster.com work. |
| `CHANGELOG.md` | Version history. |
| `starter/` | Plain HTML/CSS snippets for `br-m-*` components and a `my-schedule-day.html` page verified against Figma. |

## How to use it
- **Cursor:** open this repo (or add it to your app workspace). `.cursor/rules/blueroster.mdc` and `.cursor/rules/blueroster-build.mdc` load automatically. With the Figma MCP connected, the agent can also open linked nodes.
- **Claude Code:** `CLAUDE.md` is read automatically and points to `AGENTS.md`. Add this repo as an extra directory (`/add-dir`) when working in the app repo, or copy `AGENTS.md` there.
- **Codex:** reads `AGENTS.md` natively. Codex needs the repo on GitHub, so mirror it there if you want to use Codex cloud.
- **In the app repo:** import `tokens/tokens.css` once at the root, and set `data-theme="dark"` to switch themes.

Prompt template: *"Implement <screen> following `screens/<platform>/<screen>.md`, using only components in `components/` and tokens in `tokens/`. Follow AGENTS.md."*

## Marketing
Blue Roster marketing (blueroster.com sections, the questionnaire landing, campaign banners) is a separate layer: start at `marketing/README.md`, use `tokens/marketing.css` and Inter, and never the product `br-*` kit. Prompt template: *"Build a LinkedIn 1200x627 screen banner with Attendance Today following `marketing/banners.md` and `marketing/foundations.md`."*

## Updating
Tokens and the inventory were generated from Figma via the Plugin API (read-only). When Figma changes, re-export and replace these files; do not hand-edit `tokens.json` / `tokens.css`.

## Known gaps
- Loading, error and skeleton states are not designed.
- No formal breakpoints (only 390 / 768 / 1440 reference frames).
- Avatar has no initials variant.
- `br-input` has no textarea variant (there is a separate `br-textarea`).
- No `br/event-planned-overtime` alias: the design colors Planned overtime with `br/special-4` (`#5a2ead`), documented in `tokens/events.md`.
- Accent palette update pending (Matz's Gantt variant component is the reference).
- The Figma library is not published, so Figma MCP search cannot find its components yet.
- No Code Connect mappings yet between Figma components and Storybook code.
- Time Off request form is a placeholder pending product definition.

## Cómo pedirlo

Escribe **Blue Roster**, **Blue Roster Legacy** o **BR** en el pedido. El agente lee `AGENTS.md` y `tokens/`, elige el spec más cercano en `screens/` y dice cuál es, construye primero a 390, luego a 768 y después en desktop, usa solo tokens `br/*` como variables de `tokens/tokens.css`, solo componentes de `components/` (Mobiscroll para calendarios), deja 1–3 filtros en línea y 4 o más en `br-filter-dialog`, entrega Light y Dark, marca los huecos en vez de inventar, y arma una sola vista antes de pedir revisión.

Ejemplos:

- `Haz una agenda para Mobile usando Blue Roster Legacy` → `screens/employee-mobile/my-schedule-day.md`
- `Arma My Schedule Week a 390 con BR` → `screens/employee-mobile/my-schedule-week.md`
- `Sign in de Admin con Blue Roster, Light y Dark` → `screens/admin/sign-in.md`
- `Overtime Opportunities en desktop usando Blue Roster Legacy` → `screens/employee-desktop/overtime-opportunities-desktop-filters.md`

- `Banner de LinkedIn con la pantalla de Attendance Today con BR` → `marketing/banners.md`
- `Arma el paso 5 de la landing del cuestionario con BR` → `marketing/landing.md`

Para Claude/ChatGPT: pásale https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/llms-full.txt

## Regenerating `llms.txt` / `llms-full.txt`
`llms-full.txt` must include, verbatim: `AGENTS.md`, **`tokens/tokens.css` (full file, not only the markdown tables)**, `tokens/events.md`, `tokens/typography.md`, `patterns/*.md`, `assets/README.md`, `fixtures/schedule.json`, `starter/br-m.css`, `starter/my-schedule-day.html`, every `screens/**/*.md` with its image links rewritten to absolute `https://raw.githubusercontent.com/jpablomatz/blueroster-design-system/main/...` URLs, and `components/*.md`. The current `llms*.txt` files predate this update and must be regenerated.
