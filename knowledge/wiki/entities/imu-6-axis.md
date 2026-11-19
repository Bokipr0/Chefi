---
id: imu-6-axis
title: "Motion sensor (6-axis IMU)"
type: entity
meta-sector: technical
class: "Sensing and audio"
kind: fact
created: 2026-11-19
updated: 2026-11-19
status: seed
confidence: low
weight: 20
tags: [topic/sensing, kind/hardware, sector/technical, class/sensing-and-audio]
sources:
  - "[[wiki/sources/chefi-build-priorities]]"
  - "[[wiki/sources/chefi-current-build]]"
relations:
  - rel: part-of
    to: "[[wiki/entities/chefi]]"
    why: The IMU is listed as an owned sensor of the prototype.
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

# Motion sensor (6-axis IMU)

6-axis IMU breakout, owned. The model is to be verified (earlier list: MPU-6050 or alternatives). P2 in the build sheet.
Purpose: detect movement. Limited benefit on a stationary bench.

## Connections
- part-of [[wiki/entities/chefi]]

## Sources
- [[wiki/sources/chefi-build-priorities]]
- [[wiki/sources/chefi-current-build]]
