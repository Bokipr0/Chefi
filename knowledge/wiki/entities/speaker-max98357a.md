---
id: speaker-max98357a
title: "Speaker amplifier (MAX98357A)"
type: entity
meta-sector: technical
class: "Sensing and audio"
kind: fact
created: 2026-11-19
updated: 2026-11-19
status: seed
confidence: medium
weight: 35
tags: [topic/audio, kind/hardware, sector/technical, class/sensing-and-audio]
sources:
  - "[[wiki/sources/chefi-build-priorities]]"
  - "[[wiki/sources/chefi-current-build]]"
relations:
  - rel: part-of
    to: "[[wiki/entities/chefi]]"
    why: The amplifier drives the prototype speaker, so it is part of the device.
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

# Speaker amplifier (MAX98357A)

MAX98357A I2S amplifier driving an 8-ohm miniature speaker. Owned. P1 in the build sheet.
Purpose: speak advice hands-free while the user keeps cooking.
Speaker power rating is unverified; the earlier list says 1–2 W.

## Connections
- part-of [[wiki/entities/chefi]]

## Sources
- [[wiki/sources/chefi-build-priorities]]
- [[wiki/sources/chefi-current-build]]
