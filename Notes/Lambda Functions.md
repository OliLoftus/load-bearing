---
type: permanent
tags: [aws, serverless]
created: 2026-09-23
---

# Lambda Functions

Your code, zipped up with its dependencies, that AWS runs on demand rather
than you provisioning or managing servers for it.

Permissions come from an **execution role** - an [[IAM Roles|IAM role]] with
its own trust policy (here, allowing the Lambda service to assume it) and
permission policies (what it's actually allowed to do once running),
evaluated the same way as any other role via [[Policy Evaluation Logic]].

Triggered one of three ways:

- Manually (direct invoke)
- As part of another process - API Gateway, Step Functions, or called by
  another service
- On a schedule, via an EventBridge rule
