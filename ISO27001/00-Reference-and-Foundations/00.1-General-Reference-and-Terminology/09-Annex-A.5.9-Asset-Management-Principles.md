# Annex A 5.9 — Asset Management Principles

## 1. Intent and Standard Requirements
ISO/IEC 27001:2022 Annex A 5.9 mandates that an organization build and maintain an accurate inventory of information and other associated assets, including explicit ownership assignments. 

An asset inventory is not a passive administrative list; it is the core foundation for all downstream ISMS operations. Without a clear inventory, risk assessments become guesswork, control applicability (Statement of Applicability) lacks context, and audit evidence cannot be reliably mapped.

---

## 2. Information Assets vs. Associated Assets
The 2022 revision of the standard explicitly broadened asset management taxonomy into two primary categories:

* **Information Assets (The Primary Asset):** The data or knowledge itself (e.g., customer PII, source code, financial ledgers). Information is what holds intrinsic business value and regulatory liability.
* **Associated Assets (Supporting Infrastructure):** The containers, processing units, physical sites, transmission channels, and people that store, process, transmit, or protect the primary information asset.

```text
┌─────────────────────────────────────────────────────────────────────────┐
│                      ASSET TAXONOMY (ANNEX A 5.9)                       │
├─────────────────────────────────────────────────────────────────────────┤
│ PRIMARY ASSET                                                           │
│ └── Information / Data (KYC records, source code, payroll)             │
├─────────────────────────────────────────────────────────────────────────┤
│ ASSOCIATED SUPPORTING ASSETS                                            │
│ ├── Software / Applications (Payment APIs, SaaS platforms, databases)   │
│ ├── Hardware / Infrastructure (Cloud regions, laptops, network gear)    │
│ ├── Services (Outsourced SOC, identity verification APIs)               │
│ ├── People (Key engineers, compliance officers, system admins)          │
│ └── Facilities (Datacenters, corporate offices, secure archives)        │
└─────────────────────────────────────────────────────────────────────────┘

```

---

## 3. The 6 Core Asset Types

An auditable inventory categorizes all organizational assets across six operational types:

| Asset Type | Definition | Concrete Examples |
| --- | --- | --- |
| **1. Information / Data** | Core data, IP, or records created, received, or processed. | KYC records, transaction ledgers, employee PII, customer support tickets, source code. |
| **2. Software / Apps** | Systems and platforms hosting or processing information. | Custom payment APIs, Zendesk, HubSpot, BambooHR, PostgreSQL databases. |
| **3. Hardware / Infra** | Physical or cloud computing platforms and devices. | AWS production environments, corporate laptops, network firewalls, mobile endpoints. |
| **4. Services** | External vendors or utilities supplying operational capabilities. | Outsourced SOC providers, payment gateways, identity verification APIs, cloud regions. |
| **5. People** | Critical roles or personnel with access to sensitive assets. | Key DevOps engineers, compliance officers, lead developers, system administrators. |
| **6. Facilities** | Physical locations hosting systems, people, or paper assets. | Corporate headquarters, colocation datacenter cages, offsite paper archives. |

---

## 4. The Owner Rule & "Pays the Price" Test

The standard mandates that **every asset must have a single named human owner**. Departmental boxes (e.g., "Engineering Team" or "IT Dept") are invalid because shared ownership leads to zero accountability.

### Data Owner vs. System Owner

To ensure proper governance, every information asset is assigned two distinct owner roles:

* **Data Owner (Accountable for the Information):** The business manager accountable for the content, business value, access rules, retention, and classification of the data.
* **System Owner (Accountable for the Container):** The technical manager responsible for maintaining the security controls, availability, patching, and operational infrastructure hosting the data.

```text
  ┌────────────────────────────────────────────────────────┐
  │                 THE "PAYS THE PRICE" TEST              │
  │                                                        │
  │   "Who suffers the direct career, budget, regulatory,  │
  │   or reputational loss if this data leaks or dies?"    │
  └───────────────────────────┬────────────────────────────┘
                              │
                              ▼
  ┌────────────────────────────────────────────────────────┐
  │                      DATA OWNER                        │
  │  Example: Head of Compliance owns Customer KYC Data    │
  │  (System Owner: CTO who manages the RDS database)      │
  └────────────────────────────────────────────────────────┘

```

---

## 5. Three Complementary Discovery Methodologies

Relying on a single discovery method misses up to 30% of enterprise assets (especially shadow SaaS and vendor-hosted data copies). Implementers must combine three approaches:

```text
  ┌────────────────────────┐  ┌────────────────────────┐  ┌────────────────────────┐
  │ Top-Down Process Walk  │  │ Bottom-Up System Scan  │  │ Inside-Out Interviews  │
  ├────────────────────────┤  ├────────────────────────┤  ├────────────────────────┤
  │ Trace core workflows   │  │ Export cloud configs,  │  │ Interview business     │
  │ (e.g., onboarding) to  │  │ MDM rosters, and SaaS  │  │ unit heads to unearth  │
  │ identify created data. │  │ administrative portals.│  │ shadow tools & paper.  │
  └───────────┬────────────┘  └───────────┬────────────┘  └───────────┬────────────┘
              │                           │                           │
              └───────────────────────────┼───────────────────────────┘
                                          │
                                          ▼
                      ┌───────────────────────────────────────┐
                      │ Single Unified Information Inventory  │
                      └───────────────────────────────────────┘

```

1. **Top-Down (Process Walking):** Map key business processes (e.g., customer onboarding, payroll, claims processing) step-by-step, logging every piece of information generated, modified, stored, or transmitted.
2. **Bottom-Up (System Scanning):** Extract automated lists from infrastructure tooling (e.g., AWS Config, MDM rosters, identity provider user lists, SaaS administrative consoles).
3. **Inside-Out (Stakeholder Interviews):** Conduct 30-minute interviews with business unit heads (HR, Marketing, Sales, Legal) asking: *"What data do you rely on daily, and where does it live?"*

```

```
