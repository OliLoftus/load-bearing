---
type: fleeting
tags: []
created: 2026-09-28
---

# Terraform Patterns

Raw dump from an SDD repo scan - not yet split/triaged into atomic notes.

- Terraform plan-time vs apply-time values
- `for_each`/`count` gated on plan-time values only
- `terraform validate` vs `terraform plan`
- Config-driven `for_each` as the single control surface
- Resource cardinality under `for_each`
- Nullable, defaultless module inputs
- Terraform `nullable = false`
- Terraform cross-variable validation
- Terraform `lifecycle.precondition`
- Terraform `check` blocks
- Named locals that encode decisions
- Thresholds derived in locals
- Terraform `compact()` vs `distinct()`
- An empty IAM `Resource` failing at apply
- Failing early at plan time when a dependency is missing
- Placeholder defaults that break plans
