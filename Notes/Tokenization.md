---
type: principle
tags: [security]
created: 2026-10-16
---

# Tokenization

Credential substitution: issuing a separate substitute credential that
never exposes the real one, rather than trying to make the real credential
itself scoped or restricted.

A valet key isn't a restricted copy of your house key - it's a wholly
different key. Apple Pay doesn't send merchants your actual card number -
it sends a device-specific substitute. If the substitute leaks, it can be
revoked independently with no effect on the real credential.

Different axis to [[Least Privilege]] (what a credential can do) and
[[Ephemeral Credentials]] (how long it lasts) - this one is about whether
the real secret is ever exposed at all.

## Shows up in

- [[OAuth]] - an access token substitutes for the user's real password.
