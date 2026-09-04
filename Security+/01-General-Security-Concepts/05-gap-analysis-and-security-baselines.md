# 1.4 General Security Concepts: Gap Analysis & Security Baselines

## Overview

A gap analysis is a comprehensive study evaluating an organization's current information security posture against a desired target baseline or standard. By identifying operational weaknesses across people, processes, and systems, the gap analysis provides a strategic roadmap—complete with resource, cost, and time estimates—to bridge security deficiencies and achieve compliance.

---

## 1. Core Components of a Gap Analysis

Performing an effective gap analysis requires evaluating multiple operational domains against defined security benchmarks:

| Analysis Focus Area | Assessment Scope | Core Objectives | Example Evaluation Criteria |
| :--- | :--- | :--- | :--- |
| **Baselines & Standards** | Benchmarks established by recognized framework bodies or custom policy | Defines the target state for compliance and security controls | NIST SP 800-171 Rev. 2, ISO/IEC 27001, organizational security policies |
| **People & Competency** | Formal security experience, role training, and policy awareness | Ensures personnel are capable of executing security responsibilities | Security training records, policy acknowledgement, role-specific certifications |
| **Processes & Systems** | Technical implementation of existing controls vs. formal policies | Identifies operational weaknesses and system-level gaps | Reviewing access provisioning, privileged account management, and system logs |
| **Remediation Roadmap** | Action plan detailing time, budget, and change control requirements | Establishes a phased path to move from the current state to the target baseline | Cost-benefit analysis, hardware procurement, change management scheduling |

---

## 2. Multi-Site Gap Assessment & Prioritization Matrix

Aggregating gap analysis findings across multiple enterprise locations allows organizations to prioritize remediation efforts based on risk severity:

| System Requirement Category | Site Readiness Level | Identified Gap Summary | Recommended Remediation Path |
| :--- | :--- | :--- | :--- |
| **Access Control (AC)** | High Risk (Red) | Lack of centralized identity management and unreviewed privileged accounts | Deploy centralized AAA server (e.g., RADIUS) and enforce quarterly access reviews |
| **Audit & Accountability (AU)** | Moderate Risk (Yellow) | System logging is enabled locally but lacks centralized SIEM aggregation | Integrate local endpoint logs into a centralized SIEM for real-time monitoring |
| **Identification & Auth (IA)** | Low Risk (Green) | MFA implemented across endpoints; minor certificate renewals pending | Standardize PKI automated certificate deployment to address upcoming expirations |
| **System Protection (SC)** | High Risk (Red) | Missing cryptographic enforcement for internal data transmissions | Enforce TLS 1.3 for internal API traffic and deploy VPN concentrators for remote sites |

---

## 3. Industry Framework Cross-References

To contextualize gap analyses and security baselines within recognized global standards:

* **NIST SP 800-53 Rev. 5 / SP 800-171 Rev. 2:**
  * *Program Management (PM-9):* Risk Management Strategy / Baseline Selection
  * *Security Assessment and Authorization (CA-2, CA-7):* Control Assessments and Continuous Monitoring
  * *Access Control (3.1.1 - 3.1.5 in 800-171):* Limit system access to authorized users, processes, and devices
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 5.36 (Compliance with policies and standards for information security):* Verifies adherence to security baselines
  * *Control 8.8 (Management of technical vulnerabilities):* Evaluates system weaknesses through baseline auditing
* **CIS Critical Security Controls v8:**
  * *Control 1 (Inventory and Control of Enterprise Assets):* Establishes baseline visibility of hardware
  * *Control 2 (Inventory and Control of Software Assets):* Establishes baseline visibility of authorized software
  * *Control 4 (Secure Configuration of Enterprise Assets and Software):* Establishes and maintains secure baseline configurations
