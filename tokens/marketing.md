# Marketing foundations (`mkt`) · v0.5

Status: five decisions approved by István (art direction) on 2026-10-18 and the orange accent decided by Matz on 2026-10-19; the remaining proposals are still open. This is the marketing layer for the questionnaire landing and other blueroster.com pages. It sits **next to** the product kit and never inside it: `tokens.css` (s2d), `br/*` variables and `br-*` components are untouched.

- Figma: *Design System Legacy* → page **Marketing · Foundations** ([561:21](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=561-21)), docs board [566:80](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=566-80)
  - Sections: [Decisions 566:94](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=566-94) (decision 5: [568:23](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=568-23), decision 6: [588:11856](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=588-11856)) · [Type 566:109](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=566-109) · [Grid 567:21](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=567-21) · [Spacing 567:81](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=567-81) · [Colors 568:26](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=568-26) (Light page [568:30](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=568-30), Navy band [568:165](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=568-165)) · [Orange accent 568:300](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=568-300)
  - Variable collections: `mkt · primitives` (1 mode), `mkt` (**Light** / **Navy band**), `mkt · layout` (1440 / 1024 / 768 / 390)
  - Styles: `mkt/desktop/*`, `mkt/mobile/*` (Inter text styles) and `mkt/grid/1440|1024|768|390` (grid styles)
- CSS: [`tokens/marketing.css`](marketing.css). Import it on marketing pages only. Light is the default on `:root`. Wrap Navy sections in `[data-mkt-band="navy"]` (or `.mkt-band-navy`).

## Decisions: **Approved by István 2026-10-18**

| # | Decision | Where it lands |
|---|---|---|
| 1 | Hero **display stays at 80 px at 1440**. Mobile stays at 48 px (0.6×; no change needed). | `mkt/desktop/display`, `mkt/mobile/display`, `--mkt-font-display-size` |
| 2 | **H2 is Inter Semi Bold (600)** on desktop and mobile. **Black only for display and H1.** H3 and H4 were lowered to Semi Bold, so no heading below H2 is heavier than H2. | `mkt/*/h2`, `h3`, `h4` |
| 3 | **No Dark pages.** The second `mkt` mode is renamed **Navy band** and is used only for content inside Navy `#002458` sections. | collection `mkt`, `[data-mkt-band="navy"]` |
| 4 | **Manufacturing buttons use `#064DB7`** (`vertical/mfg/accent-strong`, 7.25:1 with white text). **`#1E75F6` stays the Mfg accent** for non-text elements (icons, illustration, highlights, dots, charts). Do not put 16 px white text on `#1E75F6` (4.05:1). | `vertical/mfg/accent`, `vertical/mfg/accent-strong` |
| 5 | **Primary buttons inside a Navy band** (Manufacturing and any vertical) are **White `#F9F9F9` with Navy `#002458` text: 14.32:1** (button vs band edge also 14.32:1). This replaces the `#6EA3FF` proposal. `#1E75F6` stays the accent for non-text elements. | `action/primary`, `action/on-primary`, `vertical/mfg/accent-strong` (Navy band), `.mkt-button-primary` |
| 6 | **Secondary accent orange is `#F66C1E`**, from Matz's Styleguide "Secondary/Default" (ramp `#903502` → `#FFCDB1`). Text on it is **Navy `#002458` (5.08:1), never white** (2.97:1). `#FF6B35` is dropped. **Decided by Matz 2026-10-19.** | `accent/secondary`, `accent/on-secondary`, `orange/*`, `.mkt-accent-secondary` |

Nothing pending in Foundations decisions.

## Status labels

| Label | Meaning |
|---|---|
| **approved** | Decided by art direction (István), with date |
| **sourced** | Taken as-is from `context.md`, the blueroster.com Wix theme CSS, or the Legacy product tokens |
| **derived** | Computed from a sourced value with the stated formula |
| **proposal** | Alex's judgment; still needs approval |
| **pending** | Decision open; no token created |

## 1. Type: Inter

Font family: **Inter**, in Regular 400, Semi Bold 600, Bold 700 and Black 900. Weight rule (**Approved by István 2026-10-18**): **Black only for display and H1**; H2–H4 are Semi Bold; eyebrow and button are Bold. Product screenshots inside mockups keep Roboto.

Site conversion: the Wix theme sizes headings in `spx` at a 1802 px design width (`--theme-spx-ratio: var(--scaling-factor) / 1802`), so a Wix size N = `N × viewport / 1802`. The desktop values below are the 1440 equivalents (×0.8). Desktop styles apply at ≥1024; mobile styles below 1024 (designed at 390).

| Role | Weight | Desktop size / LH / tracking | Mobile size / LH / tracking | Source / status |
|---|---|---|---|---|
| `display` | Black | 80 / 105% / -2.5px | 48 / 110% / -1.5px | 80px at 1440: Approved by István 2026-10-18. Source: blueroster.com Wix theme font_0 = Inter Black 100spx at the 1802 design width, which is 80px at 1440 (Wix scales ×W/1802). Weight and −2.5px: context.md. Mobile 48 (0.6× desktop, same step as H1 44→36 relative to the 390 column): proposal, kept. Line height: proposal. |
| `h1` | Black | 44 / 110% / -2.5px | 36 / 110% / -1.5px | Size: site font_2 (H2 role) Inter Black 55spx, 44px at 1440. Weight and −2.5px: context.md. Line height and mobile: proposal. |
| `h2` | Semi Bold | 34 / 115% / -1.5px | 28 / 120% / -1px | Size and weight: site font_6 Inter Semi Bold 42spx, 33.6px at 1440, rounded to 34. Semi Bold: Approved by István 2026-10-18 (Black only for display and H1). Letter spacing, line height and mobile: proposal. |
| `h3` | Semi Bold | 24 / 120% / -0.5px | 22 / 120% / -0.5px | Size: site font_4 24px (fixed px). Weight lowered from Black to Semi Bold so it is never heavier than H2 (Approved by István 2026-10-18). Line height (site 1em), letter spacing and mobile: proposal. |
| `h4` | Semi Bold | 20 / 130% / 0px | 18 / 130% / 0px | Size: proposal. Weight Semi Bold so it is never heavier than H2 (Approved by István 2026-10-18). |
| `eyebrow` (UPPER) | Bold | 14 / 140% / 1.5px | 12 / 140% / 1.2px | Proposal. Inter Bold uppercase; 14px is the most common inline size on the site. |
| `lead` | Regular | 22 / 140% / 0px | 18 / 140% / 0px | Desktop: site font_8 (Body M) Inter Regular 22spx, 1.4em. Mobile: proposal. |
| `body` | Regular | 16 / 140% / 0px | 16 / 140% / 0px | Site font_7 (Body L) Inter Regular 16px. Line height 1.4em is the site default. |
| `small` | Regular | 14 / 140% / 0px | 14 / 140% / 0px | 14px: the most common inline font-size on blueroster.com. Line height 1.4em is the site default. |
| `button` | Bold | 16 / 125% / 0px | 16 / 125% / 0px | Site font_5 Inter Bold 16px. Line height 1.25: proposal. |

Figma style names: `mkt/desktop/<role>` and `mkt/mobile/<role>`. CSS: `.mkt-<role>` classes plus `--mkt-font-<role>-{size,line-height,letter-spacing,weight}`, which switch at `min-width: 1024px`.

Site reference (Wix theme, at the 1802 design width): font_0 Inter Black 100 · font_2 (H2) Black 55 · font_3 (H3) Black 52 · font_4 (H4) Black 24px · font_5 (H5) Bold 16px · font_6 (H6) Semi Bold 42 · font_7 (Body L) Regular 16px/1.25 · font_8 (Body M) Regular 22 · font_9 (Body S) Regular 19 · font_10 DIN Next Light 12px.

## 2. Grid, breakpoints, container (**proposal**)

| Breakpoint | Range (mobile-first) | Columns | Gutter | Side margin | Content width | Figma grid style |
|---|---|---|---|---|---|---|
| 390 | < 768 | 4 | 16 | 20 | 350 (fluid) | `mkt/grid/390` |
| 768 | 768–1023 | 8 | 24 | 40 | 688 (fluid) | `mkt/grid/768` |
| 1024 | 1024–1439 | 12 | 24 | 48 | 928 (fluid) | `mkt/grid/1024` |
| 1440 | ≥ 1440 | 12 | 24 | 80 | 1280 (max) | `mkt/grid/1440` |

- The container max width is **1280** (`--mkt-container-max`), centred; the text measure max is **720** (`--mkt-content-measure`).
- 390 / 768 / 1440 match the Legacy reference frames; 1024 is new.
- blueroster.com (Wix) switches at ≤1000 and ≤750, for reference only.

### Section spacing scale (**proposal**, 4 px base from Legacy `spacing`)

| Token | 1440 | 1024 | 768 | 390 | Typical use |
|---|---|---|---|---|---|
| `section/xs` | 32 | 32 | 24 | 24 | small stacks |
| `section/sm` | 48 | 48 | 40 | 32 | heading → content |
| `section/md` | 64 | 64 | 56 | 48 | inside a section |
| `section/lg` | 96 | 80 | 72 | 64 | between sections |
| `section/xl` | 128 | 112 | 96 | 80 | hero top / final CTA |

## 3. Color: collection `mkt` (Light page / Navy band)

**Modes ({A}):** `Light` is the page. `Navy band` is **not a dark theme**: use it only for content placed inside a Navy `#002458` section, such as a CTA band, a stat band or the footer. In that mode, `surface/page` resolves to Navy.

### Vertical roles

| Role | Use |
|---|---|
| `accent` | Brand accent: decorative fills, illustration, highlights, icons where ≥3:1. **Mfg = `#1E75F6` in both modes ({A})** |
| `accent-strong` | Filled buttons, badges, selected option cards, icons that convey meaning. **Mfg Light = `#064DB7` ({A})** |
| `on-accent` | Text and icons on `accent-strong` |
| `tint` | Soft background (option card hover/selected, section band) |
| `text` | Accent-colored text on the surface **and** on `tint` (≥4.5:1 on both) |

| Token | Light page | Navy band |
|---|---|---|
| `vertical/mfg/accent` | `#1E75F6` (sourced, `blue/500`) | `#1E75F6` (sourced, `blue/500`) |
| `vertical/mfg/accent-strong` | `#064DB7` (sourced, `blue/700`) | `#F9F9F9` (sourced, `neutral/white`) |
| `vertical/mfg/on-accent` | `#F9F9F9` (sourced, `neutral/white`) | `#002458` (sourced, `navy/900`) |
| `vertical/mfg/tint` | `#C7DDFD` (sourced, `blue/100`) | `#063478` (derived, `blue/navy-tint`) |
| `vertical/mfg/text` | `#064DB7` (sourced, `blue/700`) | `#8EBAFA` (sourced, `blue/200`) |
| `vertical/health/accent` | `#14B8A6` (sourced, `teal/500`) | `#14B8A6` (sourced, `teal/500`) |
| `vertical/health/accent-strong` | `#13726E` (derived, `teal/700`) | `#14B8A6` (sourced, `teal/500`) |
| `vertical/health/on-accent` | `#F9F9F9` (sourced, `neutral/white`) | `#002458` (sourced, `navy/900`) |
| `vertical/health/tint` | `#CBECE8` (derived, `teal/100`) | `#044268` (derived, `teal/navy-tint`) |
| `vertical/health/text` | `#13726E` (derived, `teal/700`) | `#26BDAD` (derived, `teal/400`) |
| `vertical/logistics/accent` | `#BA7517` (sourced, `ochre/500`) | `#BA7517` (sourced, `ochre/500`) |
| `vertical/logistics/accent-strong` | `#87591C` (derived, `ochre/700`) | `#C89249` (derived, `ochre/400`) |
| `vertical/logistics/on-accent` | `#F9F9F9` (sourced, `neutral/white`) | `#002458` (sourced, `navy/900`) |
| `vertical/logistics/tint` | `#ECDFCC` (derived, `ochre/100`) | `#25344B` (derived, `ochre/navy-tint`) |
| `vertical/logistics/text` | `#87591C` (derived, `ochre/700`) | `#C89249` (derived, `ochre/400`) |
| `vertical/generic/accent` | `#9CA3AF` (sourced, `gray/400`) | `#9CA3AF` (sourced, `gray/400`) |
| `vertical/generic/accent-strong` | `#5F6673` (derived, `gray/700`) | `#9CA3AF` (sourced, `gray/400`) |
| `vertical/generic/on-accent` | `#F9F9F9` (sourced, `neutral/white`) | `#002458` (sourced, `navy/900`) |
| `vertical/generic/tint` | `#E6E8EA` (derived, `gray/100`) | `#1F3D69` (derived, `gray/navy-tint`) |
| `vertical/generic/text` | `#5F6673` (derived, `gray/700`) | `#A2A8B3` (derived, `gray/350`) |

### Neutral tokens

| Token | Light page | Navy band |
|---|---|---|
| `surface/page` | `#F9F9F9` (sourced) | `#002458` (sourced) |
| `surface/raised` | `#FFFFFF` (sourced) | `#143565` (derived) |
| `surface/inverse` | `#002458` (sourced) | `#F9F9F9` (sourced) |
| `text/heading` | `#002458` (sourced) | `#F9F9F9` (sourced) |
| `text/body` | `#111827` (sourced) | `#C7DDFD` (sourced) |
| `text/muted` | `#535353` (sourced) | `#8EBAFA` (sourced) |
| `text/on-inverse` | `#F9F9F9` (sourced) | `#002458` (sourced) |
| `border/default` | `#D1D5DB` (sourced) | `#324F78` (derived) |
| `action/primary` | `#064DB7` (sourced) | `#F9F9F9` (sourced) |
| `action/on-primary` | `#F9F9F9` (sourced) | `#002458` (sourced) |
| `accent/secondary` | `#F66C1E` (sourced, `orange/500`) | `#F66C1E` (sourced, `orange/500`) |
| `accent/on-secondary` | `#002458` (sourced, `navy/900`) | `#002458` (sourced, `navy/900`) |

### Primary action ({A})

| Token | Light page | Navy band | Contrast |
|---|---|---|---|
| `action/primary` | `#064DB7` | `#F9F9F9` | edge vs surface: 7.25:1 / 14.32:1 |
| `action/on-primary` | `#F9F9F9` | `#002458` | text: 7.25:1 / 14.32:1 |

Use `action/primary` for the main CTA button on any page or band. Inside a Navy band, every primary button is White with Navy text, whatever the vertical; `vertical/*/accent-strong` stays available for badges and selected states. `#064DB7` is not used in Navy bands (1.98:1 against `#002458`).

### Primitives (`mkt · primitives`): source of every value

| Primitive | Hex | Status | Source / formula |
|---|---|---|---|
| `blue/500` | `#1E75F6` | sourced | context.md Brand Blue; blueroster.com theme color_18. Mfg accent and non-text elements (Approved by István 2026-10-18) |
| `blue/700` | `#064DB7` | sourced | blueroster.com theme color_19; Legacy br/primary-dark. Mfg / primary buttons on the Light page and accent text (Approved by István 2026-10-18) |
| `blue/200` | `#8EBAFA` | sourced | blueroster.com CSS; Legacy br/primary-light |
| `blue/100` | `#C7DDFD` | sourced | context.md Blue Light; blueroster.com color_16 |
| `blue/navy-tint` | `#063478` | derived | mix 20% #1E75F6 into #002458 |
| `navy/900` | `#002458` | sourced | context.md Navy; blueroster.com color_20 |
| `navy/raised` | `#143565` | derived | mix 8% #F9F9F9 into #002458 |
| `navy/border` | `#324F78` | derived | mix 20% #F9F9F9 into #002458 |
| `neutral/white` | `#F9F9F9` | sourced | context.md White; blueroster.com color_11. Primary button fill in Navy band (Approved by István 2026-10-18) |
| `neutral/pure-white` | `#FFFFFF` | sourced | blueroster.com color_0 |
| `neutral/dark` | `#111827` | sourced | context.md Dark |
| `neutral/gray-300` | `#D1D5DB` | sourced | blueroster.com color_13 |
| `neutral/gray-600` | `#535353` | sourced | blueroster.com color_14; Legacy br/neutral |
| `teal/500` | `#14B8A6` | sourced | context.md Health accent |
| `teal/400` | `#26BDAD` | derived | mix 8% #F9F9F9 into #14B8A6 until >=4.5:1 on #002458 and on teal/navy-tint |
| `teal/700` | `#13726E` | derived | mix 44% #111827 into #14B8A6 until >=4.5:1 on #F9F9F9 and on teal/100 |
| `teal/100` | `#CBECE8` | derived | mix 20% #14B8A6 into #F9F9F9 |
| `teal/navy-tint` | `#044268` | derived | mix 20% #14B8A6 into #002458 |
| `ochre/500` | `#BA7517` | sourced | context.md Logistics accent |
| `ochre/400` | `#C89249` | derived | mix 22% #F9F9F9 into #BA7517 until >=4.5:1 on #002458 and on ochre/navy-tint |
| `ochre/700` | `#87591C` | derived | mix 30% #111827 into #BA7517 until >=4.5:1 on #F9F9F9 and on ochre/100 |
| `ochre/100` | `#ECDFCC` | derived | mix 20% #BA7517 into #F9F9F9 |
| `ochre/navy-tint` | `#25344B` | derived | mix 20% #BA7517 into #002458 |
| `gray/400` | `#9CA3AF` | sourced | context.md Generic accent |
| `gray/350` | `#A2A8B3` | derived | mix 6% #F9F9F9 into #9CA3AF until >=4.5:1 on #002458 and on gray/navy-tint |
| `gray/700` | `#5F6673` | derived | mix 44% #111827 into #9CA3AF until >=4.5:1 on #F9F9F9 and on gray/100 |
| `gray/100` | `#E6E8EA` | derived | mix 20% #9CA3AF into #F9F9F9 |
| `gray/navy-tint` | `#1F3D69` | derived | mix 20% #9CA3AF into #002458 |
| `orange/900` | `#903502` | sourced | Matz Styleguide, Secondary ramp darkest. 7.4:1 on #F9F9F9: the only orange for text |
| `orange/500` | `#F66C1E` | sourced | Matz Styleguide "Secondary/Default" (= Legacy br/illustration-secondary, blueroster.com color_23). Decided by Matz 2026-10-19 |
| `orange/100` | `#FFCDB1` | sourced | Matz Styleguide, Secondary ramp lightest |

`mix(a, b, t)` is a linear sRGB blend of t·a + (1−t)·b. Text shades step t in 2 % increments until WCAG 2.x reaches ≥4.5:1 on the surface and on the tint. Tints are 20 % accent mixed into White (Light) or Navy (Navy band). The Manufacturing Light tint is the sourced Blue Light `#C7DDFD`.

### Contrast (WCAG 2.x)

| Mode | Vertical | on-accent / accent-strong | text / surface | text / tint | accent / surface (graphics ≥3) |
|---|---|---|---|---|---|
| Light | Manufacturing | 7.25 | 7.25 | 5.52 | 4.05 |
| Light | Healthcare | 5.45 | 5.45 | 4.56 | 2.36 ⚠️ |
| Light | Logistics | 5.74 | 5.74 | 4.6 | 3.53 |
| Light | Generic | 5.49 | 5.49 | 4.7 | 2.41 ⚠️ |
| Navy band | Manufacturing | 14.32 | 7.58 | 5.96 | 3.54 |
| Navy band | Healthcare | 6.06 | 6.43 | 4.52 | 6.06 |
| Navy band | Logistics | 5.5 | 5.5 | 4.58 | 4.05 |
| Navy band | Generic | 5.94 | 6.31 | 4.55 | 5.94 |

⚠️ On the Light page, Health `#14B8A6` (2.36:1) and Generic `#9CA3AF` (2.41:1) are below 3:1. Use them only for large decorative areas and illustration; use `accent-strong` for icons, borders, focus rings and text.

### Orange accent: **decided by Matz 2026-10-19**

| Token | Light page | Navy band | Contrast |
|---|---|---|---|
| `accent/secondary` | `#F66C1E` | `#F66C1E` | vs `#F9F9F9` 2.82:1 ⚠️ · vs `#002458` 5.08:1 |
| `accent/on-secondary` | `#002458` | `#002458` | Navy on orange 5.08:1 ✅ · white on orange 2.97:1 ❌ |

- Source: Matz's Styleguide (Figma `DAuBM7JWL76akz6WcfnbZ4`, node 1:2), "Secondary/Default" `#F66C1E`, ramp `#903502` → `#FFCDB1`. The Styleguide also confirms `#064DB7` as Primary/Dark.
- Use for highlights, badges and illustration accessories (e.g. the blue men vest). It is below 3:1 on the page bg, so never the only signal for meaning, and **never a button**.
- Any text on orange is Navy (`accent/on-secondary`), **never white**. For orange-colored text use `orange/900` `#903502` (7.4:1 on `#F9F9F9`).
- `#FF6B35` (Blue men character sheet v1.0) is not in the Styleguide and is dropped.

## Changelog
- **v0.5 (2026-10-19):** decision 6 (Matz): orange accent `#F66C1E`. Added primitives `orange/900`, `orange/500`, `orange/100`, semantic `accent/secondary` + `accent/on-secondary` (Navy), and the `.mkt-accent-secondary` helper. Figma: Orange panel 568:300 now shows the token, decision 6 added to the Decisions block. (v0.4 was not packaged.)
- **v0.3 (2026-10-18):** decision 5: Navy band primary button is White `#F9F9F9` + Navy text (14.32:1). Added `action/primary` and `action/on-primary`, set `vertical/mfg/accent-strong` (Navy band) to White, removed the unused primitive `blue/300` `#6EA3FF`, and added the `.mkt-button-primary` helper.
- **v0.2 (2026-10-18):** applied István's decisions 1–4. H2–H4 are now Semi Bold. The Dark mode became Navy band, with values re-derived against Navy and Dark-only primitives removed. Documented the Mfg `#064DB7` / `#1E75F6` split. CSS: Navy band selector `[data-mkt-band="navy"]` replaces `[data-theme="dark"]`, and Inter 600 is added to the font import.
- **v0.1 (2026-10-18):** first draft.

## Open questions
1. The remaining proposals (line heights, mobile sizes, eyebrow, grid, spacing) are still waiting for approval.
