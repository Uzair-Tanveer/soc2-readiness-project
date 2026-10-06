# Evidence: Incident Response Plan (CC7.2-01)

**Control Reference:** CC7.2-01
**Evidence Type:** Policy document summary
**Status:** ✅ Implemented

## Summary
NorthLedger Technologies maintains a formal, documented incident response 
plan that defines severity classification, escalation paths, and response 
procedures for security incidents.

## Evidence Details
- **Document:** Incident Response Plan v4.0
- **Last updated:** March 2025
- **Owner:** CISO

## Severity Classification (Excerpt)

| Severity | Definition | Example | Response Time Target |
|---|---|---|---|
| Critical | Active breach or data exposure | Unauthorized access to customer database | 15 minutes |
| High | Significant service disruption or suspected compromise | Credential compromise detected | 1 hour |
| Medium | Isolated anomaly, no confirmed impact | Suspicious login flagged by SIEM | 4 hours |
| Low | Minor policy deviation, no security impact | Expired certificate on non-production system | 24 hours |

## Escalation Path
1. On-call Security Analyst triages alert
2. CISO notified for High/Critical severity within response time target
3. COO and Legal notified if customer data is confirmed impacted
4. Customer notification process initiated per `evidence/cc2-incident-comms-plan.md`

## Auditor Note
This evidence satisfies CC7.2 by demonstrating a documented, role-assigned 
response process with defined severity tiers and response time commitments. 
Note: the plan's operating effectiveness has not yet been validated via 
tabletop exercise — see `docs/02-gap-analysis.md`, Gap 7 (control CC7.3-01).