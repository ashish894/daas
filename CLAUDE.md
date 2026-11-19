# Project instructions

## Design system

Qatalyst uses its own system, built on Carbon's structure (type scale, spacing, control sizes, icons) with custom foundations. This file describes the system as it is now. Follow it exactly; do not fall back to Carbon defaults for anything defined here.

All tokens live on `:root` in `<helmet><style>` in each DC. Always use a token. Never hardcode a hex, shadow or radius that has a token. If something new needs a value no token covers, ask before adding one.

Reference order: this file first. Where it's silent, follow how Consultant already does it. If neither covers it, ask. The original DaaS OG (14.3) is reference only and is never edited.

## Color

- Brand: `--q-brand` `#191A15`. Hover `--q-brand-hover` `#2F302A`, active `--q-brand-active` `#45463F`.
- Brand tint (highlights, selected rows, info fills): `--q-brand-tint` `#E8E8E2`, hover `--q-brand-tint-hover` `#DCDCD5`.
- Text on brand: `--q-text-on-brand` (white).
- Focus outline: `--q-brand`.
- Text: `--q-text-primary`, `--q-text-secondary`, `--q-text-helper`, `--q-text-disabled`, plus `--q-text-error`, `-success`, `-warning`.
- Warning: `--q-text-warning` is for warning text only (Carbon yellow 70 `#684E00` in light, yellow 30 `#F1C21B` in dark). `--q-support-warning` is for everything else that signals a warning: bars, donuts, dots, icons, outlines (Carbon yellow 30 `#F1C21B` in both modes). Carbon yellow 60 (`#8E6A00`) is not used anywhere.
- Chart colours: every chart (bars, donuts, stacked bars, legends and the status dots that key into them) uses only the `--q-chart-*` tokens, always the Carbon 40 shade, same in light and dark mode: `--q-chart-1` purple `#BE95FF`, `--q-chart-2` green `#42BE65`, `--q-chart-3` blue `#78A9FF`, `--q-chart-4` orange `#FF832B`, `--q-chart-5` red `#FF8389`, `--q-chart-other` gray `#A8A8A8` ("everyone else" buckets). Unfilled space uses `--q-surface-strong`. Any new chart colour is added as the next `--q-chart-*` token in its 40 shade. Text beside chart colours (legends, status words) uses the default text colour. Blue 40 in charts is allowed despite the no-blue rule.
- Member status uses the chart tokens: Active `--q-chart-2`, Invited `--q-chart-3`, Deactivated `--q-chart-5`, as an 8px dot beside the status word.
- Surfaces: `--q-surface-base` (white), `-subtle`, `-muted`, `-strong`, `-heavy`, `-heaviest`, `-inverse` (tooltips), `-warning`. Layout and chat backgrounds: `--q-surface-layout`, `--q-surface-chat` (`#FAFBF8`).
- Modals, dialogs and popovers use `--q-surface-base` (`#FFFFFF`), always. No other surface for them.
- Borders: `--q-border-subtle`, `--q-border`, `--q-border-strong` (input fields), `--q-border-faint`, `--q-border-inverse`, `--q-border-on-color`, `--q-border-error`.
- Status colors beyond the tokens come from the Carbon palette only.
- No teal, and no Carbon blue as an accent.
- Exception, document type colours (Consultant only): each document type has its own Carbon hue for telling types apart, with matching ink, light background and lighter fill. Summary purple, Market research magenta, Competitive analysis orange, BRD blue, FRD teal, User stories green. BRD and FRD are the only allowed uses of blue and teal. Admin doesn't use these.
- Admin dashboards stick to tokens and status colours. If a chart ever compares teams, reuse each team's tile colour.

## Type

- Inter for all UI. JetBrains Mono for code and IDs. No IBM Plex.
- Sizes and line heights follow the Carbon type scale (12/16, 14/18, 14/20, 16/24, 20/28, 28/36, 32/40).
- Minimum size 12px. Exception: 11px only inside avatars and count badges.
- Letter-spacing 0 everywhere.
- Sentence case for all labels, buttons and titles.

## Radius

Use only these tokens:
- `--q-radius-sm` 4px: tooltips, progress bars, checkboxes, tiny squares
- `--q-radius-md` 6px: buttons, inputs, icon buttons, segmented controls, all controls
- `--q-radius-lg` 8px: menus, dropdown lists, popovers, small tiles (the dropdown's trigger is a control and uses `--q-radius-md`)
- `--q-radius-xl` 12px: dialogs, modals, cards
- `--q-radius-full` 999px: pills, chips, dots, avatars

## Elevation

Use only these shadow tokens:
- `--q-shadow-menu`: menus, dropdowns
- `--q-shadow-raised`: raised panels, hovered cards
- `--q-shadow-pop`: tooltips, small popovers
- `--q-shadow-node`: canvas nodes, floating cards
- `--q-shadow-up`: bottom bars and docks
- `--q-shadow-selected`: selected item on a tinted surface (e.g. left nav)

Borders are real borders, never inset shadows.

## Spacing and size

- Spacing steps: 2, 4, 8, 12, 16, 24, 32, 48. Nothing else.
- Icon to label gap: 8px.
- Control heights: 24, 28, 32, 40, 48.
- Input fields: full 1px `--q-border-strong` border, `--q-radius-md`.

## Components and icons

- Icons: Carbon Icon component only.
- Icon colour: icons take the colour of the text around them, always a token. `--q-text-primary` by default, `--q-text-secondary` in table headers, field icons and meta, status tokens for status (`--q-support-warning` for warning icons), `--q-text-on-brand` inside brand buttons and ticked checkboxes.
- Dropdowns that pick a value always show a trailing `chevron--down`. Icon-only menu buttons don't need one.
- Dropdown triggers look like input fields: `--q-surface-base` fill, 1px `--q-border-strong` border, `--q-radius-md`. Never filled at rest; `--q-surface-muted` only on hover and while open. Read-only values use `--q-surface-subtle` fill with a `--q-border-subtle` border and no chevron.
- No emoji in the UI.
- Gradients only for decorative backgrounds and fade masks. Never on buttons, text or components.

## Pills, badges and toggles

- Pills always have a 1px border, 20px tall (24px or 28px only next to items of that size), `--q-radius-full`, 12px text.
- Neutral pill (tags, roles): `--q-surface-subtle` fill, `--q-border` border, `--q-text-secondary` text.
- Coloured pill (status, document type, artifact): border in the pill's own text or icon colour.
- Overflow: show at most 2 pills, then "+N". The "+N" looks exactly like the pills beside it; hover and open state darken the fill to `--q-surface-strong`. Clicking opens a list panel: header with the count and context, one item per 40px row, `--q-radius-xl`, `--q-shadow-menu`, click outside to close.
- Count badges: 20px tall, min 20px wide, 11px bold, `--q-radius-full`, 1px border. Attention (pending, active filters): `--q-brand` fill and border, `--q-text-on-brand` text. Total (plain counts): `--q-surface-subtle` fill, `--q-border` border, `--q-text-secondary` text. A badge sitting on an icon may be 16px.
- Segmented controls: `--q-surface-subtle` track with 2px padding and a 1px `--q-border` border, `--q-radius-md`. Options are 28px, `--q-radius-md`; selected uses `--q-toggle-knob` fill and `--q-text-primary`, others `--q-text-secondary`.

## Layout

- Cards with long content (lists, tables, activity): the title stays fixed and only the content scrolls inside the card.
- Dashboards fit the window and never scroll as a page; their cards split the height and scroll inside.
- Every card has 16px between its title and the first element below it.
- Tables: header 48px, 14px medium weight, `--q-text-secondary`; rows 16px side padding with 16px between columns; all columns left-aligned.

## Dates and times

- Under a week old: relative, in full words. "Just now", "5 min ago", "3 hours ago", "Yesterday", "4 days ago". Never "4h" or "12d".
- A week or older: the date, "Nov 14". Add the year only if it isn't the current year: "Nov 14, 2025".
- Times: 12-hour, no leading zero, "3:42 PM". With a date: "Nov 14, 3:42 PM".
- Sentence case at the start of a line ("Just now"), lowercase mid-line ("Qatalyst · just now").

## Dark mode

Every token has a dark value under `html[data-q-theme="dark"]`. Keep existing dark values as they are. Don't design new dark mode treatments unless asked.

## Accessibility (strict)

Every color pairing must pass WCAG 2.1 AA: 4.5:1 for body text, 3:1 for large text (24px+, or 18.66px+ bold) and for UI component boundaries and icons. Check contrast against the actual background in both themes before shipping. Disabled controls are the only exemption.
