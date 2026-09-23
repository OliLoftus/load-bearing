---
type: principle
tags: [security]
created: 2026-09-23
---

# Least Privilege

Grant only the permissions needed to do a specific task, nothing more, and
narrow that grant to the smallest scope (resource, action, condition, time) that
still works.

The reasoning isn't "fewer permissions is safer" in the abstract - it's that
every unused permission is pure downside: it can't help the task succeed, it can
only be the thing an attacker or a mistake uses later. There's no upside to hold
against that risk, so the grant should shrink until removing anything further
would break the task.

Shows up anywhere an identity or process is granted access:

- [[IAM Roles]] - scope a role's permission policy to exactly what its use case
  needs, not a broad managed policy that happens to cover it.
