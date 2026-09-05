## 11. The 16-Stage ISMS Implementation Sequence

ISO/IEC 27001 implementation follows a strict operational sequence where each phase generates mandatory inputs for subsequent stages. Executing these steps out of order breaks traceability and creates audit findings during certification.

```text
  ┌─────────────────────────────────────────────────────────────────────────┐
  │ 1. Context (4.1) ──► 2. Parties (4.2) ──► 3. Scope (4.3) ──► 4. Policy  │
  └────────────────────────────────────┬────────────────────────────────────┘
                                       │
  ┌────────────────────────────────────▼────────────────────────────────────┐
  │ 5. Roles (5.3) ──► 6. Risk Method (6.1.2) ──► 7. Risk Assessment      │
  └────────────────────────────────────┬────────────────────────────────────┘
                                       │
  ┌────────────────────────────────────▼────────────────────────────────────┐
  │ 8. Treatment (6.1.3) ──► 9. SoA ──► 10. Control Impl. ──► 11. Evidence  │
  └────────────────────────────────────┬────────────────────────────────────┘
                                       │
  ┌────────────────────────────────────▼────────────────────────────────────┐
  │ 12. Int. Audit (9.2) ──► 13. Mgmt Review ──► 14. CAPA ──► 15. Cert Prep │
  └─────────────────────────────────────────────────────────────────────────┘

```

### Stage Input-Output Dependency Matrix

| Stage # | Stage Name (ISO Clause) | Prerequisite Inputs Required | Output Artifact Produced |
| --- | --- | --- | --- |
| **01** | **Context Analysis (4.1)** | Organizational Drivers, Business Goals | Context & Issues Register |
| **02** | **Interested Parties (4.2)** | Context & Issues Register | Regulatory & Stakeholder Matrix |
| **03** | **ISMS Scope (4.3)** | Context + Stakeholder Matrix | Formally Signed ISMS Scope Document |
| **04** | **Top Management Leadership (5.1)** | Scope Document | Executive Charter & Resource Plan |
| **05** | **ISMS Policy & Roles (5.2, 5.3)** | Executive Charter | Top-Level Security Policy & RACI Matrix |
| **06** | **Risk Methodology (6.1.2)** | Asset Categories + Policy Limits | Risk Assessment Methodology |
| **07** | **Risk Assessment Execution** | Risk Methodology + Scope Asset List | Populated Information Risk Register |
| **08** | **Risk Treatment & Objectives (6.1.3)** | Populated Risk Register | Risk Treatment Plan (RTP) & Objectives |
| **09** | **Statement of Applicability (SoA)** | Risk Treatment Plan + Annex A Catalog | Baseline Statement of Applicability |
| **10** | **Control Implementation (8.1)** | SoA + Risk Treatment Plan | Active Controls & Technical Safeguards |
| **11** | **Evidence Accumulation** | Implemented Controls & Specifications | Execution Logs, Records & Metrics |
| **12** | **Internal Audit (9.2)** | 3–6 Months of Records + SoA | Internal Audit Plan & Finding Reports |
| **13** | **Management Review (9.3)** | Internal Audit Report + KRI Trends | Management Review Minutes & Actions |
| **14** | **Corrective Action - CAPA (10.1)** | Management Review Actions + Audit Gaps | Closed Non-Conformity Tracker |
| **15** | **Stage 1 Certification Audit** | Complete Governance Documentation | Stage 1 Audit Report & Readiness Sign-off |
| **16** | **Stage 2 Certification Audit** | Operational Records + Stage 1 Fixes | ISO/IEC 27001 Certification |

---

## 12. Program Duration Benchmarks

The time required to move from initiation to certification depends on organizational complexity, existing security maturity, and resource allocation:

| Implementation Pace | Total Timeline | Target Organization Profile | Operational Risk Level |
| --- | --- | --- | --- |
| **Aggressive** | **6 Months** | Small startups (<30 FTEs), tech-native, single site, dedicated full-time consultant. | **High Risk:** High probability of evidence gaps, team burnout, and superficial processes that fail during year-1 surveillance audits. |
| **Realistic** | **9 Months** | Mid-size firms (50–200 FTEs), moderate complexity, hybrid infrastructure, dedicated ISMS Owner. | **Balanced:** Recommended velocity for sustainable governance, proper change management, and solid evidence collection. |
| **Sustainable** | **12 Months** | Enterprises (>200 FTEs), multi-entity, strict regulatory requirements (e.g., Fintech, Healthcare). | **Low Risk:** Ensures deep integration, thorough internal audits, and seamless long-term operational maintenance. |

---
