# Time Off · Approvals

- **Platform:** Employee app · Mobile (390; tablet 768 where noted)
- **Shell:** `br-m-app-bar` + `br-m-nav-drawer`

## Components
br-m-request-card, br-m-status-pill, br-m-empty-state

## Designed states / frames
- **Time Off · Approvals**: [Light](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=373-6748) 390×844 · [Dark](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=373-8383) 390×844
- **Time Off · Approvals · Empty**: [Light](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=373-6858) 390×844 · [Dark](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=373-8390) 390×844

## Not designed yet
Loading, error, skeleton. Do not invent them silently; flag in the PR and follow README gaps.

## Visual reference

Exported from Figma (mobile at 2x, desktop/admin at 1x). Match these pixel-for-pixel before anything else.

**Time Off · Approvals**

![Time Off · Approvals · Light](img/time-off-approvals--time-off-approvals-light.png) ![Time Off · Approvals · Dark](img/time-off-approvals--time-off-approvals-dark.png)

**Time Off · Approvals · Empty**

![Time Off · Approvals · Empty · Light](img/time-off-approvals--time-off-approvals-empty-light.png) ![Time Off · Approvals · Empty · Dark](img/time-off-approvals--time-off-approvals-empty-dark.png)

## Anatomy (extracted from the Light frame)

Order is top to bottom as in the Figma layer tree. x,y are relative to the parent. Paddings are top/right/bottom/left in px. Tokens are the variables bound in Figma. Full trimmed tree: see `json/`.

### Time Off · Approvals (`373:6748`)

| Layer | Component / type | x,y | Size | Layout · tokens |
|---|---|---|---|---|
| App bar | `br-m-app-bar` | 0,0 | 390×57 | vertical, gap 0, padding 0/0/0/0; bg br/contrast |
| ↳ Row | `fram` | 0,0 | 390×56 | horizontal, gap 0, padding 0/8/0/4 |
| ↳ Divider | `rect` | 0,56 | 390×1 | bg br/component-border |
| Body | `fram` | 0,57 | 390×571 | vertical, gap 16, padding 16/16/32/16 |
| ↳ Page header | `br-m-page-header` | 16,16 | 358×85 | vertical, gap 8, padding 0/0/0/0 |
| ↳ Req 1 | `br-m-request-card` | 16,117 | 358×130 | vertical, gap 8, padding 16/16/16/16; bg br/neutral-white; border br/component-border; radius 8 |
| ↳ Req 2 | `br-m-request-card` | 16,263 | 358×130 | vertical, gap 8, padding 16/16/16/16; bg br/neutral-white; border br/component-border; radius 8 |
| ↳ Req 3 | `br-m-request-card` | 16,409 | 358×130 | vertical, gap 8, padding 16/16/16/16; bg br/neutral-white; border br/component-border; radius 8 |

Node tree: [`json/time-off-approvals--time-off-approvals.json`](json/time-off-approvals--time-off-approvals.json)

### Time Off · Approvals · Empty (`373:6858`)

| Layer | Component / type | x,y | Size | Layout · tokens |
|---|---|---|---|---|
| App bar | `br-m-app-bar` | 0,0 | 390×57 | vertical, gap 0, padding 0/0/0/0; bg br/contrast |
| ↳ Row | `fram` | 0,0 | 390×56 | horizontal, gap 0, padding 0/8/0/4 |
| ↳ Divider | `rect` | 0,56 | 390×1 | bg br/component-border |
| Body | `fram` | 0,57 | 390×436 | vertical, gap 16, padding 16/16/32/16 |
| ↳ Page header | `br-m-page-header` | 16,16 | 358×85 | vertical, gap 8, padding 0/0/0/0 |
| ↳ Empty state | `br-m-empty-state` | 16,117 | 358×287 | vertical, gap 12, padding 32/24/32/24; border br/component-field-label; radius 8 |

Node tree: [`json/time-off-approvals--time-off-approvals-empty.json`](json/time-off-approvals--time-off-approvals-empty.json)

