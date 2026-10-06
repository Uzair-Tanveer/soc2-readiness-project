# System Architecture Diagram

This diagram illustrates the high-level architecture of the NorthLedger 
Technologies platform referenced throughout this readiness assessment.

```mermaid
graph TD
    A[Customer Browser] -->|HTTPS/TLS 1.2+| B[Load Balancer]
    B --> C[Web Application - EKS Cluster]
    C --> D[REST API Service]
    D --> E[(PostgreSQL - RDS)]
    D --> F[(S3 - Document Storage)]
    C --> G[Okta SSO / MFA]
    D --> H[Third-Party Integrations]
    C --> I[CloudWatch Logging]
    I --> J[GuardDuty / SIEM Alerting]
    J --> K[PagerDuty - Security Analyst]

    subgraph AWS us-east-1 Primary Region
        C
        D
        E
        F
    end

    subgraph AWS us-west-2 DR Region
        L[(Standby Replica - RDS)]
        M[(S3 Cross-Region Replication)]
    end

    E -.->|Replication| L
    F -.->|Replication| M