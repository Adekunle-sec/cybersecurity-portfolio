# RBAC & Least Privilege

**Classification:** Authorized production work  
**Organization:** Halisans Technologies  
**Date:** 2026-11-16  
**My role:** Lead Identity Architect & RBAC Analyst  
**Status:** Completed

## 1. Problem and objective
Design an enterprise Role-Based Access Control (RBAC) entitlement matrix, enforce Separation of Duties (SoD), and validate group-to-role assignments.

Direct user-level permissions and ad-hoc security group assignment created an unmanageable permissions web, violating Separation of Duties and least privilege principles. Structuring clean RBAC roles simplifies administration and prevents unauthorized access to critical data.

## 2. Scope, environment and authorization
- **Systems/data:** Active Directory Domain Services, Azure RBAC, Microsoft Entra ID P2, Jira Service Desk.
- **Tools:** Enterprise Entitlement Matrix & Role Definitions, PowerShell, Azure Role Definitions, AGDLP Architecture.
- **Authorization:** Approved directory restructuring charter authorized by Halisans Security Leadership.

## 3. Methodology
1. Role Discovery & AGDLP Structuring: Implemented Accounts -> Global Groups -> Domain Local Groups -> Permissions (AGDLP) architecture.
2. Separation of Duties (SoD) Mapping: Codified strict rules prohibiting Tier-1 SOC analysts from modifying SIEM detection rules without Tier-3 approval.
3. Permission Migration & Cleanup: Stripped direct ACEs on file shares and directory objects, migrating 100% of user access into defined RBAC roles.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | Enterprise RBAC Entitlement Matrix Spreadsheet | Proves comprehensive role-to-permission mapping across Tier 1, Tier 2, and Tier 3 operations. |
| E-02 | AGDLP Implementation Script (Set-RBACGroups.ps1) | Validates structured nested group architecture in Active Directory. |
| E-03 | Separation of Duties (SoD) Verification Report | Demonstrates elimination of toxic combinations across finance and IT administrative tiers. |

## 5. Findings and analysis
Discovered that 28 users possessed direct Access Control Entries (ACEs) on operational shares rather than group memberships. 4 analysts held simultaneous developer and production deployment rights.

## 6. Outcome and recommendations
- **Disposition / deliverable:** Delivered production-grade RBAC framework with zero direct user-level ACEs.
- **Action taken or recommended:** Restricted membership in privileged groups to PIM (Privileged Identity Management) with time-bound elevation approval.
- **Validation:** Conducted directory audit using PowerShell; confirmed 0 direct user permissions and 100% role-based inheritance.
- **Limitations:** Custom proprietary line-of-business applications required custom internal roles where standard Azure RBAC was unsupported.

## 7. Lessons learned
Role mining must involve business stakeholders; technical roles defined solely by IT often disrupt business operations.

## 8. References
ISO/IEC 27001:2022 Control A5.15 & A5.18, NIST SP 800-162 (Attribute/Role Based Access Control).
