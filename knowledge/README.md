# Chefi knowledge base: how to navigate

This folder is an LLM-maintained wiki about the Chefi project (a cooking assistant prototype).
It is generated from the working vault; do not edit it here. Edit the vault and sync again.

## Where to start
1. `index.md`: catalogue of every page, grouped by type.
2. `maps/sector-tree.md`: facts by sector, then class.
3. `maps/claim-tree.md`: claims and open questions by sector.
4. `CLAUDE.md`: the schema: page types, frontmatter, relation names.
5. `log.md`: chronological history of changes and open items.

## How pages are labelled
- `meta-sector`: technical, design, user-research, market, problem, storytelling.
- `class`: the sub-group inside a sector (for example Build, Trust, Behaviour).
- `kind`: `fact` (a source, a measured figure, or a build spec) or `claim` (an interpretation, open question, or synthesis).
- `type`: source, note, entity, question, synthesis, or hub (sector hub pages).
- `claim-category` (notes only): behaviour, measurement, capability, intention, attitude.
- `relations:` in each frontmatter lists typed links (supports, raises, contrasts-with, part-of, yields and so on), each with `basis` (explicit, inferred or speculative).

## Sectors, classes and pages

### Technical
- **Build**
  - [Chefi build priorities (17 Nov 2026)](wiki/sources/chefi-build-priorities.md) — fact
  - [Chefi current build (14 Nov 2026)](wiki/sources/chefi-current-build.md) — fact
  - [Chefi repo snapshot](wiki/sources/chefi-repo-snapshot.md) — fact
  - [FireBeetle 2 board](wiki/entities/firebeetle-2-board.md) — fact
  - [Is the battery in scope?](wiki/questions/battery-in-scope.md) — claim
- **Sensing and audio**
  - [Camera (OV2660)](wiki/entities/camera-ov2660.md) — fact
  - [Microphone (INMP441)](wiki/entities/microphone-inmp441.md) — fact
  - [Motion sensor (6-axis IMU)](wiki/entities/imu-6-axis.md) — fact
  - [Power sensor (INA219)](wiki/entities/current-sensor-ina219.md) — fact
  - [Speaker amplifier (MAX98357A)](wiki/entities/speaker-max98357a.md) — fact
- **AI capability**
  - [AI recipes skip steps](wiki/notes/ai-recipes-skip-steps.md) — claim
  - [Photo → ingredients](wiki/notes/photo-to-ingredients.md) — claim
  - [Server and processing](wiki/entities/server-backend.md) — fact
  - [SmartChef paper](wiki/sources/smartchef-paper.md) — fact

### Design
- **Product**
  - [Chefi](wiki/entities/chefi.md) — fact
  - [Chefs want AI for admin](wiki/notes/chefs-want-ai-for-admin.md) — claim
  - [Time saved on planning](wiki/notes/time-saved-on-planning.md) — fact
- **Trust**
  - [A third doubt accuracy](wiki/notes/third-doubt-accuracy.md) — fact
  - [Privacy is top concern](wiki/notes/privacy-top-concern.md) — fact
- **Experience**
  - [7.9% uncomfortable with AI advice](wiki/notes/7-9-percent-uncomfortable.md) — fact
  - [Comfort with AI food help](wiki/notes/comfort-with-ai-food-help.md) — fact

### User research
- **Consumer surveys**
  - [Attest survey](wiki/sources/attest-survey.md) — fact
  - [HelloFresh survey](wiki/sources/hellofresh-survey.md) — fact
  - [QS Supplies survey](wiki/sources/qs-supplies-survey.md) — fact
  - [Statista AI survey](wiki/sources/statista-survey.md) — fact
- **Behaviour**
  - [24% use AI occasionally](wiki/notes/quarter-use-ai-occasionally.md) — fact
  - [39% never used AI](wiki/notes/39-percent-never-used-ai.md) — fact
  - [Over half have used AI](wiki/notes/over-half-have-used-ai.md) — fact
  - [~20% use AI regularly](wiki/notes/fifth-use-ai-regularly.md) — fact
- **Intentions**
  - [Two-thirds expect to use](wiki/notes/two-thirds-expect-to-use.md) — fact
- **Measurement**
  - [Adoption mixes use and intent](wiki/notes/adoption-figures.md) — fact
  - [Cambom time-use data](wiki/sources/cambom-time-use.md) — fact
  - [Cooking time needs a base](wiki/notes/cooking-time-base.md) — fact
- **Professional sample**
  - [Nestlé young chefs survey](wiki/sources/nestle-young-chefs-survey.md) — fact

### Problem
- **Core**
  - [Core problem](wiki/syntheses/core-problem.md) — claim
- **Open questions**
  - [How to judge doneness?](wiki/questions/judge-doneness.md) — claim
  - [Pro demand → home?](wiki/questions/pro-demand-to-home.md) — claim
  - [Which AI service?](wiki/questions/which-ai-service.md) — claim

### Market
- **Players**
  - [Competitors](wiki/syntheses/competitors.md) — claim
  - [Nestlé Professional](wiki/entities/nestle-professional.md) — fact
- **Pricing**
  - [A third worry about cost](wiki/notes/third-worry-cost.md) — fact

### Storytelling
- **Inspiration**
  - [Discovery is top benefit](wiki/notes/discovery-top-benefit.md) — fact

Pages with kind `claim` are interpretations. Treat them as hypotheses, not facts.
