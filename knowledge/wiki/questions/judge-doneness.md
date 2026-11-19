---
id: judge-doneness
title: "How to judge doneness?"
type: question
meta-sector: problem
class: "Open questions"
kind: claim
created: 2026-11-19
updated: 2026-11-19
status: seed
confidence: low
weight: 35
tags: [topic/vision, topic/cooking, sector/problem, class/open-questions]
sources: ["[[wiki/sources/chefi-repo-snapshot]]"]
relations:
  - rel: raised-by
    to: "[[wiki/sources/chefi-repo-snapshot]]"
    why: The README lists a camera as planned without saying what it should recognize.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: raised-by
    to: "[[wiki/entities/chefi]]"
    why: Camera input is a planned feature, so a doneness target follows from the product goal.
    basis: inferred
    confidence: medium
    found: 2026-11-19
  - rel: raised-by
    to: "[[wiki/notes/photo-to-ingredients]]"
    why: A photo pipeline already exists for ingredients; it does not show that state, such as doneness, can be judged from an image.
    basis: inferred
    confidence: medium
    found: 2026-11-19
  - rel: raised-by
    to: "[[wiki/syntheses/core-problem]]"
    why: Doneness judgement is a later, riskier feature.
    basis: inferred
    confidence: medium
    found: 2026-11-19
---

# How to judge doneness?

The planned camera is the only sensor that could judge cooking state. The README does not say what Chefi should look for, or whether it should judge doneness at all.

## Why it matters
Visual doneness on a small board is hard. The answer sets the camera resolution, the model size, and whether the judgement runs on-device or in a remote service.

## What would answer it
- A list of target foods and the visual cues that matter for each.
- Whether doneness is a fixed rule (colour, time) or a learned classifier.

## Connections
- **raised-by** [[wiki/syntheses/core-problem]] — Doneness judgement is a later, riskier feature.
- **raised-by** [[wiki/sources/chefi-repo-snapshot]]
- **raised-by** [[wiki/entities/chefi]] — inferred from the planned camera.
- **raised-by** [[wiki/notes/photo-to-ingredients]] — recognition exists; state does not yet.
