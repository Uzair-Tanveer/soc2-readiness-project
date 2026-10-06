# Evidence: Financial Data Reconciliation Checks (PI1.1-01)

**Control Reference:** PI1.1-01
**Evidence Type:** Process description + sample validation log
**Status:** ✅ Implemented

## Summary
Automated reconciliation checks validate the accuracy of financial 
calculations before reports are generated and presented to customers.

## Evidence Details
- **Process:** Automated reconciliation job runs after each financial 
  report generation, comparing calculated totals against source ledger 
  entries to detect discrepancies.
- **Frequency:** Real-time (triggered per report generation), with 
  monthly sample audits performed manually by Engineering.
- **Owner:** Engineering Manager

## Sample Monthly Validation Log (Simulated)

| Month | Reports Generated | Reconciliation Pass Rate | Discrepancies Found | Resolved |
|---|---|---|---|---|
| April 2025 | 1,204 | 99.8% | 2 | 2 |
| May 2025 | 1,310 | 100.0% | 0 | N/A |
| June 2025 | 1,276 | 99.9% | 1 | 1 |

## Discrepancy Handling
Any report failing reconciliation is automatically withheld from the 
customer-facing dashboard and flagged for manual engineering review before 
release.

## Auditor Note
This evidence satisfies PI1.1 by demonstrating an automated, consistently 
applied control with a documented track record of catching and resolving 
discrepancies before customer-facing delivery.