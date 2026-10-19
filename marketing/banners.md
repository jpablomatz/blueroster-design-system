# Campaign banners

How to build Blue Roster social and display banners so they match the approved **Asset Library** and **Batch 01**. Tokens and type: [`foundations.md`](foundations.md). Reference PNGs: [`references/`](references/README.md).

Figma: banners file `95vgcOmJbHpvSOiLvybtZj`, page **"Asset Library"** (`1055:98`), which holds the cleaned library and the Batch 01 section (`1071:1400`). The page **"Social "** (`1:2`, trailing space) is the published history: read it, never edit it. Screen copies for banners live in Design System Legacy, page **"Marketing · Banner screens"** (`588:11872`); never edit the original product screens.

## Non-negotiable rules

1. **Approved stats only.** Never invent or alter stats, quotes, testimonials, customer names, logos or prices. If no approved stat fits, run a stat-free headline.
2. **Pricing never appears** in posts, banners or landings. Say **"light version"**, never "free", "free plan", "free trial" or "free under 50". (Legacy site CTA "Book a Free Demo" exists on a few older Generic pieces as verbatim site copy; do not add it to new pieces without art-direction approval.)
3. **Copy is verbatim**: headlines and body come from blueroster.com, an existing approved library line, or the approved stat wording. Trims may only drop the end of a sentence. Any new line is marked `NEW COPY — pending approval` and is not shipped.
4. **Links go in the FIRST COMMENT**, never in the caption or on the creative (a small `blueroster.com/{vertical}` footer URL on the creative is fine).
5. **No raw product screens**: no old dates, no lorem ipsum, **no real names**. Use roles and role initials.
6. **Accessibility**: text contrast **≥ 4.5:1** (check every text layer, including chips and footers), meaningful graphics and control edges ≥ 3:1, and check minimum sizes in every format (see table below). Color is never the only signal.
7. Posts in English. Tone: direct, non-salesy, **pain → mechanism → proof**. Hashtags: LinkedIn 3–5, Instagram 15–30, Facebook 0–2.

### Approved stats only

| Vertical | Approved wording |
|---|---|
| 🏭 Manufacturing | 4.5 h saved/week · <5 min to fill a shift · 100% OSHA cert enforced |
| 🏥 Healthcare | 100% cert verified · zero license gaps · <5 min gap filled |
| 🚛 Logistics | 18 min vs 22 hrs to staff a surge |
| 🌐 Generic | 216 h/year spent scheduling per manager |

Each piece carries **only its own vertical's** stat. Never move a stat to another vertical (e.g. 4.5 h on Generic), never tell a stat as a customer anecdote, and never use other site numbers (22%, 18%, $52K, 94%, +40%, 35%, $18K, "4 min", "3 hours", "0 open shifts", "go live in under a week"…).

## Formats

| Format | Size | Notes |
|---|---|---|
| LinkedIn feed | **1200x627** | Main format. One LI + one Square per piece minimum. |
| Square | **1080x1080** | LinkedIn / Instagram / Facebook feed. |
| Story | **1080x1920** | Instagram / Facebook Story. Keep text clear of the platform UI at the top and bottom (exact safe area: proposal, ~250 px). CTA "↑  Swipe up to learn more". Photos must be native resolution (no upscaled drafts). |
| Display | 300x250 · 728x90 · 300x600 | Library only; text + CTA, no screens. |

Minimum sizes: **check them on every format**. No sizes are approved yet; working **proposal** (flag anything smaller): body/support text ≥ 24 px on 1080/1200 formats, ≥ 12 px on Display; eyebrows/chips ≥ 20 px on 1080/1200; product-screen text inside a mockup must still read at feed size (crop or zoom the screen rather than shrinking it).

## Naming and library structure

Name every frame and PNG `{emoji} {Vertical} — {Topic} — {Format} {WxH}`, adding ` · 02`, ` · 03` when topic and format repeat. Emoji: 🏭 Manufacturing · 🏥 Healthcare · 🚛 Logistics · 🌐 Generic. Example: `🏭 Manufacturing — Shift Fill — LinkedIn 1200x627`. No week numbers in names or on the creative (eyebrow is "Blue Roster for {Vertical}" or "Blue Roster — Active Scheduling").

Asset Library v1 (105 pieces), sections by vertical → topic:

| Vertical | Topics |
|---|---|
| 🏭 Manufacturing | Shift Fill · Call-Outs · Active Scheduling · Certifications · Time Saved |
| 🏥 Healthcare | Certifications · Switching · Coverage Heat Map · Coverage Gaps · Call-Outs |
| 🚛 Logistics | Surge · Coverage Heat Map · Call-Outs |
| 🌐 Generic | Active Scheduling · Time Spent · Demand Matching · Time-Off · Call-Outs · Brand |

Batch 01 (Demand Matching + Time-Off × 4 verticals): 8 pieces × LI / Square / Story; object-photo Stories stay on hold until their photos are approved.

## The 5 families and rotation

| Family | What it is | Batch 01 example |
|---|---|---|
| **Big Number (BN)** | Giant approved-stat numeral (Inter Black) + Semi Bold statement line + body + CTA. Light or Navy background. | A1 Mfg "<5 min to fill a shift." (light) · B1 Health "<5 min gap filled." (Navy) |
| **Icon/Chart (IC)** | Simple diagram (Venn, dot grid, heat map, stat tiles) or redrawn product-UI panel. | A3 Logistics Venn "Open Shifts · Certified & Available · ✓ Matched" + "18 min vs 22 hrs" tiles |
| **Documentary photo (DP)** | Candid workplace photo + Navy panel/gradient with text. Open space low-left for text; screens read as a soft glow. | A2 Health (nurse at a station), B2 Logistics (supervisor in a DC office) |
| **Object photo (OP)** | Still life of a work object (desk calendar, hard hat, shift board). | A4 Generic, B4 Mfg (drafts, pending approval) |
| **Doodle "blue men" (DD)** | Blue men illustration (editable vectors, brand-mapped colors), Blue Light background. About once a month. | B3 Generic "Still guessing who covers a day off?" |

Rotation: never the same family twice in one week; doodle about once a month; each vertical uses at least two families; in the Instagram grid never put two solid-color pieces (BN, IC, DD) next to each other: alternate solid and photo.

## Layout and styling (as built in the library)

- **Type:** Inter only. Main headline Inter **Black 900**, tracking −2.5 px at 40–100 px, about −3% below 40 px, about −4.5% on giant numerals > 100 px. Secondary heavy text Semi Bold, body Regular. No Light/ExtraLight/Bold headlines.
- **Palette only:** Navy `#002458`, Blue `#1E75F6`, Blue Light `#C7DDFD`, White `#F9F9F9` (not `#FFFFFF`), Dark `#111827`, plus vertical accents (Mfg `#1E75F6`, Health `#14B8A6`, Logistics `#BA7517`, Generic `#9CA3AF`) and orange `#F66C1E` (rules below).
- **CTAs:** on Navy → White `#F9F9F9` fill with Navy text. On light, Manufacturing → `#064DB7` with White text; other verticals on light → Navy fill with White text. CTA copy from existing pieces: "Book a {Vertical} Demo →".
- **`#1E75F6` is never text.** Blue text becomes Blue Light on Navy and Navy on light. `#1E75F6` stays for non-text accents (Mfg rules/bars, eyebrow dot, doodle figure).
- **Grey `#9CA3AF` is decorative only** (Generic dots and rules), never text.
- **Highlighted headline words** use the vertical accent only where it passes on that background (Health teal, Logistics ochre on Navy); Mfg and Generic highlights on Navy use Blue Light.
- **Orange `#F66C1E`:** highlights and illustration accessories only (e.g. the blue men Mfg vest), never a background block for text and never a button. Any text on orange is Navy `#002458` (5.08:1), never white (2.82–2.97:1).
- **Eyebrow/status chips:** on dark, 15% Blue Light tint with Blue Light text; on light, solid Blue Light with Navy text.
- **Status colors in UI mocks (heat maps):** covered = Blue `#1E75F6`, partial = Blue Light `#C7DDFD`, gap = Dark `#111827` with a diagonal hatch **and** a "GAP" label. Checks are White ✓ on Blue.
- **Logo:** always the `BR-Logo` component (light-on-dark version on Navy, `BR-Logo [Day]` on light). Never typed "Blue Roster.com", never redrawn; no ".com" suffix next to it.
- **No visible internal labels** ("Week 4", placeholders, notes) on the creative.

## Banners with system screens (client priority)

Connect the promotion with the demo by showing real Blue Roster screens. Use the clean captures in Design System Legacy page "Marketing · Banner screens" (copies; originals untouched), exported at **2x**. Light versions are in [`references/screens/`](references/README.md).

| Screen | Capture | Headline (approved, sentence case + period) | Support line |
|---|---|---|---|
| **Attendance Today** (admin, desktop 1440) | `attendance-today-light@2x.png` (2880×1800). Crop just below the table. | **Never get caught short-staffed.** (site: /active-scheduling/coverage-gaps) | Optional "Under 5 min to fill a shift." (Mfg only); omit on Generic |
| **My Schedule Day** (employee mobile, 5 event types) | `my-schedule-day-light@2x.png` (780×1688) | **Time off requests, simplified.** (site: /active-scheduling/time-off-requests) · swaps alt: **Shift swaps without the headache.** (site: /active-scheduling/shift-swaps) | — |
| **Overtime cards** (employee mobile, incl. the locked "Forklift cert." card) | `overtime-cards-full-light@2x.png` (780×3020, all 4 cards) | **Cut overtime costs automatically.** (site: /active-scheduling/overtime-costs) | **No stat** (35% and $18K are not approved) |

Headline rule: take the headline **verbatim from blueroster.com** (site lines are Title Case) and set it in **sentence case with a final period**, as in Batch 01. Do not add claims.

Screen data rules:
- **Role-based example data, no real names**: rows and cards show roles (e.g. "Welder · Line 2", Operator, Line Lead, Inspector, RN, CNA) with role initials (OP, LL, QI, RN, CA). No real or realistic person names, no customer names.
- **Current dates** (the captures use the week of Mon 19 Oct 2026); never old dates or lorem ipsum.
- Prefer **Light** captures. In Dark, light-blue task blocks with white text have low contrast.
- Mockup layout per format (**proposal**, pending art direction): LinkedIn 1200x627 = headline left, screen right (cropped/zoomed); 1080x1080 = headline top, screen below; Story = headline top, tall screen (Overtime full capture) below the safe area. Place the screen inside a device or browser frame drawn with palette colors; keep product UI in its own Roboto/`--br-*` styling.
- Known flaws inherited from the product designs (do not "fix" or highlight): the Attendance side menu highlights "Action Center", and the notification badge is clipped at the top.

## Checklist before handing off

- [ ] Name follows `{emoji} {Vertical} — {Topic} — {Format} {WxH}`; all required formats exported at 1:1 (screens at 2x).
- [ ] Every line traced to blueroster.com, an approved library line, or an approved stat (keep a source table).
- [ ] Only the vertical's own approved stat, or none. No quotes, testimonials, prices or "free".
- [ ] No real names, old dates or lorem ipsum in screens.
- [ ] Text contrast ≥ 4.5:1 on every layer; minimum sizes checked per format; orange only with Navy text.
- [ ] Family rotation respected for the week; no two solids adjacent in the IG grid.
- [ ] Link planned for the first comment; hashtags within the channel range.
- [ ] Art-direction review before anything is uploaded or published.
