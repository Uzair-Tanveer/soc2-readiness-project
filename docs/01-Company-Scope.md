# System Description & Audit Scope

## 1. Company Overview

**Company Name:** NorthLedger Technologies, Inc. (fictitious)
**Industry:** B2B SaaS — Cloud-based financial reporting and bookkeeping automation platform
**Customer Base:** Small-to-mid-sized businesses (SMBs), accounting firms
**Headquarters:** Austin, TX (fictitious)
**Employee Count:** ~85 employees

NorthLedger Technologies provides a cloud-hosted SaaS platform that allows 
small businesses to automate bookkeeping, generate financial reports, and 
integrate with third-party accounting tools. The platform processes customer 
financial data, making data security, availability, and confidentiality 
central to customer trust.

## 2. Services in Scope

The following system is included in this readiness assessment:

- **NorthLedger Platform** — the core multi-tenant SaaS web application, 
  including:
  - Customer-facing web application
  - REST API used by third-party integrations
  - Backend data processing pipeline
  - Customer support ticketing system (to the extent it touches customer data)

## 3. Infrastructure Overview

- **Hosting:** AWS (us-east-1 primary region, us-west-2 for backup/DR)
- **Architecture:** Multi-tenant cloud architecture, containerized services 
  (Kubernetes/EKS)
- **Data Storage:** PostgreSQL (RDS), S3 for document storage
- **Authentication:** OAuth 2.0 / SSO support, MFA available for customer accounts
- **CI/CD:** GitHub Actions for deployment pipelines

## 4. Trust Services Criteria (TSC) in Scope

SOC 2 reports are built around five possible Trust Services Criteria. 
Not every company includes all five — scope is chosen based on what matters 
most to customers.

| Criterion | In Scope? | Rationale |
|---|---|---|
| Security (Common Criteria) | ✅ Yes | Required baseline for all SOC 2 reports |
| Availability | ✅ Yes | Customers depend on platform uptime for financial operations |
| Confidentiality | ✅ Yes | Platform handles sensitive financial data |
| Processing Integrity | ⚠️ Partial | Relevant to financial calculations accuracy |
| Privacy | ❌ Out of scope | No direct collection of consumer PII beyond business contacts (handled under separate privacy policy, not SOC 2 scope for this assessment) |

## 5. Report Type

**SOC 2 Type II (Readiness Assessment)** — this project simulates the 
*readiness* phase that typically precedes a real Type II audit, where 
controls are evaluated for both design and operating effectiveness over 
a review period (commonly 6–12 months). This project does not simulate an 
actual auditor's report — it is a readiness/gap assessment exercise.

## 6. Assessment Period (Simulated)

**Review window:** January 1, 2025 – June 30, 2025 (fictitious, for exercise purposes)

## 7. Exclusions

The following are explicitly **out of scope** for this assessment:
- Mobile applications (not yet released)
- Third-party payment processor's internal controls (covered under their 
  own SOC 2 report, referenced but not assessed here)
- Marketing website (non-production, no customer data processed)