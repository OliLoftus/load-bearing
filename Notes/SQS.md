---
type: permanent
tags: [aws, messaging]
created: 2026-09-28
---

# SQS

AWS's Simple Queue Service - an [[Asynchronous Communication|asynchronous]]
queue system that holds messages until a consumer is ready and explicitly
asks for them (polls), rather than the message being pushed the moment it
arrives.

The reason to put a queue between two services instead of calling directly:
if the receiving service is down or slow, a direct call just becomes an
error the caller has to handle right then. With a queue, the message waits
and can be retried - the sender's success doesn't depend on the receiver's
current availability.
