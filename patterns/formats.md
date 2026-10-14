# Formats and copy (as drawn in Figma)

Source: My Schedule Day / Week / Month (372:5392, 372:5508, 372:5618), `br-m-request-card` (371:5471), Overtime cards. Language: English (US) copy, 12-hour clock.

## Time
| Where | Format | Example | Notes |
|---|---|---|---|
| Hour labels in the day timeline (`br-m-hour-row`) | `h AM` / `h PM`, uppercase, no minutes, no leading zero | `5 AM`, `12 PM`, `4 PM` | Right-aligned in a 40px column. The label's **top edge sits on the hour line** (label y = line y = row top), not centred on it. |
| Event time range (`br-m-event-block`, cards) | `h:mm am - h:mm pm`, lowercase am/pm, space-hyphen-space | `6:00 am - 4:00 pm`, `5:00 pm - 12:00 am` | Midnight is `12:00 am`. |
| Shift name | Catalog name shown verbatim as the block title | `0600 10-Hr w/ Lunch - 60S` | The name already encodes start (24h `0600`) and length; the time range goes on the line below it. Title wraps to 2 lines in a half-width column. |
| Task name | Task/area name as title | `Shipping/Outside` | Same time line format below. |

## Dates
| Where | Format | Example |
|---|---|---|
| Date nav · Day view | `EEE d MMM yyyy` (weekday abbr, day without zero, month abbr, year) | `Thu 8 Oct 2026` |
| Date nav · Week view | `EEE d MMM - EEE d MMM yyyy` | `Sun 4 Oct - Sat 10 Oct 2026` |
| Date nav · Month view | `MMMM yyyy` | `October 2026` |
| Agenda day heading (Week, Month) | `EEE d MMM` | `Mon 5 Oct` |
| Request card dates | `EEE d MMM · h:mm am - h:mm pm` (middle dot) | `Thu 8 Oct · 5:00 pm - 7:00 pm` |
| Request card meta | `Requested EEE d MMM` | `Requested Mon 5 Oct` |
| Week strip | weekday abbr `EEE` above day number `d` | `Fri` / `9` |
| Month header | single-letter weekday initials, week starts **Sunday** | `S M T W T F S` |

The date nav label is **left aligned**, filling the remaining width; the controls (‹ · Today · ›) are grouped on the **right**.

## Labels and copy
- Tabs: `Day`, `Week`, `Month` (icons `view_day`, `view_week`, `calendar_view_month`).
- Legend: `Shift`, `Tasks` (plural), `Overtime`, `Planned overtime` (sentence case), `Leave`.
- Date nav button: `Today`. Arrows: Material icons `chevron_left`, `chevron_right`.
- Page title: `My Schedule` (title case). Overtime title: `Overtime`; tabs `Opportunities`, `Approvals`.
- Status pills: `Pending`, `Approved`, `Rejected`.
- Balance values: `10.00 days` (two decimals + unit).

## Visible range
- Day view timeline shows **5 AM through 4 PM** (12 hour rows) in the 390×844 frame; the 6:00 am–4:00 pm shift starts one row below the top. The rule for choosing the range in production is **TBD** (not specified in Figma); for mockups, start one hour before the earliest event.
