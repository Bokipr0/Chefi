---
id: chefi
title: "Chefi"
type: entity
meta-sector: design
class: "Product"
kind: fact
created: 2026-11-19
updated: 2026-11-19
status: seed
confidence: high
weight: 85
tags: [project/chefi, kind/product, sector/design, class/product]
sources: ["[[wiki/sources/chefi-repo-snapshot]]"]
relations:
  - rel: has-part
    to: "[[wiki/entities/firebeetle-2-board]]"
    why: The README configures the firmware for this board, which is the prototype's compute hardware.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: raises
    to: "[[wiki/questions/which-ai-service]]"
    why: The planned AI service is named in the README but not chosen.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: raises
    to: "[[wiki/questions/judge-doneness]]"
    why: Camera input is planned; the doneness target is not specified.
    basis: inferred
    confidence: medium
    found: 2026-11-19
  - rel: has-part
    to: "[[wiki/entities/camera-ov2660]]"
    why: The build sheet lists camera (ov2660) as part of the prototype.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: has-part
    to: "[[wiki/entities/microphone-inmp441]]"
    why: The build sheet lists microphone as part of the prototype.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: has-part
    to: "[[wiki/entities/speaker-max98357a]]"
    why: The build sheet lists speaker amplifier as part of the prototype.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: has-part
    to: "[[wiki/entities/imu-6-axis]]"
    why: The build sheet lists motion sensor as part of the prototype.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: has-part
    to: "[[wiki/entities/current-sensor-ina219]]"
    why: The build sheet lists power sensor as part of the prototype.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: has-part
    to: "[[wiki/entities/server-backend]]"
    why: The build sheet lists server and processing as part of the prototype.
    basis: explicit
    confidence: high
    found: 2026-11-19
---

# Chefi

A compact cooking assistant prototype. Early stage: the repo holds board configuration and starter firmware only.

## Detail
- Planned features per the README: camera, microphone, speaker, AI service, mounting.
- Built on an ESP32-S3 board. See [[wiki/entities/firebeetle-2-board]].
- Status: none of the planned features are implemented yet.

## Connections
- **has-part** [[wiki/entities/camera-ov2660]] — listed in the build sheet.
- **has-part** [[wiki/entities/microphone-inmp441]] — listed in the build sheet.
- **has-part** [[wiki/entities/speaker-max98357a]] — listed in the build sheet.
- **has-part** [[wiki/entities/imu-6-axis]] — listed in the build sheet.
- **has-part** [[wiki/entities/current-sensor-ina219]] — listed in the build sheet.
- **has-part** [[wiki/entities/server-backend]] — listed in the build sheet.
- **has-part** [[wiki/entities/firebeetle-2-board]] — the prototype's compute board.
- **raises** [[wiki/questions/which-ai-service]] — AI service undecided.
- **raises** [[wiki/questions/judge-doneness]] — camera target undefined (inferred: the camera is planned, so the question follows).

## Open questions
- [[wiki/questions/which-ai-service]]
- [[wiki/questions/judge-doneness]]

## Sources
- [[wiki/sources/chefi-repo-snapshot]]
