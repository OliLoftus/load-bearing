---
type: permanent
tags: [identity]
created: 2026-10-16
---

# OAuth

An authorization protocol for how users let a third-party app access their
resources, without exposing their actual credentials to that app.

Uses a trusted intermediary (the actual service) to issue a scoped,
revocable token as a substitute for the real credentials - a specific
application of [[Least Privilege]] (scoped), [[Ephemeral Credentials]]
(revocable/expiring), and [[Tokenization]] (a substitute, not a restricted
copy of the original).

Four roles: Resource Owner (the user), Client (the third-party app),
Authorization Server (issues tokens, handles login/consent), Resource
Server (holds the data, checks tokens).

The Authorization Code flow: the client redirects to the Authorization
Server's own login/consent page (never its own form, so it never sees the
real password) → user logs in and consents → Authorization Server
redirects back with a short-lived, single-use authorization code (not the
access token itself, since this redirect travels through the browser's
URL - too risky a channel for the real token) → client exchanges that code
for an access token via a direct, secure server-to-server request,
typically proving its identity with a client secret → client uses the
access token against the Resource Server.

OAuth proves what a token is allowed to do (scope), not who's holding it -
that's exactly the gap OpenID Connect fills on top of it.

See [[PKCE Flow]] for how clients with no secret to prove their identity
(mobile apps, single-page apps) still protect the code-exchange step.
