---
id: camera-ov2660
title: "Camera (OV2660)"
type: entity
meta-sector: technical
class: "Sensing and audio"
kind: fact
created: 2026-11-19
updated: 2026-11-19
status: seed
confidence: medium
weight: 40
tags: [topic/sensing, kind/hardware, sector/technical, class/sensing-and-audio]
sources:
  - "[[wiki/sources/chefi-build-priorities]]"
  - "[[wiki/sources/chefi-current-build]]"
relations:
  - rel: part-of
    to: "[[wiki/entities/chefi]]"
    why: The build sheet lists the camera as part of the prototype.
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

# Camera (OV2660)

Reported by Lior as an OV2660 camera; P0 in the build sheet. Purpose: observe changes, capturing ingredients, tools and actions.
The sensor label and connector are not yet verified. The current build note says not to substitute OV2640 or OV3660 silently.

## Connections
- part-of [[wiki/entities/chefi]]

## Sources
- [[wiki/sources/chefi-build-priorities]]
- [[wiki/sources/chefi-current-build]]
