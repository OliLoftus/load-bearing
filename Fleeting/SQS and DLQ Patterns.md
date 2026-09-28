---
type: fleeting
tags: []
created: 2026-09-28
---

# SQS and DLQ Patterns

Raw dump from an SDD repo scan - not yet split/triaged into atomic notes.

- SQS `ApproximateAgeOfOldestMessage`
- Source-queue alarms firing before DLQ alarms
- Thresholds for queues someone else consumes
- SQS message retention defaults
- DLQs and Event Source Mappings (one per source queue)
- DLQ replay/recovery
- Tolerant reader for downstream field names
