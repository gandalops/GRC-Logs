# 1.1 General Security Concepts: The CIA Triad

## Overview

The CIA Triad (Confidentiality, Integrity, and Availability)—sometimes referenced as the AIC Triad to avoid confusion with the U.S. Central Intelligence Agency—serves as the foundational model for establishing security policies, evaluating controls, and defining an organization's overall security posture.

---

## 1. Core Objectives of the Triad

The three security objectives define the core goals of information protection:

| Security Objective | Functional Definition | Primary Threats / Risks | Implementation Safeguards |
| :--- | :--- | :--- | :--- |
| **Confidentiality** | Restricts data access strictly to authorized entities and prevents unauthorized disclosure | Data breaches, eavesdropping, unauthorized file access | Encryption (in-transit/at-rest), Access Control Lists (ACLs), Multi-Factor Authentication (MFA) |
| **Integrity** | Guarantees that information remains accurate, untampered, and authentic throughout its lifecycle | Data modification, unauthorized alterations, man-in-the-middle attacks | Hashing algorithms, Digital Signatures, Public Key Infrastructure (PKI) Certificates |
| **Availability** | Ensures operational systems and data remain accessible to authorized users when needed | System outages, hardware failures, Denial of Service (DoS) attacks | Hardware redundancy, Fault Tolerance, continuous system patch management |

---

## 2. Key Mechanisms & Implementation Methods

Security mechanisms operationalize the core objectives across IT environments:

| Mechanism | CIA Pillar | Primary Security Function | Key Examples |
| :--- | :--- | :--- | :--- |
| **Encryption** | Confidentiality | Transforms plaintext into unreadable ciphertext to prevent interception | AES-256, TLS/SSL protocols |
| **Access Controls** | Confidentiality | Limits access permissions based on user identity or department role | Role-Based Access Control (RBAC), Least Privilege |
| **Hashing** | Integrity | Generates fixed-length cryptographic digests to verify data integrity | SHA-256, MD5 checksums |
| **Digital Signatures** | Integrity | Combines hashing and asymmetric encryption to enforce non-repudiation | RSA/ECC signed messages |
| **Fault Tolerance** | Availability | Duplicates critical components to prevent single points of failure | RAID arrays, redundant power supplies |
| **Patch Management** | Availability | Remediates system vulnerabilities to ensure system stability and uptime | Regular OS and software updates |

---

## 3. Industry Framework Cross-References

To contextualize these security objectives within recognized global standards:

* **NIST SP 800-53 Rev. 5:**
  * *Access Control (AC):* Confidentiality & Authentication
  * *System and Communications Protection (SC):* Confidentiality & Integrity (Encryption/Hashing)
  * *System and Information Integrity (SI):* Integrity & Flaw Remediation (Patching)
  * *Contingency Planning (CP):* Availability & Fault Tolerance
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 5.15 (Access control):* Confidentiality
  * *Control 8.8 (Management of technical vulnerabilities):* Availability / Integrity
  * *Control 8.14 (Redundancy of information processing facilities):* Availability
  * *Control 8.24 (Use of cryptography):* Confidentiality & Integrity
* **CIS Critical Security Controls v8:**
  * *Control 3 (Data Protection):* Confidentiality & Integrity
  * *Control 6 (Access Control Management):* Confidentiality
  * *Control 7 (Vulnerability Management):* Availability & Integrity
  * *Control 11 (Data Recovery):* Availability
