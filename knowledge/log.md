---
title: Log
type: log
updated: 2026-11-19
---

# Log

Append-only. Newest entries at the bottom.

Entry headers use a fixed prefix so the log is greppable:
`grep "^## \[" log.md | tail -5`

Kinds: `ingest` · `query` · `synthesis` · `lint` · `schema`

---

## [2026-11-19] schema | Chefi research vault initialized as an LLM Wiki
- **added:** CLAUDE.md (schema, copied from the main vault), index.md, log.md, maps/connections.canvas
- **added:** folders raw/{assets}, wiki/{sources,notes,entities,concepts,questions,syntheses,references}, maps/
- **added:** raw/chefi-readme-snapshot.md, raw/chefi-platformio-ini-snapshot.ini, raw/chefi-main-cpp-snapshot.cpp — copies from https://github.com/Bokipr0/Chefi at commit 6e36209
- **seeded:** wiki/sources/chefi-repo-snapshot-2026-11-19, wiki/entities/chefi, wiki/entities/dfrobot-firebeetle2-esp32s3, wiki/questions/which-ai-service-will-chefi-use, wiki/questions/how-will-chefi-judge-doneness
- **notes:** The repo is a starter: src/main.cpp is the PlatformIO template (myFunction adds two ints). Camera, microphone, speaker, AI service and mounting are not implemented.
- **next:** a first research source on cooking-assistant vision or voice on ESP32-class hardware.

## [2026-11-19] ingest | Git update 4903951 "Add files via upload" (Bokipr0/Chefi)
- **source of change:** https://github.com/Bokipr0/Chefi — commit 4903951 is the only commit after the 6e36209 snapshot. It adds seven research files; README and firmware are unchanged.
- **copied to raw/:** Ai use in cooking.pdf, attest_ai_in_the_kitchen_extracted.pdf, cambom_home_cooking_statistics_extracted.pdf, hellofresh_state_of_home_cooking_extracted.pdf, qs_supplies_ai_kitchen_confidence_extracted.pdf, Cookpad_GlobalAnalysis_reportYear4.pdf, Nestle-Professional-Young-Chef-Survey-Report-2026.pdf
- **added sources:** attest-ai-food-use-2026, cambom-home-cooking-statistics-2026, hellofresh-state-of-home-cooking-2025, qs-supplies-ai-kitchen-confidence-2025, smartchef-ai-recipe-generation-ijert
- **added notes:** ai-food-adoption-figures-mix-past-use-and-intent, cooking-time-depends-on-denominator, ai-recipe-generators-skip-steps-they-do-not-understand, image-to-ingredient-is-the-closest-precedent-for-camera-input
- **updated:** which-ai-service-will-chefi-use (+raised-by note), how-will-chefi-judge-doneness (+raised-by note)
- **connections:** ai-food-adoption <--analogous-to--> cooking-time-depends-on-denominator (inferred, medium); skip-steps --raises--> which-ai-service (inferred, medium); image-to-ingredient --raises--> how-will-chefi-judge-doneness (inferred, medium)
- **effects:** no belief marked contested. The doneness question has a precedent for recognition but none for state.
- **open:** (1) source→note `yields` relations have no matching `sourced-from` on the notes' frontmatter; (2) Cookpad and Nestlé reports not ingested (no PDF text tools here); (3) the note weights are provisional.

## [2026-11-19] ingest | Nestlé Professional young-chef survey + Market folder
- **trigger:** user asked to connect the Nestlé PDF to the market scheme. The market scheme is the Chefi project's `Market/Possible competitors list.docx`.
- **text extraction:** pypdf installed with `pip install --user`. Nestlé PDF read in full (25 pages).
- **copied to raw/:** market-possible-competitors-list.docx (from Chefi/Market)
- **added sources:** nestle-professional-young-chef-survey-2026
- **added notes:** young-chefs-want-ai-for-admin-not-for-cooking
- **added questions:** does-professional-kitchen-ai-demand-transfer-to-home
- **added synthesis:** market-ai-cooking-competitors (StudioChef, Looki, Meta AI glasses)
- **added entity:** nestle-professional
- **connections:** young-chefs-want-ai-for-admin --raises--> does-professional-kitchen-ai-demand-transfer-to-home (inferred, medium); market-ai-cooking-competitors --raises--> same question (inferred, low)
- **effects:** no belief contested. The admin-vs-cooking split in professional data is now a stated question for Chefi's first feature.
- **open:** Cookpad report still not ingested; competitor claims are unverified (only the list's own text).

## [2026-11-19] ingest | Statista "AI use for home cooking in the U.S." (screenshot)
- **source:** screenshot of statista.com article; copied to raw/statista-ai-home-cooking-us-screenshot.png. Underlying survey, sample and date not shown, so figures are secondary.
- **added source:** statista-ai-home-cooking-us
- **added notes (6):** over-half-of-us-consumers-have-used-ai-for-food-tasks (behaviour); over-two-thirds-expect-to-use-ai-recipe-recommendations (intention); recipe-discovery-is-the-top-perceived-benefit-of-food-ai (attitude); home-ai-value-is-time-savings-on-planning-and-shopping (attitude); accuracy-of-ai-recipes-worries-a-third-of-us-consumers (attitude); privacy-is-the-top-consumer-concern-about-food-ai (attitude)
- **new category:** attitude (used for perceived benefits and concerns)
- **updated:** ai-food-adoption-figures-mix-past-use-and-intent (+supported-by, +analogous-to); young-chefs-want-ai-for-admin-not-for-cooking (+analogous-to); ai-recipe-generators-skip-steps-they-do-not-understand (+supports); does-professional-kitchen-ai-demand-transfer-to-home (+raised-by x1); which-ai-service-will-chefi-use (+raised-by privacy note)
- **connections:**
  - over-half-used --supports--> ai-food-adoption (inferred, medium)
  - over-two-thirds-intend --analogous-to--> ai-food-adoption (inferred, medium)
  - time-savings --analogous-to--> young-chefs-admin (inferred, medium)
  - time-savings --raises--> does-professional-kitchen-ai-demand-transfer-to-home (inferred, low)
  - time-savings --contrasts-with--> recipe-discovery (inferred, medium)
  - skip-steps --supports--> accuracy-worry (inferred, low; mechanism, not measured link)
  - privacy-concern --raises--> which-ai-service-will-chefi-use (inferred, medium)
- **effects:** no belief marked contested. Privacy is now a product question for the camera-and-mic device. Recipe discovery is the leading perceived benefit, which points to recommendation as a first feature.
- **open:** Statista survey source not identified; the article's date is not visible in the screenshot.

## [2026-11-19] ingest | Statista key claims — remaining nodes
- **added notes (6):** close-to-a-fifth-of-us-consumers-use-ai-for-food-regularly (behaviour, part-of over-half); a-quarter-of-us-consumers-use-ai-for-food-occasionally (behaviour, part-of over-half); 39-percent-of-us-consumers-have-never-used-ai-for-food (behaviour, contrasts-with over-half); cost-of-ai-services-worries-a-third-of-us-consumers (attitude, analogous-to accuracy, raises which-ai); consumers-are-comfortable-with-ai-nutrition-recipes-and-meal-plans (attitude, supports intention, contrasts-with discomfort); consumers-are-uncomfortable-with-ai-nutrition-advice-at-7-9-percent (attitude, contrasts-with comfort)
- **updated:** over-half note (+has-part x2, +contrasts-with); accuracy note (+analogous-to cost); intention note (+supported-by comfort); which-ai question (+raised-by cost); statista source (+yields x6)
- **canvas:** six new nodes added in the consumer block at x=1040; all edges added; your re-layout of the block was kept
- **effects:** no belief marked contested. Cost is the second-largest concern after privacy in the Statista set.
- **open:** the 19 one-sided yields/sourced-from pairs remain (known defect).

## [2026-11-19] schema | Meta-sectors added; canvas regrouped
- **schema:** every wiki page now has `meta-sector` (technical | market | design | user-research | storytelling). Documented in CLAUDE.md §2.
- **tagged:** all 32 wiki pages.
- **counts:** technical 7 · design 7 · user-research 13 · market 4 · storytelling 1
- **canvas:** regrouped into five sector blocks (Technical, Design, User research, Market, Storytelling). All 32 pages and all edges kept; one edge re-pointed (nestle-src yields admin).
- **index:** Meta-sectors section added.
- **gap:** Storytelling has one page. No narrative source has been ingested yet. The Chefi folder has three candidates not yet read: `Pitch Workshop Presentation 2026.pdf`, `Minto pyramid principle.pdf`, and `Build/Chefi 1-pager.pdf`.

## [2026-11-19] schema | Problem sector added at the centre; canvas simplified
- **new page:** syntheses/core-problem (meta-sector problem, weight 95): home cooks want planning help, not cooking control; it must be accurate, private and affordable. Working hypothesis, low confidence.
- **problem sector (4):** core-problem; questions which-ai-service, how-will-chefi-judge-doneness, does-professional-kitchen-ai-demand-transfer-to-home (moved from technical/market).
- **links:** core supported-by time-savings, accuracy, privacy, cost (inverse `supports` written on each); core raises the three questions (inverse `raised-by` written on each).
- **titles:** all 33 pages now have short titles (frontmatter `title` and heading), 2–5 words.
- **canvas:** rebuilt. Problem sits in the centre; Technical top-left, Design top-right, User research bottom-left, Market bottom-right, Storytelling under Problem. Cards show short titles only. Provenance (yields) arrows removed from the canvas; they remain in the frontmatter. 24 relation arrows.
- **schema:** CLAUDE.md lists six meta-sectors.
- **counts:** problem 4 · technical 5 · design 7 · user-research 13 · market 3 · storytelling 1 · 33 pages.

## [2026-11-19] schema | Canvas spacing widened
- **canvas:** card pitch increased (cards 300×96, 74 px minimum gap between neighbours); group gaps 260 px; the sector blocks keep their arrangement with Problem in the centre. No pages or relations changed.

## [2026-11-19] schema | Canvas edge labels reduced
- **obsidian:** added .obsidian/snippets/canvas-small-edge-labels.css (edge labels 6px) and enabled it in appearance.json. Obsidian needs a restart or snippet reload to apply it.

## [2026-11-19] schema | Pages renamed to short slugs; canvas cards embed the originals
- **renamed:** 30 wiki pages to short slugs (e.g. over-half-of-us-consumers-... → over-half-have-used-ai). All [[links]], frontmatter ids and index entries rewritten in the same pass. Earlier log entries keep the old names as history.
- **canvas:** every card is now a file embed of the original note (no text copies), so clicking or previewing a card opens the source note. Cards 320×120.
- **validation:** no broken links; 33 cards, all inside their sector block.

## [2026-11-19] schema | Sector tree map added
- **new map:** maps/sector-tree.canvas. Each sector is a tree: sector → class → notes. Six sectors, 16 classes, 33 note cards (all embeds of the originals).
- **classes:** Technical (Build, AI capability); Design (Product, Trust, Experience); User research (Consumer surveys, Behaviour, Intentions, Measurement, Professional sample); Market (Players, Pricing); Problem (Core, Open questions); Storytelling (Inspiration).
- **gap:** no camera, microphone or speaker note exists yet, so the Build class holds only the repo and board. Add those notes to fill it.

## [2026-11-19] ingest | Build documents from the Chefi project folder
- **copied to raw/:** chefi-component-goals.pdf (Build/component + goals.pdf, 17 Nov 2026), chefi-current-build.md (Build/CURRENT_BUILD.md, 14 Nov 2026)
- **added sources:** chefi-build-priorities, chefi-current-build
- **added entities (6):** camera-ov2660, microphone-inmp441, speaker-max98357a, imu-6-axis, current-sensor-ina219, server-backend. Each is part-of chefi; chefi has-part each.
- **added question:** battery-in-scope
- **conflicts recorded (not resolved):**
  - Camera: the user's example used OV3660; both build documents record OV2660 as user-reported and say not to substitute. Flagged on the camera page.
  - Battery: the build sheet lists a solid-state battery as P1 planned; the current build defers batteries. Open question.
  - Speaker power: 1–2 W from an earlier list, not verified.
- **maps:** sector-tree and connections regenerated. Technical block now has 14 cards.
- **not ingested:** User Research/technical + meta (glasses research files).

## [2026-11-19] schema | Sector and class headers enlarged
- **maps/sector-tree.canvas:** sector headers are now level-2 headings and class headers are level-3 headings, so they render larger.

## [2026-11-19] schema | Sector tree headers moved to group labels
- **reason:** text cards were blank at low zoom in Obsidian. Class names are now group labels, which stay visible at any zoom; the domain-to-class arrows now run from the domain block to each class block.

## [2026-11-19] schema | Sector tree cards are press-to-open links
- **maps/sector-tree.canvas:** each note card is now a text card holding one link to its note, with a short title. A single press on the link opens the note in a tab. The earlier file embeds showed scrollable content.

## [2026-11-19] schema | Sector tree titles are markdown links
- **maps/sector-tree.canvas:** each card title is now a bold markdown link to its note, so the title text itself is the press target.

## [2026-11-19] fix | Sector tree titles enlarged; duplicate sources key removed
- **maps/sector-tree.canvas:** card titles are level-2 headings that link to the note, so they are larger and there is no scrollable preview.
- **notes:** removed a duplicated `sources:` key in chefi-build-priorities and chefi-current-build; it made their Properties show as invalid.

## [2026-11-19] schema | Sector tree as a title-only note
- **maps/sector-tree.md:** new. Same hierarchy as the canvas (sector, class, notes), with each note as a clickable title and no cards.
- **maps/sector-tree.canvas:** unchanged in this step. Canvas cards always have a box, so they cannot be removed while keeping the canvas; a deletion needs your confirmation.

## [2026-11-19] schema | Sector tree cards replaced with title-only cards
- **maps/sector-tree.canvas:** all 42 note cards replaced with text cards holding only a clickable heading title (320×80). Sector and class groups kept.

## [2026-11-19] schema | Canvas card titles enlarged via CSS
- **.obsidian/snippets/canvas-large-titles.css:** level-2 titles on canvas text cards at 2.4em. Enabled in appearance.json.
- **note:** Obsidian draws canvas card content only when zoomed in; at low zoom the cards look blank regardless of size.

## [2026-11-19] schema | Sector tree generated from the wiki
- **source of truth:** each page's meta-sector, class and title. All 42 pages tagged with class.
- **generator:** tools/build_sector_tree.py writes maps/sector-tree.canvas and maps/sector-tree.md. Idempotent; writes only on change.
- **automation:** a Claude Code PostToolUse hook in ~/.claude/settings.json runs the generator after Edit, Write and Bash tool calls.
- **to add a note to the tree:** set its meta-sector and class in the frontmatter. Pages without a class go under Unsorted, and pages without a meta-sector are left out.

## [2026-11-19] schema | Facts and claims separated; claim tree added
- **kind field:** every page has kind: fact or kind: claim.
- **claims (9):** chefs-want-ai-for-admin, ai-recipes-skip-steps, photo-to-ingredients, core-problem, which-ai-service, judge-doneness, pro-demand-to-home, battery-in-scope, competitors. Interpretations, open questions and syntheses.
- **facts (33):** sources, entities, and notes that state a measured figure or a stated build spec.
- **maps:** sector-tree.* now holds facts only. claim-tree.* holds claims only. Both are generated by tools/build_sector_tree.py.
- **to change a page:** edit its kind field and the trees update on the next edit.

## [2026-11-19] schema | Sector layout compacted
- **tools/build_sector_tree.py:** sectors placed in three columns (Technical and User research left; Problem and Storytelling centre; Design and Market right). Gaps 120–140 px instead of 200–260 px; block width 840 px instead of 1400 px. Problem sits centre on the claim tree.

## [2026-11-19] schema | Sector layout restored to the earlier grid
- **tools/build_sector_tree.py:** reverted the compact three-column layout to the earlier grid (Technical and Design on top, User research, Problem and Market in the middle, Storytelling below), with the original spacing and card positions.

## [2026-11-19] schema | Graph coloured by sector and class
- **tags:** every wiki page now carries sector/<sector> and class/<class> tags (42 pages).
- **graph.json:** colour groups per class (shades of its sector colour) and per sector, using the sector-tree colours: Technical green, Design cyan, User research purple, Market orange, Problem red, Storytelling yellow.
- **generator:** tools/build_sector_tree.py adds missing tags and re-syncs graph colours on each run (and so on each hook run).

## [2026-11-19] schema | Sector hubs; graph coloured by sector only
- **hubs:** wiki/concepts/sector-<sector>.md (6 pages, type hub). Each links every page in its sector by class. Hubs are skipped by the trees.
- **graph:** colours by sector only (class shades removed). nodeSizeMultiplier 1.6. Hub nodes have the most links, so they render largest.

## [2026-11-19] fix | Graph colour groups restored
- **cause:** Obsidian rewrote .obsidian/graph.json with an empty colorGroups list, overwriting the colour rules from the generator.
- **fix:** generator re-applied the six sector colour groups. Restart Obsidian (or reopen the graph view) so it reads the file and does not overwrite it again.

## [2026-11-19] schema | Sector blocks brought close together
- **tools/build_sector_tree.py:** compact three-column layout reinstated. Gap between blocks 120–140 px; block width 840 px.

## [2026-11-19] schema | Sector layout reverted to the grid
- **tools/build_sector_tree.py:** reverted the compact layout to the earlier grid (the state before the last change).

## [2026-11-19] sync | Knowledge base committed to the Chefi repo (local only)
- **tools/sync_knowledge.py:** copies the vault into the repo's knowledge/ folder and writes knowledge/README.md (how to navigate, labels, sector and page list).
- **repo:** committed locally in the repo clone (scratchpad/chefi-sync), not pushed. Raw sources and app settings are excluded.
