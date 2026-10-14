# Time Off · Request

- **Platform:** Employee app · Mobile (390; tablet 768 where noted)
- **Shell:** `br-m-app-bar` + `br-m-nav-drawer`

## Components
br-m-app-bar, br-m-page-header, br-m-balance-card, br-m-balance-row, form fields (br-input/br-select/br-range-datepicker). Form content is a placeholder pending product definition.

## Designed states / frames
- **Time Off · Request**: [Light](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=373-6634) 390×844 · [Dark](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=373-8371) 390×844

## Not designed yet
Loading, error, skeleton. Do not invent them silently; flag in the PR and follow README gaps.

## Visual reference

Exported from Figma (mobile at 2x, desktop/admin at 1x). Match these pixel-for-pixel before anything else.

**Time Off · Request**

![Time Off · Request · Light](img/time-off-request-light.png) ![Time Off · Request · Dark](img/time-off-request-dark.png)

## Anatomy (extracted from the Light frame)

Order is top to bottom as in the Figma layer tree. x,y are relative to the parent. Paddings are top/right/bottom/left in px. Tokens are the variables bound in Figma. Full trimmed tree: see `json/`.

### Time Off · Request (`373:6634`)

| Layer | Component / type | x,y | Size | Layout · tokens |
|---|---|---|---|---|
| App bar | `br-m-app-bar` | 0,0 | 390×57 | vertical, gap 0, padding 0/0/0/0; bg br/contrast |
| ↳ Row | `fram` | 0,0 | 390×56 | horizontal, gap 0, padding 0/8/0/4 |
| ↳ Divider | `rect` | 0,56 | 390×1 | bg br/component-border |
| Body | `fram` | 0,57 | 390×715 | vertical, gap 16, padding 16/16/32/16 |
| ↳ Page header | `br-m-page-header` | 16,16 | 358×85 | vertical, gap 8, padding 0/0/0/0 |
| ↳ Balance | `br-m-balance-card` | 16,117 | 358×178 | vertical, gap 4, padding 16/16/12/16; bg br/neutral-white; border br/component-border; radius 8 |
| ↳ Form | `fram` | 16,311 | 358×372 | vertical, gap 12, padding 16/16/16/16; bg br/neutral-white; border br/component-border; radius 8 |

Node tree: [`json/time-off-request.json`](json/time-off-request.json)

