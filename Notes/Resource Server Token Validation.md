---
type: permanent
tags: [identity]
created: 2026-10-26
---

# Resource Server Token Validation

The resource server's check, on every request, that an access token is
genuine, current, meant for it, and allows the requested action, before it
serves anything. It is a step in [[OAuth]] done by the resource server, not
the client.

The resource server never saw the login or the client authentication, so
all it has is a string in a header that anyone could send. It has to ask
one question: did the auth server really issue this, for me, for this?
There are two ways to answer it:

- A signed [[JWT]]: verify the signature, issuer, audience, expiry and scope
  itself, with no call back.
- An opaque token: ask the auth server's
  [[Token Introspection|introspection endpoint]] whether it is still active
  and what it allows.

An invalid or missing token gets a 401, a genuine token without enough scope
gets a 403. Tokens are bearer credentials, so holding a valid one is enough,
which is why short expiry matters ([[Ephemeral Credentials]]). Audience and
scope are [[Least Privilege]] applied to which service and which action, and
the token is the [[Tokenization]] substitute for the real credentials.

Seen in [[Client Credentials Flow]] at step 5. A specific instance of
[[Verify at the Point of Use]].
