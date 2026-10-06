# Evidence: Data Classification Policy (C1.1-01)

**Control Reference:** C1.1-01
**Evidence Type:** Policy document summary
**Status:** ⚠️ Partially Implemented — see gap note below

## Summary
A data classification policy exists defining sensitivity tiers for 
customer and company data, with corresponding handling requirements per tier.

## Evidence Details
- **Document:** Data Classification Policy v1.4
- **Owner:** CISO
- **Last updated:** January 2025

## Classification Tiers (Policy Definition)

| Tier | Definition | Example | Handling Requirement |
|---|---|---|---|
| Restricted | Highly sensitive financial/customer data | Bank account details, financial statements | Encrypted at rest + in transit, access logged |
| Confidential | Internal business data | Internal reports, employee records | Access restricted by role |
| Internal | General internal use | Internal wiki documentation | Employee access only |
| Public | No restriction | Marketing materials | No restriction |

## Gap Identified
While the policy clearly defines classification tiers, **actual labeling 
of data assets in production systems (databases, S3 buckets) is 
inconsistent.** A sample review of S3 bucket metadata found that only 
roughly 60% of buckets had classification tags applied, despite the 
policy requiring 100% coverage.

## Auditor Note
This control is marked **Partially Implemented** because the policy is 
well-defined, but enforcement/application in production is incomplete. 
See `docs/02-gap-analysis.md`, Gap 10, for remediation plan.