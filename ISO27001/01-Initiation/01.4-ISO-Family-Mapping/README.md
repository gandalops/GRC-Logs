## 1. Implementation Sequencing: Avoiding the Annex A-First Trap

The single most common root cause of Stage 2 audit failure is attempting to implement Annex A controls before completing foundational ISMS governance. Selecting safeguards without risk justification yields undefendable controls and invalidates the Statement of Applicability (SoA).

```text
  ┌────────────────────────────────────────────────────────┐
  │ 1. Organizational Context & Stakeholder Expectations  │
  ├────────────────────────────────────────────────────────┤
  │ 2. ISMS Scope Definition & Boundary Setting            │
  ├────────────────────────────────────────────────────────┤
  │ 3. Risk Assessment & Asset Impact Evaluation           │
  ├────────────────────────────────────────────────────────┤
  │ 4. Risk Treatment Plan Formulation                     │
  ├────────────────────────────────────────────────────────┤
  │ 5. Consult Annex A Control References & Build SoA      │
  ├────────────────────────────────────────────────────────┤
  │ 6. Implement Safeguards & Collect Operational Records │
  └────────────────────────────────────────────────────────┘

```

> **Rule of Governance:** Annex A is a selection taxonomy, not a baseline checklist. Controls must be chosen to mitigate identified risks or satisfy legal requirements—never installed blindly.

---

## 2. Statement of Applicability (SoA) Construction Requirements

The SoA is the central matrix evaluated during Stage 2 certification audits. For every one of the 93 controls in Annex A (2022 edition), the document must explicitly record five mandatory data points:

| SoA Component | Field Requirement | Operational Standard |
| --- | --- | --- |
| **1. Applicability State** | Binary (`Yes` / `No`) | Defines whether the control applies to the ISMS scope. |
| **2. Justification** | Specific Risk or Obligation Reference | Must reference a specific Risk Register ID (e.g., `R-012`), contractual clause, or legal requirement. Generic copy-pasted text invalidates the entry. |
| **3. Implementation Status** | Current State | Must reflect real-world status (`Implemented`, `In Progress`, or `Planned`). |
| **4. Linked Documentation** | Policy & Record IDs | Direct references to underlying Documents, Specifications, and Records (e.g., `POL-ACC-001`, `EVD-2026-Q1-LOG`). |
| **5. Exclusion Justification** | Business/Technical Rationale | Required for every control marked `No`. Must prove the associated risk does not exist within the defined scope. |

---

## 3. End-to-End Control Trace: Control A.5.15 (Access Control)

To prove audit-readiness, every applicable safeguard must demonstrate an unbroken chain of custody across standard artifacts:

```text
  ISO/IEC 27001 Annex A 5.15 Reference
         │
         ▼
  ISO/IEC 27002 5.15 Implementation Guidance
         │
         ▼
  Risk Register Linkage (Risk R-004: Unfair Privilege Escalation)
         │
         ▼
  Statement of Applicability (Applicable: Yes | Justification: R-004 + PCI-DSS v4.0)
         │
         ▼
  Governance Policy (POL-ACC-001: Access Management Policy)
         │
         ▼
  Audit Record (EVD-2026-Q1: Signed Quarterly Access Review Log)

```

### Traceability Walkthrough

1. **Annex A 5.15:** Declares the baseline requirement for access control.
2. **ISO 27002 5.15 Guidance:** Informs control design (RBAC, periodic access reviews, identity lifecycle).
3. **Risk Register:** Identifies Risk `R-004` (*Unauthorized access to production financial databases*).
4. **Statement of Applicability:** Marks A.5.15 as `Applicable`, linking it to Risk `R-004` and regulatory obligations.
5. **Policy (`POL-ACC-001`):** Mandates quarterly user access re-certifications.
6. **Record (`EVD-2026-Q1`):** Provides the unedited, dated signature log of the completed Q1 access review.

---

## 4. ISO Family Mapping Failure Modes

| Failure Mode | Root Cause | Operational Consequences | Remediation Strategy |
| --- | --- | --- | --- |
| **Annex A-First Implementation** | Commencing control deployment before running risk assessments. | Unjustified controls, bloated operational overhead, and failure during Stage 2 Clause 6.1.2 audits. | Halt technical rollouts; establish risk mapping back to every active control. |
| **Blanket Applicability (100% Yes)** | Marking all 93 controls applicable without evaluating relevance to shorten planning. | Forces auditors to sample non-existent or irrelevant processes, leading to instant non-conformities. | Formally justify exclusions for irrelevant controls (e.g., physical perimeters for cloud-native setups). |
| **Copy-Paste Justifications** | Using identical justification text across multiple distinct controls in the SoA. | Demonstrates a lack of individual control evaluation to external auditors. | Map each control to its specific Risk IDs, contracts, or statutory duties. |
| **Confusing 27001 with 27002** | Stating in documentation or audits that the organization "complies with ISO 27002." | Reveals a fundamental misunderstanding of standard taxonomy to auditors. | Use ISO 27002 strictly for internal implementation design and reference ISO 27001 for certification compliance. |

```

```
