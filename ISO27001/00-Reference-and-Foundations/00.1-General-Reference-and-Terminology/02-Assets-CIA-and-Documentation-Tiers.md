## 6. Information Asset Taxonomy & CIA Mechanics

### Data vs. Information vs. Information Asset
* **Data:** Unprocessed, discrete facts (e.g., an IP address, a timestamp, an isolated account balance).
* **Information:** Data structured to provide context and business meaning (e.g., "Account X transferred $10,000 to IP Y at 03:00 UTC").
* **Information Asset:** A managed container of information that possesses organizational value, has an assigned owner, and creates financial, operational, or legal consequences if compromised.

---

### The 6-Layer Information Footprint

Information security governance must encompass all six operational layers where information resides:

```text
  ┌────────────────────────────────────────────────────────┐
  │ 1. Cloud Infrastructure (S3, Databases, Secrets)        │
  ├────────────────────────────────────────────────────────┤
  │ 2. SaaS Platforms (CRM, Ticketing, HR, Messaging)     │
  ├────────────────────────────────────────────────────────┤
  │ 3. Endpoints (Laptops, Mobile Devices, Local Storage)  │
  ├────────────────────────────────────────────────────────┤
  │ 4. Personnel (Intellectual Property, Tacit Knowledge)  │
  ├────────────────────────────────────────────────────────┤
  │ 5. Physical Records (Contracts, ID Copies, Binders)   │
  ├────────────────────────────────────────────────────────┤
  │ 6. Third-Party Vendors (Processor DBs, SOC Logs)       │
  └────────────────────────────────────────────────────────┘

```

---

### Standard Information Classification Scheme (Annex A 5.12)

To maintain operational usability, use a simple 4-tier classification model rather than over-engineered multi-level taxonomies:

| Classification Level | Definition / Exposure Impact | Baseline CIA Orientation | Typical Asset Examples |
| --- | --- | --- | --- |
| **Public** | Information intended for public distribution; zero loss of confidentiality impact. | Low C / Low I / Med A | Marketing site content, public API docs, published PR releases. |
| **Internal** | Information restricted to employees and contractors; minor operational disruption if leaked. | Med C / Med I / Med A | Internal wikis, organizational charts, project roadmaps. |
| **Confidential** | Sensitive business data; financial, legal, or competitive damage if disclosed. | High C / High I / Med A | Customer PII, employee records, commercial contracts, financial statements. |
| **Restricted** | Highest sensitivity; severe regulatory penalties or catastrophic reputational failure if breached. | Critical C / Critical I / Med-High A | Payment card data (PCI), biometrics, government identifiers, primary cryptographic keys. |

---

### CIA Triad to Safeguard Mapping

Evaluating assets through CIA scoring directly dictates control selection during risk treatment:

| Impact Dimension | Primary Operational Focus | Safeguard & Control Categories |
| --- | --- | --- |
| **Confidentiality (C)** | Preventing unauthorized access and information disclosure. | Encryption at rest/in transit, Identity & Access Management (IAM), Data Loss Prevention (DLP), Network Segregation. |
| **Integrity (I)** | Preventing unauthorized modification, corruption, or deletion. | Input validation, cryptographic hashing, change management workflows, dual-custody (four-eyes) approvals. |
| **Availability (A)** | Ensuring timely and reliable access for authorized users. | High Availability (HA) clustering, database replication, automated backups, Disaster Recovery (DR) failover. |

---

## 7. The ISO 27000 Standard Family Taxonomy

To maintain clarity across governance documentation, distinguish between the five core structural components using the **Commercial Aviation Governance** model:

```text
  ┌────────────────────────────────────────────────────────┐
  │ 1. Mandatory Airworthiness Standard (ISO/IEC 27001)   │
  ├────────────────────────────────────────────────────────┤
  │ 2. Maintenance Engineering Guidance (ISO/IEC 27002)    │
  ├────────────────────────────────────────────────────────┤
  │ 3. Approved Parts & Safeguards Catalog (Annex A)      │
  ├────────────────────────────────────────────────────────┤
  │ 4. Fleet Operating Master Schedule (SoA)               │
  ├────────────────────────────────────────────────────────┤
  │ 5. Maintenance Flight Logs & Sign-Offs (Evidence)      │
  └────────────────────────────────────────────────────────┘

```

* **ISO/IEC 27001 (Auditable Rules):** The primary airworthiness standard. Defines mandatory requirements (Clauses 4–10) and contains Annex A reference controls. This is the only standard against which an organization achieves formal certification.
* **ISO/IEC 27002 (Implementation Guidance):** The engineering maintenance manual. Provides detailed operational guidance on how to execute each control in Annex A. It cannot be audited against directly for certification.
* **Annex A (Control Reference Set):** The approved catalog of 93 control references across 4 operational themes. Used during risk treatment to select applicable safeguards.
* **Statement of Applicability - SoA (Operating Schedule):** The formal manifest declaring which Annex A controls apply to the fleet, their implementation status, justifications for selection/exclusion, and linked evidence.
* **Evidence Records (Flight & Maintenance Logs):** The dated, unedited records (e.g., flight logs, sensor readouts, signed maintenance checklists) proving safeguards operated consistently in production.

---

## 8. Documentation Hierarchy: Three Essential Artifact Tiers

Auditors evaluate governance documentation using strict structural distinctions between information containers, specifications, and records:

| Documentation Tier | Operational Definition | System Function | Representative Examples |
| --- | --- | --- | --- |
| **Document** | High-level governance text defining how a domain operates. Version-controlled and periodically re-approved. | Establishes policy intent and operational boundaries. | Information Security Policy, Incident Response Plan, Risk Methodology. |
| **Specification** | Precise, testable rules and technical parameters. Binary compliance criteria (pass/fail). | Establishes enforceable technical baselines. | Password length rules (≥14 chars), patch deployment SLAs (≤14 days), backup frequency rules. |
| **Record** | Immutable proof that an activity or control executed at a specific point in time. Never edited. | Primary evidence requested by auditors to prove compliance. | Signed Q1 access review log, dated vulnerability scan report, employee training timestamp. |

> **Audit Caution:** Shelves of Documents and Specifications without corresponding unedited Records result in immediate audit non-conformity.

---
