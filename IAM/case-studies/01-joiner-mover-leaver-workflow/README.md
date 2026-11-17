# Joiner–Mover–Leaver Workflow

**Classification:** Supervised operational task  
**Organization:** Halisans Technologies  
**Date:** 2026-11-02  
**My role:** IAM Operations Analyst — Lifecycle Governance  
**Status:** Completed

## 1. Problem and objective
Document and enforce authorized provisioning, mover changes, and time-bound deprovisioning with verified approval trails and audit closure evidence.

Disjointed communication between HR and IT frequently causes delayed deprovisioning, orphaned active accounts, and privilege accumulation as staff change roles. Establishing a rigorous JML lifecycle eliminates unauthorized access vectors and guarantees compliance with ISO 27001 Control A5.18.

## 2. Scope, environment and authorization
- **Systems/data:** Active Directory Domain Services, Microsoft Entra ID, Jira Service Management, HR Information System (HRIS).
- **Tools:** PowerShell ActiveDirectory Module, Microsoft Graph PowerShell SDK, Jira Automation.
- **Authorization:** Authorized operational scope under Halisans Cybersecurity Operations; internal directory structures redacted.

## 3. Methodology
1. Workflow Architecture & SLA Definition: Standardized 24h onboarding SLAs and mandatory time-bound 4h deprovisioning SLAs.
2. Automated Ticket-to-Identity Provisioning: Integrated Jira Service Management access request templates with Active Directory role groups.
3. Leaver Termination Checklist Execution: Automated immediate credential invalidation, session revocation, mailbox delegation, and OU migration to Disabled_Users.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | Sanitized JML Standard Operating Procedure (SOP) | Proves formal stage-gate approval workflows for Joiner, Mover, and Leaver events. |
| E-02 | PowerShell Automated Leaver Script (Deprovision-User.ps1) | Validates instant group stripping, account disabling, and session revocation. |
| E-03 | Audit Sample of 30 Completed JML Tickets | Demonstrates 100% compliance with managerial approvals and SLA closure timestamps. |

## 5. Findings and analysis
Historical analysis revealed an average of 48 hours latency between employee departure and directory account deactivation. Identified 6 dormant accounts that remained active post-termination before JML re-engineering.

## 6. Outcome and recommendations
- **Disposition / deliverable:** Operationalized automated JML framework across 100% of internal staff and contractors.
- **Action taken or recommended:** Deployed automated webhook from HRIS to Jira triggering immediate deprovisioning tickets upon HR exit filing.
- **Validation:** Sampled 15 consecutive departures; confirmed 100% achieved complete account deactivation in < 15 minutes of exit notification.
- **Limitations:** SaaS applications lacking SCIM provisioning still require manual ticket-based verification by application administrators.

## 7. Lessons learned
Role-based mover templates prevent permission hoarding far more effectively than manual managerial discretion.

## 8. References
ISO/IEC 27001:2022 Control A5.18, NIST SP 800-53 Rev 5 AC-2 (Account Management), CIS Control 5.
