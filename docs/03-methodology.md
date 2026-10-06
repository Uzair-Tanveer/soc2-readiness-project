# Assessment Methodology

## Purpose
This document explains the approach used to conduct this SOC 2 readiness 
assessment, providing transparency into how controls were identified, 
evaluated, and rated.

## Framework Reference
This assessment is based on the AICPA Trust Services Criteria (TSC), as 
used in SOC 2 engagements. Controls are mapped to the following categories:

- **CC1–CC9:** Common Criteria (required baseline for all SOC 2 reports)
- **A1:** Availability
- **C1:** Confidentiality
- **PI1:** Processing Integrity (partial scope — see `docs/01-company-scope.md`)

Privacy criteria were excluded from scope, as documented in the company 
scope document, since NorthLedger does not process consumer PII beyond 
standard business contact information.

## Assessment Approach

1. **Scoping** — Defined system boundaries, infrastructure, and applicable 
   TSC categories (see `docs/01-company-scope.md`).
2. **Control Identification** — For each applicable TSC category, identified 
   specific, auditable controls that NorthLedger would reasonably need to 
   satisfy that criterion.
3. **Status Evaluation** — Each control was assessed as:
   - ✅ **Implemented** — control is designed and operating as intended
   - ⚠️ **Partially Implemented** — control exists but has gaps in 
     consistency, testing, or coverage
   - ❌ **Not Implemented** — control does not currently exist
4. **Evidence Mapping** — For implemented and partially implemented 
   controls, representative evidence artifacts were created to simulate 
   what an auditor would expect to review (see `evidence/` folder).
5. **Gap Analysis** — Every control rated ⚠️ or ❌ was carried into a 
   formal gap analysis (`docs/02-gap-analysis.md`), including a risk 
   rating, business impact explanation, remediation plan, owner, and 
   target completion timeframe.
6. **Risk Rating** — Gaps were rated using a Likelihood x Impact model 
   (🔴 High / 🟠 Medium / 🟡 Low), prioritizing remediation effort toward 
   the highest-risk gaps first.

## Limitations

This is a simulated/educational exercise, not a real audit engagement. 
Key differences from a real SOC 2 Type II audit include:

- No independent CPA firm testing or sign-off
- No sampling of actual system logs, access records, or transaction data
- Evidence artifacts are illustrative examples, not real operational records
- The assessment period (Jan–Jun 2025) and all findings are fictional, 
  created for demonstration purposes

## Why This Methodology Matters

A readiness assessment is only as credible as the rigor behind it. This 
methodology mirrors real-world practice: scope first, identify controls 
against a recognized framework, honestly evaluate operating effectiveness 
(not just policy existence), and translate findings into prioritized, 
owned action items — rather than simply producing a checklist.