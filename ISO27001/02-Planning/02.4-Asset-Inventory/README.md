# 02.4 Information Asset Identification Execution Guide

Building an accurate, comprehensive Information Asset Inventory satisfies ISO/IEC 27001:2022 Annex A 5.9 and serves as the baseline for all downstream ISMS operations. If an asset is missing from this inventory, it will be omitted from the risk assessment, excluded from control selection, and left unmonitored.

---

## 1. Information Asset Inventory Schema

The Information Asset Inventory must capture both the primary information asset and its supporting containers across an 8-column schema:

### 8-Column Schema

| Asset ID | Asset Type | Name & Description | Locations & Vendor Copies | Data Owner (Named) | System Owner (Named) | Classification | CIA Triad Scoring |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **AST-DAT-01** | Information | **Customer KYC Data:** Government IDs, proof of address, tax IDs, and verification records. | Production AWS S3 (`us-east-1`), encrypted backups, third-party ID vendor copy. | Head of Compliance (Jane Doe) | CTO (John Smith) | **Restricted** | **C:** High<br>**I:** High<br>**A:** Med |
| **AST-APP-01** | Software | **Payment Gateway API:** Microservice processing real-time card transactions. | AWS EKS Cluster, GitHub Enterprise Repo. | VP of Product (Alice Johnson) | Lead DevOps Engineer (Bob Lee) | **Confidential** | **C:** High<br>**I:** Critical<br>**A:** Critical |
| **AST-SVC-01** | Services | **Zendesk SaaS:** Customer support ticketing platform storing issue histories. | Vendor Cloud (US Region), local support agent browser cache. | Head of Customer Support (Mark Davis) | IT Director (Sarah Connor) | **Confidential** | **C:** Med<br>**I:** Med<br>**A:** Med |
| **AST-HW-01** | Hardware | **Engineering Laptops:** Corporate macOS endpoints used for software development. | Distributed Remote Workforce, MDM inventory. | Head of People (Elena Rostova) | IT Support Lead (Mike Brown) | **Internal** | **C:** Med<br>**I:** Med<br>**A:** Low |

---

## 2. Mandatory Metadata & Field Governance Rules

To ensure auditability, inventory entries must strictly adhere to three core metadata rules:

1. **Named Individual Rule:** Generic teams, departments, or role titles alone (e.g., "Engineering Team" or "IT") are prohibited in owner columns. Every entry must list a specific named human alongside their official job title.
2. **Vendor Copy Accounting:** The *Locations* column must list all external locations where data resides, including third-party processor backups, SaaS storage, and vendor environments.
3. **Justified CIA Triad Scoring:** Qualitative CIA levels (Low, Medium, High, Critical) must be assigned independently for Confidentiality, Integrity, and Availability based on defined business impact parameters.

---

## 3. SaaS Discovery via Financial Audits

System scans and technical tool exports miss unsanctioned or departmental SaaS platforms (e.g., Zendesk, HubSpot, BambooHR). To eliminate shadow SaaS blind spots, implementers must partner with Finance:

```text
  ┌──────────────────────────┐
  │ Finance Expense Export   │  (Monthly credit card & corporate GL exports)
  └─────────────┬────────────┘
                │
                ▼
  ┌──────────────────────────┐
  │ Software Subscription    │  (Filter transactions by software/SaaS vendor tags)
  │ Isolation                │
  └─────────────┬────────────┘
                │
                ▼
  ┌──────────────────────────┐
  │ Data Handling Review     │  (Determine if platform stores or processes company/client data)
  └─────────────┬────────────┘
                │
                ▼
  ┌──────────────────────────┐
  │ Inventory Log & Owner    │  (Assign Data/System Owners and record in Asset Inventory)
  │ Assignment               │
  └──────────────────────────┘

```

---

## 4. Maintenance Cadence & Dynamic Change Triggers

The Asset Inventory is a living document maintained through regular review cycles and event-driven operational triggers:

* **Scheduled Review Cadence:** Mandatory quarterly review by the ISMS Steering Committee and annual re-certification during the Clause 9.3 Management Review.
* **Operational Change Triggers:**
1. **SaaS Onboarding:** Procurement or HR signing a new cloud service contract.
2. **Product & Architecture Releases:** Deploying new software microservices, database instances, or public cloud regions.
3. **Vendor Engagement:** Contracting a third-party vendor to process or store internal data.
4. **Corporate Mergers & Acquisitions:** Onboarding new business units, infrastructure, or personnel.



---

## 5. Six Implementation Failure Modes & Mitigation Strategies

| Failure Mode | Operational Root Cause | Audit Impact | Mitigation Strategy |
| --- | --- | --- | --- |
| **1. Infrastructure-Only Inventory** | Passing off an AWS Config or CMDB server list as the asset inventory. | Fails Annex A 5.9; ignores primary information assets and data flows. | Walk business processes top-down to identify the underlying data before listing servers. |
| **2. Invisible Shadow SaaS** | Omitting third-party SaaS platforms holding regulated customer or HR data. | Major security blind spot; data subject to unmonitored vendor breach risks. | Perform quarterly financial expense audits to catch unsanctioned SaaS subscriptions. |
| **3. Untracked Vendor Copies** | Tracking data on internal servers while ignoring copies held by third-party processors. | Incomplete scope mapping; fails vendor risk assessment controls (A.5.19). | Require the *Locations* column to capture all external vendor and backup locations. |
| **4. Collective "Team" Ownership** | Assigning ownership to "IT Dept" or "Engineering" instead of a named individual. | Lack of personal accountability; rejected by external auditors during Stage 2. | Record a specific named person along with their job title for both Data and System Owner roles. |
| **5. Missing CIA & Classification** | Listing assets without defining data classification levels or CIA Triad impact scores. | Downstream risk assessments lack baseline severity inputs. | Enforce mandatory completion of Classification and CIA fields for every inventory row. |
| **6. Stale / Frozen Inventory** | Creating the inventory once during ISMS setup and failing to update it as the company grows. | Audit finding for unmaintained governance artifacts and lack of operational integration. | Tie inventory updates directly to procurement workflows and software launch checklists. |

```

```
