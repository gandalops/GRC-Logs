# 2.2 Threats, Vulnerabilities, and Mitigations: Threat Vectors & Attack Surfaces

## Overview

A threat vector (or attack vector) is the specific path, technique, or medium an attacker uses to gain unauthorized access to a network, system, or sensitive data asset. Threat actors continuously scan for both known and zero-day attack vectors to bypass security controls. Securing an enterprise environment requires mapping these entry points across messaging channels, active files, physical interfaces, network services, and third-party supply chains.

---

## 1. Threat Vector Classifications & Attack Surfaces

Threat vectors span physical, digital, and human entry points. The table below summarizes primary vectors, operational mechanics, and security mitigation strategies:

| Threat Vector Category | Primary Mechanics & Methods | Key Risks & Vulnerabilities | Defensive Mitigations |
| :--- | :--- | :--- | :--- |
| **Messaging Vectors** | Phishing via Email, SMiShing (SMS), Direct Messaging (DM/IM) | Malicious links, credential harvesting pages, invoice scams | Email filtering (SPF/DKIM/DMARC), user awareness training, MFA |
| **Image & File Payloads** | Embedded scripts in SVG (XML/XSS), malicious PDF objects, compressed archives (ZIP/RAR) | Execution of client-side code, obfuscated malware payloads | Input validation, content disarm & reconstruction (CDR), sandboxing |
| **Office & Browser Extensions** | VBA Macros in Office documents, malicious browser add-ins/extensions | Data exfiltration, keylogging, administrative access abuse | Disabling macros via GPO, extension whitelisting/signed manifests |
| **Voice & Dialing (Vishing)** | Voice phishing, spam over IP (VoIP), automated war dialing | Social engineering, credential coercion, unauthorized remote modems | Call authentication, strict identity verification protocols |
| **Physical & Removable Media** | USB rubber ducky (HID spoofing), dropped flash drives, air-gap bridging | Autorun execution, keystroke injection, physical data exfiltration | Disabling USB ports/storage policies, Endpoint Protection (EDR) |
| **Network & Wireless** | Rogue access points, legacy protocols (WEP/WPA/WPA2), open/unused TCP ports | Eavesdropping, unauthorized network traversal, lateral movement | Upgrading to WPA3, implementing 802.1X NAC, port filtering |
| **Supply Chain & Third-Party** | Compromised Managed Service Providers (MSPs), supply chain tampering, counterfeit hardware | Trusted lateral access from external vendor networks into sensitive subnets | Network segmentation, vendor risk management (TPRM), zero trust |

---

## 2. Technical Mechanics & Attack Surface Management

Managing attack surfaces requires continuous monitoring and strict configuration management across operational environments:

### Message & Web Application Attacks
* **Scalable Vector Graphics (SVG) Exploitation:** SVG files are XML-based vector image formats. Because SVG files support embedded HTML and JavaScript tags (`<script>`), opening or rendering an untrusted SVG image in a browser can execute client-side Cross-Site Scripting (XSS) attacks.
* **Server-Side Software & Open Ports:** Opening network ports (e.g., TCP 80, 443, 22) exposes running application daemons to external traffic. Misconfigurations or unpatched software running on these ports allow attackers to execute remote code attacks or gain initial access.

### Hardware & Removable Media Exploitation
* **Human Interface Device (HID) Spoofing:** Modified USB devices can emulate standard USB keyboards. When plugged into a target machine—even across air-gapped networks—the OS registers the device as a keyboard and automatically executes scripted keystrokes (e.g., launching PowerShell commands to fetch remote payloads).

### Legacy Systems & Default Credentials
* **Unsupported / End-of-Life (EOL) Systems:** Software and hardware no longer receiving vendor updates present unpatchable attack vectors. Attackers active on internal subnets target unmonitored EOL systems to establish persistence.
* **Default Credentials:** Out-of-the-box administrative credentials (e.g., `admin/admin`) on routers, access points, and IoT devices are publicly documented. Failure to enforce mandatory credential changes upon deployment leaves management interfaces vulnerable to automated exploitation.

---

## 3. Industry Framework Cross-References

To contextualize threat vectors and attack surface management within recognized global governance frameworks:

* **NIST SP 800-53 Rev. 5:**
  * *Access Control (AC-18, AC-19):* Wireless Access and Access Control for Mobile Devices
  * *System and Communications Protection (SC-7, SC-38):* Boundary Protection and Operations Security
  * *Supply Chain Risk Management (SR-3, SR-5):* Supply Chain Controls and Acquisition Procedures
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 8.9 (Configuration management):* Prevents unauthorized open ports, services, and default credentials
  * *Control 8.20 (Network security):* Secures network entry points, wireless interfaces, and segregation
  * *Control 8.30 (Outsourced development):* Manages supply chain software and vendor access vulnerabilities
* **CIS Critical Security Controls v8:**
  * *Control 4.7 (Manage Default Accounts on Enterprise Assets and Software):* Mandates changing default credentials on all devices
  * *Control 9.2 (Ensure Network Ports, Protocols, and Services Are Configured):* Disables unneeded ports and protocols to shrink the attack surface
  * *Control 15.1 (Establish and Maintain an Inventory of Service Providers):* Secures third-party and MSP supply chain vectors
