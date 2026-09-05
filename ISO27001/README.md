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
├── 01-Initiation/               # Business Case, Stakeholders, Context, and Executive Buy-in
├── 02-Planning/                 # Scope, Asset Inventory, Risk Methodology, Roadmap, and SoA
├── 03-Execution/                # Governance, Sub-Policies, RACI, Training, and Control Rollout
├── 04-Monitoring-and-Control/   # KPIs, Evidence Management, Internal Audit, and Management Review
└── 05-Closing-and-SignOff/      # CAPA Resolution, Certification Audits, and Operational Handover

```

---

## Module Breakdown Across the Implementation Lifecycle along with Mapped to ISO/IEC 27001:2022

The table below maps every module deliverable directly to its standard ISO/IEC 27001 requirement clause or Annex A control family.

| Lifecycle Phase | Module Deliverable | ISO/IEC 27001:2022 Mapping | Primary Focus & Standard Requirement |
| :--- | :--- | :--- | :--- |
| **01. Initiation** | `01.1-Business-Case-and-Context` | Project Governance | Establishes commercial drivers and leadership justification. |
| | `01.2-ISMS-Operating-Model` | **Clause 4.4** / **Clause 5.3** | Defines operational security processes and governance loops. |
| | `01.3-Information-Assets-and-CIA` | **Clause 6.1.2** / **Annex A 5.9** | Baseline CIA impact scoring across primary informational assets. |
| | `01.4-ISO-Family-Mapping` | **ISO 27001 / 27002** | Structural relationship between requirements and control guidance. |
| **02. Planning** | `02.1-Organizational-Context` | **Clause 4.1** | Analysis of internal and external issues affecting ISMS outcomes. |
| | `02.2-Interested-Parties` | **Clause 4.2** | Requirement register for legal, regulatory, and contractual stakeholders. |
| | `02.3-ISMS-Scope-Statement` | **Clause 4.3** | Defining physical, logical, operational, and organizational boundaries. |
| | `02.4-Asset-Inventory` | **Annex A 5.9 - 5.11** | Asset ownership, classification, acceptable use, and return protocols. |
| | `02.5-Implementation-Roadmap` | **Clause 6.2** | Security objectives, project milestones, and timeline planning. |
| | `02.6-Gap-Assessment` | **Clause 6.1.1** | Clause-by-clause baseline analysis to determine current readiness. |
| | `02.7-Risk-Assessment-Methodology` | **Clause 6.1.2** | Defining risk criteria, scoring matrices, and impact evaluation models. |
| | `02.8-Statement-of-Applicability-SoA` | **Clause 6.1.3(d)** | Formal selection/exclusion baseline for all Annex A security controls. |
| **03. Execution** | `03.1-Leadership-Commitment` | **Clause 5.1** / **Clause 5.2** | Top management sign-off, resource commitment, and security policy. |
| | `03.2-Information-Security-Policies` | **Clause 5.2** / **Annex A 5.1** | Topic-specific sub-policies, standards, and operational guidelines. |
| | `03.3-Roles-Responsibilities-RACI` | **Clause 5.3** / **Annex A 5.2** | Operational RACI matrix establishing security authorities and duties. |
| | `03.4-Competence-and-Awareness` | **Clause 7.2** / **Clause 7.3** | Security awareness training, competency records, and evaluation. |
| | `03.5-Control-Implementation` | **Clause 8.1** / **Annex A 5-8** | Operational execution of technical, physical, and organizational controls. |
| | `03.6-Risk-Treatment-Execution` | **Clause 6.1.3** / **Clause 8.3** | Executing risk treatment plans and obtaining residual risk acceptance. |
| **04. Monitoring** | `04.1-Evidence-Collection` | **Clause 7.5** | Control of documented information, logging, and evidence repositories. |
| | `04.2-Monitoring-Measurement-KPIs` | **Clause 9.1** | Evaluating security performance through key performance indicators (KPIs). |
| | `04.3-Internal-Audit-Program` | **Clause 9.2** | Independent internal audit schedules, checklists, and audit findings. |
| | `04.4-Management-Review` | **Clause 9.3** | Formal executive management review meetings, inputs, and action items. |
| | `04.5-Nonconformity-and-CAPA` | **Clause 10.1** / **Clause 10.2** | Corrective action management, root cause analysis, and continuous improvement. |
| **05. Closing** | `05.1-Certification-Readiness` | External Audit Prep | Readiness verification for Stage 1 & Stage 2 certification audits. |
| | `05.2-Capstone-ISMS-Handover` | **Clause 4.4** / **Clause 10.1** | Operational handover from implementation project phase to steady-state governance. |
