---
id: microphone-inmp441
title: "Microphone (INMP441)"
type: entity
meta-sector: technical
class: "Sensing and audio"
kind: fact
created: 2026-11-19
updated: 2026-11-19
status: seed
confidence: high
weight: 35
tags: [topic/sensing, kind/hardware, sector/technical, class/sensing-and-audio]
sources:
  - "[[wiki/sources/chefi-build-priorities]]"
  - "[[wiki/sources/chefi-current-build]]"
relations:
  - rel: part-of
    to: "[[wiki/entities/chefi]]"
    why: Build sheet and current build list the microphone as part of the prototype.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: sourced-from
    to: "[[wiki/sources/chefi-build-priorities]]"
    why: The build documents record this component.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: sourced-from
    to: "[[wiki/sources/chefi-current-build]]"
    why: The build documents record this component.
    basis: explicit
    confidence: high
    found: 2026-11-19
---

# Microphone (INMP441)

INMP441 I2S microphone, owned. P1 in the build sheet.
Purpose: capture questions, corrections and fridge ingredients outside the camera view.

## Connections
- part-of [[wiki/entities/chefi]]

## Sources
- [[wiki/sources/chefi-build-priorities]]
- [[wiki/sources/chefi-current-build]]
