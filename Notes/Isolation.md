---
type: principle
tags: [software]
created: 2026-09-29
---

# Isolation

Giving each independent unit its own state, so altering one doesn't affect
another. If two things share and alter the same thing instead, it affects
both - which breaks the guarantee that each one is independent.

Shows up as a fresh browser context per test ([[Test Runner]]), a
container's own filesystem rather than sharing the host's, each chef in a
shared kitchen getting their own clean workstation rather than reusing
whatever the last one left behind.

## Shows up in

- [[Test Runner]]
