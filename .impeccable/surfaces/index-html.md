---
version: 1
slug: "index-html"
primary_target: "index.html"
related_targets: []
---

# Carnet de suivi (gamification)

Scope: new `screen-progress` inside `index.html`, plus a masthead entry chip, a start-screen card, and a stamp moment on the results screen. Visitor mode: Operate.

Audience: Georges and his wife, separate devices, drilling for the naturalisation civics exam. Job: see whether they practised today, how they rank against each other, and start another session. Content is real local practice data plus the partner's synced figures (Firebase Realtime Database, free tier; room code is the shared secret). Constraints: French only, mobile-first, Tailwind v4 browser build for the new UI only, incumbent CSS untouched, no accounts.

Unresolved: badge thresholds are mine to set; user must create the Firebase project and paste its web config.

## Direction contract

THESIS: progress as an official French record book — registre de présence, échelons, tampons, relevé comparatif. It refuses the XP-bar-and-trophy game screen the category ships.

OWN-WORLD: incumbent palette and type (paper/ink/navy/red/gold, EB Garamond display, Lato labels, ruled-margin sheet). New components: day-cell attendance strip, échelon ladder with grade names, authored circular ink seals with rim lettering, two-column comparative relevé.

STORY: they see the streak they must not break tonight, their administrative grade, the seals earned, their partner's figures beside their own — and start another séance.

FIRST VIEWPORT: register strip of 14 day cells (today ringed) above the échelon line with grade name and rule-bar; the "Commencer une séance" action sits directly beneath, before badges and comparison.

FORM: extension of an established surface, no concept tournament (narrow, precisely specified request); seed key: n/a — extension.

FINISH: unreviewed and undocumented is unfinished; this build ends with the finish review, the verdict, DESIGN.md, and every shipping raster carrying its provenance.
