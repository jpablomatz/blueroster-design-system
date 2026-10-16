# B · Coverage holes — Proposal (new, not in Legacy)

A **hole** is a line/position with no one covering it for a time range (e.g. a leave or swap request removes the only person).

## Token
`--br-event-hole` (Figma `br/event-hole`): Light → `--br-semantic3-3`, Dark → `--br-semantic3-2`. Declared in `tokens/tokens.css` (marked PROPOSAL).

## Components (Figma page "Proposals · not in Legacy")
- **`br-event-hole`** ([498:910](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=498-910)): same geometry as `br-m-event-block` (padding 6/8, r4), bg `--br-event-hole`, 1px dashed `--br-semantic3`, `warning` icon 16 `--br-semantic3`, title Roboto Medium 12 + time 11 `--br-neutral-darkest`. Props: Title, Time. CSS: `.br-event-hole`.
- **`br-coverage-warning`** ([498:915](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=498-915)): banner, bg `--br-semantic3-3`, 1px `--br-semantic3`, r8, padding 12/16, `warning` 20 + copy Roboto Medium 14: **"This request will leave a hole in Line 1, Position 1"**. CSS: `.br-coverage-warning`. Shown on a request (time off, sick time, shift swap) before approving.
- **Action Center · Live view · coverage** ([498:37452](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=498-37452)): 1144 content; header "Thu 8 Oct 2026 · Live view · 2 coverage holes", warning banner, hours 5 AM–7 PM (56 px/h), one lane per Line · Position (52 tall, label 160). Two holes: Line 1 · Position 1 (6 am–4 pm) and Line 2 · Position 2 (6–10 am).

## Open questions
Who can fill a hole (overtime offer?), whether holes appear on employee mobile, and the exact rule that defines a hole.
