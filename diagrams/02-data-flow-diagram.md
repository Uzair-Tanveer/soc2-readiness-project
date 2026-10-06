# Data Flow Diagram — Customer Financial Data

This diagram illustrates how customer financial data flows through the 
NorthLedger platform, relevant to Confidentiality and Processing Integrity 
controls referenced in this assessment.

```mermaid
flowchart LR
    A[Customer Uploads Financial Data] --> B{Input Validation}
    B -->|Valid| C[Data Ingestion Pipeline]
    B -->|Invalid| Z[Rejected / Error Returned to Customer]

    C --> D[Data Classification Tagging]
    D --> E[(PostgreSQL - Encrypted at Rest)]
    D --> F[(S3 - Document Storage, Encrypted)]

    E --> G[Reconciliation / Integrity Checks]
    G -->|Pass| H[Financial Report Generation]
    G -->|Fail| Y[Flagged for Manual Review]

    H --> I[Customer-Facing Dashboard]
    H --> J[REST API Response to Integrations]

    E --> K[Data Retention Policy Engine]
    K -->|Retention Period Expired| L[Automated Secure Deletion]

    subgraph Access Controls
        M[RBAC Enforcement]
        N[MFA-Protected Access]
    end

    I --> M
    J --> M
    M --> N