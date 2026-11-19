---
id: current-sensor-ina219
title: "Power sensor (INA219)"
type: entity
meta-sector: technical
class: "Sensing and audio"
kind: fact
created: 2026-11-19
updated: 2026-11-19
status: seed
confidence: high
weight: 25
tags: [topic/power, kind/hardware, sector/technical, class/sensing-and-audio]
sources:
  - "[[wiki/sources/chefi-build-priorities]]"
  - "[[wiki/sources/chefi-current-build]]"
relations:
  - rel: part-of
    to: "[[wiki/entities/chefi]]"
    why: The power sensor is a test item of the prototype.
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

# Power sensor (INA219)

INA219 current-sensor breakout, owned. P1 test item.
Purpose: measure power demand and compare workloads. It does not provide automatic protection.

## Connections
- part-of [[wiki/entities/chefi]]

## Sources
- [[wiki/sources/chefi-build-priorities]]
- [[wiki/sources/chefi-current-build]]
