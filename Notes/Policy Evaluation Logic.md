---
type: permanent
tags: [aws, iam]
created: 2026-09-23
---

# Policy Evaluation Logic

Start with implicit deny, then check for explicit deny - an explicit deny
always wins over any allow, no matter where it comes from.

If nothing explicitly allows the action, nothing happens - the request is
denied. Absence of a deny does not mean allowed; you need an explicit allow
for the action to go through at all.

This is part of the permission policy, not the trust policy - it governs what
an already-assumed [[IAM Roles|role]] (or user) can actually do, separate from
who's allowed to assume the role in the first place.
