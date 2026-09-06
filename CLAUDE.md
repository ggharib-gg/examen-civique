# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A single-file, static French "examen civique" (naturalization civics test) trainer. The entire app — HTML, CSS, and JS — lives in `index.html`; there is no build step, no bundler, no framework, and no package.json. `404.html` is a plain not-found page. Hosted on Vercel as a static site (no `vercel.json` — zero-config static hosting); there is no server-side code.

Two CDN dependencies load at runtime, both optional to the core exam flow: the **Tailwind v4 browser build** (compiles utility classes in the page; used only by the carnet UI) and the **Firebase JS SDK**, dynamically `import()`ed only when a duel code is configured, for the two-device score comparison.

## Running it

Just serve the directory and open `index.html` — no install/build step exists:

```
python -m http.server 8000   # then open http://localhost:8000/index.html
```

There is no test suite, linter, or build command. "Testing" a change means loading the page in a browser (or headless Chromium via Playwright if the claude-in-chrome extension isn't connected — check for a running `chrome.exe` process and launch it first) and clicking through the actual flow: start an exam, answer/navigate/flag questions, finish and check the results screen; separately check the flashcards screen. For any mobile-facing change, test at a narrow viewport (~390px) specifically.

## Architecture

Everything hangs off one in-memory question bank and one mutable `state` object, both defined in the `<script>` at the bottom of `index.html`.

- **`const BANK`** — the full question bank, one object per question: `{theme, type, q, o, a, e}` where `theme` is one of the four official keys in `THEME_LABELS` (`histoire`, `institutions`, `citoyennete`, `europe`), `type` is `'connaissance'` (knowledge) or `'situation'` (mise en situation), `o` is the 4 options in canonical order, `a` is the correct option's index into `o`, and `e` is the explanation shown on the flashcard back / in the exam review. When adding questions, match this shape and the existing tone exactly, and insert them under the right `// ---- THEME ----` comment block — `BANK` is grouped by theme, not alphabetical or chronological.
- **`BANK_ID`** — `BANK` with a stable numeric `id` per question (its index), used by the anti-repeat draw logic below. Never reorder or delete entries from the middle of `BANK`; that silently reassigns every later question's `id` in `usedIds`'s bookkeeping across a session (harmless per-session, but avoid it anyway since it makes diffs noisy).
- **`drawQuestions(n)`** — draws `n` questions for an exam run: tracks `usedIds` (module-level `Set`) so a fresh browser session doesn't repeat a question until the whole bank has been shown once, then enforces a ~30% quota of `type:'situation'` questions (capped by how many exist), fills the rest with `'connaissance'`, and shuffles each question's own options (remapping the correct-answer index) independently of the original `o` order. This is the one function both the exam draw and the ~30% situation quota depend on — a new `situation` question is automatically eligible the moment it's added to `BANK` with that `type`.
- **`state`** — the single source of truth for an in-progress exam (mode, question count/duration, the drawn `questions`, per-question `answers`/`flagged`, `current` index, timer). `renderQuestion()` re-renders the current question from `state` and is called after every mutation (answer selected, flag toggled, navigation) — it does not itself scroll or animate, so don't add scroll/animation side effects there; hook them into the call sites instead (see `stepQuestion`, `scrollExamToTop`, and the swipe handler for the existing pattern of keeping render vs. navigation-side-effects separate).
- **Screens** — five `<section>`s (`screen-start`, `screen-exam`, `screen-results`, `screen-flashcards`, `screen-progress`) toggled via the `screens` map / `showScreen(name)`, which just shows one and hides the rest. Flashcards render straight from `BANK` filtered by theme (`renderFlashcards`), independent of exam state.
- **`progress`** — the carnet's own state, entirely separate from `state`: streak, points, badges, per-theme totals, persisted to `localStorage` under `examen-civique-progress`. `finishExam` calls `recordSession()` (the single write path — it updates the streak with its one-grace-day-per-ISO-week rule, awards points, evaluates `BADGES`, saves, and pushes to the duel), and `renderCarnet()` reads it. Badge criteria are pure functions of `progress`, so they re-evaluate correctly on any session; add a badge by appending to `BADGES` with a pictogram in `SEAL_ART`. The exam itself never reads `progress` — nothing about scoring or drawing depends on it.
- **Relevé comparatif (duel)** — optional Firebase Realtime Database sync at `duels/<code>/<playerId>`. The config is pasted by the user in the carnet UI and kept in `localStorage`; with none, `duelConfigured()` is false and the carnet renders setup instructions instead. Every other part of the carnet works offline and without it.
- **Exam navigation** — centralized in `stepQuestion(delta)` (bounds-checked, updates `state.current`, re-renders, scrolls to top). Précédente/Suivante buttons, the question-map jump buttons, and the touch-swipe handler on `#question-card` all funnel through it (or replicate its bounds logic for the map-jump case) — keep it that way rather than duplicating the increment/bounds logic at a new call site.
- **Scrolling to a fresh question** — `#question-card` has `scroll-margin-top` sized to the sticky `.exam-bar`, and navigation calls `card.scrollIntoView(...)`. Don't try to compute the scroll offset from `.exam-bar`'s own `getBoundingClientRect()` — it's `position:sticky`, so once stuck it always reports `top:0`, which was a dead end already hit once in this file's history.
- **Swipe navigation** — a self-contained IIFE near the bottom of the script, attached only to `#question-card` (exam screen). It locks touch gestures to an axis after ~10px of movement so vertical scrolling and the flashcards' tap-to-flip are never intercepted; only a locked horizontal drag calls `preventDefault`.
- **Theming** — CSS custom properties on `:root` plus a `dark` class/attribute toggled via `localStorage.getItem('examen-civique-theme')`; most visual elements list `background-color/border-color/color/box-shadow` in their `transition` for the toggle to animate smoothly. When adding a new element that should theme-aware, give it CSS vars, not hardcoded colors.

## Conventions specific to this file

- All UI copy, comments, and explanations are in French; keep new content consistent with that (including the terse, factual explanation style — one sentence citing the relevant law/institution, no filler).
- This is a single HTML file edited with targeted `Edit` calls, not a multi-file diff — when adding many similar entries (e.g. a batch of `BANK` questions), insert them as one contiguous block at the right spot rather than scattering them.
