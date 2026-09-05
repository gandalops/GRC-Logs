# 2.1 Threats, Vulnerabilities, and Mitigations: Threat Actors & Attributes

## Overview

A threat actor is an entity responsible for an event that impacts the security, integrity, or availability of organizational assets. Categorizing threat actors by their origin, resources, sophistication, and motivation enables security teams to perform accurate risk assessments, model operational threat intelligence, and deploy targeted defensive controls.

---

## 1. Threat Actor Categorization & Matrix

Threat actors vary significantly across operational capabilities, funding sources, and attack vectors:

| Threat Actor Category | Location / Origin | Resource & Funding Level | Technical Sophistication | Primary Motivation |
| :--- | :--- | :--- | :--- | :--- |
| **Nation-State / APT** | External (Government) | Extensive (Government-backed) | High / Advanced | Geopolitical advantage, espionage, infrastructure disruption |
| **Organized Crime** | External | High (Financially sustained) | High | Financial gain, extortion (e.g., ransomware) |
| **Hacktivist** | External (Rarely Internal) | Variable / Community-funded | High to Moderate | Ideological, political, or social causes |
| **Insider Threat** | Internal (Employees, Contractors) | Leverages Internal Assets | Moderate to Low | Revenge, financial gain, coercion |
| **Unskilled (Script Kiddie)** | External / Internal | Minimal / Low | Low (Runs pre-built scripts) | Egotism, curiosity, minor disruption |
| **Shadow IT** | Internal (Non-IT Staff) | Departmental Budget | Low to Moderate | Operational convenience, bypassing IT friction |

---

## 2. Technical Mechanics & Attribute Breakdown

Understanding specific attributes helps security operations centers (SOCs) prioritize threat hunting and incident response workflows:

* **Nation-State & Advanced Persistent Threats (APTs):**
  * *Mechanics:* Highly funded entities capable of discovering zero-day vulnerabilities and executing stealthy, persistent, multi-year campaigns (e.g., Stuxnet targeting industrial control systems).
  * *Impact:* Targets critical infrastructure, military networks, and financial institutions to achieve strategic geopolitical objectives.
* **Organized Cybercrime Operations:**
  * *Mechanics:* Functions like formal business enterprises, complete with specialized teams for malware development, initial access brokerage, data sales, and ransomware customer support.
  * *Impact:* Direct financial loss, operational downtime, and widespread exfiltration of sensitive records.
* **Insider Threats & Shadow IT Risks:**
  * *Mechanics:* Insiders bypass perimeter defenses by using legitimate credentials. Shadow IT introduces unauthorized cloud services and infrastructure outside the visibility of IT change management controls.
  * *Impact:* Unauthorized data exposure, lack of regulatory compliance, unmonitored attack surfaces, and missing backups.

---

## 3. Industry Framework Cross-References

To contextualize threat actor profiling within recognized global standards:

* **NIST SP 800-53 Rev. 5:**
  * *Program Management (PM-12, PM-16):* Insider Threat Program and Threat Awareness Program Implementation
  * *Risk Assessment (RA-3):* Threat Identification and Vulnerability Assessment
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 5.7 (Threat intelligence):* Gathering and analyzing information regarding threat actor capabilities and tactics
  * *Control 6.8 (Information security event reporting):* Identifying malicious activity linked to specific threat profiles
* **CIS Critical Security Controls v8:**
  * *Control 17.1 (Establish and Maintain an Incident Response Process):* Incorporates threat actor profiles into escalation playbooks
  * *Control 18.1 (Establish and Maintain a Penetration Testing Program):* Simulates sophisticated external and insider attack vectors
