# 2.3 Threats, Vulnerabilities, and Mitigations: Phishing & Social Engineering Techniques

## Overview

Social engineering leverages human psychological manipulation to trick individuals into divulging confidential information, granting unauthorized system access, or executing financial transactions. Phishing represents the primary communication-based attack vector for initial entry, relying on domain spoofing, typosquatting, and deceptive pretexting to breach security perimeters.

---

## 1. Phishing & Social Engineering Taxonomy

Social engineering attacks vary by delivery mechanism, target specificity, and operational objectives:

| Attack Vector | Communication Medium | Primary Mechanics & Indicators | Defensive Mitigations |
| :--- | :--- | :--- | :--- |
| **Phishing (Email)** | Email | Mass email campaigns using domain spoofing, urgency/fear, embedded malicious links, and fake credential login pages | Email filtering (SPF/DKIM/DMARC), Security Awareness Training (SAT), MFA |
| **Smishing (SMS)** | Short Message Service (SMS) | Text messages impersonating postal services, banks, or delivery alerts containing malicious tracking links | Mobile Threat Defense (MTD), SMS link blocking, user reporting |
| **Vishing (Voice)** | Telephony / VoIP | Phone calls using Caller ID spoofing and technical support or financial verification pretexts | strict identity verification, out-of-band validation, call filtering |
| **Typosquatting** | Web Browsers / DNS | Registering domain names closely resembling legitimate domains (e.g., `professormessor.com` vs. `professormesser.com`) | Brand protection monitoring, proactive domain purchasing, DNS filtering |
| **Pretexting** | Multi-channel (Voice/Email) | Constructing a fabricated scenario or backstory to establish trust and extract credentials or financial data | Verifying requests via independent communication channels, zero-trust culture |

---

## 2. Technical Attack Mechanics & Anomaly Indicators

Recognizing technical anomalies in phishing artifacts is essential for threat analysis and SOC email gateway rule design:

### Email Anomaly Analysis
* **Header & Identity Mismatches:** Discrepancies between the visible "From" display name, the envelope sender address, and actual source servers (e.g., an email claiming to originate from Rackspace support sent via an `@icloud.com` account).
* **Urgency & Coercion Indicators:** Time-sensitive deadlines (e.g., "Account suspended within 24 hours") designed to bypass logical user evaluation and force immediate interaction with payload links.
* **Typographical & Visual Artefacts:** Rendering flaws, poor font consistency, misaligned HTML tables, and odd kerning on cloned login portals.

### Credential Harvesting & Account Takeover (ATO)
* **Look-alike Portals:** Fake login interfaces hosted on attacker-controlled infrastructure designed to record inputted username/password combinations.
* **Secondary Exploitation Vectors:** Once credentials are stolen, threat actors utilize account access to perform password resets across connected third-party services (e.g., PayPal), exfiltrate internal correspondence, or deploy secondary phishing emails from trusted internal accounts.

---

## 3. Industry Framework Cross-References

To contextualize phishing prevention within standard security control frameworks:

* **NIST SP 800-53 Rev. 5:**
  * *Awareness and Training (AT-2):* Security Literacy Training (including phishing identification)
  * *System and Communications Protection (SC-8):* Transmission Confidentiality and Integrity
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 5.14 (Information transfer):* Securing external electronic communication channels
  * *Control 6.3 (Information security awareness, education and training):* Periodic phishing simulation testing and training
* **CIS Critical Security Controls v8:**
  * *Control 14.1 (Establish and Maintain a Security Awareness Program):* Educating users on recognizing phishing, smishing, and social engineering attacks
  * *Control 14.2 (Train Workforce Members to Recognize Social Engineering Attacks):* Targeted testing and simulated attacks to measure resilience
