---
id: chefi-current-build
title: "Chefi current build (14 Nov 2026)"
type: source
meta-sector: technical
class: "Build"
kind: fact
created: 2026-11-19
updated: 2026-11-19
status: stable
confidence: high
weight: 30
tags: [topic/build, kind/status, sector/technical, class/build]
sources: []
relations:
  - rel: yields
    to: "[[wiki/questions/battery-in-scope]]"
    why: The current build note says batteries and charging are deferred.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: yields
    to: "[[wiki/entities/camera-ov2660]]"
    why: The current build note records the camera as reported OV2660, unverified.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: yields
    to: "[[wiki/entities/firebeetle-2-board]]"
    why: The current build note records the board as DFR0975-U, 16 MB flash, 8 MB PSRAM.
    basis: explicit
    confidence: high
    found: 2026-11-19
---

# Chefi current build (14 Nov 2026)

Stationary, externally powered sensing, audio and Wi-Fi proof of concept. Batteries, charging, clamp actuation and servos are deferred.
Owned: FireBeetle 2 ESP32-S3-U, camera reported as OV2660, INMP441 microphone, MAX98357A amplifier, 8-ohm speaker, 6-axis IMU, INA219 current sensor.
Not owned or deferred: LiPo battery, TP4056 charger, MT3608 boost, N20 motor and servos.
The camera name is user-reported. Do not silently substitute OV2640 or OV3660.

## Connections
- [[wiki/entities/camera-ov2660]] — reported, unverified
- [[wiki/questions/battery-in-scope]] — deferred here, planned in the priorities sheet

## Sources
- [[wiki/sources/chefi-current-build]]
