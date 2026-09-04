# 1.17 General Security Concepts: Digital Certificates & PKI

## Overview

Digital certificates are electronic credentials that bind a public key to an identity (such as a domain name, individual, or organization) using standard formats like X.509. By leveraging a Public Key Infrastructure (PKI) and trusted Certificate Authorities (CAs), digital certificates establish cryptographic trust, enable encrypted communications (TLS/HTTPS), and enforce identity authentication across public and private networks.

---

## 1. Digital Certificate Architecture & Lifecycle Operations

Establishing trust and managing digital certificates involves standardized request, validation, and issuance workflows:

| Component / Stage | Technical Mechanics | Operational Function |
| :--- | :--- | :--- |
| **X.509 Standard** | Defines the structured data format containing public key, serial number, signature algorithm, issuer, validity period, and subject identity. | Ensures universal interoperability across web browsers, operating systems, and network devices. |
| **Certificate Signing Request (CSR)** | Generated on the endpoint; combines the public key with organizational identity details to request a signed certificate. | Transmits public key credentials to a CA without exposing the corresponding private key. |
| **CA Validation & Signing** | The Certificate Authority verifies the requester's ownership/identity and signs the certificate using the CA's **Private Key**. | Establishes explicit trust by creating a cryptographically verifiable signature on the issued certificate. |
| **Subject Alternative Name (SAN) / Wildcard** | Incorporates multiple Fully Qualified Domain Names (FQDNs) or wildcard subdomains (`*.domain.com`) into a single certificate. | Simplifies administrative overhead by enabling one certificate to secure multiple services or domain endpoints. |

---

## 2. Trust Models & Revocation Mechanisms

PKI relies on predefined trust topologies and continuous status verification to guard against compromised or decommissioned keys:

### Trust Models
* **Hierarchical / Root of Trust:** CAs are pre-installed into browser and OS trusted root stores. Trust in a public or internal enterprise CA automatically extends to all certificates issued and signed by that CA.
* **Web of Trust:** A decentralized trust model (commonly used in PGP/GPG) where participants peer-sign each other's certificates rather than relying on a centralized authority.
* **Internal / Enterprise CA:** An in-house CA deployed via domain services (e.g., Active Directory Certificate Services) to issue certificates for internal systems without incurring third-party costs.

### Revocation Verification Methods
