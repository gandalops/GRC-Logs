# 1.14 General Security Concepts: Data Obfuscation, Steganography & Masking Techniques

## Overview

Data obfuscation takes clear, easily understandable information and conceals it in plain sight to prevent unauthorized analysis. Unlike strong mathematical encryption, obfuscation often relies on process secrecy or non-mathematical substitution mechanisms. Reversing obfuscation requires knowledge of the exact hiding method, substitution scheme, or token lookup table.

---

## 1. Obfuscation Approaches & Implementation Mechanics

Security teams deploy distinct obfuscation strategies depending on the data type and network transmission constraints:

| Technique | Operating Mechanism | Typical Use Cases / Examples | Key Security Attributes |
| :--- | :--- | :--- | :--- |
| **Steganography** | Conceals secret data ("concealed writing") within a covertext media object. | Image files, network TCP packet headers, audio/video tracks, printer yellow Machine Identification Codes (MIC). | Represents security through obscurity; easily reversed if the concealment algorithm is known. |
| **Tokenization** | Replaces sensitive data with a non-sensitive surrogate value (token) with no mathematical relationship to the original data. | Mobile contactless payments (Apple/Google Pay), Social Security Number (SSN) substitution. | Uses single-use, temporary tokens stored in local secure enclaves and validated via remote Token Service Servers. |
| **Data Masking** | Hides specific portions of sensitive data fields while displaying remaining digits for verification. | Payment receipts showing only the last 4 credit card digits, customer support views. | Prevents credential theft on printed outputs or internal employee views. |

---

## 2. Tokenization Transaction Lifecycle

Contactless payment security relies on dynamic tokenization to isolate credit card numbers from network traffic:

1. **Registration:** Mobile device registers a payment card with a remote **Token Service Server**.
2. **Token Provisioning:** Server issues a pool of one-time-use tokens stored on the mobile device.
3. **Point of Sale Transmission:** The device transmits a temporary token to the merchant via Near Field Communication (NFC).
4. **Validation & Resolution:** The merchant passes the token to the Token Service Server, which performs a secure database lookup to resolve the actual account details and approve the payment.
5. **Token Invalidation:** The used token is discarded locally, ensuring captured traffic cannot be replayed by attackers.

---

## 3. Industry Framework Cross-References

To contextualize obfuscation mechanisms within recognized global standards:

* **NIST SP 800-53 Rev. 5:**
  * *System and Communications Protection (SC-28):* Protection of Information at Rest (Tokenization/Masking)
  * *System and Information Integrity (SI-3):* Malicious Code Protection (Analyzing steganographic covertext payloads)
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 8.11 (Data masking):* Mandates data masking and tokenization rules in alignment with organization access policies
* **CIS Critical Security Controls v8:**
  * *Control 3.3 (Configure Data Access Control Lists):* Restricts plain-text exposure using role-based data masking
  * *Control 3.4 (Enforce Hard Drive Encryption):* Complements tokenization to secure backend token vault databases
