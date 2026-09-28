---
type: fleeting
tags: []
created: 2026-09-28
---

# CloudWatch Alarms and Metrics

Raw dump from an SDD repo scan - not yet split/triaged into atomic notes.

- CloudWatch alarm thresholds checked against how often the metric actually publishes
- `treat_missing_data` (`notBreaching` vs `breaching`)
- Choosing a CloudWatch statistic (`Maximum` vs `Sum`)
- Alarms that don't depend on how often the schedule runs
- `period`, `evaluation_periods` and `datapoints_to_alarm`
- CloudWatch's 86400s maximum alarm period
- CloudWatch custom metrics with `PutMetricData`
- Designing metric dimensions
- No PII in metric dimensions
- CloudWatch log metric filters (plain-string vs JSON selector)
- Outcome metrics vs infrastructure-proxy metrics
- Compliance-window / SLO-age metric
- Publishing zero explicitly
- Schedule-liveness alarms
- Watch-the-watcher monitoring and its limits
- Best-effort telemetry that never fails the business operation
- Lambda `Errors` alarms
- Lambda `Throttles` alarms
- Lambda reserved concurrency
- Excluding mocks from on-call
- Testing alarms by lowering the threshold
- Siting-invariant alarm tests
- Testing the exact SLO boundary
- Side effects of widening an alarm's scope
- Alarms declared in the module that owns the resource
