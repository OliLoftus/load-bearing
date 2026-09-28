---
type: principle
tags: [software]
created: 2026-09-28
---

# Leasing

A time-bound, exclusive grant that automatically expires and reverts if the
holder doesn't finish or renew it in time - the thing becomes available
again, so failure is assumed rather than requiring an explicit failure
report, and it can be retried rather than block forever.

Same shape shows up outside software too: a restaurant holding your
reserved table for a grace period, a library holding a requested book on a
shelf for a set number of days - both revert to available if not claimed
in time.

Mechanically similar to [[Ephemeral Credentials]] (something time-bound
that expires automatically), but a different motivation: that one bounds
security exposure, this one turns silence into an automatic failure signal
so recovery doesn't need an explicit report.

## Shows up in

- [[SQS Visibility Timeout]]
