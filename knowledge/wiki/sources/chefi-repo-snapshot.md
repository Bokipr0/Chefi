---
id: chefi-repo-snapshot
title: "Chefi repo snapshot"
type: source
meta-sector: technical
class: "Build"
kind: fact
created: 2026-11-19
updated: 2026-11-19
status: stable
confidence: high
weight: 30
tags: [project/chefi, kind/repo, sector/technical, class/build]
sources: []
relations:
  - rel: raises
    to: "[[wiki/questions/which-ai-service]]"
    why: README lists the AI service as not yet implemented; the choice is open.
    basis: explicit
    confidence: high
    found: 2026-11-19
  - rel: raises
    to: "[[wiki/questions/judge-doneness]]"
    why: README lists camera support as planned; the recognition target is not specified.
    basis: explicit
    confidence: high
    found: 2026-11-19
---

# Chefi repo snapshot

Snapshot of https://github.com/Bokipr0/Chefi at commit 6e36209, taken as three files in `raw/`:
`chefi-readme-snapshot.md`, `chefi-platformio-ini-snapshot.ini`, `chefi-main-cpp-snapshot.cpp`.

## Key claims
- Chefi is an early PlatformIO project for a compact cooking assistant prototype. The README says so explicitly.
- Target board: `dfrobot_firebeetle2_esp32s3`, Arduino framework, espressif32 platform.
- Camera, microphone, speaker, AI service and mounting are **not implemented**. The README states this.
- `src/main.cpp` is the PlatformIO starter template. `setup()` and `loop()` are empty. `myFunction(int, int)` returns the sum of its two arguments. No cooking logic exists yet.

## Quotes
- README: "Camera, microphone, speaker, AI service, and mounting features have not yet been implemented."

## Connections
- **raises** [[wiki/questions/which-ai-service]] — AI service unimplemented.
- **raises** [[wiki/questions/judge-doneness]] — camera planned, target unspecified.

## Open questions
- [[wiki/questions/which-ai-service]]
- [[wiki/questions/judge-doneness]]

## Sources
- raw/chefi-readme-snapshot.md
- raw/chefi-platformio-ini-snapshot.ini
- raw/chefi-main-cpp-snapshot.cpp
