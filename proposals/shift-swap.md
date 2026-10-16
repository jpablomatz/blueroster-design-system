# C · Shift swap — Proposal (new, not in Legacy)

Not in Storybook; Legacy only has the `br-placeholder` Type=Shift swap empty-state illustration (reuse it for the empty list).

## Mobile — `br-m-shift-swap-card` ([498:918](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=498-918))
Same anatomy as `br-m-request-card` (358 wide, padding 16, gap 8, r8, bg `--br-neutral-white`, 1px `--br-component-border`): icon `swap_horiz` 22 `--br-primary` · title "Shift swap" · `br-m-status-pill` · dates "Thu 8 Oct · 6:00 am - 4:00 pm" · detail "Employee 2 with Employee 5 · 0600 10-Hr w/ Lunch - 60S" · meta "Requested Mon 5 Oct".

## Admin — `br-shift-swap-request-row` ([498:949](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=498-949))
Row 1110×64 for Action Center · Requests: icon · who · when/shift · requested · status pill · (Pending only) `br-button` stroked "Decline" + raised "Approve".

## States
| Status | Pill variant | Token | Actions |
|---|---|---|---|
| Pending | Pending | `--br-semantic3` | Decline, Approve (admin) |
| Approved | Approved | `--br-semantic1` | — |
| Declined | Rejected (label "Declined") | `--br-semantic2` | — |

If approving would leave a hole, show `br-coverage-warning` above the actions (see `coverage-holes.md`).
