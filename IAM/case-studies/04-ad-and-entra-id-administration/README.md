# AD and Entra ID Administration

**Classification:** Authorized production work  
**Organization:** Halisans Technologies  
**Date:** 2026-11-23  
**My role:** Directory Services & Identity Administrator  
**Status:** Completed

## 1. Problem and objective
Document enterprise identity configuration, Group Policy Objects (GPO) security baselines, and secure hybrid access controls.

Misconfigured domain controllers, weak password policies, and unmonitored hybrid synchronizations represent prime targets for lateral movement and credential theft. Hardening Active Directory and Microsoft Entra ID establishes a resilient identity perimeter.

## 2. Scope, environment and authorization
- **Systems/data:** Windows Server 2022 Domain Controllers, Microsoft Entra Connect, Azure AD Hybrid Joined endpoints.
- **Tools:** Group Policy Management Console (GPMC), PingCastle, Microsoft Entra Admin Center, PowerShell.
- **Authorization:** Authorized directory hardening scope under Halisans Cybersecurity Operations.

## 3. Methodology
1. Security Baseline Assessment: Ran PingCastle and Microsoft Security Compliance Toolkit to evaluate domain health and risk score.
2. GPO Hardening Deployment: Engineered GPOs enforcing SMB signing, disabling NTLMv1/LM, enforcing Kerberos AES encryption, and setting screen lock timeouts.
3. Entra ID Security Configuration: Enforced Conditional Access policies requiring MFA for all cloud admin portals and blocking legacy basic authentication.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | PingCastle Domain Security Assessment Report | Proves domain risk score reduction from 58/100 (High) to 12/100 (Low). |
| E-02 | Documented GPO Baseline Settings Export | Validates implementation of CIS Microsoft Windows Server Benchmark settings. |
| E-03 | Conditional Access Policy Configuration Snapshot | Demonstrates mandatory MFA enforcement and legacy auth blocking in Entra ID. |

## 5. Findings and analysis
Identified that NTLMv1 was active on two legacy file services, exposing the domain to credential relay attacks. 14 service accounts were configured with passwords that never expired and lacked AES encryption.

## 6. Outcome and recommendations
- **Disposition / deliverable:** Successfully hardened hybrid identity architecture with CIS Level 1 GPO compliance.
- **Action taken or recommended:** Disabled NTLMv1 across all domain controllers, migrated service accounts to Group Managed Service Accounts (gMSA), and enabled PIM for Global Admins.
- **Validation:** Simulated relay attacks in test environment; verified SMB signing and NTLM restrictions successfully blocked exploitation.
- **Limitations:** Certain legacy third-party operational scanners required temporary isolated exemptions from Kerberos-only enforcement.

## 7. Lessons learned
Group Managed Service Accounts (gMSA) eliminate 100% of service account password management friction and credential reuse risks.

## 8. References
CIS Microsoft Windows Server 2022 Benchmark, Microsoft Entra Security Best Practices.
