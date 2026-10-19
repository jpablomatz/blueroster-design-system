# Blue Roster Marketing design system

Everything an AI needs to replicate Blue Roster **marketing** output: blueroster.com sections, the questionnaire landing (Wix) and campaign banners. It is a separate layer from the product (Legacy) kit: product screens follow `AGENTS.md`, `tokens/tokens.css` and `components/`; marketing follows this folder.

| File | What |
|---|---|
| [foundations.md](foundations.md) | Colors (Light page + Navy band modes), 20 `mkt` text styles, 4 grid styles, section spacing, and the 6 approved decisions. |
| [../tokens/marketing.css](../tokens/marketing.css) | `--mkt-*` CSS variables and `.mkt-*` helpers (v0.5). Import on marketing pages only. |
| [../tokens/marketing.md](../tokens/marketing.md) | Full token tables, primitives, sources, contrast and changelog (v0.5). |
| [landing.md](landing.md) | Questionnaire landing: `mkt-*` components, frames, flow, copy, rules and the Wix build notes. |
| [banners.md](banners.md) | Campaign banners: formats, families, styling, system-screen banners, approved stats, compliance checklist. |
| [references/](references/README.md) | Approved reference PNGs: 3 Light screen captures and 6 banners. |

## Keyword → file

| Keywords | Read |
|---|---|
| marketing, mkt, website section, blueroster.com, Inter, Navy band | `marketing/foundations.md` + `tokens/marketing.css` |
| landing, questionnaire, cuestionario, Wix, form, lead form | `marketing/landing.md` |
| banner, post, LinkedIn, Instagram, Story, social, campaign, campaña | `marketing/banners.md` + `marketing/references/` |
| screen banner, banner with screens, mockup with app screens | `marketing/banners.md` → "Banners with system screens" |

## Ten rules (summary)

1. Inter only; Black for display/H1 and banner headlines, H2–H4 Semi Bold. Product screenshots keep Roboto.
2. Light page; Navy `#002458` only as a band (`[data-mkt-band="navy"]`). No Dark pages.
3. Primary CTA `#064DB7` + White on light; White `#F9F9F9` + Navy text on Navy.
4. `#1E75F6` and vertical accents are non-text; text uses `text/*` or `vertical/*/text`.
5. Orange `#F66C1E`: accent only, Navy text on it, never white, never a button.
6. Text contrast ≥ 4.5:1; check minimum sizes in every format.
7. Approved stats only, per vertical. Never invent stats, quotes, testimonials, names or prices.
8. Say "light version" (up to 50 users), never "free". All 3 landing options for everyone.
9. Headlines verbatim from blueroster.com, sentence case + period. Links in the first comment.
10. Market is US only. Unknowns stay `TBD`; flag gaps instead of inventing.
