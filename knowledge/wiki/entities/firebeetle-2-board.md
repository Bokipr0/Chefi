---
id: firebeetle-2-board
title: "FireBeetle 2 board"
type: entity
meta-sector: technical
class: "Build"
kind: fact
created: 2026-11-19
updated: 2026-11-19
status: seed
confidence: high
weight: 40
tags: [kind/hardware, platform/esp32-s3, sector/technical, class/build]
sources: ["[[wiki/sources/chefi-repo-snapshot]]"]
relations:
  - rel: part-of
    to: "[[wiki/entities/chefi]]"
    why: The firmware targets this board as the prototype's controller.
    basis: explicit
    confidence: high
    found: 2026-11-19
---

# FireBeetle 2 board

The development board named in Chefi's `platformio.ini` (`board = dfrobot_firebeetle2_esp32s3`). It runs the Arduino framework on the espressif32 platform.

## Detail
- Board ID used by PlatformIO for the build target.
- Its camera, microphone and speaker interfaces are not covered by the snapshot. Whether it can drive the planned peripherals is unverified.

## Connections
- **part-of** [[wiki/entities/chefi]] — the controller board for the prototype.

## Sources
- [[wiki/sources/chefi-repo-snapshot]]
