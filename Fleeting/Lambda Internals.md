---
type: fleeting
tags: []
created: 2026-09-28
---

# Lambda Internals

Raw dump from an SDD repo scan - not yet split/triaged into atomic notes.

- Lambda layers
- Pinned layer ARN vs a layer version lookup
- Lambda arm64/runtime compatibility
- Dynatrace OneAgent Lambda layer
- Checking that a Lambda extension fails open
- Structured logging as single-line JSON
- Event discriminator field in logs
- Key collisions from object spread order
- Testing the real handler's env-var reads
- Mocking AWS SDK v3 `prototype.send`
- Deterministic time in tests
