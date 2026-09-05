# 02.2 Interested Parties & Requirements Execution Guide

Identifying interested parties forms the critical bridge between organizational context (Clause 4.1) and ISMS scope (Clause 4.3). While Clause 4.1 defines the internal and external realities of the organization, Clause 4.2 identifies who holds expectations regarding those realities and specifies their concrete demands.

---

## 1. Interested-Party Register Execution Framework

The Interested-Party Register provides a structured methodology for logging stakeholder entities, categorizing their demands, and defining the precise operational ISMS response.

### 5-Column Schema

Every entry in the register must follow this 5-column structure:

| Entity ID | Stakeholder Category | Specific Named Entity | Needs, Expectations & Requirements | ISMS Scope Decision & Response |
| :--- | :--- | :--- | :--- | :--- |
| **IP-EXT-01** | Regulatory Body | New York State Dept. of Financial Services (NY DFS) | **Requirement:** Annual 23 NYCRR 500 compliance certification, mandatory CISO reporting, and multi-factor authentication enforcement. | **In ISMS Scope:** Governed via Clauses 4–10 frameworks, mapped Annex A access controls, and annual compliance filing workflow. |
| **IP-EXT-02** | Enterprise Client | Enterprise Client Tier (e.g., Enterprise Client Alpha) | **Requirement:** Executed DPA requiring 72-hour security incident notification window and right-to-audit clauses. | **In ISMS Scope:** Governed via Incident Management Procedure (A.8.16) and third-party audit facilitation SLA. |
| **IP-INT-01** | Internal Personnel | Full-time Engineering & Operational Workforce | **Expectation:** Safeguarding of personal HR/payroll records and transparent, fair employee monitoring rules. | **In ISMS Scope:** Governed via Acceptable Use Policy, explicit monitoring privacy notices, and RBAC on HR databases. |
| **IP-EXT-03** | Cyber Insurance | Cyber Risk Underwriters Co. | **Requirement:** Mandated Multi-Factor Authentication (MFA) across all identity providers, admin portals, and remote endpoints. | **In ISMS Scope:** Mapped to Identity & Access Management Controls (A.5.15 & A.8.5) with quarterly verification logs. |

---

## 2. ISMS Applicability Filtering Rules

Clause 4.2(c) explicitly requires the organization to decide **which** identified requirements will be addressed through the ISMS. Not every stakeholder demand belongs inside the information security management system.

```text
┌─────────────────────────────────────────────────────────────────────────┐
│                   STAKEHOLDER REQUIREMENT FILTERING                     │
├────────────────────────────────────┬────────────────────────────────────┤
│    ADDRESSED THROUGH THE ISMS      │    ADDRESSED VIA OTHER CHANNELS    │
├────────────────────────────────────┼────────────────────────────────────┤
│ • Cryptographic & data encryption  │ • Corporate DE&I targets (HR)      │
│ • System availability & SLA uptime │ • Commercial pricing models (Sales)│
│ • Access control & authentication  │ • Anti-money laundering (Legal)    │
│ • Incident notification timelines  │ • Feature requests (Product/R&D)   │
└────────────────────────────────────┴────────────────────────────────────┘

```

### Filtering Decision Rules

1. **Security, Confidentiality, Integrity, Availability Impact:** If the demand directly affects data protection, network resilience, or operational access, route it **into** the ISMS.
2. **Non-ISMS Business Channels:** If the demand pertains purely to commercial pricing, human resources policy, or non-security legal compliance (e.g., AML/financial reporting), document it in the register but mark it as **"Addressed Outside ISMS"**.
3. **Defense Against Scope Creep:** Explicitly recording non-ISMS requirements provides auditors with clear evidence that boundary decisions are deliberate and managed.

---

## 3. Dynamic Onboarding Workflows

The Interested-Party Register must function as a living operational document rather than a static setup artifact.

```text
  ┌──────────────────────────┐
  │ Procurement/Sales Intake │  (New customer contract or DPA execution)
  └─────────────┬────────────┘
                │
                ▼
  ┌──────────────────────────┐
  │ Security Handoff Review  │  (Identify custom security commitments or SLAs)
  └─────────────┬────────────┘
                │
                ▼
  ┌──────────────────────────┐
  │ Register Log Entry       │  (Update Interested-Party Register with new Entity ID)
  └─────────────┬────────────┘
                │
                ▼
  ┌──────────────────────────┐
  │ Control & Risk Mapping   │  (Ensure Risk Register & SoA reflect new obligations)
  └──────────────────────────┘

```

* **Commercial Trigger:** Sales and procurement handoffs automatically send executed DPAs/MSAs with custom security language to the compliance team for register logging.
* **Regulatory Trigger:** Legal counsel notifies the ISMS owner of newly enacted statutory or sector-specific regulations to trigger an immediate register update.
* **Annual Governance Trigger:** Re-evaluate all entries during the annual Clause 9.3 Management Review cycle.

---

## 4. Six Implementation Failure Modes & Mitigation Strategies

| Failure Mode | Operational Root Cause | Audit Impact | Mitigation Strategy |
| --- | --- | --- | --- |
| **1. Generic Entities** | Documenting broad categories like "Customers" or "Vendors" without specific names. | Auditors flag lack of specificity and test unmentioned major clients. | Name top tier clients, explicit regulators, and core infrastructure vendors. |
| **2. Omission of Internal Parties** | Excluding employees, contractors, board members, or internal teams. | Leaves internal operational risks and workforce access expectations unmanaged. | Add internal personnel to the register, capturing privacy and access requirements. |
| **3. Entity vs. Requirement Confusion** | Listing "GDPR" or "HIPAA" as the party rather than the governing body or client. | Creates analytical confusion between stakeholder entities and regulatory frameworks. | Maintain clear distinctions: Entity = *EU Data Protection Board*; Requirement = *GDPR Article 32*. |
| **4. Written-Only Scope** | Capturing written contracts while ignoring unwritten expectations. | System fails when unwritten expectations trigger client friction following incidents. | Interview business leads to surface implicit customer and staff operational assumptions. |
| **5. Disconnected Response** | Listing stakeholder demands without defining specific ISMS controls or policies. | Fails Clause 4.2(c); unable to prove how demands map to security operations. | Ensure every requirement links explicitly to an ISMS policy, control, or evidence artifact. |
| **6. Static Register** | Register created during setup and never updated as new clients or laws arrive. | Triggers non-conformities during Stage 2 audits for unmaintained governance artifacts. | Embed register updates directly into contract review pipelines and change management. |

```

```
