# 2.12 Threats, Vulnerabilities, and Mitigations: Code Injection & SQL Injection

## Overview

Code injection occurs when an application accepts user-supplied input without proper validation or sanitization, allowing an attacker to insert arbitrary code that alters the execution flow. When targeting relational databases, this technique is known as Structured Query Language Injection (SQLi). SQLi allows threat actors to manipulate database queries directly from a web browser, bypassing access controls to view, modify, or delete administrative data.

---

## Step 1: Code Injection Vectors & SQLi Overview

Applications communicate with backend databases using structured queries. When input fields lack bounds checking and parameter sanitization, attackers inject SQL commands into input fields, forcing the database engine to execute unintended instructions.

* **HTML Injection:** Inserting malicious HTML markup to alter web page presentation or capture input data.
* **XML Injection:** Manipulating XML parsers to tamper with application logic or disclose file contents.
* **SQL Injection (SQLi):** Injecting raw SQL commands into application fields to read, exfiltrate, or destroy database records.

---

## Step 2: Technical Execution Mechanics & WebGoat Example

SQLi exploits rely on inserting boolean conditions that evaluate to true (e.g., `' OR '1'='1'`) to override standard authentication and record lookup logic.

### Vulnerable Query Execution

* **Legitimate Query:**  
  `SELECT * FROM users WHERE name = 'Smith' AND tan = '3SL99A';`  
  *Result:* Returns only records strictly matching the specific user and password/TAN combination.

* **Injected Payload String:**  
  `Smith' OR '1'='1`

* **Modified Query Executed by Database:**  
  `SELECT * FROM users WHERE name = 'Smith' OR '1'='1';`  
  *Result:* Because `'1'='1'` is perpetually true, the database ignores authentication parameters and dumps the entire user table to the browser screen.

---

## Step 3: Industry Framework Cross-References

Aligning input validation and database query protections with recognized security control standards:

* **NIST SP 800-53 Rev. 5:**
  * *SI-10 (Information Input Validation):* Enforcing input checking to prevent malformed code execution.
  * *SA-11 (Developer Testing and Evaluation):* SAST/DAST testing to identify unescaped query syntax.
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 8.28 (Secure coding):* Mandatory use of parameterized queries (prepared statements) and input sanitization.
  * *Control 8.29 (Security testing in development and acceptance):* Testing applications against OWASP Top 10 web vulnerabilities.
* **CIS Critical Security Controls v8:**
  * *Control 16.2 (Establish and Maintain a Secure Application Architecture):* Incorporating input sanitization and parameterized database layers into web applications.
  * *Control 16.3 (Leverage Vetted Software Components):* Utilizing standard object-relational mapping (ORM) libraries to neutralize SQL syntax manipulation.
