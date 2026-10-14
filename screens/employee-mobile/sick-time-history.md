# Sick Time · History

- **Platform:** Employee app · Mobile (390; tablet 768 where noted)
- **Shell:** `br-m-app-bar` + `br-m-nav-drawer`

## Components
br-m-request-card, br-m-status-pill, br-m-empty-state

## Designed states / frames
- **Sick Time · History**: [Light](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=373-7082) 390×844 · [Dark](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=373-8407) 390×844
- **Sick Time · History · Empty**: [Light](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=373-7192) 390×844 · [Dark](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=373-8413) 390×844

## Not designed yet
Loading, error, skeleton. Do not invent them silently; flag in the PR and follow README gaps.

## Visual reference

Exported from Figma (mobile at 2x, desktop/admin at 1x). Match these pixel-for-pixel before anything else.

**Sick Time · History**

![Sick Time · History · Light](img/sick-time-history--sick-time-history-light.png) ![Sick Time · History · Dark](img/sick-time-history--sick-time-history-dark.png)

**Sick Time · History · Empty**

![Sick Time · History · Empty · Light](img/sick-time-history--sick-time-history-empty-light.png) ![Sick Time · History · Empty · Dark](img/sick-time-history--sick-time-history-empty-dark.png)

## Anatomy (extracted from the Light frame)

Order is top to bottom as in the Figma layer tree. x,y are relative to the parent. Paddings are top/right/bottom/left in px. Tokens are the variables bound in Figma. Full trimmed tree: see `json/`.

### Sick Time · History (`373:7082`)

| Layer | Component / type | x,y | Size | Layout · tokens |
|---|---|---|---|---|
| App bar | `br-m-app-bar` | 0,0 | 390×57 | vertical, gap 0, padding 0/0/0/0; bg br/contrast |
| ↳ Row | `fram` | 0,0 | 390×56 | horizontal, gap 0, padding 0/8/0/4 |
| ↳ Divider | `rect` | 0,56 | 390×1 | bg br/component-border |
| Body | `fram` | 0,57 | 390×425 | vertical, gap 16, padding 16/16/32/16 |
| ↳ Page header | `br-m-page-header` | 16,16 | 358×85 | vertical, gap 8, padding 0/0/0/0 |
| ↳ Req 1 | `br-m-request-card` | 16,117 | 358×130 | vertical, gap 8, padding 16/16/16/16; bg br/neutral-white; border br/component-border; radius 8 |
| ↳ Req 2 | `br-m-request-card` | 16,263 | 358×130 | vertical, gap 8, padding 16/16/16/16; bg br/neutral-white; border br/component-border; radius 8 |

Node tree: [`json/sick-time-history--sick-time-history.json`](json/sick-time-history--sick-time-history.json)

### Sick Time · History · Empty (`373:7192`)

| Layer | Component / type | x,y | Size | Layout · tokens |
|---|---|---|---|---|
| App bar | `br-m-app-bar` | 0,0 | 390×57 | vertical, gap 0, padding 0/0/0/0; bg br/contrast |
| ↳ Row | `fram` | 0,0 | 390×56 | horizontal, gap 0, padding 0/8/0/4 |
| ↳ Divider | `rect` | 0,56 | 390×1 | bg br/component-border |
| Body | `fram` | 0,57 | 390×452 | vertical, gap 16, padding 16/16/32/16 |
| ↳ Page header | `br-m-page-header` | 16,16 | 358×85 | vertical, gap 8, padding 0/0/0/0 |
| ↳ Empty state | `br-m-empty-state` | 16,117 | 358×303 | vertical, gap 12, padding 32/24/32/24; border br/component-field-label; radius 8 |

Node tree: [`json/sick-time-history--sick-time-history-empty.json`](json/sick-time-history--sick-time-history-empty.json)

