---
id: chefi-build-priorities
title: "Chefi build priorities (17 Nov 2026)"
type: source
meta-sector: technical
class: "Build"
kind: fact
created: 2026-11-19
updated: 2026-11-19
status: stable
confidence: high
weight: 30
tags: [topic/build, kind/plan, sector/technical, class/build]
sources: []
relations:
  - rel: yields
    to: "[[wiki/entities/camera-ov2660]]"
    why: The build sheet lists the camera as P0, owned, reported OV2660.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: yields
    to: "[[wiki/entities/microphone-inmp441]]"
    why: The build sheet lists the microphone as P1, owned.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: yields
    to: "[[wiki/entities/speaker-max98357a]]"
    why: The build sheet lists the speaker amplifier as P1, owned.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: yields
    to: "[[wiki/entities/imu-6-axis]]"
    why: The build sheet lists the IMU as P2, model to verify.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: yields
    to: "[[wiki/entities/current-sensor-ina219]]"
    why: The build sheet lists the INA219 as a P1 test item.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: yields
    to: "[[wiki/entities/server-backend]]"
    why: The build sheet lists the server and processing backend as P0, to configure.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: yields
    to: "[[wiki/questions/battery-in-scope]]"
    why: The build sheet lists a solid-state battery as P1 planned, not owned.
    basis: explicit
    confidence: high
    found: 2026-11-19
---

# Chefi build priorities (17 Nov 2026)

Build priorities for the proof of concept. Core goal: remember cooking progress and available ingredients, then give useful, context-aware advice.
Priorities: P0 essential to the core demo; P1 add next; P2 optimise later; P3 future wearable.
Demo: show an onion and butter, remove the butter from view, then chop the onion. Chefi should recall the butter, track the onion state, suggest a next step, and keep a user correction.

## Connections
- [[wiki/entities/camera-ov2660]] — P0
- [[wiki/entities/microphone-inmp441]] — P1
- [[wiki/entities/speaker-max98357a]] — P1
- [[wiki/entities/imu-6-axis]] — P2
- [[wiki/entities/current-sensor-ina219]] — P1 test
- [[wiki/entities/server-backend]] — P0
- [[wiki/questions/battery-in-scope]] — planned, not owned

## Sources
- [[wiki/sources/chefi-build-priorities]]
