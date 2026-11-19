---
id: smartchef-paper
title: "SmartChef paper"
type: source
meta-sector: technical
class: "AI capability"
kind: fact
created: 2026-11-19
updated: 2026-11-19
status: stable
confidence: medium
weight: 35
tags: [topic/ai-service, topic/vision, topic/recipe-generation, sector/technical, class/ai-capability]
sources: []
relations:
  - rel: yields
    to: "[[wiki/notes/ai-recipes-skip-steps]]"
    why: The paper reports that generated recipes drop steps and that the model lacks the reasons behind them.
    basis: explicit
    confidence: medium
    found: 2026-11-19
  - rel: yields
    to: "[[wiki/notes/photo-to-ingredients]]"
    why: The paper's photo-to-ingredients step is the closest working precedent for camera input.
    basis: explicit
    confidence: high
    found: 2026-11-19
---

# SmartChef paper

Dsouza & Sumangala, St Joseph Engineering College, Mangaluru. Describes a web app that uses Google Gemini to generate recipes from typed ingredients or photos. Peer-reviewed venue; evaluation is functional testing, informal user feedback, and recipe review, not a controlled study. Extracted in `raw/Ai use in cooking.pdf`.

## Key claims
- Text and image input both work. Images go through a two-step pipeline: first identify ingredients, then generate the recipe. The authors chose this for control and reproducibility.
- Post-processing checks ensure every listed ingredient appears in the instructions. A safety filter removes or regenerates unsafe recipes.
- Failure modes reported: vague steps ("cook until done"), omitted steps, duplicate or missing ingredients, odd pairings, and unsafe suggestions such as bleach or chlorine gas.
- Proposed fixes: a second "recipe critic" model, nutrition checks, and human oversight.
- Voice assistance for hands-free steps is listed as future work.

## Caveats
- Single small application. Results are not benchmarked against a baseline.

## Connections
- **yields** [[wiki/notes/ai-recipes-skip-steps]]
- **yields** [[wiki/notes/photo-to-ingredients]]

## Sources
- raw/Ai use in cooking.pdf
