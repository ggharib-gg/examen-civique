---
version: 1
slug: "index-html"
primary_target: "index.html"
related_targets: []
---

# index.html — l'application entière

Scope: all five screens (accueil, examen, résultats, fiches, carnet) in one static file. Visitor mode: Operate.

Audience: Georges and his wife, on their own phones, most evenings, in the months before the naturalisation civics exam. Job: run a session that matches the real exam, see where they stand, and keep each other going. Content is the real question bank plus each person's local practice record; the partner's figures arrive over Firebase Realtime Database (free tier, config pasted in-app, room code is the shared secret). Constraints: French only, mobile-first, Tailwind v4 browser build, no build step, no accounts.

History: the first build extended the incumbent "official French administrative document" world. The user rejected that world outright ("looks like shit"), scoped the redesign to the whole app, and asked for a safer register on the re-roll. Everything below replaces it; the old paper/serif/ruled-margin system is an anti-reference, not a base.

Unresolved: the user must create the Firebase project and paste its web config; badge thresholds are mine.

## Direction contract

THESIS: L'Affiche — mid-century French poster (Cassandre, Savignac). Flat saturated ink fields, huge confident lettering, geometry as structure. It refuses both the discarded government-form look and the white-card, rounded-sans, green-streak quiz-app default.

OWN-WORLD: inks constant across themes — bleu nuit #14335E, vermillon #E1432D / #B82F1C, or #F2B417, vert #1F6B4A, crème #F7F1E4; only paper and body text flip for dark. Archivo at variable width: 122% width / 900 weight for display, normal for text. Square corners at 2px; circles only for letter roundels and the cockade mark. Each of the four themes owns one ink, used identically on question plates, result bars, mastery bars and the corrigé.

STORY: they see the epreuve stated at poster scale, pick a format, sit the exam, get a verdict that prints like a bill, and find their streak, échelon, tampons and their partner's figures in the carnet.

FIRST VIEWPORT: navy masthead band with the cockade; a full-bleed vermilion field carrying the display headline and the four exam facts; then the format choice and the primary action on paper below.

FORM: replacement visual world, chosen by the user after a re-roll in the safer register; grounded candidate "affiche française" from the audience's own graphic culture; seed key 4c31bae3, re-roll round 1.

FINISH: unreviewed and undocumented is unfinished; this build ends with the finish review, the verdict, DESIGN.md, and every shipping raster carrying its provenance.
