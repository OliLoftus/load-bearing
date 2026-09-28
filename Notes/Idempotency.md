---
type: principle
tags: [software]
created: 2026-09-28
---

# Idempotency

An operation designed so that if it happens more than once, the outcome is
the same as if it happened once - repeating it doesn't repeat the effect
(charging a card twice, double-submitting a form).

Not just a plain "if not done, do it" check - that has a race condition,
since two duplicate attempts can both pass the check before either marks
itself done. It needs an **idempotency key** (a unique ID for that specific
operation) and an atomic check-and-mark step, not two separate ones - e.g. a
database write with a uniqueness constraint, or a conditional write like
[[DynamoDB Conditional Writes|DynamoDB's attribute_not_exists]]. If the
write succeeds, proceed; if it fails because the key already exists, it's a
duplicate - skip straight to the stored result from the first attempt.

## Shows up in

- [[At Least Once Delivery]] - the reason this is needed at all: reliable
  delivery can't promise exactly-once, so whatever receives the message has
  to be safe against receiving it twice.
