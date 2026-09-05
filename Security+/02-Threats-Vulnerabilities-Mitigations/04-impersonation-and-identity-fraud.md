# 2.4 Threats, Vulnerabilities, and Mitigations: Impersonation & Identity Fraud

## Overview

Impersonation occurs when a threat actor fraudulently poses as a trusted individual, enterprise role, or reputable authority to gain the trust of a target. By leveraging authority pretexts, social engineering tactics, or technical terminology, attackers manipulate victims into surrendering confidential data (elicitation) or executing unauthorized actions. Unchecked impersonation often serves as the foundational vector for identity fraud.

---

## 1. Impersonation Pretexts & Attack Vectors

Attackers employ a wide variety of operational pretexts to bypass personal and organizational skepticism:

| Pretext Type | Attack Vector / Vehicle | Primary Tactics & Mechanics | Operational Impact |
| :--- | :--- | :--- | :--- |
| **Tech Support / Helpdesk** | Voice (Vishing), Inbound Messaging | Pretends to be internal IT/helpdesk resolving urgent computer errors or system outages. | Credential harvesting, unauthorized remote access, password exposure. |
| **Government / Executive Authority** | Phone, Voicemail, Email | Impersonates government agencies (e.g., Treasury, IRS) or C-suite executives (e.g., VP of Finance) to demand compliance. | Unauthorized wire transfers, regulatory non-compliance fear, rapid data leakage. |
| **Financial / Debt Relief** | Vishing, Automated Calls | Claims fake qualification for 0% interest rates, fraudulent payment updates, or bank error resolutions. | Credit card harvesting, bank routing data extraction. |
| **Identity Fraud Creation** | Multi-channel Reconnaissance | Uses stolen personal identifiable information (PII) to impersonate a victim to third parties. | Fraudulent credit lines, unauthorized bank accounts, tax refund theft. |

---

## 2. Elicitation, Identity Fraud, & Preventive Controls

Understanding how actors extract information and how organizations counter these attempts is critical to building zero-trust human operations:

### Information Elicitation Mechanics
* **Constructed Narrative (Storytelling):** Attackers construct elaborate scenarios requiring confidential items (e.g., Social Security Numbers, corporate credentials, or banking details) under the guise of an urgent operational necessity.
* **Technical Jargon & Overwhelm:** Attackers intentionally deploy complex terms to distract targets, forcing them to defer to the attacker's perceived expertise rather than questioning the legitimacy of the contact.

### Real-World Identity Fraud Impacts
* **Credit & Banking Exploitation:** Attackers open credit accounts using stolen victim PII but direct physical card delivery to attacker-controlled addresses. They can also open fake bank accounts to launder funds or take out non-repayable loans under the victim's identity.
* **Tax & Benefit Fraud:** Submitting fraudulent tax returns using target details to steal government refunds prior to legitimate filing by the victim.

### Defensive & Mitigation Controls
* **Never Volunteer Information:** Strict policy prohibiting the disclosure of credentials, PII, or internal details via phone or unverified messaging. Support teams should never request user passwords.
* **Out-of-Band Verification:** Requiring independent identity verification using verified public numbers or formal internal communication channels before acting on sensitive requests.
* **Formalized Organizational Verification Protocols:** Establishing standard verification frameworks so no employee processes high-risk financial or technical requests at face value.

---

## 3. Industry Framework Cross-References

To align impersonation and identity fraud defenses with established standards:

* **NIST SP 800-53 Rev. 5:**
  * *Personnel Security (PS-7):* Third-Party Personnel Security & Verification
  * *Access Control (AC-2):* Account Management and Identity Verification Controls
  * *Awareness and Training (AT-2):* Literacy Training on Elicitation and Impersonation Defense
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 5.16 (Identity management):* Verification of identities throughout access life cycles
  * *Control 6.3 (Information security awareness, education and training):* Training personnel to counter social engineering and vishing tactics
* **CIS Critical Security Controls v8:**
  * *Control 14.2 (Train Workforce Members to Recognize Social Engineering Attacks):* Specific instruction on detecting vishing, impersonation, and identity fraud tactics
  * *Control 14.5 (Train Workforce on Information Handling Responsibilities):* Guidance on preventing accidental elicitation during routine communications
