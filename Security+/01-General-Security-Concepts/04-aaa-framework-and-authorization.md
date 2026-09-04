# 1.3 General Security Concepts: AAA Framework & Authorization Models

## Overview

The AAA framework (Authentication, Authorization, and Accounting) provides a structured architecture for managing access control across systems and networks. By enforcing identity verification, restricting system permissions, and recording user activity, the framework safeguards enterprise assets while supporting scalable identity management via centralized servers and role-based abstraction.

---

## 1. AAA Framework Core Pillars

The AAA framework separates access management into three distinct functional steps:

| AAA Pillar | Core Functional Purpose | Primary Objective | Typical Technical Controls |
| :--- | :--- | :--- | :--- |
| **Authentication** | Verifies the identity claimed during the initial identification step | Confirms "Who you are" using credentials or certificates | Passwords, MFA, PKI Device Certificates, Centralized AAA Servers (e.g., RADIUS/TACACS+) |
| **Authorization** | Determines the scope of access and permissions granted to a verified identity | Limits "What you can do" based on policy or organizational role | Role-Based Access Control (RBAC), Group Policies, Access Control Lists (ACLs) |
| **Accounting** | Records user sessions, executed commands, resource usage, and timestamps | Ensures "What you did" is logged for auditing and compliance | Audit logs, SIEM integration, session connection/disconnect logs |

---

## 2. Authentication Methods & Authorization Scalability

Access control strategies must balance strong identity verification with administrative scalability across large enterprise environments:

| Implementation Concept | Architectural Approach | Administrative Advantage | Operational Example |
| :--- | :--- | :--- | :--- |
| **Centralized AAA Server** | Separates the network device (e.g., VPN concentrator) from the identity database | Centralizes credential management across thousands of endpoints | A VPN concentrator queries a central AAA server to validate remote user logins |
| **PKI Device Authentication** | Issues digitally signed device certificates via a Certificate Authority (CA) | Authenticates headless/remote machines securely without storing static passwords | Corporate laptops present a CA-signed device certificate to access internal resources |
| **Direct Mapping (Non-Scaled)** | Assigns permissions directly to individual user accounts | Simple for isolated users or very small environments | Manually granting one user access to specific shipping label files |
| **Group-Based Abstraction (Scaled)** | Places users into administrative groups that hold resource permissions | Scales effortlessly across hundreds or thousands of users and systems | Adding 100 employees to a "Shipping & Receiving" group to automatically inherit necessary rights |

---

## 3. Industry Framework Cross-References

To contextualize AAA and authorization models within recognized global standards:

* **NIST SP 800-53 Rev. 5:**
  * *Access Control (AC-2, AC-3, AC-6):* Account Management, Access Enforcement, and Least Privilege
  * *Identification and Authentication (IA-2, IA-5):* Identification and Authentication (Organizational Users & Authenticator Management)
  * *Audit and Accountability (AU-2, AU-12):* Event Logging and Audit Record Generation
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 5.15 (Access control):* Enforces access rights in alignment with business requirements
  * *Control 5.16 (Identity management):* Manages the full lifecycle of digital identities
  * *Control 8.15 (Logging):* Records user activity, exceptions, and security events
* **CIS Critical Security Controls v8:**
  * *Control 5 (Account Management):* Manages access credentials and enterprise user accounts
  * *Control 6 (Access Control Management):* Enforces role-based and centralized access controls
  * *Control 8 (Audit Log Management):* Collects, alerts, and retains detailed accounting logs
