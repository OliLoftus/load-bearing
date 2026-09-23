---
type: principle
tags: [security]
created: 2026-09-23
---

# Ephemeral Credentials

If a credential expires on its own, the window for it to be abused if leaked
is smaller - it self-limits rather than relying on someone noticing and
manually rotating it.

This narrows *how long* a credential can be used, as opposed to
[[Least Privilege]] narrowing *what* it can be used for - two different axes
of the same goal: shrink exposure.

## Shows up in

- [[IAM Roles]] - `AssumeRole` returns temporary credentials rather than a
  long-lived access key.
