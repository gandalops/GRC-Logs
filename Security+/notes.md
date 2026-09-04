# Architecture & Framework Mapping Notes

## 1. ISO/IEC 27001:2022 Cryptographic Mapping (Control 8.24)

Across Topics 11 through 18, **ISO/IEC 27001:2022 Annex A Control 8.24 ("Use of Cryptography")** is cited as the primary framework cross-reference. This is an intentional design choice reflecting the 2022 standard update.

### Rationale & Consolidation Context
In the ISO 27001:2022 revision, controls were consolidated from 114 to 93 across 4 themes (Organizational, People, Physical, Technological). **Control 8.24** serves as the single umbrella control governing all sub-disciplines of cryptography.

### Cryptographic Domain Summary

| Domain / Topic | Primary Focus under Control 8.24 | Complementary ISO Controls |
| :--- | :--- | :--- |
| **Symmetric / Asymmetric Encryption** | Data confidentiality, key generation, and rotation rules | Control 8.12 (Data Leakage Prevention) |
| **Key Exchange & HSMs** | Physical/logical protection of root keys and key exchange protocols | Control 8.10 (Information Deletion / Crypto-Erasure) |
| **Hashing & Password Salting** | Data integrity functions and credential storage mechanisms | Control 5.17 (Authentication Information) |
| **Blockchain & DLT** | Distributed consensus hashing and key architecture | Control 8.14 (Redundancy) |
| **Digital Certificates & PKI** | Certificate lifecycle, CA key protection, and revocation | Control 5.15 (Access Control), Control 8.5 (Secure Authentication) |

---

## 2. General Documentation Standards

* **Structure:** All topic files strictly adhere to standardized Markdown formatting with clear table layouts, bulleted technical mechanics, and industry framework cross-references.
* **Future Framework Notes:** Additional standard consolidations, framework overlaps (e.g., NIST SP 800-53 or CIS Controls), or architectural rationale will be logged in this document.
