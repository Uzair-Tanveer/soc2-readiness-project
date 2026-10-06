# SOC 2 Readiness Gap Analysis — NorthLedger Technologies

**Reference:** This analysis is derived from `matrix/01-control-matrix.md`
**Assessment period:** January 1, 2025 – June 30, 2025 (simulated)
**Total gaps identified:** 11 (8 Partially Implemented, 3 Not Implemented)

## Risk Rating Methodology

Each gap is rated using a simple **Likelihood x Impact** model:

| Rating | Description |
|---|---|
| 🔴 High | Likely to cause audit finding or material control failure; remediate before audit |
| 🟠 Medium | Moderate risk; should be remediated but unlikely to cause audit failure alone |
| 🟡 Low | Minor process gap; low risk but should be tracked |

---

## Gap 1: Organizational Chart Not Regularly Reviewed (CC1.4-01)

- **Risk Rating:** 🟡 Low
- **Finding:** Organizational chart exists but has not been reviewed/updated in 9 months, risking inaccurate segregation-of-duties mapping.
- **Why this matters:** Auditors use the org chart to validate that segregation of duties claims elsewhere in the matrix (e.g., CC5.3) are actually true. An outdated chart undermines confidence in other controls.
- **Remediation Plan:** Implement a recurring quarterly calendar reminder for the COO to review and formally re-approve the org chart.
- **Owner:** COO
- **Target Completion:** 30 days before audit kickoff

---

## Gap 2: Incident Communication Plan Not Tested (CC2.3-01)

- **Risk Rating:** 🟠 Medium
- **Finding:** A customer/stakeholder incident communication plan exists on paper but has never been exercised.
- **Why this matters:** An untested plan often fails in real execution — unclear escalation paths during an actual incident could delay customer notification, a common point of audit scrutiny and regulatory concern.
- **Remediation Plan:** Conduct a tabletop exercise simulating a customer-impacting incident; document lessons learned and update the plan accordingly.
- **Owner:** CISO
- **Target Completion:** 60 days before audit kickoff

---

## Gap 3: Quarterly Risk Register Review Skipped (CC3.2-01)

- **Risk Rating:** 🟠 Medium
- **Finding:** Q2 risk register review was skipped, breaking the control's stated cadence.
- **Why this matters:** A broken review cadence is one of the most common Type II audit findings — auditors specifically sample multiple periods to confirm consistency, not just a single point-in-time snapshot.
- **Remediation Plan:** Perform the missed Q2 review immediately; implement a calendar-based reminder system (not reliant on manual memory) going forward.
- **Owner:** CISO
- **Target Completion:** Immediate + ongoing

---

## Gap 4: No Internal Control Self-Assessments Performed (CC4.1-02)

- **Risk Rating:** 🔴 High
- **Finding:** Semi-annual internal control self-assessments are not currently being performed at all.
- **Why this matters:** This control is meant to catch issues like the other gaps in this document *before* an external auditor finds them. Its absence means the company has no internal mechanism for self-detecting control failures.
- **Remediation Plan:** Design and schedule a formal self-assessment process; assign a checklist based on this control matrix itself, to be completed every 6 months by the CISO with sign-off from the COO.
- **Owner:** CISO
- **Target Completion:** 90 days before audit kickoff

---

## Gap 5: Segregation of Duties Partially Enforced (CC5.3-01)

- **Risk Rating:** 🟠 Medium
- **Finding:** Two senior engineers retain both development and production deployment access, violating segregation-of-duties principles.
- **Why this matters:** This is a classic audit finding — even with strong change management policy (CC5.2), retained dual access creates a single point of failure/fraud risk that policy alone doesn't mitigate.
- **Remediation Plan:** Revoke standing production access for both engineers; implement a "break-glass" temporary elevated access process requiring approval and logging for emergency situations.
- **Owner:** Engineering Manager
- **Target Completion:** 45 days before audit kickoff

---

## Gap 6: Quarterly Access Reviews Falling Behind Schedule (CC6.2-01)

- **Risk Rating:** 🟡 Low
- **Finding:** Q2 user access review is overdue by 3 weeks.
- **Why this matters:** Delayed access reviews increase the window where terminated or role-changed employees retain inappropriate access.
- **Remediation Plan:** Complete the overdue review immediately; automate review reminders via the ticketing system rather than relying on manual tracking.
- **Owner:** IT Manager
- **Target Completion:** Immediate

---

## Gap 7: Incident Response Plan Not Tested via Tabletop Exercise (CC7.3-01)

- **Risk Rating:** 🔴 High
- **Finding:** A documented incident response plan exists (CC7.2), but it has never been tested through a tabletop exercise during the review period.
- **Why this matters:** This is one of the most frequently cited gaps in real SOC 2 Type II audits. A plan that exists only on paper provides no assurance that the team can execute it under real conditions.
- **Remediation Plan:** Schedule and conduct a full incident response tabletop exercise simulating a realistic scenario (e.g., credential compromise); document results and update the plan with findings.
- **Owner:** CISO
- **Target Completion:** 60 days before audit kickoff

---

## Gap 8: Patch Management SLA Inconsistently Met for Non-Critical Patches (CC7.4-01)

- **Risk Rating:** 🟡 Low
- **Finding:** Critical patches are applied within SLA, but medium/low severity patches are frequently delayed beyond policy.
- **Why this matters:** While lower risk individually, accumulated unpatched medium-severity vulnerabilities can be chained together in real attacks, and auditors will note policy non-compliance even for "minor" severity tiers.
- **Remediation Plan:** Introduce automated patch tracking dashboards with escalation alerts when SLA thresholds are approaching, not just missed.
- **Owner:** Engineering Manager
- **Target Completion:** 30 days before audit kickoff

---

## Gap 9: BC/DR Plan Not Tested via Failover Simulation (CC9.1-02)

- **Risk Rating:** 🔴 High
- **Finding:** A documented BC/DR plan exists with defined RTO/RPO targets, but no failover simulation has been performed during the review period.
- **Why this matters:** RTO/RPO targets are meaningless without validation. This is consistently one of the top findings in real SOC 2 audits, especially for companies claiming aggressive recovery targets (4 hr RTO) without proof.
- **Remediation Plan:** Conduct a full failover simulation to the backup region (us-west-2); document actual recovery time achieved versus the stated 4-hour target, and remediate any discrepancies.
- **Owner:** Engineering Manager
- **Target Completion:** 90 days before audit kickoff

---

## Gap 10: Inconsistent Application of Data Classification Labels (C1.1-01)

- **Risk Rating:** 🟠 Medium
- **Finding:** A data classification policy exists, but classification labels are not consistently applied to data assets in practice.
- **Why this matters:** Without consistent classification, downstream controls (encryption requirements, access restrictions, retention rules) can't be reliably mapped to the right data sensitivity level.
- **Remediation Plan:** Conduct a data inventory and classification sweep across production databases and storage; implement classification tagging in S3 and database metadata going forward.
- **Owner:** CISO
- **Target Completion:** 90 days before audit kickoff

---

## Gap 11: Incomplete Edge-Case Input Validation (PI1.2-01)

- **Risk Rating:** 🟡 Low
- **Finding:** Input validation is implemented for core financial data fields, but edge-case scenarios (e.g., malformed currency formats, extreme values) are not fully covered.
- **Why this matters:** Given the platform's core function is financial reporting, incomplete validation creates processing integrity risk, even if the likelihood of exploitation is currently low.
- **Remediation Plan:** Expand automated test coverage for edge-case input scenarios; add fuzz testing to the CI/CD pipeline for financial data entry points.
- **Owner:** Engineering Manager
- **Target Completion:** 60 days before audit kickoff

---

## Summary Table

| Gap # | Control ID | Risk Rating | Owner | Target Completion |
|---|---|---|---|---|
| 1 | CC1.4-01 | 🟡 Low | COO | 30 days pre-audit |
| 2 | CC2.3-01 | 🟠 Medium | CISO | 60 days pre-audit |
| 3 | CC3.2-01 | 🟠 Medium | CISO | Immediate |
| 4 | CC4.1-02 | 🔴 High | CISO | 90 days pre-audit |
| 5 | CC5.3-01 | 🟠 Medium | Engineering Manager | 45 days pre-audit |
| 6 | CC6.2-01 | 🟡 Low | IT Manager | Immediate |
| 7 | CC7.3-01 | 🔴 High | CISO | 60 days pre-audit |
| 8 | CC7.4-01 | 🟡 Low | Engineering Manager | 30 days pre-audit |
| 9 | CC9.1-02 | 🔴 High | Engineering Manager | 90 days pre-audit |
| 10 | C1.1-01 | 🟠 Medium | CISO | 90 days pre-audit |
| 11 | PI1.2-01 | 🟡 Low | Engineering Manager | 60 days pre-audit |

**Overall Readiness Assessment:** NorthLedger Technologies demonstrates a mature 
baseline control environment, with strong implementation in access control, 
encryption, and change management. However, three high-risk gaps — the absence 
of internal control self-assessments (CC4.1-02), an untested incident response 
plan (CC7.3-01), and an unvalidated BC/DR failover process (CC9.1-02) — represent 
the most significant barriers to audit readiness. These three gaps share a common 
theme: **documented plans exist, but none have been operationally tested.** 
This is the single most important pattern for leadership to address before 
proceeding to a formal Type II audit.

**Recommended next step:** Prioritize remediation of all 🔴 High gaps within 
90 days, followed by 🟠 Medium gaps, before scheduling a formal audit engagement 
with a licensed CPA firm.