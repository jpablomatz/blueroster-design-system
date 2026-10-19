# Marketing foundations (`mkt`)

Source: Figma **Design System Legacy** (`k05NWBKMjsvo5hEugQc2Tq`) → page **Marketing · Foundations** ([561:21](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=561-21)), docs board [566:80](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=566-80). Read from Figma on 2026-10-19 (read-only). Tokens version: **v0.5**.

Code: [`../tokens/marketing.css`](../tokens/marketing.css) (CSS variables) · full value tables, sources and contrast: [`../tokens/marketing.md`](../tokens/marketing.md).

The marketing layer sits **next to** the product kit, never inside it. Product screens keep `tokens/tokens.css` (`--br-*`), Roboto and the `br-*` components. Marketing pages (blueroster.com, the questionnaire landing) and campaign banners use `--mkt-*`, Inter and the `mkt-*` components. Product screenshots placed inside a marketing piece keep their own Roboto/`--br-*` look.

## Decisions (approved, Figma block [566:94](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=566-94))

| # | Decision | Status |
|---|---|---|
| 1 | Hero **display stays 80 px at 1440** (mobile 48 px). | István 2026-10-18 |
| 2 | **H2 is Inter Semi Bold (600)** on desktop and mobile. **Black (900) only for display and H1.** H3 and H4 are Semi Bold, so no heading below H2 is heavier than H2. | István 2026-10-18 |
| 3 | **No Dark pages.** The `mkt` collection has two modes: **Light** (the page) and **Navy band** (only for content inside Navy `#002458` sections: CTA band, stat band, confirmation, footer). | István 2026-10-18 |
| 4 | **Manufacturing buttons use `#064DB7`** (`vertical/mfg/accent-strong`, 7.25:1 with white text). **`#1E75F6` is the Mfg accent for non-text elements only** (icons, illustration, highlights, dots, charts). Never 16 px white text on `#1E75F6` (4.05:1). | István 2026-10-18 |
| 5 | **Primary button inside a Navy band** (any vertical) is **White `#F9F9F9` with Navy `#002458` text** (14.32:1). Tokens `action/primary` + `action/on-primary`. | István 2026-10-18 |
| 6 | **Secondary accent orange `#F66C1E`** (Matz Styleguide "Secondary/Default", ramp `#903502` → `#FFCDB1`). **Text on orange is only Navy `#002458`** (5.08:1), **never white** (2.97:1). Orange is never a button and never the only signal for meaning. Orange-colored text uses `orange/900` `#903502`. `#FF6B35` is dropped. | Matz 2026-10-19 |

Nothing is pending in the Foundations decisions. Line heights, mobile sizes, eyebrow, grid and spacing values are still **proposals** (usable, but flag them if you change them).

## 1. Colors: collection `mkt` (modes Light / Navy band)

Brand base: Navy `#002458`, Blue `#1E75F6`, Blue Light `#C7DDFD`, White `#F9F9F9`, Dark `#111827`. Vertical accents: Manufacturing `#1E75F6`, Healthcare `#14B8A6`, Logistics `#BA7517`, Generic `#9CA3AF`.

CSS: Light is the default on `:root`. Wrap anything placed on a Navy section in `[data-mkt-band="navy"]` (or `.mkt-band-navy`); every value re-resolves inside it.

### Neutral and action tokens

| Token | CSS variable | Light page | Navy band |
|---|---|---|---|
| `surface/page` | `--mkt-surface-page` | `#F9F9F9` | `#002458` |
| `surface/raised` | `--mkt-surface-raised` | `#FFFFFF` | `#143565` |
| `surface/inverse` | `--mkt-surface-inverse` | `#002458` | `#F9F9F9` |
| `text/heading` | `--mkt-text-heading` | `#002458` | `#F9F9F9` |
| `text/body` | `--mkt-text-body` | `#111827` | `#C7DDFD` |
| `text/muted` | `--mkt-text-muted` | `#535353` | `#8EBAFA` |
| `text/on-inverse` | `--mkt-text-on-inverse` | `#F9F9F9` | `#002458` |
| `border/default` | `--mkt-border-default` | `#D1D5DB` | `#324F78` |
| `action/primary` | `--mkt-action-primary` | `#064DB7` | `#F9F9F9` |
| `action/on-primary` | `--mkt-action-on-primary` | `#F9F9F9` | `#002458` |
| `accent/secondary` | `--mkt-accent-secondary` | `#F66C1E` | `#F66C1E` |
| `accent/on-secondary` | `--mkt-accent-on-secondary` | `#002458` | `#002458` |

### Vertical tokens (`vertical/<mfg|health|logistics|generic>/<role>`)

Roles: `accent` (decorative fills, illustration, highlights) · `accent-strong` (filled buttons, badges, selected cards, meaningful icons) · `on-accent` (text on `accent-strong`) · `tint` (soft background, selected option card) · `text` (accent-colored text, ≥4.5:1 on surface and tint).

| Vertical | accent | accent-strong (Light / Navy) | on-accent (Light / Navy) | tint (Light / Navy) | text (Light / Navy) |
|---|---|---|---|---|---|
| Manufacturing | `#1E75F6` | `#064DB7` / `#F9F9F9` | `#F9F9F9` / `#002458` | `#C7DDFD` / `#063478` | `#064DB7` / `#8EBAFA` |
| Healthcare | `#14B8A6` | `#13726E` / `#14B8A6` | `#F9F9F9` / `#002458` | `#CBECE8` / `#044268` | `#13726E` / `#26BDAD` |
| Logistics | `#BA7517` | `#87591C` / `#C89249` | `#F9F9F9` / `#002458` | `#ECDFCC` / `#25344B` | `#87591C` / `#C89249` |
| Generic | `#9CA3AF` | `#5F6673` / `#9CA3AF` | `#F9F9F9` / `#002458` | `#E6E8EA` / `#1F3D69` | `#5F6673` / `#A2A8B3` |

On the Light page Health `#14B8A6` (2.36:1) and Generic `#9CA3AF` (2.41:1) are below 3:1: decorative areas only; use `accent-strong` for icons, borders, focus rings and text. Primitives (31 values in `mkt · primitives`) and the full contrast table are in [`../tokens/marketing.md`](../tokens/marketing.md).

## 2. Typography: 20 text styles (`mkt/desktop/*` + `mkt/mobile/*`)

Family **Inter** (Regular 400, Semi Bold 600, Bold 700, Black 900). Desktop styles apply at ≥1024 px, mobile below 1024 (designed at 390). CSS: `.mkt-<role>` classes and `--mkt-font-<role>-{size,line-height,letter-spacing,weight}`, which switch at `min-width: 1024px`. Values below are read from the Figma text styles.

| Role | Weight | Desktop (size / LH / tracking) | Mobile (size / LH / tracking) |
|---|---|---|---|
| `display` | Black | 80 / 105% / −2.5px | 48 / 110% / −1.5px |
| `h1` | Black | 44 / 110% / −2.5px | 36 / 110% / −1.5px |
| `h2` | Semi Bold | 34 / 115% / −1.5px | 28 / 120% / −1px |
| `h3` | Semi Bold | 24 / 120% / −0.5px | 22 / 120% / −0.5px |
| `h4` | Semi Bold | 20 / 130% / 0 | 18 / 130% / 0 |
| `eyebrow` (UPPERCASE) | Bold | 14 / 140% / +1.5px | 12 / 140% / +1.2px |
| `lead` | Regular | 22 / 140% / 0 | 18 / 140% / 0 |
| `body` | Regular | 16 / 140% / 0 | 16 / 140% / 0 |
| `small` | Regular | 14 / 140% / 0 | 14 / 140% / 0 |
| `button` | Bold | 16 / 125% / 0 | 16 / 125% / 0 |

Rules: Black only for `display` and `h1` · H2–H4 Semi Bold · eyebrow and button Bold · no Light/ExtraLight headlines. Wix theme mapping is in [`landing.md`](landing.md#wix-theme-site-styles).

## 3. Grid: 4 grid styles (`mkt/grid/*`) and collection `mkt · layout`

| Breakpoint | Range | Columns | Gutter | Side margin | Content measure | Figma grid style |
|---|---|---|---|---|---|---|
| 1440 | ≥ 1440 | 12 | 24 | 80 | 720 | `mkt/grid/1440` |
| 1024 | 1024–1439 | 12 | 24 | 48 | 720 | `mkt/grid/1024` |
| 768 | 768–1023 | 8 | 24 | 40 | 688 | `mkt/grid/768` |
| 390 | < 768 | 4 | 16 | 20 | 350 | `mkt/grid/390` |

Container max width **1280** (`--mkt-container-max`), centred. Text measure max **720** (`--mkt-content-measure`). Grid variables: `--mkt-grid-columns`, `--mkt-grid-gutter`, `--mkt-grid-margin`. 390 / 768 / 1440 match the Legacy reference frames; 1024 is new. (Proposal.)

## 4. Spacing: section scale (4 px base)

| Token | CSS variable | 1440 | 1024 | 768 | 390 | Use |
|---|---|---|---|---|---|---|
| `section/xs` | `--mkt-section-xs` | 32 | 32 | 24 | 24 | small stacks |
| `section/sm` | `--mkt-section-sm` | 48 | 48 | 40 | 32 | heading → content |
| `section/md` | `--mkt-section-md` | 64 | 64 | 56 | 48 | inside a section |
| `section/lg` | `--mkt-section-lg` | 96 | 80 | 72 | 64 | between sections |
| `section/xl` | `--mkt-section-xl` | 128 | 112 | 96 | 80 | hero top / final CTA |

Component-level spacing uses the Legacy 4 px base (`--spacing`). (Proposal.)

## 5. Quick rules for any marketing output

- Light page by default. Navy appears only as a **band** (`[data-mkt-band="navy"]`), never as a full dark theme. One Navy band per landing page (the confirmation).
- Primary CTA: `--mkt-action-primary` + `--mkt-action-on-primary` (Light `#064DB7`/White, Navy band White/Navy). Mfg uses the same `#064DB7` on light.
- `#1E75F6` and the vertical `accent` colors are for non-text elements; text uses `text/*` or `vertical/*/text`.
- Orange `#F66C1E`: highlights and illustration accessories only (e.g. the blue men vest); Navy text on it, never white; never a button.
- Contrast: text ≥ 4.5:1 (≥ 3:1 only for large text ≥ 24 px, or 18.66 px bold), UI control edges and meaningful graphics ≥ 3:1.
- Known gaps: no error/feedback token (the landing uses literal `#B42318`), no `border/strong` token (field edges use `text/muted`).
