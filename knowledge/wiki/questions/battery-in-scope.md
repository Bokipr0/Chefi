---
id: battery-in-scope
title: "Is the battery in scope?"
type: question
meta-sector: technical
class: "Build"
kind: claim
created: 2026-11-19
updated: 2026-11-19
status: seed
confidence: low
weight: 35
tags: [topic/power, sector/technical, class/build]
sources:
  - "[[wiki/sources/chefi-current-build]]"
  - "[[wiki/sources/chefi-build-priorities]]"
relations:
  - rel: raised-by
    to: "[[wiki/sources/chefi-current-build]]"
    why: The current build note defers batteries and charging.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: raised-by
    to: "[[wiki/sources/chefi-build-priorities]]"
    why: The build sheet lists a solid-state battery as P1, planned, not owned.
    basis: explicit
    confidence: high
    found: 2026-11-19
---

# Is the battery in scope?

The two build documents disagree. The build sheet (17 Nov 2026) lists a solid-state battery as P1 for untethered operation. The current build note (14 Nov 2026) says the proof of concept is stationary and batteries, charging and motors are deferred.
Decide before wiring the power path.

## Connections
- raised-by [[wiki/sources/chefi-current-build]]
- raised-by [[wiki/sources/chefi-build-priorities]]

## Sources
- [[wiki/sources/chefi-current-build]]
- [[wiki/sources/chefi-build-priorities]]
