---
type: fleeting
tags: []
created: 2026-09-28
---

# PagerDuty and Alerting

Raw dump from an SDD repo scan - not yet split/triaged into atomic notes.

- Page-tier vs notify-tier alerting
- Actionability/irreversibility test for alert severity
- P1-P4 severity mapping
- Runbooks as the on-call's only context
- Runbook URLs in `alarm_description`
- Per-environment alerting posture
- PagerDuty Amazon CloudWatch integration vs Events API v2
- PagerDuty per-integration URL vs `routing_key` payload
- PagerDuty urgency defaults
- PagerDuty `service_incident_urgency_rules`
- PagerDuty orchestration rules
- Severity set by matching a substring of the alarm name
- PagerDuty-Slack workspace authorisation
- Out-of-hours escalation routing
- SNS HTTPS subscriptions and subscription confirmation
