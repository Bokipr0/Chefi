---
id: which-ai-service
title: "Which AI service?"
type: question
meta-sector: problem
class: "Open questions"
kind: claim
created: 2026-11-19
updated: 2026-11-19
status: seed
confidence: low
weight: 35
tags: [topic/ai-service, sector/problem, class/open-questions]
sources: ["[[wiki/sources/chefi-repo-snapshot]]"]
relations:
  - rel: raised-by
    to: "[[wiki/sources/chefi-repo-snapshot]]"
    why: The README lists the AI service among unimplemented features.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: raised-by
    to: "[[wiki/entities/chefi]]"
    why: The product's planned feature list includes an AI service with no chosen provider.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: raised-by
    to: "[[wiki/notes/ai-recipes-skip-steps]]"
    why: Generators drop steps, so any recipe service needs a checking layer; where that layer runs is part of this choice.
    basis: inferred
    confidence: medium
    found: 2026-11-19
  - rel: raised-by
    to: "[[wiki/notes/privacy-top-concern]]"
    why: Data privacy is the top consumer concern, so cloud versus on-device processing is also a trust question.
    basis: inferred
    confidence: medium
    found: 2026-11-19
  - rel: raised-by
    to: "[[wiki/notes/third-worry-cost]]"
    why: Cost is a concern for a third of consumers, and the service model sets the price model.
    basis: inferred
    confidence: low
    found: 2026-11-19
  - rel: raised-by
    to: "[[wiki/syntheses/core-problem]]"
    why: The problem leaves the service choice open.
    basis: inferred
    confidence: medium
    found: 2026-11-19
---

# Which AI service?

The README names an AI service as planned but unimplemented. The vault does not yet know whether it will be a cloud model, a local model, or a rule-based system, nor what it must do.

## Why it matters
The service decides what the ESP32-S3 has to send and receive: audio, images, or text. Hardware and latency depend on that choice.

## What would answer it
- The intended role of the service: recipe guidance, timing, or recognition.
- Whether the board must work offline.

## Connections
- **raised-by** [[wiki/syntheses/core-problem]] — The problem leaves the service choice open.
- **raised-by** [[wiki/sources/chefi-repo-snapshot]]
- **raised-by** [[wiki/entities/chefi]]
- **raised-by** [[wiki/notes/ai-recipes-skip-steps]] — recipe checks may need to run in the service.
- **raised-by** [[wiki/notes/privacy-top-concern]] — cloud versus on-device is a privacy question too.
- **raised-by** [[wiki/notes/third-worry-cost]] — the service model sets the price model.
