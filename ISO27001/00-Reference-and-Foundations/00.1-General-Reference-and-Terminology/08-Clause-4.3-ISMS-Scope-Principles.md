# Clause 4.3 — ISMS Scope Principles

## 1. Intent and Standard Requirements
ISO/IEC 27001:2022 Clause 4.3 mandates that an organization explicitly define the boundaries and applicability of its Information Security Management System (ISMS). Scope defines the formal perimeter around what the ISMS protects, monitors, and certifies.

The standard explicitly requires that the organization shall determine the scope by considering:
1. **Internal & External Context:** Factors identified under Clause 4.1.
2. **Stakeholder Requirements:** Expectations and legal/contractual requirements established under Clause 4.2.
3. **Interfaces and Dependencies:** Operational interactions between the organization and external parties under Clause 4.3(c).

---

## 2. The 6 Scope Dimensions
A comprehensive, defendable scope statement defines system boundaries across six explicit dimensions. Omitting any dimension results in an ambiguous boundary:

```text
┌─────────────────────────────────────────────────────────────────────────┐
│                       THE 6 SCOPE DIMENSIONS                            │
├───────────────────────────────────┬─────────────────────────────────────┤
│ 1. Products & Services            │ 4. Physical & Cloud Locations       │
│    Which offerings are covered.   │    Where systems & teams reside.    │
├───────────────────────────────────┼─────────────────────────────────────┤
│ 2. Business Processes             │ 5. People & Workforce               │
│    Which core workflows run it.   │    Which functions & roles operate. │
├───────────────────────────────────┼─────────────────────────────────────┤
│ 3. Information Assets             │ 6. Technology & Infrastructure      │
│    Which data types are protected.│    Which networks, tools & SaaS run.│
└───────────────────────────────────┴─────────────────────────────────────┘

```

| Dimension | Scope Mapping Focus | Example Implementation Boundary |
| --- | --- | --- |
| **Products / Services** | Specific customer-facing software or service offerings. | Enterprise SaaS Platform & public REST APIs. |
| **Business Processes** | Core operational workflows handling in-scope data. | Software development lifecycle (SDLC), customer onboarding, and incident response. |
| **Information Assets** | Enterprise data categories subject to protection. | Customer PII, source code, production databases, and system logs. |
| **Locations** | Physical offices, data centers, and public cloud regions. | AWS `us-east-1` region and remote workforce endpoints. |
| **People** | Personnel, contractors, and specialized teams. | Engineering, Customer Support, DevOps, and Security operations personnel. |
| **Technology** | Infrastructure, SaaS tools, and network perimeters. | Production Kubernetes clusters, Okta IdP, and GitHub enterprise repositories. |

---

## 3. The Dependency Rule & "Depends On" Test

Clause 4.3(c) introduces the **Dependency Rule**: *An organization cannot exclude an asset, process, or vendor from scope if the security of the ISMS depends upon it.*

```text
  ┌──────────────────────────────────────────────────┐
  │                 EXCLUSION CLAIM                  │
  │  ("We want to exclude this vendor or component") │
  └────────────────────────┬─────────────────────────┘
                           │
                           ▼
  ┌──────────────────────────────────────────────────┐
  │              THE "DEPENDS ON" TEST               │
  │ "Does the ISMS rely on this component/vendor     │
  │  for any security outcome, integrity safeguard,  │
  │  or customer contractual obligation?"            │
  └───────────────┬──────────────────┬───────────────┘
                  │                  │
        YES       │                  │       NO
  ┌───────────────▼────────┐        ┌▼────────────────────────┐
  │   CANNOT EXCLUDE       │        │ LEGITIMATE EXCLUSION    │
  │  Must include as a     │        │ Document formal boundary│
  │  Supplier Dependency   │        │ and reason in Scope.    │
  │  (A.5.19 / A.5.23)     │        └─────────────────────────┘
  └────────────────────────┘

```

### Common Dependency Examples

* **Cloud Infrastructure (AWS/GCP):** Cannot exclude infrastructure simply because it is managed by a third party. Included as a Cloud Supplier Dependency.
* **Third-Party Payment Processors:** Transaction processing environments holding customer data must be included as critical vendor dependencies.
* **Managed Security Service Providers (MSSP/SOC):** External SOC monitoring production systems is directly in scope as a managed security dependency.

---

## 4. Legitimate Exclusion Categories

Exclusions are permitted only when an asset, location, or process has zero functional dependency on the protected information assets within the ISMS. All exclusions require written justification within the Scope Statement:

1. **Separate Legal Entities:** Autonomous corporate subsidiaries with completely isolated infrastructure, separate management teams, and independent regulatory perimeters.
2. **Non-Dependent Business Units:** Internal operations or product lines that never touch, process, or store the information assets defined within the ISMS (e.g., physical retail store software in a company whose ISMS scope covers only cloud payment processing).
3. **Pre-Launch / R&D Capabilities:** Products or environments currently in early development that do not store live production data or interact with customer workloads. (Must be formally added to scope upon commercial production launch).

```

```
