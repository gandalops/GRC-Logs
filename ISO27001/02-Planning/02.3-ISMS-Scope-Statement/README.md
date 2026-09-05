# 02.3 Determining the ISMS Scope Execution Guide

The Scope Statement is the single most heavily audited document in an Information Security Management System (ISMS). Defining a scope that is too narrow produces a meaningless certificate, while defining a scope that is too broad causes program execution to stall. Getting the scope right ensures that every downstream risk assessment, policy, and Annex A control points to a well-defined boundary.

---

## 1. Document Schema: The 4-Section Scope Statement

An audit-ready Scope Statement must be a concise, formal document (typically 1–2 pages) structured into four explicit sections:

```text
┌─────────────────────────────────────────────────────────────────────────┐
│                       ISMS SCOPE STATEMENT SCHEMA                       │
├─────────────────────────────────────────────────────────────────────────┤
│ 1. INCLUSIONS STATEMENT                                                 │
│    Explicitly defines the 6 scope dimensions (Products, Processes,      │
│    Assets, Locations, People, Technology).                              │
├─────────────────────────────────────────────────────────────────────────┤
│ 2. DEFENDABLE EXCLUSIONS & JUSTIFICATIONS                               │
│    Lists excluded entities or product lines with written rationales     │
│    anchored to legitimate exclusion categories.                         │
├─────────────────────────────────────────────────────────────────────────┤
│ 3. SUPPLIER & INTERFACE DEPENDENCIES                                    │
│    Identifies critical external providers (Cloud, SaaS, MSSP)           │
│    that support in-scope assets under the Dependency Rule.              │
├─────────────────────────────────────────────────────────────────────────┤
│ 4. GOVERNANCE APPROVAL & REVISION LOG                                   │
│    Contains top management sign-off (CISO/CEO), timestamps, and         │
│    formal annual/event-driven review schedules.                         │
└─────────────────────────────────────────────────────────────────────────┘

```

### Mandatory Section Specifications

1. **Inclusions Statement:** Captures the core boundary using unambiguous business and technical language.
> *Example:* "The ISMS applies to the information security management of the Enterprise Cloud Platform and supporting public REST APIs, including all customer data processing workflows, operated by Engineering, Product, and Support personnel across remote workforce locations and AWS `us-east-1` cloud infrastructure."


2. **Defendable Exclusions:** Documents what is excluded along with an explicit rationale proving the exclusion does not impact in-scope security.
> *Example Exclusion:* "Physical retail point-of-sale software is EXCLUDED. Rationale: Operates on a completely segmented network under a separate corporate legal entity with no shared infrastructure or data flows to the Enterprise Cloud Platform."


3. **Supplier & Interface Dependencies:** Lists third-party entities that host, process, or monitor in-scope data.
> *Example Dependencies:* "AWS (Cloud Hosting - A.5.23), Okta (Identity Provider - A.5.19), Datadog (Log Monitoring - A.8.15)."


4. **Governance Approval:** Formal sign-off block including executive role, signature, approval date, and next review date.

---

## 2. Avoiding the "Convenient Exclusion" Trap

The most common scope failure is attempting to exclude messy, complex, or unmanaged operational areas (e.g., legacy codebases, customer support teams, marketing databases) to make certification easier.

```text
  ┌───────────────────────────────┐
  │   Proposed Scope Exclusion    │  (e.g., "Exclude Customer Support Team")
  └───────────────┬───────────────┘
                  │
                  ▼
  ┌───────────────────────────────┐
  │     Dependency Interrogation  │  "Does Customer Support access, handle,
  └───────────────┬───────────────┘   or view in-scope customer PII?"
                  │
                  ├─── YES ───► [CONVENIENT EXCLUSION TRAP DETECTED]
                  │             Exclusion invalid; auditor will flag finding.
                  │
                  └─── NO  ───► [LEGITIMATE EXCLUSION]
                                Document isolation proof in Scope Statement.

```

### How Auditors Spot Convenient Exclusions

* **Data Flow Tracing:** Auditors trace sample data packets or customer support tickets. If an "excluded" team handles in-scope data, the exclusion fails.
* **Shared Infrastructure Scans:** If an excluded legacy application shares a database or network subnet with an in-scope system, the boundary is breached.

---

## 3. Change Control Triggers

The Scope Statement is a dynamic governance document. It must be formally re-evaluated upon reaching any of the following operational triggers:

* **1. Product Launches:** Expanding services, introducing new product lines, or deploying major software features.
* **2. Architectural Migrations:** Moving workloads to new public cloud providers, opening new physical offices, or changing identity providers.
* **3. Corporate Restructuring:** Mergers, acquisitions, divestitures, or establishing new operating subsidiaries.
* **4. Regulatory Adjustments:** Entry into new geographic markets or onboarded statutory frameworks with strict data residency boundaries.
* **5. Annual Governance Cadence:** Mandatory review as part of the annual Clause 9.3 Management Review.

---

## 4. Six Implementation Failure Modes & Mitigation Strategies

| Failure Mode | Operational Root Cause | Audit Impact | Mitigation Strategy |
| --- | --- | --- | --- |
| **1. Convenient Exclusions** | Excluding messy or non-compliant departments (e.g., Support, Sales CRM) to pass the audit easily. | Major non-conformity during Stage 1/Stage 2 data-flow tracing. | Apply the "depends on" test to every boundary claim before finalizing scope. |
| **2. Unjustified Exclusions** | Marking components as "Out of Scope" or "Not Applicable" without written rationales. | Audit finding for non-compliance with Clause 4.3 documentation rules. | Document explicit, contextual justifications referencing one of the 3 legitimate categories. |
| **3. Supplier Omission** | Excluding cloud hosts, SaaS tools, or SOC providers because they are operated by third parties. | Fails Clause 4.3(c); leaves critical external attack vectors unmonitored. | Include all supporting third parties in the Scope Statement under *Supplier Dependencies*. |
| **4. Organizational Box Scoping** | Defining scope by department names (e.g., "The IT Dept") rather than data and systems. | Leaves cross-departmental data flows and vendor tools unmanaged. | Scope by information assets, business processes, and technology stacks—not org charts. |
| **5. Unsigned / Undated Document** | Maintaining a Scope Statement without executive signatures or formal version history. | Auditor treats scope as an informal staff opinion rather than top management intent. | Secure signed executive sign-off (CEO/CISO) with clear approval dates and review cadences. |
| **6. Frozen Boundaries** | Keeping the exact same scope document for years while the company expands architecture or products. | Non-conformity for failing to review and update system boundaries alongside business growth. | Tie scope review workflows directly to corporate change management and product launch checklists. |

```

```
