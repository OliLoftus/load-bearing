---
type: principle
tags: [security]
created: 2026-10-26
---

# Proof of Possession

A claimed identity proves nothing. It has to be backed by something only
the real party holds, and that thing must be kept out of the places the
claim travels.

A name badge is a claim anyone can write; a passport or key is the proof.
A `client_id` is the claim, the `client_secret` is the proof. In PKCE the
challenge is the claim and the verifier is the proof.

Different from [[Least Privilege]], [[Ephemeral Credentials]] and
[[Tokenization]]: those limit what a credential can do, how long it lasts,
or whether the real one is exposed. This one is about whether the caller
really is who it says.

## Shows up in

- [[Client Authentication]]
- [[PKCE Flow]]
