# 00.1 Standard Taxonomy, Anatomy & Core ISMS Architecture

## 1. Deconstructing the Standard: ISO/IEC 27001:2022

Understanding the exact naming convention and structure prevents common governance missteps during internal and external audits.

* **ISO/IEC:** Published jointly by the **International Organization for Standardization (ISO)** and the **International Electrotechnical Commission (IEC)** in Geneva. International technical committees made up of experts from over 100 member nations consensus-build these standards.
* **27000 Series:** The dedicated standards family for information security governance. 
  * **ISO/IEC 27001:** Specifies the mandatory **Requirements** for an Information Security Management System (ISMS). This is the only standard in the family against which an organization can achieve formal certification.
  * **ISO/IEC 27002:** Provides implementation **Guidance** and best-practice descriptions for the controls referenced in Annex A. It cannot be audited against directly for certification.
  * **ISO/IEC 27005:** Focuses specifically on information security **Risk Management** guidance.
* **2022 Revision:** The active edition. Earlier versions (e.g., 2005, 2013) contain outdated control sets and structural clauses. Always specify `:2022` in official governance documentation.
* **Requirements vs. Guidance:** Clauses 4 through 10 of ISO 27001 contain mandatory rules ("shall" statements). Failure to satisfy a mandatory requirement results in audit non-conformity.

---

## 2. Core ISMS System Architecture: The Operational Loop

An ISMS is an integrated operational lifecycle, not a static binder of policies. It functions as an interconnected loop across six distinct operational layers:

```text
  ┌────────────────────────────────────────────────────────┐
  │ 1. Context & Interested Parties (Clauses 4.1 / 4.2)     │
  └───────────────────────────┬────────────────────────────┘
                              │
                              ▼
  ┌────────────────────────────────────────────────────────┐
  │ 2. Risk Assessment & Treatment (Clause 6.1)            │
  └───────────────────────────┬────────────────────────────┘
                              │
                              ▼
  ┌────────────────────────────────────────────────────────┐
  │ 3. Control Deployment & SoA (Clause 6.1.3 / Annex A)   │
  └───────────────────────────┬────────────────────────────┘
                              │
                              ▼
  ┌────────────────────────────────────────────────────────┐
  │ 4. Operational Evidence Collection (Clause 7.5 / 8.1)  │
  └───────────────────────────┬────────────────────────────┘
                              │
                              ▼
  ┌────────────────────────────────────────────────────────┐
  │ 5. Performance Evaluation & Review (Clause 9.1 / 9.3)  │
  └───────────────────────────┬────────────────────────────┘
                              │
                              ▼
  ┌────────────────────────────────────────────────────────┐
  │ 6. Continual Improvement & CAPA (Clauses 10.1 / 10.2)  │
  └───────────────────────────┬────────────────────────────┘
                              │
                              └───────> (Feeds back into Context)
```

## The System Validation Test
To verify if a control is part of a functional ISMS or just an isolated policy, select any security control (e.g., Privileged Access Management) and trace its linkage:

- Context/Driver: Which regulatory requirement or business context demands this control?
- Risk: Which specific risk scenario on the Risk Register does it mitigate?
- Execution: Who owns the control, and what SOP governs its operation?
- Evidence: Where is the immutable log or record proving it ran consistently?
- Evaluation: When was this control last evaluated during an internal audit or management review?

If any connection in this chain is broken, governance exists only as unverified documentation.

## 3. The 8-Stage ISMS Feedback Loop

An ISMS is an active control loop—analogous to a closed-loop climate system—that continuously evaluates and adapts to business shifts rather than functioning as a passive document repository.

1. **Context Analysis:** Internal and external operational parameters, legal drivers, and organizational dependencies.
2. **Boundary Scope Definition:** The physical, logical, and operational perimeters governed by the ISMS.
3. **Risk Identification & Assessment:** Cataloging threat scenarios, vulnerabilities, and potential CIA impacts.
4. **Risk Treatment Strategy:** Formal decisions to mitigate, transfer, avoid, or accept specific risks.
5. **Control Deployment:** Implementing targeted technical, administrative, and physical safeguards.
6. **Operational Evidence Generation:** Collecting logs, sign-offs, and records proving consistent control operation.
7. **Internal Audit Verification:** Independent assessment verifying system effectiveness and standard adherence.
8. **Executive Management Review:** Strategic oversight evaluating performance, resource needs, and continuous improvement actions.

```text
  [1. Context] ──► [2. Scope] ──► [3. Risk Assessment] ──► [4. Risk Treatment]
       ▲                                                          │
       │                                                          ▼
  [8. Mgmt Review] ◄── [7. Internal Audit] ◄── [6. Evidence] ◄── [5. Controls]

```

The feedback loop completes as **Stage 8 (Management Review)** feeds actionable directives back into **Stage 1 (Context)**, sustaining continuous adaptation.

---

## 4. Boundary Definitions: Core ISMS Misconceptions

| Misconception | Operational Reality | Governance Correction |
| --- | --- | --- |
| **"The ISMS is our policy folder."** | Policies are static outputs. | The ISMS is the active operating system that generates, enforces, and updates policies. |
| **"Security tooling (SIEM, MFA) is our ISMS."** | Tools are inputs to individual controls. | Technical safeguards represent only stage 5 of the 8-stage operational loop. |
| **"Periodic status meetings equal an ISMS."** | Meetings cover partial review functions. | Governance requires complete end-to-end integration across all 8 stages. |

---

## 5. Control Integrity Validation: The 60-Second Loop Test

To verify if a security mechanism is integrated into an active ISMS or operating as an isolated practice, evaluate these five operational linkages:

1. **Risk Alignment:** Which specific Risk ID in the risk register mandates this control?
2. **Ownership Assignment:** Who is the named individual accountable for running the control?
3. **Evidence Artifact:** Where is the log or record stored, and what is its retention schedule?
4. **Audit Scope:** On what date was this control last evaluated during an internal audit?
5. **Management Review:** What executive decisions or performance metrics were logged for this control during the last governance review?

---

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

## 9. Structural Evolution: 2013 vs. 2022 Revision Delta

The ISO/IEC 27001:2022 update restructured control references to align with cloud-first architectures:

```text
  ISO/IEC 27001:2013                         ISO/IEC 27001:2022
  ┌────────────────────────┐                 ┌────────────────────────┐
  │ 114 Controls           │ ──────────────► │ 93 Controls            │
  │ 14 Control Families    │   Consolidated  │ 4 Operational Themes   │
  └────────────────────────┘                 └────────────────────────┘

```

### The 4 Operational Themes (2022 Edition)

1. **Organisational Controls (Theme 5):** 37 controls governing policy, governance, asset management, and vendor oversight.
2. **People Controls (Theme 6):** 8 controls governing background screening, security awareness, remote work, and offboarding.
3. **Physical Controls (Theme 7):** 14 controls governing secure perimeters, equipment protection, and clear desk policies.
4. **Technological Controls (Theme 8):** 34 controls governing access control, cryptography, secure coding, network security, and logging.

### Critical 2022 Control Additions

* **A.5.7** Threat Intelligence
* **A.5.23** Information Security for Use of Cloud Services
* **A.5.30** ICT Readiness for Business Continuity
* **A.8.9** Configuration Management
* **A.8.10** Information Deletion
* **A.8.11** Data Masking
* **A.8.12** Data Leakage Prevention (DLP)
* **A.8.16** Monitoring Activities
* **A.8.22** Web Filtering
* **A.8.28** Secure Coding

---

## 10. The Complete ISO 27000 Series Standard Map

| Category / Domain | Standard Number | Title & Primary Purpose |
| --- | --- | --- |
| **Core Baseline** | **ISO/IEC 27000** | Vocabulary, definitions, and foundational concepts across the 27000 family. *(Free)* |
|  | **ISO/IEC 27001** | Mandatory ISMS requirements for certification (Clauses 4–10 + Annex A). |
|  | **ISO/IEC 27002** | Operational implementation guidance for Annex A controls. |
| **Process Guidance** | **ISO/IEC 27003** | Practical ISMS implementation guidance for Clauses 4–10. |
|  | **ISO/IEC 27004** | Security performance evaluation, measurement, metrics, and KPIs (Clause 9.1). |
|  | **ISO/IEC 27005** | Information security risk management methodology and assessment guidance (Clause 6.1.2). |
|  | **ISO/IEC 27007** | Guidelines for internal and external ISMS auditing practices (Clause 9.2). |
|  | **ISO/IEC 27008** | Technical guidelines for evaluating information security controls. |
| **Domain Extensions** | **ISO/IEC 27017** | Information security controls for cloud services (pairs with A.5.23). |
|  | **ISO/IEC 27018** | Protection of Personally Identifiable Information (PII) in public cloud environments. |
|  | **ISO/IEC 27701** | Privacy Information Management System (PIMS) extension for GDPR compliance. |
| **Specialized Guidance** | **ISO/IEC 27031** | ICT readiness for business continuity (pairs with A.5.30). |
|  | **ISO/IEC 27034** | Application security guidelines across software development lifecycles. |
|  | **ISO/IEC 27035** | Incident management planning, response execution, and lessons learned (A.5.24–A.5.27). |
|  | **ISO/IEC 27036** | Security governance across supplier and vendor relationships (A.5.19–A.5.22). |

```
