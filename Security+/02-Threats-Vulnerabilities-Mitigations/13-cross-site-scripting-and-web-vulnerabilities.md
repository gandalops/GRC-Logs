# 2.13 Threats, Vulnerabilities, and Mitigations: Cross-Site Scripting (XSS)

## Overview

Cross-Site Scripting (XSS) is a prevalent web application vulnerability that exploits the implicit trust a user's web browser has for a legitimate website. XSS occurs when an application includes untrusted input in a web page without proper validation or escaping, allowing attackers to execute malicious scripts—typically JavaScript—in the victim's client session. This enables attackers to steal session tokens, hijack accounts, or alter site behavior.

---

## 1. Primary Cross-Site Scripting (XSS) Variants

XSS attacks are broadly classified by how the malicious script is delivered to and processed by the client browser:

| XSS Classification | Execution Mechanism & Delivery Channel | Impact Scope & Persistence |
| :--- | :--- | :--- |
| **Reflected (Non-Persistent) XSS** | Attackers deliver a malicious link containing embedded scripts (via email, messaging, or social engineering). The server reflects the script back to the victim upon user interaction. | **Non-Persistent:** Impacts only users who actively click the crafted malicious link. |
| **Stored (Persistent) XSS** | Attackers inject malicious scripts directly into persistent data stores (e.g., database fields, social media posts, comment sections, or shopping carts). | **Persistent:** Automatically executes against *all* users visiting the affected web page without requiring direct user targeting. |

---

## 2. Technical Mechanics & Case Study

### Exploit Execution Path
1. **Script Delivery / Storage:** The attacker identifies an unvalidated input field (such as a search box or credit card field) and enters executable JavaScript payload syntax.
2. **Payload Reflection / Execution:** The application renders the payload in the browser. The browser interprets the text as executable script code rather than standard data.
3. **Session Exfiltration:** The script extracts confidential local data—such as session IDs or authentication cookies (`document.cookie`)—and transmits it to an attacker-controlled server in the background.

### Real-World Vulnerability Case Study: Subaru Vehicle Management Portal (2017)
* **Vulnerability:** Security research revealed that authentication tokens issued by the vehicle control portal failed to expire.
* **XSS Vector:** Reflected XSS on the site allowed attackers to send crafted links that exfiltrated non-expiring victim tokens upon click.
* **Impact:** Once stolen, the static token granted attackers permanent administrative control over registered vehicle features and permitted adding attacker email accounts to third-party vehicles.

---

## 3. Defense & Mitigation Strategies

Preventing XSS requires implementing multi-tiered security controls across both development and operational environments:

### Developer Controls
* **Input Validation & Sanitization:** Verify all incoming user parameters against strict type and character rules before acceptance.
* **Output Encoding / Escaping:** Contextually encode dynamic data (e.g., HTML, attribute, or JavaScript encoding) before rendering it to the client browser.
* **Content Security Policy (CSP):** Deploy HTTP CSP headers to restrict the origins from which scripts can execute and disable inline JavaScript execution.
* **Session Lifecycle Security:** Enforce strict session token expiration limits and set the `HttpOnly` flag on sensitive cookies to prevent script-based access.

### User & Endpoint Defenses
* **Patch Management:** Regularly update web browsers and application extensions to patch underlying script engine vulnerabilities.
* **Safe Browsing Practices:** Avoid clicking unverified links in communications; navigate directly to domain names.
