---
type: fleeting
tags: []
created: 2026-09-23
---

# Foundations Backlog

Gaps `/learning-foundations` has found but that haven't been learned/written up
yet. A plain checklist, not generated note content - ask Claude to tackle any
line here directly, any time, formal command not required.

- [ ] Actionable alerting - synthesised from SDD repo scan, see [[CloudWatch Alarms and Metrics]] and PagerDuty/alerting captures
- [ ] Silent vs loud failure detection - synthesised from SDD repo scan, see [[CloudWatch Alarms and Metrics]]
- [ ] Fail as early in the pipeline as possible - synthesised from SDD repo scan, Terraform plan-time captures
- [ ] Config as the single control surface - synthesised from SDD repo scan, Terraform captures
- [ ] Design data/metrics around the real access pattern - synthesised from SDD repo scan, CloudWatch/DynamoDB captures
- [ ] Be liberal in what you accept from something you don't control - synthesised from SDD repo scan, SQS/DLQ captures
- [ ] Use each tool only for what it's actually good at - synthesised from SDD repo scan, Dynatrace/PagerDuty captures
- [ ] Structured, machine-parseable output over ad-hoc text - synthesised from SDD repo scan; likely the same idea as [[Metadata Separation]], to confirm
- [ ] Server-side proof-of-possession check (hash the verifier, compare to the stored challenge) - from /socratic-visualizer on PKCE, see [[PKCE Flow]]
- [ ] Front channel vs back channel (why the auth code travels through the exposed browser redirect) - from /socratic-visualizer on PKCE, see [[PKCE Flow]]
- [ ] Registry as the distribution point (push and pull move images between machines) - from /socratic-visualizer on Container Image, see [[Container Image]]
- [ ] Image vs container (image is the read-only template, run starts a container from it, Dockerfile only matters at build time) - from /socratic-visualizer on Container Image, see [[Container Image]]
