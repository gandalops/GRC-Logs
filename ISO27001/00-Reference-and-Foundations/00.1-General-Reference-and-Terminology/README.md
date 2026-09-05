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
