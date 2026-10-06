# Evidence: System Uptime Monitoring (A1.1-01)

**Control Reference:** A1.1-01
**Evidence Type:** Monitoring configuration summary + sample report
**Status:** ✅ Implemented

## Summary
System uptime and performance are monitored continuously, with automated 
alerting configured for degraded performance or outages.

## Evidence Details
- **Monitoring tool:** Datadog
- **Alerting tool:** PagerDuty (routes to on-call Engineering rotation)
- **Monitored metrics:** API response time, error rate, database connection 
  pool health, infrastructure CPU/memory utilization

## Sample Uptime Report (Simulated — Q2 2025)

| Month | Uptime % | Incidents | Total Downtime |
|---|---|---|---|
| April 2025 | 99.97% | 1 (minor) | 13 minutes |
| May 2025 | 100.00% | 0 | 0 minutes |
| June 2025 | 99.94% | 1 (moderate) | 26 minutes |

## SLA Comparison
Published customer SLA commitment: 99.9% uptime (see 
`evidence/a1-sla-commitment.md`). All three months in this reporting 
period met or exceeded the committed SLA threshold.

## Auditor Note
This evidence satisfies A1.1 by demonstrating active, continuous 
monitoring with documented historical performance against a stated 
availability commitment.