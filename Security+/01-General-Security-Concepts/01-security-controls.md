# 1.0 General Security Concepts: Security Controls Framework

## Overview
Security controls are safeguards or countermeasures designed to preserve the confidentiality, integrity, and availability (CIA triad) of information systems. Controls are evaluated across two primary dimensions: **Category** (how the control is implemented) and **Type** (the operational purpose of the control).

---

## 1. Security Control Categories

Control categories define the underlying mechanism used to put a safeguard into place:

| Category | Implementation Mechanism | Key Examples |
| :--- | :--- | :--- |
| **Technical** | Enforced through hardware, software, or system logic | Firewalls, ACLs, OS permissions, encryption, IDS/IPS |
| **Managerial** | Governance, administrative oversight, and written policies | Security policies, onboarding procedures, compliance auditing |
| **Operational** | Daily processes executed by human personnel | Security guards, awareness training, routine system maintenance |
| **Physical** | Tangible barriers and physical security measures | Locks, fences, bollards, environmental controls, badge readers |

---

## 2. Security Control Types & Functional Matrix

Control types define **what function** the security measure performs relative to an incident:

| Control Type | Functional Objective | Technical | Managerial | Operational | Physical |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Preventive** | Stops an incident before it occurs | Firewall rule | Onboarding policy | ID check at entrance | Deadbolt lock |
| **Deterrent** | Discourages potential attackers | Warning banner | Demotion policy | Security desk | Warning sign |
| **Detective** | Identifies and logs ongoing or past breaches | SIEM / System logs | Audit report review | Guard patrols | Motion sensor |
| **Corrective** | Reverses or mitigates damage after an event | Backup restore | Incident response policy | Calling law enforcement | Fire extinguisher |
| **Compensating** | Temporary alternative when primary control is absent | Port blocking (pre-patch) | Separation of duties | Dual-custody procedures | Backup generator |
| **Directive** | Directs compliance with security practices | Mandatory folder setup | Compliance policy | Security awareness training | "Authorized Only" sign |

---

## 3. Industry Framework Cross-References

To contextualize these controls within recognized global standards:

* **NIST SP 800-53 Rev. 5:**
  * *Access Control (AC):* Technical & Preventive
  * *Physical & Environmental Protection (PE):* Physical & Preventive/Detective
  * *Awareness & Training (AT):* Operational & Directive
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 5.1 (Policies for info security):* Managerial / Directive
  * *Control 7.1 & 7.4 (Physical security perimeters & monitoring):* Physical / Preventive & Detective
  * *Control 8.20 (Network security management):* Technical / Preventive
* **CIS Critical Security Controls v8:**
  * *Control 3 (Data Protection)*
  * *Control 6 (Access Control Management)*
