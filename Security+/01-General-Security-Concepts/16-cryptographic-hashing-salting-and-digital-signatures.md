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

# 1.15 General Security Concepts: Cryptographic Hashing, Salting & Digital Signatures

## Overview

Cryptographic hashes generate fixed-length digital fingerprints (message digests) from variable-length inputs to guarantee data integrity. Unlike encryption, hashing is a one-way mathematical function and cannot be reversed to restore original plaintexts. Hashes underpin download verification, credential storage through salting mechanisms, and non-repudiation controls via digital signatures.

---

## 2. Digital Signature Operations & Lifecycle

Digital signatures utilize combined asymmetric key operations and cryptographic hashes to deliver **authentication**, **integrity**, and **non-repudiation**:

* **Signature Generation (Sender):**
  1. The plain text message is passed through a hashing algorithm to compute a message digest.
  2. The digest is encrypted using the sender's **Private Key**, creating the digital signature.
  3. The signature is attached to the original message (or sent alongside it) and transmitted to the recipient.
* **Signature Verification (Recipient):**
  1. The recipient receives the plain text message and the attached digital signature.
  2. The recipient decrypts the digital signature using the sender's **Public Key** to reveal the original hash.
  3. The recipient independently hashes the received plain text message.
  4. If the newly computed hash matches the decrypted signature hash, the signature is verified, confirming message integrity and sender authenticity.

---

## 3. Industry Framework Cross-References

To contextualize hashing, salting, and signature mechanisms within recognized global standards:

* **NIST SP 800-53 Rev. 5:**
  * *Identification and Authentication (IA-5):* Authenticator Management (Mandates salted password hashing and stored credential protection)
  * *System and Communications Protection (SC-12, SC-13):* Cryptographic Key and Protection Management (Standardizes Secure Hash Algorithms like SHA-2/SHA-3)
  * *System and Information Integrity (SI-7):* Software, Firmware, and Information Integrity (Digital signature verification for binaries and patches)
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 8.24 (Use of cryptography):* Mandates secure hashing algorithms for password vaults and cryptographic non-repudiation controls
* **CIS Critical Security Controls v8:**
  * *Control 3.3 (Configure Data Access Control Lists):* Protects authentication databases containing salted hashes
  * *Control 5.2 (Use Secure Passwords):* Enforces salted, high-iteration password hashing mechanisms
