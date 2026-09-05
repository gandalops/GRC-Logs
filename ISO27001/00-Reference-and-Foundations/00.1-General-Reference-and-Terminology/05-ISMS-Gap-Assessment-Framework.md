## 13. ISMS Gap Assessment Framework

An **ISMS Gap Assessment** is a structured quantitative evaluation performed during program initiation to measure an organization’s current operational state against the mandatory requirements of ISO/IEC 27001. Rather than evaluating technical controls, it establishes an objective governance baseline to define resource requirements, funding needs, and the implementation timeline.

---

## 14. Scope Focus: Clauses 4–10 vs. Annex A

A fundamental governance boundary must be maintained between management system requirements and technical safeguard selection:

```text
  ┌────────────────────────────────────────────────────────┐
  │ Gap Assessment Focus: Clauses 4–10 (Management System) │
  │ ├─ Context, Leadership, Planning, Support, Operations, │
  │ └─ Performance Evaluation, Continual Improvement       │
  └──────────────────────────┬─────────────────────────────┘
                             │
                             ▼ Generates Risk Treatment & SoA
  ┌────────────────────────────────────────────────────────┐
  │ Statement of Applicability Focus: Annex A (Safeguards) │
  │ ├─ Organisational, People, Physical, Technological     │
  └────────────────────────────────────────────────────────┘

```

* **Clauses 4–10 (Management System Scope):** The Gap Assessment **only** measures compliance against the core management system clauses. Evaluating Annex A controls at this initial phase is prohibited because control applicability cannot be established prior to completing the risk assessment (Clause 6.1.2) and generating the Statement of Applicability (Clause 6.1.3).
* **Annex A Controls (Risk Treatment Scope):** Evaluated later in the sequence. Assessing all 93 Annex A safeguards upfront creates unnecessary administrative overhead and produces undefendable applicability scores.

---

## 15. The 3-Tier Evaluation Scoring Methodology

To prevent binary pass/fail distortion, each requirement across Clauses 4–10 is scored using a 3-tier evaluation taxonomy:

| Compliance Rating | Technical & Operational Definition | Actionable Program Impact |
| --- | --- | --- |
| **Compliant** | The requirement is fully established, operational, and supported by unedited evidence records. | **Maintain:** No project remediation work required. |
| **Partially Compliant** | Processes exist informally or partially, but lack full documentation, operational consistency, or evidence artifacts. | **Refine:** Needs formalization, policy mapping, or record integration. |
| **Non-Compliant** | The requirement is completely unaddressed, missing, or functionally absent. | **Build:** Requires design and implementation from ground zero. |

> **Evaluation Rule:** Ratings must be backed by tangible evidence. In the absence of verifiable records or signed documentation, the clause must be rated **Non-Compliant** regardless of verbal assertions.

---

## 16. Standard Gap Analysis Report Structure

The primary deliverable of the initiation phase is a 7-part executive **Gap Analysis Report** structured for leadership sign-off and project funding authorization:

1. **Executive Summary:** High-level summary of organizational readiness, key baseline metrics, and primary compliance obstacles.
2. **Program Scope:** Explicit statement defining the target organizational boundaries and confirming that evaluation was restricted to Clauses 4–10.
3. **Assessment Methodology:** Explanation of the 3-tier scoring scale, evidence verification standards, and interview parameters.
4. **Detailed Findings Matrix:** Itemized clause-by-clause breakdown listing current operational status, gap descriptions, and missing evidence artifacts.
5. **Quantitative Summary:** Statistical distribution table detailing the count and percentage of Compliant, Partially Compliant, and Non-Compliant clauses.
6. **Prioritized Remediation Roadmap:** Sequenced implementation plan prioritizing Non-Compliant gaps before Partial gaps in alignment with the 16-stage roadmap.
7. **Resource & Budget Estimate:** Financial, tooling, and headcount projections required to achieve full certification readiness.

```
