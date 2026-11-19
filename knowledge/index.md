---
title: Index
type: index
updated: 2026-11-19
---

# Index

Catalog of every page in the Chefi research wiki. Read this first when answering a question,
then drill into the relevant pages and follow their `relations` one hop out.

Maintained by the LLM on every ingest — see [[CLAUDE]] for the schema.
Chronological history lives in [[log]]. Arrowed maps live in [maps/](maps/).

**Counts:** 10 sources · 17 notes · 9 entities · 0 concepts · 4 questions · 2 syntheses · 0 references
**Pending:** `raw/Cookpad_GlobalAnalysis_reportYear4.pdf` is in raw/ but not yet ingested. Its text is not extractable with the tools here (pypdf is now installed in user site-packages, so it can be tried next).

---

## Sources
*One page per file in `raw/`. Newest first.*

- [[wiki/sources/statista-survey]] — Statista (screenshot, source survey unknown): over half of US consumers used AI for food tasks; 45.2% link AI to time savings; 33.9% worry about accuracy
- [[wiki/sources/nestle-young-chefs-survey]] — Nestlé Professional, 300 young chefs (ANZ), June 2026: 78% use AI somewhere; 57% expect AI to cut admin, 25% expect it to automate cooking
- [[wiki/sources/attest-survey]] — Attest, US/UK consumers, n=1,993: 63.8% past AI food-tool use; Nov 2026
- [[wiki/sources/cambom-time-use]] — Cambom recalculation of BLS time-use: 63.6 vs 40.2 min/day food prep; July 2026
- [[wiki/sources/hellofresh-survey]] — HelloFresh/Wakefield, US n=5,000: 69% used-or-open AI for dinner; 2025
- [[wiki/sources/qs-supplies-survey]] — QS Supplies, UK/US n=1,000: confidence and planned AI use; Nov 2025
- [[wiki/sources/smartchef-paper]] — SmartChef (Gemini) recipe app paper: image-to-ingredients, step-dropping failure modes
- [[wiki/sources/chefi-build-priorities]] — build sheet, 17 Nov 2026: priorities P0–P3
- [[wiki/sources/chefi-current-build]] — current build note, 14 Nov 2026: owned and deferred items
- [[wiki/sources/chefi-repo-snapshot]] — Chefi repo at commit 6e36209: README, platformio.ini, starter firmware

## Notes
*Atomic claims, one idea each.*

- [[wiki/notes/adoption-figures]] — Adoption headlines mix past use, intent and "used or open"; do not pool them
- [[wiki/notes/cooking-time-base]] — Same BLS data gives 63.6 and 40.2 min/day; state the population before using a time figure
- [[wiki/notes/ai-recipes-skip-steps]] — Generators drop steps they lack the reasons for; a checking layer is needed
- [[wiki/notes/photo-to-ingredients]] — Photo-to-ingredients shows recognition; doneness (state) is not shown
- [[wiki/notes/chefs-want-ai-for-admin]] — Professional young chefs want AI for admin and ideas, not for cooking
- [[wiki/notes/over-half-have-used-ai]] — Behaviour: over half of US consumers have used AI for food tasks; 39.2% never
- [[wiki/notes/two-thirds-expect-to-use]] — Intention: over two-thirds likely to use AI recipe recommendations
- [[wiki/notes/discovery-top-benefit]] — Attitude: finding new recipes is the leading perceived benefit
- [[wiki/notes/time-saved-on-planning]] — Attitude: 45.2% link AI to time savings on planning and shopping
- [[wiki/notes/third-doubt-accuracy]] — Attitude: 33.9% concerned about accuracy of AI recommendations
- [[wiki/notes/privacy-top-concern]] — Attitude: data privacy is the chief concern, shared by slightly under half
- [[wiki/notes/fifth-use-ai-regularly]] — Behaviour: close to 20% use AI for food regularly (part of the over-half figure)
- [[wiki/notes/quarter-use-ai-occasionally]] — Behaviour: 24.4% use AI for food occasionally (part of the over-half figure)
- [[wiki/notes/39-percent-never-used-ai]] — Behaviour: 39.2% have never used AI for food (complement of over-half)
- [[wiki/notes/third-worry-cost]] — Attitude: 34.1% concerned about the cost of AI services
- [[wiki/notes/comfort-with-ai-food-help]] — Attitude: comfort is high for nutrition advice, recipe recommendations and meal plans
- [[wiki/notes/7-9-percent-uncomfortable]] — Attitude: 7.9% uncomfortable with AI nutrition advice

## Entities
*Products, hardware, tools, organizations.*

- [[wiki/entities/chefi]] — Compact cooking assistant prototype; ESP32-S3 based; early stage
- [[wiki/entities/firebeetle-2-board]] — Target board for the firmware
- [[wiki/entities/camera-ov2660]] — camera, reported OV2660, unverified (P0)
- [[wiki/entities/microphone-inmp441]] — microphone, owned (P1)
- [[wiki/entities/speaker-max98357a]] — speaker amplifier, owned (P1)
- [[wiki/entities/imu-6-axis]] — 6-axis IMU, model to verify (P2)
- [[wiki/entities/current-sensor-ina219]] — power sensor, test item (P1)
- [[wiki/entities/server-backend]] — server and processing, to configure (P0)
- [[wiki/entities/nestle-professional]] — Foodservice brand; sponsor of the young-chef survey; professional-kitchen incumbent

## Concepts
*Features, mechanisms, methods.*

*(none yet)*

## Questions
*Open — the vault cannot yet answer these.*

- [[wiki/questions/battery-in-scope]] — build sheet says battery planned (P1); current build defers it
- [[wiki/questions/which-ai-service]] — The README names an AI service as unimplemented; which one is undecided
- [[wiki/questions/judge-doneness]] — Camera is planned; what it must recognize is not yet specified
- [[wiki/questions/pro-demand-to-home]] — Do professional-kitchen AI priorities (admin, ideas) carry over to home cooks?

## Syntheses
*Cross-cutting analysis and filed-back answers.*

- [[wiki/syntheses/core-problem]] — Home cooks want planning help, not cooking control; it must be accurate, private and affordable
- [[wiki/syntheses/competitors]] — Market list: StudioChef, Looki, Meta AI glasses; none yet shown to target home cooks

## Maps
- `maps/connections.canvas` — running arrowed map of all typed relations, grouped by sector
- `maps/sector-tree.canvas` — facts only, per sector: sector → class → notes
- `maps/claim-tree.canvas` — claims and open questions only, per sector

## References
*(none yet)*

---

## Meta-sectors
*Six sectors. Problem sits at the centre of the map; the others sit around it.*

- **Problem** (4): [[wiki/syntheses/core-problem]], [[wiki/questions/which-ai-service]], [[wiki/questions/judge-doneness]], [[wiki/questions/pro-demand-to-home]]
- **Technical** (14): [[wiki/sources/chefi-repo-snapshot]], [[wiki/sources/smartchef-paper]], [[wiki/entities/firebeetle-2-board]], [[wiki/notes/ai-recipes-skip-steps]], [[wiki/notes/photo-to-ingredients]], [[wiki/sources/chefi-build-priorities]], [[wiki/sources/chefi-current-build]], [[wiki/questions/battery-in-scope]], [[wiki/entities/camera-ov2660]], [[wiki/entities/microphone-inmp441]], [[wiki/entities/speaker-max98357a]], [[wiki/entities/imu-6-axis]], [[wiki/entities/current-sensor-ina219]], [[wiki/entities/server-backend]]
- **Design** (7): [[wiki/entities/chefi]], [[wiki/notes/chefs-want-ai-for-admin]], [[wiki/notes/time-saved-on-planning]], [[wiki/notes/third-doubt-accuracy]], [[wiki/notes/privacy-top-concern]], [[wiki/notes/comfort-with-ai-food-help]], [[wiki/notes/7-9-percent-uncomfortable]]
- **User research** (13): [[wiki/sources/nestle-young-chefs-survey]], [[wiki/sources/attest-survey]], [[wiki/sources/hellofresh-survey]], [[wiki/sources/qs-supplies-survey]], [[wiki/sources/cambom-time-use]], [[wiki/sources/statista-survey]], [[wiki/notes/adoption-figures]], [[wiki/notes/cooking-time-base]], [[wiki/notes/over-half-have-used-ai]], [[wiki/notes/fifth-use-ai-regularly]], [[wiki/notes/quarter-use-ai-occasionally]], [[wiki/notes/39-percent-never-used-ai]], [[wiki/notes/two-thirds-expect-to-use]]
- **Market** (3): [[wiki/entities/nestle-professional]], [[wiki/syntheses/competitors]], [[wiki/notes/third-worry-cost]]
- **Storytelling** (1): [[wiki/notes/discovery-top-benefit]] — thin; no narrative source ingested yet.

## Contested claims
*Pages with `status: contested` — check here first.*

*(none yet)*

## Superseded
*Retired beliefs, kept for history.*

*(none yet)*
