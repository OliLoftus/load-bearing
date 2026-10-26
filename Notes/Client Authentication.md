---
type: permanent
tags: [identity]
created: 2026-10-26
---

# Client Authentication

A client proving its identity to the authorization server at the token
endpoint, using a public `client_id` plus a `client_secret` that only the
client and the server know, sent over the direct back channel. It proves
which application is calling, not which person is using it.

In [[Client Credentials Flow]] there is no user, so this is the only check.
Without the secret, anyone who knows the public ID could ask for a token
and get a real one carrying that client's access.

It only works for confidential clients that can keep a secret.
[[PKCE Flow]] covers the clients that cannot. A specific instance of
[[Proof of Possession]].
