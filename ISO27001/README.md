# ISO/IEC 27001 Implementation & ISMS Governance Framework

## Overview & Purpose

This repository serves as a practical workspace, technical reference guide, and implementation portfolio for establishing, operating, and evaluating an Information Security Management System (ISMS) based on **ISO/IEC 27001:2022** and **ISO/IEC 27002:2022**.

Rather than viewing ISO 27001 purely through an academic or audit-only lens, this repository approaches ISMS deployment as a structured, end-to-end corporate initiative. By combining **Project Management Principles** with **Information Security Governance**, this workspace demonstrates how to systematically move an organization from business case validation to formal certification readiness.

---

## Strategic Methodology: The Dual-Lens Framework

Every module in this repository is analyzed using a **Dual-Lens Approach** combining **Project Management** (how to build it) with **Audit & Governance** (how to pass the audit).

---

### 1. Project Management Lens (Delivery)
Focuses on running the ISMS setup like a structured corporate project across five phases: **Initiation**, **Planning**, **Execution**, **Monitoring & Controlling**, and **Closing**.

* **Phase & Scope Control:** Setting clear project boundaries and timelines.
* **Milestone & Asset Planning:** Tracking deliverables, inventories, and resources.
* **Risk & Issue Mitigation:** Identifying project blockers before they happen.

---

### 2. Audit & Governance Lens (Quality & Compliance)
Focuses on ensuring all security work satisfies strict third-party audit requirements.

* **Core Concept Synthesis:** Straightforward explanations of ISO 27001 clause requirements.
* **Auditor Evaluation Criteria:** The exact evidence, logs, and questions auditors use to test controls.
* **Implementation Pitfalls:** Common mistakes and operational failure modes to avoid.

---

## Standard & Framework Alignment

* **ISO/IEC 27001:2022** — Information Security Management Systems (Requirements)
* **ISO/IEC 27002:2022** — Information Security Controls (Guidance)

---

## Repository Structure & Project Lifecycle Mapping

```
ISO27001/
├── 00-Reference-and-Foundations/ # Cross-cutting concepts, reference architecture, and general GRC knowledge
├── 01-Initiation/               # Business Case, Stakeholders, Context, and Executive Buy-in
├── 02-Planning/                 # Scope, Asset Inventory, Risk Methodology, Roadmap, and SoA
├── 03-Execution/                # Governance, Sub-Policies, RACI, Training, and Control Rollout
├── 04-Monitoring-and-Control/   # KPIs, Evidence Management, Internal Audit, and Management Review
└── 05-Closing-and-SignOff/      # CAPA Resolution, Certification Audits, and Operational Handover

```

---

## Module Breakdown Across the Implementation Lifecycle along with Mapped to ISO/IEC 27001:2022 Clauses

### Phase 0: Foundations & Reference Workspace
* `00.1-General-Reference-and-Terminology/` — Master glossary of GRC terms, abbreviation registers, and ISO taxonomy mappings. *(Standard Vocabulary Baseline)*
* `00.2-GRC-Framework-Crosswalks/` — Comparative mappings between ISO 27001:2022, NIST CSF, SOC 2, and CIS Controls. *(Framework Interoperability)*
* `00.3-Tooling-and-Evidence-Templates/` — General repository templates, evidence collection guidelines, and Markdown scaffolding notes. *(Operational Support)*

### Phase 1: Project Initiation (Foundations & Context)
* `01.1-Business-Case-and-Context/` — Commercial drivers, executive buy-in, and organizational context. *(Project Governance Baseline)*
* `01.2-ISMS-Operating-Model/` — Structural feedback loops, governance architecture, and operating models. *(Clause 4.4 & Clause 5.3)*
* `01.3-Information-Assets-and-CIA/` — High-level asset identification and CIA impact baseline. *(Clause 6.1.2 & Annex A 5.9)*
* `01.4-ISO-Family-Mapping/` — Comparative analysis of ISO 27001, ISO 27002, and Annex A controls. *(Standard Alignment Baseline)*

### Phase 2: Project Planning (Scope, Risk & Strategy)
* `02.1-Organizational-Context/` — Context registers, internal/external issue analysis. *(Clause 4.1)*
* `02.2-Interested-Parties/` — Regulatory, legal, contractual, and stakeholder requirement registers. *(Clause 4.2)*
* `02.3-ISMS-Scope-Statement/` — Defining physical, logical, operational, and organizational boundaries. *(Clause 4.3)*
* `02.4-Asset-Inventory/` — Detailed asset classification, categorization, and ownership assignment. *(Annex A 5.9, 5.10, 5.11)*
* `02.5-Implementation-Roadmap/` — Project work breakdown structures, milestones, and timelines. *(Clause 6.2)*
* `02.6-Gap-Assessment/` — Clause-by-clause baseline assessment and readiness analysis. *(Clause 6.1.1)*
* `02.7-Risk-Assessment-Methodology/` — Risk criteria, likelihood/impact scoring models, and risk registers. *(Clause 6.1.2)*
* `02.8-Statement-of-Applicability-SoA/` — Annex A control selection, exclusions, and justifications. *(Clause 6.1.3d)*

### Phase 3: Project Execution (Governance & Control Deployment)
* `03.1-Leadership-Commitment/` — Governance structures, resource allocation, and policy sign-off. *(Clause 5.1 & Clause 5.2)*
* `03.2-Information-Security-Policies/` — Policy architecture, operational standards, and SOPs. *(Clause 5.2 & Annex A 5.1)*
* `03.3-Roles-Responsibilities-RACI/` — Control ownership assignment and operational RACI matrices. *(Clause 5.3 & Annex A 5.2)*
* `03.4-Competence-and-Awareness/` — Security awareness program rollout and training tracking. *(Clause 7.2, Clause 7.3 & Annex A 6.3)*
* `03.5-Control-Implementation/` — Deploying technical, administrative, physical, and organizational controls. *(Clause 8.1 & Annex A Controls 5–8)*
* `03.6-Risk-Treatment-Execution/` — Executing mitigation plans and risk treatment schedules. *(Clause 6.1.3 & Clause 8.3)*

### Phase 4: Monitoring & Controlling (Performance & Quality Assurance)
* `04.1-Evidence-Collection/` — Log retention strategies, operational records, and evidence repositories. *(Clause 7.5)*
* `04.2-Monitoring-Measurement-KPIs/` — Measuring security performance, KPIs, and key risk indicators (KRIs). *(Clause 9.1)*
* `04.3-Internal-Audit-Program/` — Independent internal audit planning, testing, and reporting. *(Clause 9.2)*
* `04.4-Management-Review/` — Executive oversight meetings, inputs, decisions, and minute tracking. *(Clause 9.3)*
* `04.5-Nonconformity-and-CAPA/` — Root-cause analysis, corrective action plans, and remediation logs. *(Clause 10.1 & Clause 10.2)*

### Phase 5: Closing & Sign-Off (Certification & Handover)
* `05.1-Certification-Readiness/` — Stage 1 and Stage 2 external audit preparation. *(External Audit Governance)*
* `05.2-Capstone-ISMS-Handover/` — Final portfolio pack, operational handover to steady-state, and project closeout. *(Clause 4.4 & Clause 10.1)*
