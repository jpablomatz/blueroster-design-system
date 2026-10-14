# Typography tokens

Generated from Figma variables (s2d). CSS var = `--` + name with `/` → `-`.

| Variable | Type | Light | Dark |
|---|---|---|---|
| `flex/1-2` | color | #323200 | #323200 |
| `flex/1-4` | color | #191900 | #191900 |
| `flex/1-5` | color | #141400 | #141400 |
| `flex/2` | color | #020200 | #020200 |
| `flex/2-4` | color | #323200 | #323200 |
| `flex/2-5` | color | #282800 | #282800 |
| `flex/3` | color | #030300 | #030300 |
| `flex/3-4` | color | #4b4b00 | #4b4b00 |
| `flex/3-5` | color | #3c3c00 | #3c3c00 |
| `flex/3-6` | color | #323200 | #323200 |
| `flex/4` | color | #040400 | #040400 |
| `flex/4-5` | color | #505000 | #505000 |
| `flex/5` | color | #050500 | #050500 |
| `font/weight-bold` | number | 700 | 700 |
| `font/weight-extrabold` | number | 800 | 800 |
| `font/weight-medium` | number | 500 | 500 |
| `font/weight-normal` | number | 400 | 400 |
| `font/weight-semibold` | number | 600 | 600 |
| `line/clamp-10` | number | 10 | 10 |
| `line/clamp-7` | number | 7 | 7 |
| `line/clamp-8` | number | 8 | 8 |
| `line/clamp-9` | number | 9 | 9 |
| `text-5xl/line-height` | number | 1 | 1 |
| `text/2xl` | number | 24 | 24 |
| `text/5xl` | number | 48 | 48 |
| `text/base` | number | 16 | 16 |
| `text/lg` | number | 18 | 18 |
| `text/sm` | number | 14 | 14 |
| `text/xl` | number | 20 | 20 |
| `text/xs` | number | 12 | 12 |

---

# Type in use (extracted from Figma frames)

**Font family: Roboto** (weights Regular 400, Medium 500, Bold 700) for all UI text. **Icons: Material Icons Outlined** (Regular). Line height is `auto` (font default, ~1.17 for Roboto) unless listed. No text styles are applied in the frames; sizes are raw values that map to the `text/*` variables where one exists.

Exceptions seen in Figma (Inter): `br-select-field` value/label text (Inter Regular 16, e.g. "Skills", "Earliest first" in the Overtime filter bar and `br-filter-dialog`), the desktop `br-filter-dialog` title (Inter Bold 16), and in the **employee desktop proposal** the employee name (Inter Medium 18) and the month hint "Pick a day to open it." (Inter Regular 16). Everything on My Schedule is Roboto. Treat Inter as a Figma inconsistency to confirm; the Angular components render their own font.

```css
font-family: "Roboto", system-ui, sans-serif;   /* no font-family token exists in tokens.css */
```

## Employee app · Mobile

| Element | Component | Family / weight | Size | Line height | Color token | Align |
|---|---|---|---|---|---|---|
| Page title ("My Schedule", "Overtime") | `br-m-page-header` | Roboto Bold 700 | 24 (`text/2xl`) | auto (28px box) | `--br-neutral-darkest` | left |
| Tab label (Day / Week / Month) | `br-page-tab` | Roboto Medium 500 | 15 | auto (18px box) | active `--br-primary-dark`, default `--br-text-label` | left of icon row |
| Tab icon | `br-page-tab` | Material Icons Outlined | 24 | 24 | same as label | center |
| Legend label | `br-m-legend` | Roboto Regular 400 | 12 (`text/xs`) | auto (14px) | `--br-text-label` | left |
| Date nav label ("Thu 8 Oct 2026") | `br-m-date-nav` | Roboto Medium 500 | 14 (`text/sm`) | auto (16px) | `--br-neutral-darkest` | left |
| "Today" button label | `br-m-date-nav` | Roboto Medium 500 | 13 | auto (15px) | `--br-neutral-darkest` | center |
| Hour label ("6 AM") | `br-m-hour-row` | Roboto Regular 400 | 11 | auto (13px) | `--br-text-label` | **right**, in a 40px column |
| Event title | `br-m-event-block` | Roboto Medium 500 | 12 (`text/xs`) | auto (14px), wraps | per event type (see `events.md`) | left |
| Event time ("6:00 am - 4:00 pm") | `br-m-event-block` | Roboto Regular 400 | 11 | auto (13px) | per event type | left |
| Week-day weekday ("Fri") | `br-m-week-day` | Roboto Regular 400 | 11 | auto | `--br-text-label` | center |
| Week-day number | `br-m-week-day` | Roboto Medium 500 | 15 | auto (18px) | `--br-neutral-darkest`; Today `--br-on-primary` | center |
| Agenda day heading ("Mon 5 Oct") | My Schedule Week/Month | Roboto Medium 500 | 13 | auto (15px) | `--br-text-label` | left |
| Month weekday initials (S M T …) | My Schedule Month | Roboto Medium 500 | 11 | auto | `--br-text-label` | center |
| Month day number | `br-m-month-cell` | Roboto Regular 400 | 13 | auto | `--br-neutral-darkest`; Outside `--br-component-disabled`; Today `--br-on-primary` | center |
| App bar badge count | `br-m-app-bar` | Roboto Bold 700 | 11 | auto | `--br-on-primary` | center |
| Avatar initials ("JM") | `br-m-app-bar` | Roboto Medium 500 | 13 | auto | `--br-neutral-darkest` | center |
| Request card title | `br-m-request-card` | Roboto Medium 500 | 16 (`text/base`) | auto | `--br-neutral-darkest` | left |
| Request card dates | `br-m-request-card` | Roboto Bold 700 | 15 | auto | `--br-neutral-darkest` | left |
| Request card detail | `br-m-request-card` | Roboto Regular 400 | 14 | auto | `--br-text-label` | left |
| Request card meta | `br-m-request-card` | Roboto Regular 400 | 12 | auto | `--br-neutral-dark` | left |
| Status pill label | `br-m-status-pill` | Roboto Medium 500 | 12 | auto | status color | left |
| Balance card title / row | `br-m-balance-card` / `-row` | Roboto Medium 500 | 16 / 14 | auto | `--br-neutral-darkest`; value `--br-primary` | left / right |
| Balance card subtitle | `br-m-balance-card` | Roboto Regular 400 | 12 | auto | `--br-text-label` | left |
| Filter button label | `br-filter-button` | Roboto Medium 500 | 14 | auto | `--br-neutral-darkest`; Active `--br-primary` | left |
| Filter button badge count | `br-filter-button` | Roboto Medium 500 | 11 | auto | `--br-on-primary` on `--br-primary` | center |

Other sizes found in desktop/admin frames: Roboto Regular 13 (table cells, most frequent), Roboto Regular 14/20 and 14/40 letter-spacing 1.25 (Material buttons), Roboto Medium 16 / 18, Roboto Bold 18 (section titles), Roboto Regular 12.8/22 (Material badge).
