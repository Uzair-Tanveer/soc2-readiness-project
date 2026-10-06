# Evidence: Business Continuity & Disaster Recovery Plan (CC9.1-01)

**Control Reference:** CC9.1-01
**Evidence Type:** Policy document summary
**Status:** ✅ Implemented

## Summary
NorthLedger maintains a documented Business Continuity and Disaster 
Recovery (BC/DR) plan defining recovery objectives and failover procedures 
in the event of a regional infrastructure outage.

## Evidence Details
- **Document:** BC/DR Plan v2.3
- **Owner:** COO (business continuity), Engineering Manager (technical failover)
- **Last updated:** February 2025

## Recovery Objectives

| Metric | Target | Definition |
|---|---|---|
| RTO (Recovery Time Objective) | 4 hours | Maximum acceptable time to restore service after an outage |
| RPO (Recovery Point Objective) | 1 hour | Maximum acceptable data loss, measured in time |

## Failover Architecture
- Primary region: AWS us-east-1
- Standby region: AWS us-west-2
- Database replication: Continuous (PostgreSQL RDS cross-region read replica)
- Storage replication: S3 cross-region replication (near real-time)

## Plan Scope
- Identifies critical systems requiring failover (web application, API, database)
- Defines roles and responsibilities during a declared disaster event
- Includes customer communication triggers during extended outages

## Auditor Note
This evidence satisfies CC9.1 by demonstrating a documented plan with 
specific, measurable recovery targets. However, these targets have not 
yet been validated through an actual failover simulation — see 
`docs/02-gap-analysis.md`, Gap 9 (control CC9.1-02), for the related gap 
and remediation plan.