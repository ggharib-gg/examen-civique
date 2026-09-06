---
name: Examen Civique
description: A mid-century French poster put to work as a civics-exam trainer — flat ink fields, huge Archivo lettering, paper that flips for dark.
colors:
  nuit: "#14335E"
  nuit-deep: "#0B1F3B"
  nuit-clair: "#5C8FD6"
  vermillon: "#E1432D"
  vermillon-deep: "#B82F1C"
  vermillon-clair: "#FF7F68"
  or: "#F2B417"
  or-deep: "#8A6207"
  vert: "#1F6B4A"
  vert-clair: "#5FC393"
  creme: "#F7F1E4"
  ground: "#F3EBDA"
  ground-2: "#E7DCC4"
  panel: "#FFFAEF"
  ink: "#15181D"
  ink-soft: "#6B6555"
  line: "#D9CDB3"
  ground-dark: "#060D16"
  ground-2-dark: "#0C1726"
  panel-dark: "#101F33"
  ink-dark: "#F2EADB"
  ink-soft-dark: "#9FB0C4"
  line-dark: "#223854"
typography:
  display:
    fontFamily: "Archivo, system-ui, -apple-system, sans-serif"
    fontSize: "36px"
    fontWeight: 900
    lineHeight: 0.94
    letterSpacing: "-0.012em"
    fontVariation: "'wdth' 122"
  headline:
    fontFamily: "Archivo, system-ui, -apple-system, sans-serif"
    fontSize: "23px"
    fontWeight: 700
    lineHeight: 1.28
  title:
    fontFamily: "Archivo, system-ui, -apple-system, sans-serif"
    fontSize: "16px"
    fontWeight: 800
    lineHeight: 1.3
  body:
    fontFamily: "Archivo, system-ui, -apple-system, sans-serif"
    fontSize: "14px"
    fontWeight: 400
    lineHeight: 1.6
  body-small:
    fontFamily: "Archivo, system-ui, -apple-system, sans-serif"
    fontSize: "13px"
    fontWeight: 400
    lineHeight: 1.55
  label:
    fontFamily: "Archivo, system-ui, -apple-system, sans-serif"
    fontSize: "11.5px"
    fontWeight: 800
    lineHeight: 1.35
    letterSpacing: "0.09em"
    fontVariation: "'wdth' 110"
  figures:
    fontFamily: "Archivo, system-ui, -apple-system, sans-serif"
    fontSize: "15px"
    fontWeight: 700
    fontFeature: "tabular-nums"
rounded:
  bloc: "2px"
  rond: "50%"
spacing:
  xs: "4px"
  sm: "8px"
  md: "12px"
  lg: "16px"
  xl: "20px"
  section: "36px"
  bloc-y: "32px"
components:
  button-primary:
    backgroundColor: "{colors.nuit}"
    textColor: "{colors.creme}"
    rounded: "{rounded.bloc}"
    padding: "15px 22px"
    typography: "{typography.title}"
  button-primary-hover:
    backgroundColor: "{colors.nuit-deep}"
    textColor: "{colors.creme}"
  button-secondary:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    rounded: "{rounded.bloc}"
    padding: "15px 22px"
  button-secondary-hover:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.ground}"
  button-danger:
    backgroundColor: "{colors.vermillon-deep}"
    textColor: "{colors.creme}"
    rounded: "{rounded.bloc}"
    padding: "15px 22px"
  button-on-ink:
    backgroundColor: "transparent"
    textColor: "{colors.creme}"
    rounded: "{rounded.bloc}"
    padding: "15px 22px"
  option:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    rounded: "0"
    padding: "16px 14px"
  option-selected:
    backgroundColor: "{colors.nuit}"
    textColor: "{colors.creme}"
  option-correct:
    backgroundColor: "{colors.vert}"
    textColor: "{colors.creme}"
  option-incorrect:
    backgroundColor: "{colors.vermillon-deep}"
    textColor: "{colors.creme}"
  chip:
    backgroundColor: "transparent"
    textColor: "{colors.ink-soft}"
    rounded: "{rounded.bloc}"
    padding: "9px 14px"
  chip-active:
    backgroundColor: "{colors.ink}"
    textColor: "{colors.ground}"
  theme-tag:
    backgroundColor: "{colors.nuit}"
    textColor: "{colors.creme}"
    rounded: "{rounded.bloc}"
    padding: "5px 10px"
  input:
    backgroundColor: "{colors.panel}"
    textColor: "{colors.ink}"
    rounded: "{rounded.bloc}"
    padding: "10px 12px"
  card-panel:
    backgroundColor: "{colors.panel}"
    textColor: "{colors.ink}"
    rounded: "{rounded.bloc}"
    padding: "16px"
  qmap-cell:
    backgroundColor: "{colors.panel}"
    textColor: "{colors.ink-soft}"
    rounded: "{rounded.bloc}"
    size: "34px"
  qmap-cell-answered:
    backgroundColor: "{colors.nuit}"
    textColor: "{colors.creme}"
  verdict-pass:
    backgroundColor: "{colors.vert}"
    textColor: "{colors.creme}"
  verdict-fail:
    backgroundColor: "{colors.vermillon-deep}"
    textColor: "{colors.creme}"
---

# Design System: Examen Civique

## Overview

**Creative North Star: "L'Affiche"**

The app is a mid-century French poster (Cassandre, Savignac) that happens to run an exam. Nothing is decorated: colour arrives as a flat saturated field that runs edge to edge of the viewport, type arrives at poster scale in one very wide, very heavy face, and structure is made by geometry — a full-bleed ink band, a 2px rule, a 760px column of text sitting on cream paper. There is no illustration, no gradient, no photographic texture, no drop shadow anywhere in the build.

The register is civic rather than playful: navy masthead with a cockade, tabular figures, uppercase labels that read like the caption under a printed plate ("QUESTIONS", "SEUIL", "ÉCHELON"). Density is generous on the ink fields and tight in the working screens — the exam is a sticky bar, a headline plate, and four answer lines separated by rules, nothing else. Progress rewards are printed, not popped: a badge is a hand-drawn ink seal that lands on the page, a result is a verdict that prints in from the top edge.

Two structural facts define the world more than any single token. First, the inks never change: the six poster colours are constants across light and dark, and only the paper layer (ground, panel, body ink, rules) flips. Second, colour carries meaning — each of the four exam themes owns one ink and wears it on every surface it appears on, so a vermilion plate always means *histoire* and never means "accent". The discarded government-form look (ruled margins, serif text, stamped-paper chrome) is a live anti-reference: it is not a base to extend.

**Key Characteristics:**
- Flat saturated ink fields that bleed the full viewport width while text stays in a 760px measure
- One superfamily, Archivo variable, driven by width (122%) and weight (900) rather than by a second face
- Square-cornered everything at 2px; circles reserved for letter roundels, badge seals and the cockade
- Constant inks, flipping paper: dark mode changes the sheet, not the palette
- Zero shadows; depth is field-versus-paper and 2px inset rules
- Exactly two authored motion moments, both disabled under reduced motion

## Colors

Six poster inks printed flat on a warm cream sheet, with one accent (or) reserved for attention and one neutral ramp that is the only thing dark mode touches.

### Primary
- **Bleu Nuit** (`{colors.nuit}`): the institutional voice — masthead band, primary buttons, selected answers, answered cells in the question map, the échelon panel, and the *institutions* theme ink. Its deep variant is the hover state and the modal scrim; its light variant (`{colors.nuit-clair}`) exists only so buttons and links stay legible on the dark sheet.
- **Crème** (`{colors.creme}`): the type colour on every ink field. Cream on ink, never white on ink — white would read as a UI card, cream reads as printed paper.

### Secondary
- **Vermillon** (`{colors.vermillon}`): the poster's shout — the hero field on the start screen (in its deep variant), the exam progress fill, the timer warning, the *histoire* theme ink, and every failure state (wrong answer, "AJOURNÉ" verdict, destructive action). The deep variant is the one used on cream; the clair variant is its dark-sheet counterpart in text.
- **Or** (`{colors.or}`): attention only, never surface chrome — the focus ring, the flag marker, the selected radio dot, the current question in the map, the *europe* theme ink (with dark type, since gold cannot carry cream), and the numbers that matter in the carnet. `{colors.or-deep}` is the on-cream text version.

### Tertiary
- **Vert** (`{colors.vert}`): correctness and nothing else — the correct answer, the "ADMIS" verdict, the *citoyenneté* theme ink. `{colors.vert-clair}` is its dark-sheet text counterpart.

### Neutral
- **Papier** (`{colors.ground}` light / `{colors.ground-dark}` dark): the sheet the whole app is printed on.
- **Papier creusé** (`{colors.ground-2}` / `{colors.ground-2-dark}`): the empty half of a progress track and the answer hover tint.
- **Panneau** (`{colors.panel}` / `{colors.panel-dark}`): the slightly brighter surface of raised blocks — mode cards, corrigé entries, map cells, inputs, the modal.
- **Encre** (`{colors.ink}` / `{colors.ink-dark}`): body text and the timer plate.
- **Encre douce** (`{colors.ink-soft}` / `{colors.ink-soft-dark}`): captions, labels, secondary figures, disabled map cells.
- **Filet** (`{colors.line}` / `{colors.line-dark}`): every hairline and 2px inset rule.

### Named Rules

**The Constant Ink Rule.** The six poster inks are the same hex in both themes. Only `--ground`, `--ground-2`, `--panel`, `--ink`, `--ink-soft`, `--line` and `--seal-ink` flip under `[data-theme="dark"]`. A new colour is either an ink (constant) or paper (flipping); nothing is allowed to be both.

**The One Ink Per Theme Rule.** Each exam theme owns exactly one ink — histoire/vermillon-deep, institutions/nuit, citoyenneté/vert, europe/or-on-dark-type — and wears it identically on question plates, flashcard fronts, result bars, mastery bars, filter chips and corrigé tags. Theme-coloured elements set `data-t="<theme>"` and let CSS pick the ink; they never hardcode a hex.

**The Two-Signal Rule.** Colour is never the sole carrier of meaning. The corrigé pairs red/green with a drawn ✓/✗; the attendance register pairs a filled ink cell with a gold ring for today, a dashed border plus a "T" for a tolerance day, and a spelled-out legend. Any new state that means pass/fail/now must ship a second, non-chromatic signal.

**The Contrast Floor Rule.** Every text-on-background pair in the build clears 4.5:1 (3:1 at large display sizes) in both themes. That is why gold fields carry near-black type, why `nuit-clair` / `vermillon-clair` / `vert-clair` exist at all, and why they are text-only counterparts rather than new fields.

## Typography

**Display Font:** Archivo (variable, self-hosted `archivo.woff2`, wght 400–900, wdth 75–125), fallback `system-ui, -apple-system, sans-serif`
**Body Font:** Archivo, same file, normal width
**Label Font:** Archivo at 110% width, uppercase

**Character:** One grotesque doing all the work, separated by width instead of by family. At 122% width and weight 900 it is a printing-press headline; at normal width and 400 it is quiet, factual French administrative prose. The pairing has no contrast of style, only of pressure.

### Hierarchy
- **Affiche / Display** (900, 122% width, uppercase, -0.012em, 0.94 line-height): every poster moment — the hero headline (36px → 68px), the verdict word (56px → 84px), section titles in the carnet (21–22px), and big figures (24–32px). Always uppercase, always tight.
- **Headline** (700, 23px → 29px, 1.28): the question itself on the ink plate. Sentence case, not display — the question is read, not shouted.
- **Title** (800, 16px, ~1.3): mode-card names, corrigé question lines, button labels (15px, 108% width, +0.02em).
- **Body** (400, 14px, ~1.6): explanatory paragraphs. 13.5px for secondary prose, 13px for footnotes and disclaimers. The 760px column holds these to roughly 70–80 characters.
- **Libellé / Label** (800, 11.5px, 110% width, uppercase, +0.09em): the caption under a printed plate — section headings, definition-list terms, statuses. Never longer than a few words.
- **Figures** (tabular numerals): timer, score, streak, points, dates, question counters. Anything that changes in place is tabular so it does not jitter.

### Named Rules

**The One Superfamily Rule.** Archivo is the only face in the system. Hierarchy is made with width and weight axes, never by introducing a second family — no serif for "official", no mono except the Firebase config textarea where the value is literally code.

**The Latin-Only Rule.** One font file ships and it declares no `unicode-range`, so any glyph it lacks falls back silently to `system-ui` and breaks the voice mid-word. Copy stays French/Latin; no symbol glyphs, no emoji, no icon font.

**The Shout Once Rule.** Display type appears once per viewport-height of scroll — a plate, a verdict, a section title. Two display blocks stacked read as a broken poster, not a loud one.

## Layout

A single centered column of `max-width:760px` with 20px side padding (32px from the `sm` breakpoint), sitting on the paper ground; the header, main and footer all share that measure so the column edge is continuous down the page.

Full-bleed ink fields are the counter-move: the `bleed` utility pulls an element to `100vw` (`margin-inline: calc(50% - 50vw)`) and re-pads it to `max(20px, calc(50vw - 380px))`, so the field spans the window while its text lands back on the 760px measure. This depends on `body { overflow-x: clip }` — `hidden` would make the body a scroll container and unstick the exam bar, so the clip value is load-bearing, not cosmetic.

Rhythm runs on a 4px base: 8–10px between sibling controls, 12–16px inside blocks, 20–24px between a heading and its content, 36–40px between sections, and 32–48px of vertical padding inside ink fields (larger at `sm`). Responsive behaviour is mobile-first and modest: one breakpoint does most of the work (`sm`, 640px) by widening padding, going from one column to two or four in the fact list and card grids, and stepping display sizes up; `lg` only raises the hero headline; the badge grid and register strip add a third step at `md` / `sm` respectively. The exam bar is `position: sticky; top: 0` on the ground colour, and `#question-card` carries `scroll-margin-top: 94px` — a fixed value, because the sticky bar reports `top: 0` once stuck and cannot be measured.

## Elevation & Depth

There are no shadows in this system. `box-shadow` appears only as `inset 0 0 0 2px` — a drawn rule, not a light source. Depth is entirely tonal and graphic: an ink field is "above" the paper because it is a saturated plane running past both edges; a panel is "above" the ground because it is a brighter cream (or a lighter navy in dark) inside a 2px inset rule; a divider is a 2px `--line` border under a row. The modal is the only overlay, and it separates by scrim (`nuit-deep` at 70% with a 2px backdrop blur), not by lift.

### Named Rules

**The Printed-Not-Lifted Rule.** Nothing floats. If an element needs to separate from its background, give it an ink field, a paper step, or a 2px inset rule — never a drop shadow, never a glow, never a border-radius large enough to imply a physical card.

## Shapes

Corners are square at 2px (`--radius-bloc`) on every rectangle in the system: buttons, panels, chips, map cells, inputs, tags, modal. Answer rows are 0 — they are divisions ruled onto the paper, not boxes. Circles are rationed to three roles and nothing else: the 28px option letter roundel (inset 2px ring, filled gold when selected), the 100-unit badge seal, and the four-ring cockade in the masthead. Borders are one of two weights: a hairline `--line` for text separators, or a 2px inset ring for anything interactive; 3px appears only as a state (flagged map cell, the gold focus outline, the "today" ring).

Icons are inline SVG on a 20 or 24 viewBox, `fill="none"`, `stroke="currentColor"`, round caps and joins, stroke-width 2.2–2.6 — drawn at the same pressure as the 2px rules, so they read as part of the same printing. Badge seals are the one denser drawing: two concentric rings, a 3.1-weight motif, curved rim text and three dots at the foot, tilted a few degrees so it looks stamped by hand.

## Components

### Buttons
- **Shape:** square-cornered (2px), inline-flex with a 8px gap for an optional leading/trailing icon.
- **Primary:** navy field, cream type, 15px/800 at 108% width, 15px × 22px padding. In dark it becomes `nuit-clair` with near-black type so it stays a field rather than a hole.
- **Secondary:** transparent with a 2px inset ink ring; on hover it inverts to a solid ink field with ground-coloured type.
- **Danger:** deep vermilion field (`vermillon` in dark), used for destructive confirmation only.
- **On-ink:** transparent with a 2px cream ring, for buttons sitting on an ink field; inverts to cream-on-navy on hover.
- **States:** hover treatments are gated behind `(hover:hover) and (pointer:fine)` so touch never sticks a hover; `:active` nudges 1px down; disabled drops to 45% opacity. Focus is the global 3px gold outline at 2px offset.
- **Link (`lien`):** a bare button styled as 700-weight underlined text, 2px underline at 3px offset. Used for "mark for review" and destructive text actions.

### Chips
- **Style:** transparent with a 2px inset `--line` ring, 12.5px/800 at 106% width, soft-ink type, 9px × 14px.
- **State:** active fills with ink and takes ground-coloured type — except theme filters, which take their theme's ink via `data-t`.

### Cards / Containers
- **Panel block** (corrigé entry, session gain, modal): panel background, 2px inset `--line` ring, 2px corners, 16–20px padding.
- **Mode card:** the same panel block made selectable — 22px circular radio with a 2px inset ring, and on selection the whole card becomes a navy field with a gold dot in the radio.
- **Ink field:** `bleed` + a flat ink background + 32–48px vertical padding, inner content re-centered at 760px. This is the system's real container; panels are the exception.

### Inputs / Fields
- **Style:** panel background, 1px `--line` border, 2px corners, 12px × 10px padding, 15px type; the duel code input is uppercase with 0.2em tracking and tabular figures.
- **Focus:** border shifts to navy and a 2px gold outline appears at 1px offset.
- **Error:** a deep-vermilion message line below the field (vermilion-clair in dark); the field itself is not recoloured.

### Navigation
- **Masthead:** a navy band (deep navy in dark) holding the cockade, the wordmark in display type (19px → 22px), and three compact controls on `creme/12` fills that brighten to `creme/22` on hover; the reference/disclaimer line sits beneath at 12.5px on `creme/70`.
- **Screen switching** is a full swap — five sections toggled by a `hidden` class, no tabs, no transitions between screens.
- **Question map:** a wrapping grid of 34px square cells; answered fills navy, flagged takes a 3px gold inset ring, current takes the 3px gold outline. Ring and fill are independent so a cell can be both.

### Answer list (signature)
Four rows ruled onto the paper: 2px `--line` separators, a 28px circled letter, the option text at 16px/1.45, and a trailing 22px mark slot that is transparent until the corrigé reveals it. Selection paints the whole row navy with a gold letter roundel; grading paints it green or deep vermilion and reveals the drawn ✓/✗. No radio inputs, no boxes, no rounded corners.

### Verdict plate (signature)
A full-bleed field carrying the result word in display at 56px → 84px, the score in tabular figures, and a label caption. Green when passed, deep vermilion when failed, navy before it resolves. It is the one element that animates in.

### Badge seal (signature)
An inline SVG stamp on a 100 viewBox: an outer ring (dashed when unearned), an inner hairline ring, a stroked motif, curved rim text and three foot dots, inked in `--seal-ink` (navy on paper, light blue on dark) at 42% opacity when unearned, tilted a few degrees per index. A newly earned seal plays the `stamp-land` animation.

### Motion
The budget is two authored moments plus one guarded signal, all neutralised under `prefers-reduced-motion` (animations cut to 1ms, the timer pulse to none, the flip transition to 1ms):
- **`impression`** (0.55s, `--ease-affiche`): the verdict prints in from the top via `clip-path: inset(0 0 100% 0)` → `inset(0)`.
- **`stamp-land`** (0.5s): a newly earned seal scales from 1.35 with a 3px blur down to rest, keeping its tilt.
- **`#timer.warn`**: a 1s opacity pulse on a vermilion timer plate, the only looping animation in the file.
State transitions elsewhere are 120–180ms colour/box-shadow changes on `--ease-affiche` (`cubic-bezier(.2,.9,.25,1)`); the flashcard flip is 0.5s on the same curve.

## Do's and Don'ts

### Do:
- **Do** put every new full-width colour plane through the `bleed` utility and re-center its content at 760px, and keep `body { overflow-x: clip }` exactly as it is.
- **Do** give theme-coloured elements `data-t="histoire|institutions|citoyennete|europe"` and let the shared `.theme-tag / .ink-fill / .chip.active` rule pick the ink.
- **Do** write rules that must win in dark mode as real CSS (`[data-theme="dark"] .x { … }`). The `dark:` variant is built on `:where()` and carries zero specificity, so a `dark:` utility does not outrank a plain one — source order decides, and two bugs already came from assuming otherwise.
- **Do** ship a second, non-chromatic signal (drawn icon, ring, letter, legend) with every colour-coded state.
- **Do** use tabular figures (`figures`) for any number that updates in place.
- **Do** state pressure with the Archivo width and weight axes — 122%/900 uppercase for display, 110%/800 for labels.
- **Do** draw icons inline as SVG at stroke-width 2.2–2.6 with round caps, matching the 2px rule weight.

### Don't:
- **Don't** add a `box-shadow` that casts. The only legal shadow is `inset 0 0 0 Npx` used as a drawn rule.
- **Don't** introduce a second font family, an icon font, or emoji; Archivo carries display, body and label.
- **Don't** recolour an ink for dark mode. Flip paper tokens only; if something is illegible on the dark sheet, reach for the existing `-clair` text counterpart.
- **Don't** round a corner past 2px, and don't add circles outside the three sanctioned roles (option roundel, badge seal, cockade).
- **Don't** measure the sticky exam bar with `getBoundingClientRect()` to compute scroll offset — it reports `top: 0` once stuck; `scroll-margin-top` owns that job.
- **Don't** add a third animated moment, a page-transition, or a looping animation beyond the timer warning; and never ship motion that ignores `prefers-reduced-motion`.
- **Don't** reintroduce the discarded administrative-document world — ruled paper margins, serif body text, stamped-form chrome. It is an anti-reference, not a fallback.
