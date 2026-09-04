# 1.15 General Security Concepts: Cryptographic Hashing, Salting & Digital Signatures

## Overview

Cryptographic hashes generate fixed-length digital fingerprints (message digests) from variable-length inputs to guarantee data integrity. Unlike encryption, hashing is a one-way mathematical function and cannot be reversed to restore original plaintexts. Hashes underpin download verification, credential storage through salting mechanisms, and non-repudiation controls via digital signatures.

---

## 1. Cryptographic Hash Characteristics & Implementations

Hashing functions rely on uniform output properties and collision resistance to safeguard data:

| Feature / Concept | Technical Mechanics | Security Impact & Applications |
| :--- | :--- | :--- |
| **Fixed Output & Avalanche Effect** | Changes to a single input character drastically alter the generated hexadecimal hash string (e.g., SHA-256 yields 64 hex characters). | Prevents output predictability and verifies exact file integrity during downloads (e.g., Linux ISOs). |
| **Collision Resistance** | Algorithmic requirement preventing two distinct inputs from generating an identical output hash. | Cryptographic failure in legacy algorithms like **MD5** allowed collisions, making MD5 deprecated for security applications. |
| **Password Salting** | Appends unique, random data strings to user passwords prior to hashing. | Generates distinct hashes for identical passwords, invalidating pre-computed **rainbow tables** and forcing computationally expensive brute-force attacks. |

---

## 2. Digital Signature Operations & Lifecycle

Digital signatures utilize combined asymmetric key operations and cryptographic hashes to deliver **authentication**, **integrity**, and **non-repudiation**:
