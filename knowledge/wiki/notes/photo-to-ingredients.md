---
id: photo-to-ingredients
title: "Photo → ingredients"
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
tags: [topic/vision, topic/cooking, claim/capability, sector/technical, class/ai-capability]
sources:
  - "[[wiki/sources/smartchef-paper]]"
relations:
  - rel: raises
    to: "[[wiki/questions/judge-doneness]]"
    why: Identifying ingredients from a photo is recognition, not state; the open question is whether the same pipeline can judge doneness.
    basis: inferred
    confidence: medium
    found: 2026-11-19
  - rel: sourced-from
    to: "[[wiki/sources/smartchef-paper]]"
    why: The source page yields this claim.
    basis: explicit
    confidence: high
    found: 2026-11-19
---

# Photo → ingredients

SmartChef sends a photo to a vision model to list ingredients, then generates a recipe from that list. The authors split the work into two steps for control and reproducibility.

This shows that a camera can feed a cooking pipeline. It does not show that a camera can judge doneness. Ingredient identity is a recognition task. Doneness depends on state, colour and time, and the paper does not address it.

## Connections
- **raises** [[wiki/questions/judge-doneness]] — the precedent covers recognition, not state.

## Sources
- [[wiki/sources/smartchef-paper]]
