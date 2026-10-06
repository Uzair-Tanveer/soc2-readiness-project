# SOC 2 Control Matrix — NorthLedger Technologies

**Scope reference:** See `docs/01-company-scope.md` for full system description.
**Assessment period:** January 1, 2025 – June 30, 2025 (simulated)

Status Key: ✅ Implemented | ⚠️ Partially Implemented | ❌ Not Implemented

---

## CC1 — Control Environment

| Control ID | Control Description | Type | Status | Owner | Evidence Ref | Notes / Gap |
|---|---|---|---|---|---|---|
| CC1.1-01 | Code of conduct and ethics policy is documented and acknowledged by all employees annually | Preventive | ✅ | HR Director | evidence/cc1-code-of-conduct.md | Signed acknowledgments tracked in HRIS |
| CC1.1-02 | Background checks performed on all new hires prior to start date | Preventive | ✅ | HR Director | evidence/cc1-background-checks.md | Third-party vendor used |
| CC1.4-01 | Formal organizational chart defines reporting lines and segregation of duties | Preventive | ⚠️ | COO | evidence/cc1-org-chart.md | Org chart exists but not reviewed/updated in 9 months |

## CC2 — Communication and Information

| Control ID | Control Description | Type | Status | Owner | Evidence Ref | Notes / Gap |
|---|---|---|---|---|---|---|
| CC2.1-01 | Security policies are published and accessible to all employees via internal wiki | Preventive | ✅ | CISO | evidence/cc2-policy-portal.md | Hosted on Confluence, access-controlled |
| CC2.3-01 | Incident communication plan defines escalation paths to customers and stakeholders | Corrective | ⚠️ | CISO | evidence/cc2-incident-comms-plan.md | Plan drafted, not yet tested via tabletop exercise |

## CC3 — Risk Assessment

| Control ID | Control Description | Type | Status | Owner | Evidence Ref | Notes / Gap |
|---|---|---|---|---|---|---|
| CC3.1-01 | Formal annual risk assessment conducted covering security, availability, and confidentiality risks | Detective | ✅ | CISO | evidence/cc3-risk-assessment-2025.md | Completed Q1 2025 |
| CC3.2-01 | Risk register maintained and reviewed quarterly by leadership | Detective | ⚠️ | CISO | evidence/cc3-risk-register.md | Register exists; Q2 review was skipped |

## CC4 — Monitoring Activities

| Control ID | Control Description | Type | Status | Owner | Evidence Ref | Notes / Gap |
|---|---|---|---|---|---|---|
| CC4.1-01 | Continuous security monitoring via SIEM with alerting for anomalous activity | Detective | ✅ | Security Analyst | evidence/cc4-siem-config.md | AWS GuardDuty + centralized logging |
| CC4.1-02 | Internal control self-assessments performed semi-annually | Detective | ❌ | CISO | evidence/cc4-control-self-assessment.md | Not currently performed — identified gap |

## CC5 — Control Activities

| Control ID | Control Description | Type | Status | Owner | Evidence Ref | Notes / Gap |
|---|---|---|---|---|---|---|
| CC5.2-01 | Change management policy requires peer review and approval before production deployment | Preventive | ✅ | Engineering Manager | evidence/cc5-change-mgmt-policy.md | Enforced via GitHub branch protection rules |
| CC5.3-01 | Segregation of duties enforced between development and production deployment access | Preventive | ⚠️ | Engineering Manager | evidence/cc5-sod-matrix.md | Mostly enforced; 2 senior engineers retain both access levels |

## CC6 — Logical and Physical Access Controls

| Control ID | Control Description | Type | Status | Owner | Evidence Ref | Notes / Gap |
|---|---|---|---|---|---|---|
| CC6.1-01 | Multi-factor authentication (MFA) required for all employee access to production systems | Preventive | ✅ | IT Manager | evidence/cc6-mfa-enforcement.md | Enforced via Okta SSO |
| CC6.1-02 | Role-based access control (RBAC) governs access to customer data based on job function | Preventive | ✅ | IT Manager | evidence/cc6-rbac-policy.md | Reviewed quarterly |
| CC6.2-01 | User access reviews performed quarterly to validate least-privilege access | Detective | ⚠️ | IT Manager | evidence/cc6-access-review-q2.md | Q1 completed; Q2 review overdue by 3 weeks |
| CC6.3-01 | Access immediately revoked upon employee termination (same business day) | Preventive | ✅ | IT Manager | evidence/cc6-offboarding-log.md | Automated via HRIS-to-Okta integ