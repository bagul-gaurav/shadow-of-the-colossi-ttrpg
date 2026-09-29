---
name: Survey of Ecerah
description: The party's journal and quest ledger drawn as a surveyor's sheet of Ecerah, embedded in the Shadow of the Colossi wiki.
colors:
  ground: "#eef2ee"
  ground-2: "#e2e9e4"
  ground-3: "#d6dfd9"
  ink: "#1c2327"
  ink-2: "#48534e"
  ink-3: "#58625e"
  terrain: "#8a5129"
  contour: "rgba(138, 81, 41, .30)"
  hydro: "#1d5a85"
  hydro-tint: "rgba(29, 90, 133, .10)"
  overprint: "#a8215f"
  on-overprint: "#ffffff"
  danger: "#a3312a"
  rule: "#b7c2bb"
  rule-strong: "#1c2327"
  night-ground: "#131a1e"
  night-ground-2: "#1a2328"
  night-ground-3: "#243037"
  night-ink: "#e4ebe7"
  night-ink-2: "#aab7b1"
  night-ink-3: "#85938d"
  night-terrain: "#d49b6b"
  night-contour: "rgba(212, 155, 107, .20)"
  night-hydro: "#86bde3"
  night-hydro-tint: "rgba(134, 189, 227, .12)"
  night-overprint: "#e5609f"
  night-on-overprint: "#1a0b12"
  night-danger: "#f08b80"
  night-rule: "#2e3b42"
  night-rule-strong: "#c9d3ce"
typography:
  display:
    fontFamily: "Barlow Semi Condensed, Arial Narrow, sans-serif"
    fontSize: "clamp(1.953rem, 5vw, 2.441rem)"
    fontWeight: 600
    lineHeight: 1.05
    letterSpacing: "0.04em"
  headline:
    fontFamily: "Barlow Semi Condensed, Arial Narrow, sans-serif"
    fontSize: "1.953rem"
    fontWeight: 600
    lineHeight: 1.1
    letterSpacing: "0.01em"
  title:
    fontFamily: "Barlow Semi Condensed, Arial Narrow, sans-serif"
    fontSize: "1.5625rem"
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: "0.02em"
  body:
    fontFamily: "Source Sans 3, Source Sans Pro, system-ui, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.55
  body-small:
    fontFamily: "Source Sans 3, Source Sans Pro, system-ui, sans-serif"
    fontSize: "0.875rem"
    fontWeight: 400
    lineHeight: 1.55
  label:
    fontFamily: "Barlow Semi Condensed, Arial Narrow, sans-serif"
    fontSize: "0.75rem"
    fontWeight: 600
    lineHeight: 1.2
    letterSpacing: "0.14em"
  button:
    fontFamily: "Barlow Semi Condensed, Arial Narrow, sans-serif"
    fontSize: "0.875rem"
    fontWeight: 600
    lineHeight: 1
    letterSpacing: "0.1em"
  lettering:
    fontFamily: "Barlow Semi Condensed, Arial Narrow, sans-serif"
    fontSize: "1.953rem"
    fontWeight: 600
    lineHeight: 1
    letterSpacing: "0.5em"
rounded:
  hair: "2px"
  sm: "3px"
spacing:
  s-1: "0.25rem"
  s-2: "0.5rem"
  s-3: "0.75rem"
  s-4: "1rem"
  s-5: "1.5rem"
  s-6: "2rem"
  s-7: "3rem"
components:
  button-overprint:
    backgroundColor: "{colors.overprint}"
    textColor: "{colors.on-overprint}"
    typography: "{typography.button}"
    rounded: "{rounded.sm}"
    padding: "0 1.5rem"
    height: "2.75rem"
  button-ink:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.ground}"
    typography: "{typography.button}"
    rounded: "{rounded.sm}"
    padding: "0 1.5rem"
    height: "2.75rem"
  button-line:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    typography: "{typography.button}"
    rounded: "{rounded.sm}"
    padding: "0 1.5rem"
    height: "2.75rem"
  button-text:
    backgroundColor: "transparent"
    textColor: "{colors.ink-2}"
    typography: "{typography.button}"
    padding: "0 0.5rem"
    height: "2.75rem"
  field-ruled:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    padding: "0.5rem 0.25rem"
    height: "2.75rem"
  select-plain:
    backgroundColor: "transparent"
    textColor: "{colors.hydro}"
    typography: "{typography.body-small}"
    rounded: "{rounded.sm}"
    padding: "0.25rem 2rem 0.25rem 0.5rem"
    height: "2.25rem"
  entry-row:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    padding: "1rem 0.75rem 1rem 0.5rem"
  entry-row-current:
    backgroundColor: "{colors.hydro-tint}"
  quest-row:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    typography: "{typography.body}"
    padding: "0.5rem 0"
    height: "3.5rem"
  survey-mark:
    backgroundColor: "transparent"
    textColor: "{colors.ink-2}"
    rounded: "{rounded.sm}"
    size: "2.75rem"
  survey-mark-done:
    textColor: "{colors.hydro}"
---

# Design System: Survey of Ecerah

## Overview

**Creative North Star: "Survey of the Colossi"**

The party's record is a surveyor's sheet of Ecerah. Journal entries are field notes indexed in a map legend; quests are plotted survey marks in a ruled ledger. Everything is drawn the way a printed survey sheet is drawn: a pale grey-green ground, near-black ink, hairline rules instead of boxes, spaced condensed capitals for map lettering, and contour lines that fill empty ground. Colour is not decoration; each ink carries one meaning, the way map inks do.

Density is working-document density: rows are ruled, not carded; labels are small spaced caps; there is one magenta action per screen. By night the sheet becomes a night chart on deep slate, with every ink lifted to stay legible and every role preserved. The app has no theme toggle of its own; it reads the parent wiki's `saved-theme` attribute (and its `themechange` event), falling back to `prefers-color-scheme` only when the parent cannot be read.

The world rejects the notes-app sidebar and the SaaS checklist: no cards, no pills, no drop shadows, no checkbox ticks for quests.

**Key Characteristics:**
- Two themes, one role map: survey sheet (light) and night chart (dark).
- One ink, one meaning: ink for text, terrain for meta and contours, hydro for the party and selection, overprint for the single primary action.
- Hairline rules and a title-block label grid carry all structure.
- Condensed spaced capitals (Barlow Semi Condensed) for lettering; Source Sans 3 for everything read.
- Contours only in margins and empty ground; never behind reading text.
- The signature motion: ticking a quest inks its survey mark from the base up.

## Colors

A restrained map palette: a near-neutral grey-green ground with four inks, each bound to one job.

### Primary
- **Overprint Magenta** (`overprint`; night `night-overprint`): the one primary action per view (New entry, Log in, Add quest). Named for the magenta overprint printed over a finished survey. Text on it is `on-overprint`.

### Secondary
- **Hydro Blue** (`hydro`; night `night-hydro`): the party. Player names (italic, 600), assignee selects, filter selects, the current legend row's ref, completed survey marks, focus outlines, the hover/focus underline of ruled fields. `hydro-tint` is the selected-row wash and the text selection colour.

### Tertiary
- **Contour Brown** (`terrain`; night `night-terrain`): terrain and meta. Field labels, E- and Q-refs, list markers, the Uncharted lettering, prose h3/h4, blockquote rule, strike-through colour on completed quests. `contour` is the same hue at 30% (20% by night) and is used only for contour lines.

### Neutral
- **Survey Ground** (`ground`, `ground-2`, `ground-3`; night variants): the sheet, hover wash and editor/code fill, and a third step reserved for deeper fills.
- **Surveyor's Ink** (`ink`, `ink-2`, `ink-3`): primary text; secondary text and meta; placeholders, statuses and quiet controls.
- **Rules** (`rule`, `rule-strong`): hairline dividers between rows; `rule-strong` (equal to ink) for the neatline, section heads and field underlines.
- **Danger** (`danger`): delete actions and login errors only, as text colour; never as a fill.

### Named Rules
**The One Ink, One Meaning Rule.** Every colour has a single job. Hydro means the party or the current selection; terrain means meta or terrain; overprint means the primary action. Never use one ink for another's job.

**The Single Overprint Rule.** At most one overprint button is visible per view. Committing (Save) uses ink, not overprint.

**The Night Chart Rule.** Dark mode is a parallel palette, not an inversion. Every light token has a night twin with the same role; set both when adding a role.

## Typography

**Display Font:** Barlow Semi Condensed 500/600 (with Arial Narrow, sans-serif)
**Body Font:** Source Sans 3 400/600, italic 400 (with Source Sans Pro, system-ui, sans-serif)

Both load from Google Fonts in a single stylesheet request.

**Character:** Condensed, engineered capitals that read as map lettering, over a plain humanist sans for everything a player actually reads and writes.

### Hierarchy
The scale is `--t-xs .75rem`, `--t-sm .875rem`, body 1rem, then roughly 1.25 steps: `--t-md 1.25rem`, `--t-lg 1.5625rem`, `--t-xl 1.953rem`, `--t-2xl 2.441rem`.
- **Display** (600, clamp(t-xl, 5vw, t-2xl), 1.05, 0.04em, uppercase): the sheet title in the title block only.
- **Headline** (600, t-xl, 1.1): the open entry's title and the editor's title input; drops to t-lg on phones.
- **Title** (600, t-lg / t-md, 1.2, 0.02em): markdown h1/h2 inside entries.
- **Body** (400, 1rem, 1.55; prose 1.65, max 68ch): entry text, row titles (600), inputs.
- **Body small** (400, t-sm): meta lines, statuses, player names, selects.
- **Label** (600, t-xs, 0.14em, uppercase, terrain): title-block field labels and list heads. Refs use the same face at 0.08em without uppercase transform.
- **Button** (600, t-sm, 0.1em, uppercase): all buttons.
- **Lettering** (600, t-xl, 0.5em tracking, uppercase, terrain): the Uncharted empty-state word only.

### Named Rules
**The Lettering Rule.** Barlow Semi Condensed is for things printed on the map (titles, labels, refs, buttons). Anything a player writes or reads at length is Source Sans 3.

**The Tabular Refs Rule.** Refs, dates and the sheet subline use tabular numerals.

## Layout

A single sheet with fluid side margins (`clamp(1rem, 4vw, 2rem)`), capped by the wiki iframe it lives in; the iframe grows to the body height, so the app never scrolls internally. Spacing follows one 4px-based rhythm (`s-1` to `s-7`); section gaps are `s-6`, row padding `s-2` to `s-4`, the gap before the completed ledger `s-7`.

- **Title block** spans full width: sheet name and subline left; sheet number, scale bar and surveyor (player, Log out, New entry) right-aligned at 640px+.
- **Journal split** at 640px+: legend index `minmax(12rem, 34%)` beside the open field note, top-aligned, `s-6` gap. Below 640px the legend and the note are alternate views: the note is hidden until one is opened, then comes first, with a "Back to legend" text button.
- **Quest ledger** row grid: survey mark (2.75rem), text, assignee, delete. On phones the assignee drops under the text and delete stays on the first line.
- **Phone title block** (below 640px): contours and the sheet-number/scale row are removed; the surveyor row fills the width, the player name ellipsizes, and New entry tightens to `s-4` padding.
- Touch targets are at least 2.75rem (44px) for buttons, marks and delete; selects are 2.25rem.

## Elevation & Depth

Flat. There are no shadows anywhere in the system. Depth is conveyed the way a printed sheet conveys it: rule weight (hairline `rule`, strong `rule-strong`, a 3px double neatline at the top of the title block), tonal washes (`ground-2` on hover, `hydro-tint` on selection), and contour lines drawn behind empty ground. The only box-shadow in the build is a 1px hydro underline doubling a focused field's rule; it is a rule, not an elevation.

### Named Rules
**The Printed Sheet Rule.** Nothing floats. Separate with rules and washes, never with shadows or cards.

## Shapes

Square and ruled. Buttons, selects, marks and the editor well take a barely-there 3px corner; inline code takes 2px. Rows and fields have no radius at all; fields are a single bottom rule, rows are separated by bottom hairlines. The recurring silhouettes are cartographic: the survey-mark triangle, the alternating scale bar, and irregular concentric contour rings (generated in-page, 0.7px strokes with every fourth ring at 1.3px).

## Components

### Buttons
Uppercase map lettering on a flat block; overprint creates, ink commits, text buttons do the rest.
- **Shape:** 3px corners, min-height 2.75rem, `s-5` horizontal padding, 1px transparent border.
- **Overprint:** magenta fill, the single primary action. Hover mixes 14% ink into it.
- **Ink:** ink fill with ground text, for committing (Save). Hover mixes 18% hydro into it.
- **Line:** transparent with a `rule` border (Edit); hover darkens the border to `ink-2`.
- **Text:** no border, `ink-2`, hover to `ink` (Log out, Close, Back to legend). Danger text variant underlines on hover.
- **States:** colour transitions 0.18s on `--ease`; press scales to 0.98; disabled at 45% opacity; focus is the global 2px hydro outline, 2px offset.

### Inputs / Fields
- **Style:** ruled, not boxed: transparent, no radius, single 1px `rule-strong` bottom rule, min-height 2.75rem. Placeholders `ink-3`; caret overprint.
- **Hover / Focus:** the rule turns hydro; focus adds a 1px hydro underline beneath it.
- **Editor well:** the entry body textarea is the one boxed field: `ground-2` fill, 1px `rule` border, 3px corners, min 16rem tall, 1.65 line height. The title input is a headline-sized ruled field.

### Selects
- **Plain select** (legend and ledger filters, quest assignee): hydro text at t-sm, no border, 3px corners, a masked SVG chevron in currentColor; hover shows `ground-2` (filters) or a `rule` border (assignee).
- **Form select** (login roster, new-quest assignee): a ruled field with the same chevron.

### Entry legend rows
The journal index. Each row is a full-width button: a 3.25rem ref column (E-01, E-02, stable by recording order, terrain, spanning two lines) beside the title (600) and a t-sm meta line. Bottom hairline, hover `ground-2`, current row `hydro-tint` with its ref in hydro.

### Title-block label grid
The head of an open entry: a row of cells (Ref, Surveyor, Recorded or Status), each a label over a t-sm value, separated by vertical hairlines, with a strong rule above and a hairline below. The surveyor value is the hydro italic player name.

### Quest ledger rows
Dense ruled rows (min 3.5rem): survey mark, quest text with a t-sm "Q-03 · Plotted by …" line, assignee select, delete (SVG cross, `ink-3`, danger on hover). Completed quests move under a separate ledger head, text in `ink-3` with a terrain strike-through.

### Survey mark (signature)
An open SVG triangle (1.6 stroke, currentColor) in a 2.75rem hit area. Ticking a quest sets `aria-pressed`, turns it hydro, and inks the fill upward from the base (scaleY 0 to 1, 0.26s, `--ease` cubic-bezier(.22, 1, .36, 1)), then a ground-coloured trig point fades in after 0.14s. The mark inks first; the list re-sorts when the data confirms. Reduced motion removes the transitions.

### Uncharted empty state
Empty ground is drawn, never blank: a hairline-bounded panel (min 14rem) with centred contour rings behind the spaced lettering "Uncharted" in terrain and one line of `ink-2` guidance. Loading uses ruled skeleton rows in `ground-2`.

### Title block (navigation)
The page header is a sheet cartouche: 3px double neatline on top, strong rule below, contour rings masked into the right margin, sheet name, sheet number with a scale bar, and the surveyor row. Navigation between Journal and Quests belongs to the wiki; the app switches view by URL hash.

## Do's and Don'ts

### Do:
- **Do** give every colour a single role and set its night twin when adding a role.
- **Do** keep one overprint action per view; commit with ink.
- **Do** separate with hairline rules (`rule`) and strong rules (`rule-strong`), not boxes.
- **Do** set labels, refs and buttons in Barlow Semi Condensed 600 with tracking; set read and written text in Source Sans 3.
- **Do** give every new list item a stable, zero-padded ref in its own prefix (E-, Q-), numbered by creation order.
- **Do** fill empty ground with contours and the Uncharted lettering.
- **Do** keep touch targets at 2.75rem and follow the parent wiki's theme.

### Don't:
- **Don't** add shadows, cards or floating panels; the sheet is flat.
- **Don't** draw contours behind reading text or on the phone title block.
- **Don't** use overprint magenta for anything but the primary action, or danger as a fill.
- **Don't** replace the survey mark with a checkbox or a glyph; marks and crosses are inline SVG.
- **Don't** use spaced-caps labels as decorative eyebrows above headings; labels name a field or a list.
