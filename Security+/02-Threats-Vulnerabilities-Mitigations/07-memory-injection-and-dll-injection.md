# 2.7 Threats, Vulnerabilities, and Mitigations: Memory Injection & DLL Injection

## Overview

All executables and running software on a system must be loaded into system RAM and processed by the CPU to operate. Consequently, malware must reside in memory to execute. Rather than launching as a standalone process that can be easily flagged by endpoint security software, advanced malware utilizes process memory injection—such as Dynamic-Link Library (DLL) injection—to hide within legitimate, trusted system processes.

---

## 1. Process Injection & DLL Injection Mechanics

Process injection allows malware to execute within the memory space of an existing process between its starting and ending virtual memory addresses:

| Execution Method | Operational Mechanism | Key Security Impacts |
| :--- | :--- | :--- |
| **Standalone Process** | Malware creates its own process in system memory. | Easily detected by process monitoring tools, Endpoint Detection and Response (EDR), and basic anti-malware. |
| **Process / Memory Injection** | Malware injects malicious code directly into the memory space of a legitimate, running process. | Eades process-based security controls; inherits the security context, rights, and permissions of the targeted host process (privilege escalation). |
| **DLL Injection** | Threat actor places a malicious DLL on accessible storage and forces a target process to reference and load it into memory. | Executes arbitrary code under the umbrella of a legitimate Windows application using shared dynamic libraries. |

---

## 2. Technical Attack Sequence: DLL Injection

Understanding the step-by-step execution path of a DLL injection attack helps security analysts configure process monitoring and memory protection controls:


```

[1. Malicious DLL Staged on Disk]
│
▼
[2. Attacker Modifies Target Process Memory / Registry Path]
│
▼
[3. Target Application Calls Path to Load DLL]
│
▼
[4. Malicious DLL Loaded into Memory Space]
│
▼
[5. Code Executes with Target Process Privileges]

```

1. **Storage Staging:** The attacker installs or drops a malicious `.dll` file onto storage accessible by the victim system.
2. **Memory Modification:** The attacker modifies the target application's memory space or registry hooks to insert a path pointing to the malicious DLL.
3. **Execution & Privilege Escalation:** As the target application executes, it reads the inserted path reference, loads the malicious DLL into its own memory space, and executes the payload. The payload inherits the elevated rights and user privileges of the parent process.

---

## 3. Industry Framework Cross-References

To align memory injection defenses and process monitoring controls with recognized cybersecurity frameworks:

* **NIST SP 800-53 Rev. 5:**
  * *SI-7 (Software, Firmware, and Information Integrity):* Code signing and unauthorized code execution prevention
  * *SI-16 (Memory Protection):* Implementing hardware/software safeguards against unauthorized code execution in system memory
* **ISO/IEC 27001:2022 / 27002:2022 Annex A:**
  * *Control 8.7 (Protection against malware):* Utilizing advanced endpoint protection to detect process injection and unauthorized library loading
  * *Control 8.16 (Monitoring activities):* Monitoring system calls, dynamic library loadings, and process memory address space anomalies
* **CIS Critical Security Controls v8:**
  * *Control 10.1 (Deploy and Maintain Anti-Malware Software):* Enforcing behavior-based monitoring to detect memory injection techniques
  * *Control 10.5 (Enable Anti-Exploitation Features):* Enabling features such as Data Execution Prevention (DEP) and Address Space Layout Randomization (ASLR)
