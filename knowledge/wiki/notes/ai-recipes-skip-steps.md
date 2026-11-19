---
id: ai-recipes-skip-steps
title: "AI recipes skip steps"
type: note
meta-sector: technical
class: "AI capability"
kind: claim
created: 2026-11-19
updated: 2026-11-19
status: developing
confidence: medium
weight: 30
claim-category: capability
tags: [topic/ai-service, topic/recipe-reliability, claim/capability, sector/technical, class/ai-capability]
sources:
  - "[[wiki/sources/smartchef-paper]]"
relations:
  - rel: raises
    to: "[[wiki/questions/which-ai-service]]"
    why: If generators drop steps, any recipe service needs a checking layer, which changes what the service must do and where it runs.
    basis: inferred
    confidence: medium
    found: 2026-11-19
  - rel: supports
    to: "[[wiki/notes/third-doubt-accuracy]]"
    why: The documented step-dropping is a concrete mechanism behind consumer doubts about recommendation accuracy; the survey does not link them.
    basis: inferred
    confidence: low
    found: 2026-11-19
  - rel: sourced-from
    to: "[[wiki/sources/smartchef-paper]]"
    why: The source page yields this claim.
    basis: explicit
    confidence: high
    found: 2026-11-19
---

# AI recipes skip steps

SmartChef's authors report that the model produces "average" recipes from what it saw online. If common examples skipped a step, so did the model. It also does not know why a step matters, so it may drop or change one. Baking and techniques such as tempering and deglazing were most affected.

The evidence is informal. The authors used functional tests and user impressions, not a controlled comparison.

## Connections
- **raises** [[wiki/questions/which-ai-service]] — the answer depends on whether checks run on the device or in the service.
- **supports** [[wiki/notes/third-doubt-accuracy]] — a mechanism for the accuracy worry, not a measured link.

## Sources
- [[wiki/sources/smartchef-paper]]
