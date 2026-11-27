<p align="center">
  <img src="../cybersecurity-banner.svg" width="100%" alt="Cybersecurity Defense & Operations Portfolio" />
</p>

<p align="center">
  <a href="https://github.com/Adekunle-sec"><img src="https://img.shields.io/badge/Author%20Profile-Adekunle--sec-24292e?style=for-the-badge&logo=github&logoColor=white" /></a>
  <a href="https://www.linkedin.com/in/adekunle-olanrewaju-20261844b"><img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="https://github.com/Adekunle-sec/cybersecurity-portfolio"><img src="https://img.shields.io/badge/Parent%20Portfolio-Cybersecurity%20Portfolio-38BDF8?style=for-the-badge&logo=shield&logoColor=white" /></a>
  <a href="mailto:tayour.ola@gmail.com"><img src="https://img.shields.io/badge/Email-Direct%20Inquiry-EA4335?style=for-the-badge&logo=gmail&logoColor=white" /></a>
</p>

---

# Adekunle Olanrewaju | Identity & Access Management (IAM) Analyst

**Identity Governance | Active Directory | Microsoft Entra ID | RBAC & Entitlement Matrices**

📍 Lagos, Nigeria · [LinkedIn](https://www.linkedin.com/in/adekunle-olanrewaju-20261844b) · [tayour.ola@gmail.com](mailto:tayour.ola@gmail.com) · [GitHub Profile](https://github.com/Adekunle-sec)

---

## 🎯 Professional Profile

I am an **Identity & Access Management (IAM) Analyst** with hands-on experience working in cybersecurity operations at **Halisans Technologies**, where I have been involved in identity lifecycle management, user access provisioning, role-based access control (RBAC), Active Directory administration, access reviews, and security policy implementation.

Through my work at Halisans Technologies, I have gained practical experience supporting **Joiner, Mover, and Leaver (JML) processes**, managing user identities and permissions, implementing access controls, and documenting IAM activities in alignment with organizational security policies and industry best practices.

Beyond operational experience, I have independently developed technical projects and lab environments that demonstrate my ability to configure, secure, troubleshoot, and govern enterprise identity infrastructure.

---

## 💼 Practical Experience | Halisans Technologies

**Role:** IAM Analyst  
**Period:** 2026 – Present  
**Environment:** Supervised Cybersecurity Operations & Enterprise Defense Labs

### Core Operational Responsibilities & Workflows:
- **Enterprise Provisioning & Entitlement Management:**
  - Provisioned corporate user identities in **Microsoft Entra ID (Azure AD)** and on-premises Active Directory Domain Services based on standardized RBAC entitlement matrices and GRC compliance standards.
  - Managed corporate SaaS identity onboarding including **Jira Service Desk account provisioning** via the Jira Portal and mapping staff to departmental groups.
- **Defense-in-Depth & MFA Security Layering:**
  - Implemented multi-factor authentication policies enforcing the three core authentication pillars:
    - *What you know:* Passcodes, complex passwords, knowledge-based security questions.
    - *What you are:* Biometrics (fingerprint, facial recognition, voiceprint).
    - *What you have:* Hardware tokens (FIDO2 keys) and software time-based one-time password (TOTP) authenticators.
- **Role-Based Access Control (RBAC) & Administrative Segregation:**
  - Designed role segregation structures within **Microsoft Defender XDR** (`Defender -> Configuration -> Permissions -> Roles`), defining granular permissions for **SOC Manager, SOC Tier 1, and SOC Tier 2** analysts to enforce least-privilege principles.
  - Provisioned administrative access for cloud SIEM via **Microsoft Sentinel Resource Group IAM** role assignments.
  - Configured automated security alert email notifications across user groups in Defender XDR (`Settings -> Microsoft Defender XDR -> Email notifications`) in compliance with **ISO/IEC 27001:2022 Control A5.18**.
- **GRC Compliance & Audit Evidence Delivery:**
  - Collaborated directly with the GRC team to provide auditable evidence of user creation, group memberships, and role assignments, validating compliance against organizational governance rules.
  - Automated identity lifecycle and alert handling via Sentinel Automation Rules.

---

## 🚀 Architectural Project Contribution: Student Login Portal Security Assessment

As part of the [Student Login Portal Threat Modeling & Risk Assessment](../SOC/threat-modeling-risk-assessment-saas/), IAM designed the **Identity Trust Perimeters**, **Authentication Mechanisms**, and **Access Authorization Controls** protecting against STRIDE Spoofing (`NST01`) and Elevation of Privilege (`NST38`):

### Key IAM Engineering Contributions:
- **Anti-Spoofing & Credential Protection (`NST01`):** Mandated Multi-Factor Authentication (MFA) via TOTP / WebAuthn, enforced sliding-window rate limiting on `/login`, and implemented salted **Argon2id** password hashing ($m=65536, t=3, p=4$) to mitigate credential stuffing.
- **Anti-Privilege Escalation & Authorization (`NST38`):** Engineered server-side Role-Based Access Control (RBAC) where profile access permissions are derived strictly from cryptographically validated JWT session claims, preventing Insecure Direct Object References (IDOR/BOLA).
- **Session Security & Boundary Isolation:** Structured ephemeral session token minting stored exclusively in `HttpOnly`, `Secure`, `SameSite=Strict` cookies, preventing cross-site scripting (XSS) token exfiltration.
- **Regulatory Control Mapping:** Aligned identity defenses to **ISO/IEC 27001:2022 Controls A.5.15 (Access Control), A.5.18 (Access Rights), and A.8.5 (Secure Authentication)**, and **NIST SP 800-53 IA-2 (Identification & Authentication) / AC-6 (Least Privilege)**.

| IAM Deliverable | Focus & Description | Direct Link |
|---|---|---|
| **Identity Architecture in DFD** | Level-1 Data Flow Diagram illustrating Student Entity, Registration, Login, and Profile trust perimeters. | [View DFD (`DFD.png`)](../SOC/threat-modeling-risk-assessment-saas/DFD.png) |
| **Control Mapping Matrix (IAM Controls)** | Verification matrix mapping identity mitigations against ISO 27001:2022 and NIST SP 800-53 standards. | [Download Matrix (`Control_Mapping_Matrix.xlsx`)](../SOC/threat-modeling-risk-assessment-saas/Control_Mapping_Matrix.xlsx) |
| **Full Threat Model Report** | Comprehensive 24-page technical assessment report generated via OWASP Threat Dragon v2.6.2. | [View Report (`OWASP_Threat_Dragon_Report.pdf`)](../SOC/threat-modeling-risk-assessment-saas/OWASP_Threat_Dragon_Report.pdf) |

---

| Case Study | Objective & Scope | Key Artifacts |
|---|---|---|
| **[01. Joiner–Mover–Leaver Workflow](./case-studies/01-joiner-mover-leaver-workflow/)** | End-to-end lifecycle governance: automated provisioning, ticket verification, and same-day deprovisioning. | JML process maps, approval workflows, and deprovisioning audit records. |
| **[02. Quarterly Access Review](./case-studies/02-quarterly-access-review/)** | Access certification campaign: reviewing high-privilege entitlements, identifying orphaned accounts, and revoking stale access. | Access review spreadsheet, exception tracker, and sign-off verification. |
| **[03. RBAC & Least Privilege](./case-studies/03-rbac-and-least-privilege/)** | Role-Based Access Control matrix design: decoupling individual user permissions into standardized functional roles. | Role entitlement matrix, group membership audit, and least-privilege report. |
| **[04. AD and Entra ID Administration](./case-studies/04-ad-and-entra-id-administration/)** | Hybrid identity administration: OU structure design, security GPOs, and Entra ID cloud access controls. | GPO hardening checklist, OU architecture diagram, and policy verification. |

---

## 🔬 Hands-On IAM Technical Labs

| Lab Environment | Description | Lab Directory |
|---|---|---|
| **IAM RBAC Entitlement Matrix Lab** | Design and implementation of an enterprise RBAC framework, testing SOD (Segregation of Duties) and privilege inheritance in Active Directory. | [`./labs/02-iam-rbac-entitlement-matrix/`](./labs/02-iam-rbac-entitlement-matrix/) |

---

## 🛠️ Technical Capabilities

- **Directory Services:** Active Directory Domain Services (AD DS), Microsoft Entra ID (Azure AD), Azure AD Connect
- **Access Governance:** Role-Based Access Control (RBAC), Least Privilege, Segregation of Duties (SOD), Access Certifications
- **Administration & Scripting:** PowerShell (`ActiveDirectory` module), Group Policy Management Console (GPMC)
- **ITSM & Audit:** Jira Service Management, ServiceNow Identity Workflows, Audit Evidence Repositories
- **Standards:** ISO/IEC 27001:2022 Control A5.18, NIST SP 800-63B (Digital Identity Guidelines)

---

## 🛡️ Evidence & Documentation Standards

Every featured case study includes a realistic scenario, scope and authorization, individual contribution, methodology, sanitized evidence, analysis, result, limitations, and lessons learned.

**Confidentiality:** No real credentials, tokens, internal IPs, customer data, sensitive alerts, personal identifiers, or unapproved screenshots. All evidence uses synthetic or redacted data conforming to strict security standards.

---

## 📬 Contact & Links

- **LinkedIn:** [linkedin.com/in/adekunle-olanrewaju-20261844b](https://www.linkedin.com/in/adekunle-olanrewaju-20261844b)
- **Email:** [tayour.ola@gmail.com](mailto:tayour.ola@gmail.com)
- **GitHub:** [github.com/Adekunle-sec](https://github.com/Adekunle-sec)

---
*All cases are labeled as simulated, supervised, or operational as appropriate. All outcomes are evidence-backed.*
