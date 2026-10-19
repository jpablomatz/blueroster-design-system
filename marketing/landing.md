# Questionnaire landing (Wix)

Figma: **Design System Legacy** → page **Marketing · Questionnaire landing** ([570:21](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=570-21)) · Read me [577:40287](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=577-40287) · components frame "Components · mkt landing" [570:22](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=570-22).
Built with [`foundations.md`](foundations.md) (mkt v0.5) and the `br-blue-men` poses (Raising hand, Standing thinking, Arms up, Waving). State: v0.1, final decisions by Matz 2026-10-19. Copy: Hemmingway v3 / v3.1.

Funnel: social post → this single-scroll questionnaire landing → one of 3 next steps (learn more · book a demo · try the light version). Every answer lands in a Google Sheet for sales.

## Hard rules

1. **Market: United States only** (Matz, 2026-10-19). The Country field is a dropdown: **United States** (default) · **Other** ("Other" shows a short text field by a Wix Rule). Mexico is removed; no other countries, no Spanish version.
2. **All 3 options for everyone**, any company size. No size cutoff and no Rule depends on company size. The employee ranges (1–49 · 50–200 · 201–500 · 500+) are data for sales only.
3. **Light version**: open to any company, allows **up to 50 users** in the system. Option helper (helper style, `mkt/small`, `text/muted`): **"Up to 50 users."** Always say "light version", never "free" (no pricing anywhere).
4. **Demo**: option text **"A 20–45 minute demo."**
5. **Industry rule**: only Manufacturing, Healthcare and Logistics (they have their own page) carry "for [industry]". Food & beverage, Retail, Security & facilities and Other go to the general page and drop it (table below).
6. **Consent lines** (Hemmingway, privacy policy draft):
   - Checkbox A, **required** when `next_step` = demo or light: "Blue Roster can email me about my request and related product updates. I can unsubscribe anytime."
   - Notice under it, always shown, helper style (`mkt/small` 14, `text/muted` `#535353`): "We use your answers to reply to your request and follow up about Blue Roster. Details in our Privacy Policy." ("Privacy Policy" links to the policy page, URL TBD.)
   - Checkbox B, **optional, unchecked by default**: "Blue Roster can call or text me at the number above, including with automated technology, about its products. Consent isn't required to buy anything. Reply STOP to opt out." Keep it only if sales will call/text (pending client); stored as its own column `consent_call_text`.
7. No testimonials, no prices, no logos other than `br-logo`. Approved stats only (see [`banners.md`](banners.md#approved-stats-only)). Orange `#F66C1E` is not used in the form UI.
8. Hero: **"See your schedule run itself."** (option A, decided by Matz).

## Frames

| Row | Frames (desktop 1440 / mobile 390) |
|---|---|
| 1 | D0 Hero [574:51](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=574-51) → D1 Step 1 Industry [574:174](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=574-174) → D2 Step 2 Company [574:371](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=574-371) → D3 Step 3 Team [574:494](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=574-494) → D4 Step 4 How it runs today [574:606](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=574-606) |
| 2 | D5 Step 5 What's next × 4 industry treatments: Manufacturing [575:137](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=575-137) · Healthcare [575:264](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=575-264) · Logistics [575:391](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=575-391) · General (Food / Retail / Security / Other) [575:518](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=575-518) |
| 3 | Post-submit confirmation, the one Navy band per page: D6 Learn more (Mfg) [576:141](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=576-141) · D7 Book a demo [576:257](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=576-257) · D8 Light version [576:370](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=576-370) · D9 `/light-version` placeholder [576:483](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=576-483) |
| 4 | Mobile 390: M0 Hero [577:21](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=577-21) · M1 Industry [577:126](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=577-126) · M2 Company, error state [577:253](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=577-253) · M5 Step 5, demo + errors [577:376](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=577-376) · M6 Confirmation [577:501](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=577-501) |

Yellow notes in the frames are build/TBD annotations, not UI.

## Components (`mkt-*`, frame 570:22)

All bind to `mkt` variables and `mkt/*` text styles. Never use `br-*` product components on marketing pages.

| Component | Node | Props / variants | Anatomy and tokens |
|---|---|---|---|
| `mkt-button` | [571:21](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=571-21) | Variant Primary · Secondary · Tertiary × Size L 56 · M 48 · S 40; text Label | Radius 8, gap 8, horizontal padding L 32 · M 24 · S 16, text `mkt/*/button`. Primary fill `action/primary` + label `action/on-primary` (Light `#064DB7`/`#F9F9F9` 7.25:1, Navy band `#F9F9F9`/`#002458` 14.32:1). Secondary = 1.5 px outline `action/primary`. Tertiary = text link, no padding. CSS helper `.mkt-button-primary`. |
| `mkt-text-field` | [571:40](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=571-40) | State Default · Focus · Filled · Error; Label; Show helper | 480 wide, gap 8. Label `mkt/*/button`, value/placeholder `mkt/*/body`, helper `mkt/*/small` (`text/muted`). Field edge `text/muted` (3:1 for controls). Error text and edge: literal `#B42318` (gap: no mkt feedback token). Example error "Add your company name to continue." |
| `mkt-progress` | [570:68](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=570-68) | Step 1–5; Show note | Segmented bar, 5 segments, 480 wide, label "Step N of 5" (`mkt/*/small`). Wix Forms has no progress bar: always also put "Step N of 5" in the page title; the bar is optional decoration. |
| `mkt-option-card` | [572:343](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=572-343) | Type Single (radio) · Multi (checkbox) × State Default · Hover · Selected; Label; Description; Show description | 480 × 100, radius 12, padding 20/24, gap 16. Default `surface/raised` + 1 px `border/default`; Hover 2 px `vertical/mfg/accent`; Selected fill `vertical/mfg/tint` + 2 px `vertical/mfg/accent-strong`. Label `mkt/*/h4`, description `mkt/*/small`. Indicator stroke `text/muted` (7.31:1). Keyboard focus = Hover look. |
| `mkt-result-card` | [573:21](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=573-21) | Industry Manufacturing · Healthcare · Logistics · General × State Default · Hover · Selected; Eyebrow, Title, Body, Stat value, Stat label, Destination, Helper (+ Show toggles) | Step 5 choice card, 400 wide, radius 16. Industry sets accent bar, eyebrow, stat and selected colors (`vertical/<k>/*`); Selected = `vertical/<k>/tint` + 2 px `vertical/<k>/accent-strong`. Eyebrow `mkt/*/eyebrow`, title `mkt/*/h3`, stat value `mkt/*/h2`, stat label/helper `mkt/*/small`. General = Food, Retail, Security & facilities, Other (generic tokens + 216 h stat). Health and General accent bars are decorative (below 3:1). Helper "Up to 50 users." shows on the light-version card only. |
| `mkt-step` | [572:457](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=572-457) | Viewport Desktop (720 wide, gap 32) · Mobile (350 wide, gap 24) × Content Cards · Input; Question, Hint, Tag, Show toggles | One step per screen: progress ("Step N of 5"), question (`mkt/*/h2`), hint (`mkt/*/body`), options (8 slots, hide unused) or input, Back/Next. Multi-question steps (2–5) compose the same pieces inside a step frame. |
| `mkt-select` | [573:170](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=573-170) | State Default · Focus · Filled; Label | Wix Forms Dropdown. 480 wide, label `mkt/*/button`, value `mkt/*/body`, edge `text/muted`. Country: "United States" (default) · "Other". |
| `mkt-checkbox` | [573:186](https://www.figma.com/design/k05NWBKMjsvo5hEugQc2Tq/Design-System-Legacy?node-id=573-186) | State Default · Checked · Error; Label; Privacy line; Show privacy | Wix Forms Checkbox. 480 wide, gap 6, label and helper `mkt/*/small`. Error "Check the box so we can reply." in literal `#B42318`. The component's **default** text is the superseded "I agree… / As described in the Privacy Policy"; instances in the frames carry the final lines from rule 6. Always use the rule 6 copy. |

Observed in Figma (flag, do not copy): the `mkt-result-card` Hover state uses `vertical/mfg/accent` as its stroke for every industry, and `mkt-step` Mobile uses the desktop `small` style for the progress label.

## Flow and copy (one Wix Form, 5 pages)

**Hero (D0/M0).** Headline **"See your schedule run itself."** · Sub "Tell us how your shifts run. Five quick steps, then pick what's next." · CTA **Start** (scrolls to / opens the form) · blue man illustration. Header = logo only; no header CTA, so every demo request goes through the form.

**Step 1 of 5 · Your industry.** "What industry are you in?" (required, single choice): Manufacturing · Healthcare · Logistics & warehousing · Food & beverage · Retail · Security & facilities · Other [short text].

**Step 2 of 5 · Your company.** Company name (required) · "How many employees do you schedule?" (required) 1–49 · 50–200 · 201–500 · 500+ · "How many sites?" (required) 1 · 2–5 · 6+ · "Do you run 24/7?" (optional) Yes · No · **Country** (required, dropdown): **United States** (default) · Other [short text by Rule].

**Step 3 of 5 · Your team.** "What roles do your people work?" (required, multi; shown by industry):
- Manufacturing: Line operators · Machine operators · Maintenance · Quality · Supervisors
- Healthcare: RNs · CNAs · Techs · Support staff · Supervisors
- Logistics: Pickers & packers · Forklift operators · Drivers · Supervisors
- Food, Retail, Security, Other: Hourly staff · Shift leads · Supervisors · Other

"Which certifications do you check before a shift?" (optional): OSHA · RN / CNA / BLS · Forklift · None · Other. Role and certification lists are TBD with the client.

**Step 4 of 5 · How it runs today.** "How do you schedule today?" (required) Spreadsheets · Paper or whiteboard · Group texts · Another scheduling tool · HR system · "What breaks most often?" (optional, up to 2) Last-minute call-outs · Overtime cost · Expired certifications · Demand surges · Swaps and time-off · "When do you want this fixed?" (optional) This month · This quarter · Just exploring.

**Step 5 of 5 · What's next.** "What would you like to do?" (required, last question so it lands in the file), 3 `mkt-result-card`s for everyone:
- Learn more about Blue Roster for [industry] (see industry rule)
- Book a demo: "A 20–45 minute demo."
- Try the light version: helper "Up to 50 users."

Contact (required for demo and light; optional for learn more): First name · Last name · Work email · Job title (optional) · Phone (optional), then the consent lines (rule 6). CTA **Continue**.

Approved stat per industry on the cards: Mfg 4.5 h saved per week · Health under 5 min to fill a gap · Logistics 18 min vs 22 hrs to staff a surge · General managers spend 216 h a year scheduling.

**After submit (D6–D9, Navy band, White primary button).**
- Redirect titles: Learn more "Taking you to Blue Roster for [industry]…" (general: "Taking you to Blue Roster…") · Demo "Taking you to booking…" + "We'll come in knowing your team." · Light "Opening the light version…"
- Fallback buttons (if the redirect stalls, approved): "Continue to Blue Roster for [industry]" (general: "Continue to Blue Roster") · "Open the calendar" · "Open the light version".
- `/light-version` placeholder (hidden, no-index): "The light version is almost ready." · "We saved your answers." · buttons "Book a demo" · "Learn more about Blue Roster for [industry]" (general: "Learn more about Blue Roster").

**Errors.** Required choice "Pick one to continue." · required text "Add your [company name / first name / last name] to continue." · email "Enter a valid work email." · consent "Check the box so we can reply." · submit failed "Something went wrong. Try again."

**Footer.** "© 2026 Blue Roster · Privacy (URL TBD) · blueroster.com".

### [industry] token rule

| Line | Manufacturing / Healthcare / Logistics | Food & beverage · Retail · Security & facilities · Other |
|---|---|---|
| Step 5 option | Learn more about Blue Roster for [industry] | Learn more about Blue Roster |
| Redirect title | Taking you to Blue Roster for [industry]… | Taking you to Blue Roster… |
| Fallback button | Continue to Blue Roster for [industry] | Continue to Blue Roster |
| /light-version button | Learn more about Blue Roster for [industry] | Learn more about Blue Roster |

---

## Wix build notes

Copied from the team's `design/landing-wix-notes.md` (2026-10-19, final decisions by Matz). Field keys and element IDs are placeholders.

### Wix theme (Site Styles)

All Inter (Google Font in Wix). Black only for display and H1; H2–H4 Semi Bold.

| Wix theme text | mkt style | Desktop (1440) | Mobile (390) |
|---|---|---|---|
| Heading 1 | `mkt/display` | Inter Black 80 / 105%, −2.5 px | 48 / 110%, −1.5 |
| Heading 2 | `mkt/h1` | Inter Black 44 / 110%, −2.5 | 36 / 110%, −1.5 |
| Heading 3 | `mkt/h2` (step titles, question titles) | Inter Semi Bold 34 / 115%, −1.5 | 28 / 120%, −1 |
| Heading 4 | `mkt/h3` (choice cards) | Semi Bold 24 / 120%, −0.5 | 22 |
| Heading 5 | `mkt/h4` (field questions, option labels) | Semi Bold 20 / 130% | 18 |
| Paragraph 1 | `mkt/lead` | Regular 22 / 140% | 18 |
| Paragraph 2 | `mkt/body` | Regular 16 / 140% | 16 |
| Paragraph 3 | `mkt/small` | Regular 14 / 140% | 14 |
| Button | `mkt/button` | Bold 16 / 125% | 16 |
| (eyebrow, set per element) | `mkt/eyebrow` | Bold 14, UPPER, +1.5 | 12, +1.2 |

Wix scales type with the viewport: set desktop values on the 1440 breakpoint and mobile values on the mobile breakpoint by hand.

- **Colors (Light page):** page `#F9F9F9` · cards/fields `#FFFFFF` · headings `#002458` · body `#111827` · muted `#535353` · dividers `#D1D5DB` · primary button `#064DB7` with `#F9F9F9` text (7.25:1) · progress/hover accent `#1E75F6` (non-text only) · selected tint `#C7DDFD`.
- **Navy band (confirmation section only):** bg `#002458` · primary button `#F9F9F9` with `#002458` text (14.32:1) · body `#C7DDFD` · muted/eyebrow `#8EBAFA`.
- **Industry accents on Step 5 cards:** Mfg `#1E75F6` / text `#064DB7` / tint `#C7DDFD` · Health `#14B8A6` / `#13726E` / `#CBECE8` · Logistics `#BA7517` / `#87591C` / `#ECDFCC` · General `#9CA3AF` / `#5F6673` / `#E6E8EA`. Health and General accent bars are decorative only (under 3:1).
- **Orange:** `#F66C1E` highlights and illustration only, never a button; Navy text on it, never white. Not used in the form UI.
- **Not in mkt:** error red `#B42318` (literal, flagged as a gap).
- **Grid:** 12 col, 24 gutter, 80 margin, 1280 max at 1440 · 4 col, 16 gutter, 20 margin at 390.

### Figma piece → Wix element

| Figma | Wix |
|---|---|
| Header (logo only) / Footer | Site header + footer: "© 2026 Blue Roster · Privacy (URL TBD) · blueroster.com". No header CTA. |
| D0 Hero | Section: text + button (scrolls to / opens the form) + image (blue man exported as SVG/PNG from `br-blue-men`) |
| One Wix Form, 5 pages | **Wix Forms multi-step** ("Pages"), one page per step |
| `mkt-progress` + "Step N of 5" | No native progress bar: "Step N of 5" in each page title; the segmented bar is optional decoration |
| `mkt-option-card` · Single | **Single choice** field (radio) styled as cards |
| `mkt-option-card` · Multi | **Multi choice** field (checkboxes). "Up to 2" on pain: confirm Wix can cap it, otherwise validate in Velo |
| `mkt-text-field` | **Short text** (Company name, First/Last name, Job title) · **Email** (Work email) · **Phone** |
| `mkt-select` | **Dropdown** Country: **United States** (default) · Other. "Other" shows a Short text field by a Rule. Market: US only (Mexico removed). |
| `mkt-checkbox` × 2 + notice | Rule 6 lines. Checkbox A required when `next_step` = demo or light; notice as checkbox help text or a text element under it; checkbox B optional, unchecked, own column `consent_call_text` |
| Step 2 employees | **Single choice** ranges 1–49 · 50–200 · 201–500 · 500+ (sales data; no Rule depends on it) |
| Step 3 roles by industry | One Multi choice field per industry, shown by a **Rule** on `industry` |
| `mkt-result-card` (Step 5) | **Single choice** `next_step` (`learn_more` / `demo` / `light`), required, last question. All 3 options for everyone. Built as two fields (see below). Card stat and "Goes to…" lines are option descriptions or static text |
| Contact required for demo/light | **Rules**: name + work email + consent required when `next_step` = demo or light; optional for learn_more |
| `mkt-button` Back / Next / Continue | Form's own Previous / Next / Submit buttons (primary `#064DB7`) |
| D6–D8 confirmation (Navy band) | Form success message (or a short success section), then Velo redirect |
| D9 /light-version | Hidden, no-index page `/light-version` |

**Two `next_step` fields (industry label rule).** Wix Forms can't change an option label from an earlier answer, so (decision Hugo/István) use two fields + a Wix Rule, no Velo for the label:
- `next_step_industry`: "Learn more about Blue Roster for [industry]", "Book a demo", "Try the light version". Shown when `industry` = Manufacturing / Healthcare / Logistics.
- `next_step_general`: "Learn more about Blue Roster", "Book a demo", "Try the light version". Shown when `industry` = Food & beverage / Retail / Security & facilities / Other.
- Both store `learn_more` / `demo` / `light` and are required when visible. The Google Sheet automation merges them into one `next_step` column (or formula `=IF(A2<>"",A2,B2)`); Velo reads `v.next_step_industry || v.next_step_general`.

### Where the sales file comes from

1. Every submission lands in **Forms & Submissions**; CSV export is the backup (times in UTC).
2. **Wix Automation:** "Form submitted" → **Update Google Sheets** → sheet "BR · Questionnaire leads", one row per lead, every field mapped. If the Google permission is removed, skipped rows are not backfilled, so keep the CSV backup.
3. Hidden fields set by Velo: `lead_id`, `utm_source`, `utm_campaign`, `landing_url`.
4. Contact fields map to Wix Contacts. Demo bookings (Wix Bookings) join the row by **work email**.
5. Optional: automation email to sales, flag `next_step = demo` in the subject.

### Velo redirect + /light-version

Native redirect is one URL for everyone, so routing needs Velo (Dev Mode). Log `values` once; v2 choice fields return the option **value**, not the label.

```js
import wixLocationFrontend from 'wix-location-frontend';
const LIGHT_URL = '/light-version';               // swap for the real light version later (URL TBD)
// Only these industries have their own page and carry "for [industry]" in copy
const PAGES = { manufacturing: '/manufacturing', healthcare: '/healthcare', logistics: '/logistics' };
const NAMES = { manufacturing: 'Manufacturing', healthcare: 'Healthcare', logistics: 'Logistics' };
const GENERAL = '/';                              // TBD: '/' or '/active-scheduling' (Food, Retail, Security & facilities, Other)
const DEMO = '/booking-calendar/intro-to-blue-roster-software';
const hasPage = (ind) => Boolean(PAGES[ind]);
const forIndustry = (ind) => hasPage(ind) ? ` for ${NAMES[ind]}` : '';   // '' for general-page industries
let v = {};
$w.onReady(() => {
  const q = wixLocationFrontend.query;
  $w('#form').setFieldValues({ lead_id: crypto.randomUUID(), utm_source: q.utm_source || '', utm_campaign: q.utm_campaign || '', landing_url: wixLocationFrontend.url });
  $w('#form').onSubmit(values => { v = values; });
  $w('#form').onSubmitSuccess(() => {
    v.next_step = v.next_step_industry || v.next_step_general;   // two fields, one value
    const p = new URLSearchParams({ lead: v.lead_id, industry: v.industry, size: v.employee_bucket }).toString();
    if (v.next_step === 'demo')  return wixLocationFrontend.to(DEMO);
    if (v.next_step === 'light') return wixLocationFrontend.to(`${LIGHT_URL}?${p}`);
    // learn_more: confirmation copy + destination depend on whether the industry has its own page
    $w('#redirectTitle').text = `Taking you to Blue Roster${forIndustry(v.industry)}…`;
    $w('#fallbackButton').label = `Continue to Blue Roster${forIndustry(v.industry)}`;
    const url = hasPage(v.industry) ? PAGES[v.industry] : GENERAL;
    $w('#fallbackButton').link = url;
    wixLocationFrontend.to(url);
  });
});
// /light-version page code: same rule for its Learn more button
// const ind = wixLocationFrontend.query.industry;
// $w('#learnMoreButton').label = `Learn more about Blue Roster${forIndustry(ind)}`;
// $w('#learnMoreButton').link = hasPage(ind) ? PAGES[ind] : GENERAL;
```

- `/light-version` reads `lead`, `industry`, `size` from the query and offers Book a demo + Learn more. When the real light version exists, change `LIGHT_URL` only.
- No-code fallback if Velo is not allowed: one hidden "Next steps" page with 3 static buttons (Learn more can't follow the industry, and the click isn't in the file).

### Limitations / to confirm

- **Plan:** 5 form steps need Wix **Core / Business or higher** (Light allows 3 steps). Exact plan to be confirmed.
- No step branching in new Wix Forms (only show/hide/required Rules), so the 5 pages are fixed for everyone.
- No native progress bar and no native UTM capture (hidden fields + Velo).
- Choice fields have limited styling: cards may render as styled radios/checkboxes. Keep label, selected color and 3:1 control edges; the hover shadow can be dropped.
- Velo needs Dev Mode and someone to maintain it.
- **Privacy Policy page:** Wix has no policy generator; create it manually once the client/attorney fills the TBDs, and link it in the footer ("Privacy"), the form notice ("Privacy Policy") and the cookie banner. URL TBD.

## Open items (TBD, do not invent)

Privacy Policy page content and URL · call/text checkbox (keep only if sales calls/texts, incl. automated) · role and certification lists · general page URL (`/` or `/active-scheduling`) · light-version URL · exact Wix plan.
