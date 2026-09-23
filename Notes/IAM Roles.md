---
type: permanent
tags: [aws, iam]
created: 2026-09-23
---

# IAM Roles

An IAM role is an identity with permission policies attached, but no long-term
credentials - it's assumed by a trusted principal (a user, service, or another
account) for a temporary session, rather than logged into directly.

- Assuming a role returns temporary credentials (`AssumeRole`), not a
  long-lived password/key - see [[Ephemeral Credentials]].
- Who can assume the role is controlled by its **trust policy**; what the role can
  do once assumed is controlled by its **permission policies** - two separate
  documents, easy to conflate.
- Whether a specific action is actually allowed once both policies are in play
  comes down to [[Policy Evaluation Logic]].
- Roles are the mechanism for cross-account access and for giving AWS services
  (e.g. an EC2 instance, a Lambda function) permissions without embedding static
  credentials - a direct application of [[Least Privilege]].
