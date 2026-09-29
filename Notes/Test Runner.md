---
type: permanent
tags: [testing]
created: 2026-09-29
---

# Test Runner

A tool that's invoked to act as the orchestrator for your tests - it sits
above your actual test code, rather than being part of it.

Test code alone is just a pile of independent functions describing what
should happen. It can't discover every test file, keep one test's leftover
state from leaking into another, survive a crash without taking down the
whole batch, or produce a single pass/fail answer across potentially
thousands of tests. Given that a CI system needs exactly that - one
reliable answer from many independently-written pieces of test code -
something has to sit above the test code doing discovery, execution,
isolation, and reporting. That's the runner's job.

For example: it launches a fresh, [[Isolation|isolated]] [[Headless
Browser]] per test by default.
