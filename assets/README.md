# assets/

Exported read-only from Figma **Design System Legacy** (`k05NWBKMjsvo5hEugQc2Tq`). Do not redraw these.

## Logo — `br-logo` (229:405)
| File | Variant | Size | Notes |
|---|---|---|---|
| `br-logo-isotype-light.svg` | Type=Isotype (229:404) | 32×34 | Light colors. Used centered in `br-m-app-bar` (x 153, y 11). |
| `br-logo-isotype-dark.svg` | Type=Isotype | 32×34 | Same paths with the Dark values of the bound tokens. |
| `br-logo-isotype-tokens.svg` | Type=Isotype | 32×34 | Fills as `var(--br-…)` (works only when the SVG is inlined in HTML). |
| `br-logo-full-light.svg` / `-dark.svg` / `-tokens.svg` | Type=Full (229:379) | 168×34 | Isotype + "BlueRoster" wordmark. |

Logo tokens (Light → Dark): `br/illustration-primary-dark` `#064db7` → `#8ebafa` (R/B body), `br/illustration-primary-darkest` `#002458` → `#c7ddfd` (dots and bars), `br/illustration-primary-lightest` `#c7ddfd` → `#345287` (small square), `br/neutral-dark` `#111827` → `#c8cdd7` (wordmark).

## Avatar with initials (as drawn in `br-m-app-bar`, 341:26)
There is no avatar-initials component (known gap); the app bar draws it inline:
- 32×32 circle (radius 16) inside a 48×48 touch target, fill `--br-neutral-light` (`#d1d5db` / `#373c4b`).
- Initials: Roboto Medium 13, `--br-neutral-darkest` (`#121212` / `#f5f6f8`), centered. Sample: "JM".
- The photo avatar component is `br-user-avatar` (53:3553): 36×36 round image + name Roboto Regular 16/24 `--br-text-label`. PNG: `br-user-avatar.png`.

## Badges
- **App bar notification badge** (inside `br-m-app-bar`): absolute at (26, 6) over the 48×48 bell button, height 18, min width 17, padding 0 5, radius 9, fill `--br-primary`, count Roboto Bold 11 `--br-on-primary`. PNG: `br-m-app-bar.png`.
- **Filter count badge** (`br-filter-button`, 393:8769): 20×20 circle, `--br-primary`, Roboto Medium 11 `--br-on-primary`. PNG: `br-filter-button.png`.
- **Material badge** `br-badge` (247:673) and `br-notification-badge` (53:2029): 22×22, radius 11, `--br-primary`, Roboto Regular 12.8/22 `mat/badge-text-color`. PNG: `br-badge.png`.

## Other reference PNGs (2x)
`br-m-event-block.png` (all 5 types), `br-m-status-pill.png` (Pending / Approved / Rejected).
