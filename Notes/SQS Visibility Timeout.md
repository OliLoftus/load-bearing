---
type: permanent
tags: [aws, messaging]
created: 2026-09-28
---

# SQS Visibility Timeout

When a consumer polls and receives a message from [[SQS]], the message isn't
deleted immediately - it becomes invisible to other consumers for a set
period (the visibility timeout, default 30s, max 12 hours), giving the
consumer time to process it.

If the consumer deletes the message before the timeout expires, it's gone
for good. If the timeout completes without the message being deleted (the
consumer crashed, hung, or was just too slow), the message becomes visible
again - failure is assumed rather than requiring an explicit failure
report, so it can be retried rather than block.

A specific instance of [[Leasing]].
