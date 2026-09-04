# 1.10 General Security Concepts: Public Key Infrastructure & Cryptographic Foundations

## Overview

Public Key Infrastructure (PKI) encompasses the hardware, software, policies, and procedures required to create, distribute, manage, store, and revoke digital certificates. By binding cryptographic keys to verified user or device identities, PKI serves as a foundational layer for identity verification, secure communication, and data confidentiality across enterprise environments.

---

## 1. Cryptographic Paradigm Comparison

Symmetric and asymmetric encryption algorithms address different security and performance operational requirements:

| Feature / Metric | Symmetric Encryption | Asymmetric Encryption |
| :--- | :--- | :--- |
| **Key Architecture** | Single shared secret key for both encryption and decryption | Pair of mathematically related keys: one **Public Key** and one **Private Key** |
| **Key Access Control** | Must be kept strictly secret between authorized parties | Public key is freely distributed; Private key is kept strictly confidential |
| **Computational Speed** | Fast execution speed with minimal computational overhead | Slower execution with higher computational overhead |
| **Scalability** | Poor scalability; managing/distributing shared keys across 10+ endpoints is difficult | High scalability; public keys can be published freely without exposing private keys |
| **Primary Use Cases** | Bulk data encryption, disk encryption, fast data transmission | Key exchange, digital signatures, non-repudiation, PKI authentication |

---

## 2. Asymmetric Key Operations & Management

Asymmetric encryption relies on specific mathematical properties to perform key generation, encryption flows, and long-term key management:

* **Key Pair Generation:** Public and private key pairs are generated simultaneously using large prime numbers and cryptographic randomization. Although mathematically linked, the private key cannot be derived or reverse-engineered from the public key.
* **Encryption / Decryption Mechanics:**
  * **Sender Action:** Plaintext is encrypted using the recipient's **Public Key** to generate ciphertext.
  * **Recipient Action:** The recipient uses their unique **Private Key** to decrypt the ciphertext back into plaintext. No other key can decrypt the message.
  * **Local Protection:** Private keys are secured locally using strong passphrases/passwords to prevent unauthorized extraction.
* **Key Escrow & Recovery:** Enterprise environments often utilize **key escrow**—storing private key copies securely with a trusted third party or local system—to ensure data recovery if an employee departs or keys are lost.

---

## 3. Industry Framework Cross-References

To contextualize PKI and cryptographic controls within recognized global standards:

* **NIST SP 800-53 Rev. 5:**
  * *Identification and Authentication (IA-5):* Authenticator Management (PKI Certificate and Key Management)
  * *System and Communications Protection (SC-12):* Cryptographic Key Establishment and Management
  * *System and Communications Protection (SC-13):* Cryptographic Protection
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 8.24 (Use of cryptography):* Enforces policies on key management, lifecycle, and encryption algorithms
* **CIS Critical Security Controls v8:**
  * *Control 3 (Data Protection):* Mandates standard encryption algorithms for data in transit and at rest
  * *Control 6 (Access Control Management):* Uses PKI digital certificates for multifactor authentication and device identification
