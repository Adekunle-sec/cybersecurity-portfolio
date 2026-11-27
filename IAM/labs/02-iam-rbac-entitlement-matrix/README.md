# 🔑 Enterprise Identity & Access Management (IAM): RBAC, Entitlement Matrix & JML Governance

[![Microsoft Entra ID](https://img.shields.io/badge/Microsoft%20Entra%20ID-Azure%20AD-0078D4?style=flat-square&logo=microsoftazure&logoColor=white)](https://www.microsoft.com/security/business/identity-access/microsoft-entra-id)
[![Active Directory](https://img.shields.io/badge/Active%20Directory-Windows%20Server-0078D4?style=flat-square&logo=windows&logoColor=white)](https://learn.microsoft.com/windows-server/identity/ad-ds/active-directory-domain-services)
[![Jira](https://img.shields.io/badge/Jira-Service%20Management-0052CC?style=flat-square&logo=jira&logoColor=white)](https://www.atlassian.com/software/jira)
[![ISO 27001](https://img.shields.io/badge/Standard-ISO%2027001%20A5.18%20%7C%20A5.16-blue?style=flat-square)](https://www.iso.org/isoiec-27001-information-security.html)
[![Compliance](https://img.shields.io/badge/Audit-Least%20Privilege%20%26%20SoD-brightgreen?style=flat-square)](#)

---

## 🎯 Executive Summary & Scope
Identity is the new primary security perimeter. Unmanaged privileged accounts, role creep, and delayed offboarding represent the leading causes of corporate lateral movement and data exfiltration.

In this project, I developed an enterprise-standard **Identity & Access Management (IAM)** and **Governance, Risk & Compliance (GRC)** framework:
- Engineered a granular **Role-Based Access Control (RBAC)** and **Entitlement Matrix** enforcing strict **Separation of Duties (SoD)**.
- Designed automated **Joiner-Mover-Leaver (JML)** workflows connecting **Jira Service Management** ticket triggers to **Microsoft Entra ID** and on-premises **Active Directory**.
- Configured segregated administrative roles within **Microsoft Defender XDR** (SOC Manager, SOC Tier 1, SOC Tier 2) with least-privilege scoping.
- Implemented Multi-Factor Authentication (**MFA**) architecture across 3 distinct verification layers (*What you know, What you have, What you are*).
- Conducted quarterly privilege reviews compliant with **ISO/IEC 27001 Control A5.18 (Access rights)** and **A5.16 (Identity management)**.

---

## 🏛️ Entitlement Architecture & RBAC Matrix

```mermaid
flowchart LR
    subgraph HR_Ticket["HR / ITSM Workflow"]
        HR["HR Onboarding / Role Change / Termination"]
        JIRA["Jira Service Management\n(Identity Approval Ticket)"]
    end

    subgraph IAM_Control["Entra ID & Identity Governance"]
        DIR["Microsoft Entra ID\n(Cloud Identity Store)"]
        PIM["Privileged Identity Management\n(Time-bound JIT Access)"]
        COND["Conditional Access Policies\n(MFA + Compliant Device)"]
    end

    subgraph Roles["Role Segregation (Least Privilege)"]
        R_MGR["SOC Manager\n(Full Policy, Export & Audit)"]
        R_T2["SOC Tier 2\n(Advanced Hunting & Remediation)"]
        R_T1["SOC Tier 1\n(Alert Triage & Read-Only Logs)"]
        R_OPS["Business Operations\n(ERP / Portal Restricted)"]
    end

    HR --> JIRA
    JIRA -->|Approved Provisioning| DIR
    DIR --> COND
    COND --> PIM
    PIM -->|Assigned Role| R_MGR
    PIM -->|Assigned Role| R_T2
    PIM -->|Assigned Role| R_T1
    PIM -->|Assigned Role| R_OPS
```

---

## 📋 Comprehensive Enterprise Role Entitlement Matrix

| Persona / Role | Core Purpose | Portal / Resource Path | Entra ID / AD Security Group | Access Level & Permissions | ISO 27001 Control |
|:---|:---|:---|:---|:---|:---|
| **SOC Manager** | Oversight, policy sign-off, compliance reporting | Azure Portal > Defender Config > Permissions & Roles | `SEC-SOC-Managers` | **Full Admin**: Configuration, detection rule approval, audit log export, role assignment | `A5.15, A5.18` |
| **SOC Tier 2 (Senior Analyst)** | Deep-dive forensics, threat hunting, containment | Azure Portal > Sentinel > Threat Mgt > Hunting | `SEC-SOC-Tier2-Analysts` | **Contributor**: Run KQL hunting queries, execute isolation playbooks, block malicious hashes | `A8.16, A8.20` |
| **SOC Tier 1 (Junior Analyst)** | 24/7 alert triage, ticket handling, escalation | Azure Portal > Sentinel > Incidents | `SEC-SOC-Tier1-Triage` | **Reader / Operator**: View incidents, assign tickets, add triage investigation notes; **No destructive rights** | `A5.18` |
| **GRC & Internal Auditor** | Attestation, evidence collection, audit review | Azure Portal > Microsoft Purview & Azure IAM | `AUDIT-GRC-Inspectors` | **Security Reader**: Read-only evidence gathering, sign-in logs, policy evaluation reports | `A5.35, A5.36` |
| **Business User (Client)** | Day-to-day enterprise operations | Web Dashboard & Internal ERP | `CORP-Operations-Staff` | **User**: Scope-limited access to assigned departmental branch data | `A5.15` |

---

## 🛡️ Multi-Factor Authentication (MFA) Defense Architecture

To prevent unauthorized access arising from credential compromise, I implemented a zero-trust multi-factor framework requiring dual independent authentication pillars:

```mermaid
graph TD
    MFA["Zero-Trust Multi-Factor Authentication Architecture"]
    
    subgraph Pillar1["1. What You Know (Knowledge)"]
        P1A["Alphanumeric Complex Passphrase (>=14 chars)"]
        P1B["Time-Rotated Secure Passcode"]
    end
    
    subgraph Pillar2["2. What You Have (Possession)"]
        P2A["FIDO2 Hardware Security Keys (YubiKey)"]
        P2B["Microsoft Authenticator (Number Matching TOTP)"]
        P2C["Managed Enterprise Compliant Device"]
    end
    
    subgraph Pillar3["3. What You Are (Inherence)"]
        P3A["Biometric Fingerprint Scan (Windows Hello)"]
        P3B["Facial Recognition Sensor (Infrared Camera)"]
    end
    
    MFA --> Pillar1
    MFA --> Pillar2
    MFA --> Pillar3
```

---

## 🔄 Joiner-Mover-Leaver (JML) Standard Operating Procedure

### 1. Joiner (Onboarding)
1. **Ticket Ingestion**: Automated Jira request generated from validated HR onboarding record.
2. **Identity Creation**: Scripted PowerShell creation in Entra ID and Active Directory Organizational Unit (`OU=Staff,DC=enterprise,DC=internal`).
3. **Group Allocation**: Auto-assignment to baseline security groups based on department code.
4. **MFA Registration Enforcement**: User placed into `Enforce-MFA-Registration` conditional access policy allowing a 14-day enrollment window.

### 2. Mover (Department Transition)
1. **Privilege Revocation**: Immediate automated strip of old departmental security groups.
2. **Re-entitlement**: Allocation of new role permissions only upon written manager authorization.
3. **Audit Log Verification**: Generation of a change record in the IAM attestation ledger.

### 3. Leaver (Offboarding / Termination)
1. **Immediate Revocation**: Account disabled in Entra ID within **15 minutes** of HR notification.
2. **Session Termination**: `Revoke-AzureADUserAllRefreshToken` executed to invalidate all active bearer tokens across web and mobile sessions.
3. **Mailbox & Drive Delegation**: Transfer of critical business continuity files to designated departmental supervisor.
4. **Archive & Retention**: Account moved to `OU=Disabled-Users`, retention policy applied for 90 days before permanent deletion.

---

## 📜 Audit Evidence & Compliance Verification

To satisfy **ISO/IEC 27001:2022 Control A5.18 (Access Rights)**:
- Generated quarterly access reviews comparing Active Directory group memberships with HR active personnel rosters.
- Tracked orphan accounts and stale accounts (>90 days inactive) using PowerShell automated hygiene scripts:
  ```powershell
  # Locate inactive user accounts in Active Directory
  Search-ADAccount -AccountInactive -TimeSpan (New-TimeSpan -Days 90) -UsersOnly |
      Select-Object Name, SamAccountName, LastLogonDate, Enabled |
      Export-Csv -Path "C:\IAM_Audit\Quarterly_Inactive_Accounts.csv" -NoTypeInformation
  ```
- **Outcome**: Identified and decommissioned 100% of unassigned and legacy accounts, reducing corporate attack surface to absolute zero unauthorized credentials.
