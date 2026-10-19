# Changelog

## v6.1 · 2026-10-19 · Approved banner sizes, Story safe zone and mockup layout

István (art direction) approved the banner values that v6 shipped as proposals, with adjustments. The proposal markers are removed and the values are now marked "approved by István 2026-10-19".

**Changed**
- `marketing/banners.md`: Story safe zone is **250 px top and bottom** (was "proposal, ~250 px"). Minimum sizes approved: support/body text ≥ 24 px on 1080/1200 formats (never 16 px), eyebrows/chips and button text ≥ 20 px on 1080/1200, all Display text ≥ 12 px. Mockup layout per format approved as is. The accessibility rule and the hand-off checklist now state the values.
- `marketing/README.md` (rule 6), `AGENTS.md` (section 11), `.cursor/rules/br-marketing.mdc`, `skills/BR_Legacy/SKILL.md`, `claude/BR_Legacy/SKILL.md` and `claude/BR_Legacy.zip` (Marketing mode self-check), `gpt/instructions.md`, `gemini/gem-instructions.md` (step 7): same minimum sizes and safe zone.
- `llms-full.txt`: the embedded `AGENTS.md`, `SKILL.md`, `marketing/README.md` and `marketing/banners.md` updated to match.

**Note:** the 3 screen banners (Attendance, My Schedule, Overtime) in Figma are being updated by Mc Bess to 24 px support lines and 20 px button text in all three formats; they are not in `marketing/references/` yet.

## v6 · 2026-10-19 · Marketing design system

Adds the Blue Roster **marketing** layer so any AI can replicate the campaign banners and the questionnaire landing. The product (Legacy) kit is unchanged.

**Added**
- `marketing/README.md`: index, keyword → file table and ten rules.
- `marketing/foundations.md`: from Figma *Design System Legacy* page "Marketing · Foundations" (561:21): colors (Light page + Navy band), 20 `mkt` text styles (display 80 px at 1440; H2–H4 Semi Bold; Black only for display/H1), 4 `mkt/grid` styles, section spacing, and the 6 approved decisions (no Dark pages, Navy bands; Mfg buttons `#064DB7`, `#1E75F6` non-text accent; Navy band button White `#F9F9F9` with Navy text; orange `#F66C1E` with Navy text only, never white).
- `marketing/landing.md`: questionnaire landing (page 570:21, Read me 577:40287): `mkt-button`, `mkt-text-field`, `mkt-progress`, `mkt-option-card`, `mkt-result-card`, `mkt-step`, `mkt-select`, `mkt-checkbox`; frames, flow and copy; rules (3 options for everyone, light version "Up to 50 users.", industry rule, consent lines, US-only market with Country = United States default · Other); Wix build notes.
- `marketing/banners.md`: formats (LinkedIn 1200x627, 1080x1080, Story 1080x1920, Display), naming, Asset Library structure, 5 families and rotation, styling rules, banners with system screens (Attendance Today, My Schedule Day, Overtime cards), approved headlines, approved-stats-only rule, accessibility and a hand-off checklist.
- `marketing/references/`: 3 Light screen captures (2x) and 6 approved banners (one per family + Display).
- `tokens/marketing.css` and `tokens/marketing.md` (mkt v0.5, orange `accent/secondary` `#F66C1E` with Navy `accent/on-secondary`).
- `.cursor/rules/br-marketing.mdc`: Cursor rule for marketing requests.
- `CHANGELOG.md` (this file).

**Changed**
- `AGENTS.md`: marketing note at the top, new section 11 "Marketing layer", marketing rows in the keyword → spec table, marketing-over-product disambiguation.
- `.cursor/rules/blueroster.mdc`, `.cursor/rules/blueroster-build.mdc`, `.cursor/rules/br-legacy.mdc`: point marketing work to `marketing/`.
- `skills/BR_Legacy/SKILL.md`, `claude/BR_Legacy/SKILL.md`, `claude/BR_Legacy.zip`: new "Marketing mode".
- `gpt/instructions.md`, `gemini/gem-instructions.md`: marketing step 7 and marketing knowledge files.
- `skills/README.md`, `README.md`: marketing install and usage notes.
- `llms.txt`: marketing summary, keyword rows and a Marketing link section. `llms-full.txt`: updated `AGENTS.md` and `SKILL.md`, plus the marketing files appended.

Earlier versions (v1–v5) were shipped as archives without a changelog.
