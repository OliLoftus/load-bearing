---
type: fleeting
tags: []
created: 2026-09-28
---

# IAM KMS and Secrets

Raw dump from an SDD repo scan - not yet split/triaged into atomic notes.

- SNS topic encryption with the AWS-managed key vs a customer-managed key
- KMS key policies
- KMS key ARNs vs aliases in IAM `Resource`
- Secrets Manager `kms_key_id` (empty string for AWS-managed keys)
- SSM Parameter Store reads at plan time
- SSM SecureString and `with_decryption`
- AFT account-request custom fields
- Plan-time identity vs Lambda execution role
- Extending IAM through a shared module with dynamic statements
