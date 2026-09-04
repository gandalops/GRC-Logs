# 1.11 General Security Concepts: Data Encryption States & Key Protection Mechanisms

## Overview

Data encryption safeguards information across three primary operational states: at rest, in transit, and during storage or processing within databases. Securing these states relies on robust cryptographic algorithms, adequate key lengths, and key stretching techniques designed to withstand brute-force attacks.

---

## 1. Encryption Domains Across Systems & Networks

Security administrators apply specific cryptographic tools and standards depending on where data resides or traverses:

| Deployment Domain | Operational Scope | Native Implementation / Standard | Key Capabilities & Considerations |
| :--- | :--- | :--- | :--- |
| **Full Disk / Volume (Data at Rest)** | Entire storage volume / disk drive | Windows BitLocker, macOS FileVault | Encrypts whole storage media; protects all system and user files on the OS volume. |
| **File-Level (Data at Rest)** | Specific files or directories | Windows EFS (NTFS), 3rd-party software | Encrypts discrete files using advanced attributes without converting the full drive. |
| **Database Encryption** | Transparent or Column-level | Transparent Data Encryption (TDE), Symmetric keys | **Transparent:** Encrypts the entire database file.<br>**Column-Level:** Encrypts specific sensitive fields (e.g., SSNs) to reduce query overhead. |
| **Data in Transit** | Network communications | HTTPS (TLS), Client VPNs (SSL/TLS), Site-to-Site VPNs (IPsec) | Creates encrypted tunnels across public or private networks to prevent eavesdropping. |

---

## 2. Cryptographic Algorithms, Key Strengths, and Hardening

The strength of cryptographic controls depends on open algorithm standards paired with protected, sufficiently complex keys:

* **Algorithm Transparency:** Modern cryptographic algorithms (e.g., AES, DES) are publicly documented. Security relies entirely on maintaining key secrecy, not on hiding algorithm inner workings. Both communicating parties must utilize identical/compatible algorithms.
* **Symmetric Key Sizing:** Minimum 128-bit key lengths are recommended for standard symmetric protection to mitigate brute-force capabilities.
* **Asymmetric Key Sizing:** Requires significantly larger keys (e.g., 3072-bit or higher) to resist mathematical factorization and brute-force attempts as processing power advances.
* **Key Stretching / Strengthening:** A technique that repeatedly runs data or passwords through a cryptographic hashing/encryption algorithm multiple times. This introduces intentional computational overhead, drastically slowing down offline brute-force attacks.

---

## 3. Industry Framework Cross-References

To contextualize cryptographic implementations within recognized global standards:

* **NIST SP 800-53 Rev. 5:**
  * *System and Communications Protection (SC-8):* Protection of Confidentiality/Integrity in Transit
  * *System and Communications Protection (SC-13):* Cryptographic Protection
  * *System and Communications Protection (SC-28):* Protection of Information at Rest
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 8.24 (Use of cryptography):* Mandates data encryption in transit, at rest, and key management standards
* **CIS Critical Security Controls v8:**
  * *Control 3.4 (Enforce Hard Drive Encryption):* Requires automated full-disk encryption on mobile and end-user devices
  * *Control 3.11 (Encrypt Sensitive Data in Transit):* Mandates transport-layer security protocols (TLS, IPsec) for sensitive traffic
