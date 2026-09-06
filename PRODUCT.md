# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Two named users: Georges and his wife, preparing together for the French naturalisation / carte de résident / titre pluriannuel civics exam ("examen civique"). This is a personal project built for their own use, not a public product with unknown visitors.

## Product Purpose

A private study tool that simulates the official French civics exam so the two of them can drill until they reliably clear the real pass threshold. Success means both of them walk into the actual exam (at a CCI Paris or France Éducation International center) confident they'll pass.

## Positioning

Fidelity to the real exam's official conditions (décret n° 2025-648 du 15 juillet 2025, arrêté du 10 octobre 2025 — 40 questions, 45 minutes, 80% pass threshold, ~30% mise-en-situation quota) rather than a generic quiz. On top of that, the explicit next differentiator the users asked for: gamifying the experience so studying stays engaging for two people over repeated sessions instead of fizzling out.

## Operating Context

- Studied solo and together, likely on phone and laptop, in the run-up to a scheduled naturalisation interview/exam appointment.
- The real exam is proctored at an approved center (CCI Paris, France Éducation International); this tool is explicitly independent and not affiliated with the administration (already stated in the page copy) — that disclaimer is a fact to preserve, not decorative text.
- No accounts, no backend, no server-side state: per CLAUDE.md this is a single static `index.html` with no build step, hosted zero-config on Vercel. Any "progress" or "gamification" state today can only live client-side (in-memory `state` during a session, or `localStorage`, as the theme preference already does).

## Capabilities and Constraints

- Single-file architecture (`index.html`): one in-memory question bank (`BANK`/`BANK_ID`) and one mutable `state` object drive everything; four screens (start, exam, results, flashcards) toggled via `showScreen`.
- No test suite, linter, or build command; "testing" means clicking through the real flow in a browser (see CLAUDE.md Running it / Architecture sections for the exact mechanics — `drawQuestions`, `stepQuestion`, swipe handling, theming — which is the authoritative reference, not this file).
- No user accounts or persistence layer beyond `localStorage` today. Any gamification (streaks, scores over time, badges, XP, etc.) that needs to persist across sessions for two distinct people is an open technical decision, not yet made.
- Content is French-only; all UI copy, comments, and explanations stay in French per existing convention.

## Brand Commitments

None beyond what's already in the page: the "RÉPUBLIQUE FRANÇAISE · MINISTÈRE DE L'INTÉRIEUR"-styled masthead is an intentional pastiche of the official exam's look (to feel like "the real thing"), paired with an explicit non-affiliation disclaimer. Preserve both the pastiche and the disclaimer together — one without the other changes what the page claims.

## Evidence on Hand

- The question bank itself (`BANK` in `index.html`) is the only content asset; no external question sources, past papers, or citations beyond the decree/arrêté referenced in the page's own rules text.
- No user testimonials, usage data, or analytics exist or should be fabricated — this is a two-person personal tool, not a product with a user base to cite.

## Product Principles

1. Match the real exam's conditions exactly (question count, timing, pass threshold, situation-question ratio) — realism is the core value, not a nice-to-have.
2. Zero friction to open and use: no install, no build, no login — stays a single static file.
3. Keep it engaging for two specific repeat users, not a broad audience — gamification choices should be judged by "will Georges and his wife actually keep using this," not by generic engagement metrics.
4. Content accuracy matters: explanations cite the relevant law/institution and must stay factually correct, since this is genuine exam prep with real consequences.
5. French-only, terse, factual tone throughout — no filler, matching the existing explanation style.

## Accessibility & Inclusion

No specific accessibility requirement beyond standard accessible web practice (confirmed with the user — not a population-specific constraint here).
