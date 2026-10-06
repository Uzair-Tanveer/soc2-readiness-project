# Evidence: SIEM Monitoring Configuration (CC4.1-01)

**Control Reference:** CC4.1-01
**Evidence Type:** System configuration summary + alert sample

## Summary
Continuous security monitoring is implemented via AWS GuardDuty, with 
centralized log aggregation and alerting configured for anomalous activity.

## Evidence Details
- **Tooling:** AWS GuardDuty (threat detection) + CloudWatch Logs (centralized logging)
- **Alert routing:** PagerDuty, escalating to on-call Security Analyst
- **Monitored activity:** Unusual API calls, unauthorized access attempts, 
  port scanning, IAM privilege escalation attempts

## Sample Alert Log (Simulated)

| Timestamp | Severity | Finding | Response Time |
|---|---|---|---|
| 2025-03-11 02:14 UTC | Medium | Unusual IAM API call pattern from new region | 18 min |
| 2025-04-02 14:52 UTC | Low | Port scan detected against non-production subnet | 42 min |
| 2025-05-19 09:03 UTC | High | Failed login brute-force pattern on admin account | 6 min |

## Auditor Note
Response times demonstrate active monitoring and triage, satisfying the 
detective control requirement under CC4.1.