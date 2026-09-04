# Core Security Principles (CIA Triad)

| Security Objective | Core Purpose | Implementation Methods |
| :--- | :--- | :--- |
| **Confidentiality** | Restricts information access exclusively to authorized individuals and prevents unauthorized exposure. | • Data Encryption (symmetric/asymmetric)<br>• Access Control Lists (ACLs) & Role-Based Access<br>• Multi-Factor Authentication (MFA) |
| **Integrity** | Guarantees that data remains unaltered, accurate, and trustworthy during transmission and storage. | • Cryptographic Hashing<br>• Asymmetric Digital Signatures<br>• PKI Certificates<br>• Non-repudiation controls |
| **Availability** | Ensures operational systems and data remain continuously accessible to authorized users when needed. | • Fault-tolerant infrastructure<br>• System redundancy<br>• Routine patch management |

### Key Takeaways

* **Terminology Distinctions:** The CIA Triad is sometimes ordered as AIC to prevent confusion with the US Central Intelligence Agency, though both terms represent the same core security objectives.
* **Confidentiality Mechanics:** Access management isolates data by operational roles (e.g., granting marketing teams presentation access while blocking access to financial records), supported by robust authentication steps.
* **Integrity & Trust:** Hashing verifies that incoming data matches the sender's original transmission; digital signatures extend this by combining asymmetric encryption to validate both data accuracy and origin identity.
* **Non-Repudiation:** Assures system logs and cryptographic proofs bind transactions to specific origins, preventing users from denying their actions.
* **Operational Availability:** Continuous uptime requires proactive software updating and fault-tolerant architecture to eliminate single points of failure.

---

### Standard Mapping

* **NIST SP 800-53 Rev. 5:**
  * AC-1 through AC-25 (Access Control)
  * SC-8 (Transmission Confidentiality and Integrity)
  * SC-12 (Cryptographic Key Establishment and Management)
  * CP-1 through CP-13 (Contingency Planning)
* **ISO/IEC 27001:2022 / ISO/IEC 27002:2022 Annex A:**
  * A.5.15 (Access Control)
  * A.8.24 (Use of Cryptography)
  * A.8.14 (Redundancy of Information Processing Facilities)
* **CIS Critical Security Controls v8:**
  * Control 3: Data Protection
  * Control 6: Access Control Management
  * Control 7: Continuous Vulnerability Management
