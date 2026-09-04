# 1.2 General Security Concepts: Non-Repudiation & Cryptographic Integrity

## Overview

Non-repudiation provides indisputable proof of data origin and integrity, preventing a sender from denying the authenticity of a transmitted message or transaction. It builds upon cryptographic integrity mechanisms by combining hashing algorithms with asymmetric public key infrastructure (PKI).

---

## 1. Integrity vs. Origin Proof Mechanics

Achieving full non-repudiation requires combining proof of integrity with proof of origin:

| Security Objective | Cryptographic Mechanism | Capabilities | Limitations |
| :--- | :--- | :--- | :--- |
| **Proof of Integrity** | Cryptographic Hashing (e.g., SHA-256) | Detects any alteration or tampering of data in-transit or at-rest (avalanche effect). | Cannot verify *who* generated the data; lacks identity association. |
| **Proof of Origin** | Asymmetric Encryption (Sender's Private Key) | Authenticates the exact sender identity; assures non-repudiation. | Requires key management infrastructure (PKI) to distribute public keys. |
| **Non-Repudiation** | Digital Signatures (Hash + Private Key Encryption) | Validates both data integrity and sender identity simultaneously. | Dependent on the absolute secrecy and protection of the sender's private key. |

---

## 2. Digital Signature Lifecycle Matrix

Digital signatures operationalize non-repudiation through a dual-stage process: creation (signing) and validation (verifying).

| Operational Stage | Execution Process | Technical Action | Operational Outcome |
| :--- | :--- | :--- | :--- |
| **1. Digest Creation** | Sender side | Runs plaintext message through a hashing function | Generates a unique, fixed-length message digest (fingerprint) |
| **2. Signature Generation** | Sender side | Encrypts the resulting digest using the **sender's private key** | Produces the digital signature attached to the plaintext |
| **3. Decryption & Verification** | Recipient side | Decrypts the signature using the **sender's public key** | Extracts the original message digest created by the sender |
| **4. Integrity Validation** | Recipient side | Hashes the received plaintext and compares it to the decrypted digest | **Match:** Validates integrity + origin<br>**Mismatch:** Indicates tampering or key failure |

---

## 3. Industry Framework Cross-References

To contextualize non-repudiation and cryptographic integrity within recognized global standards:

* **NIST SP 800-53 Rev. 5:**
  * *System and Communications Protection (SC-8):* Protection of Confidentiality and Integrity
  * *System and Communications Protection (SC-12):* Cryptographic Key Establishment and Management
  * *System and Information Integrity (SI-7):* Software, Firmware, and Information Integrity
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 8.24 (Use of cryptography):* Enforces policies on key management and digital signatures
  * *Control 8.12 (Data leakage prevention):* Protects integrity and prevents unauthorized transmission
* **CIS Critical Security Controls v8:**
  * *Control 3.14 (Authenticate Application Data Transmissions):* Enforces digital signatures and PKI authentication
  * *Control 6.8 (Configure Centralized Access Management):* Manages cryptographic identity credentials
