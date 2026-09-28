---
type: permanent
tags: [messaging]
created: 2026-09-28
---

# At Least Once Delivery

A delivery guarantee: a message might get sent/delivered more than once, but
at least one delivery is guaranteed to land - never zero.

[[SQS Visibility Timeout]] is what produces this in SQS specifically: if a
consumer processes a message but crashes or is too slow to delete it before
the timeout expires, the message is redelivered - even though it was
already handled once. The guarantee is reliability (nothing is silently
lost); the cost is that whatever receives the message has to cope with
getting the same one more than once, which is exactly what
[[Idempotency]] is for.
