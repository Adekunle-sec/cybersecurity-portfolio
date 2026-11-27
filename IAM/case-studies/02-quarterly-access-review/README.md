# Quarterly Access Review

**Classification:** Authorized production work  
**Organization:** Halisans Technologies  
**Date:** 2026-11-09  
**My role:** Identity Governance & Access Certification Analyst  
**Status:** Completed

## 1. Problem and objective
Review enterprise user entitlements, identify privilege escalation outliers, record asset owner certification decisions, and track revocation remediation.

Over time, employees accumulate unnecessary privileges as they shift projects (privilege creep). Without recurring quarterly recertification, excessive permissions remain undetected, drastically expanding the organization blast radius in the event of credential compromise.

## 2. Scope, environment and authorization
- **Systems/data:** Active Directory security groups, Microsoft Entra ID Enterprise Applications, Microsoft 365 licensing portal.
- **Tools:** Microsoft Entra Access Reviews, Automated Identity Data Reconciliation, PowerShell.
- **Authorization:** Authorized quarterly identity audit mandated by Halisans Information Security Officer.

## 3. Methodology
1. Identity Inventory Extraction: Exported active group memberships across privileged tiers (Domain Admins, HLS-SOC, Finance, Executive).
2. Business Owner Review Campaigns: Dispatched customized entitlement rosters to 14 department heads with mandatory 10-day certification deadlines.
3. Remediation & Deprovisioning: Processed owner revocation requests, removed excessive memberships, and generated audit reconciliation logs.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | Quarterly Access Review Master Workpaper | Proves comprehensive review of 320 user accounts across 48 sensitive security groups. |
| E-02 | Owner Decision Attestation Forms | Validates explicit approval or revocation sign-offs from 14 operational managers. |
| E-03 | Remediation Confirmation Log | Demonstrates execution of 34 access revocations with before/after directory diff snapshots. |

## 5. Findings and analysis
Identified 34 instances of privilege creep where transferred employees retained permissions from prior departments. Uncovered 2 contractor accounts that maintained access 3 weeks past contract conclusion.

## 6. Outcome and recommendations
- **Disposition / deliverable:** 100% certification completed across all enterprise organizational units; revocation executed for all flagged exceptions.
- **Action taken or recommended:** Enforced mandatory quarterly review schedules and established automated alerts for contractor accounts nearing expiration.
- **Validation:** Re-queried Active Directory group memberships post-remediation; confirmed all 34 flagged permissions were completely removed.
- **Limitations:** Manual reviews are vulnerable to rubber-stamping by managers; requires ongoing training on least-privilege principles.

## 7. Lessons learned
Providing managers with last logon date metadata alongside group names dramatically increases the quality of revocation decisions.

## 8. References
ISO/IEC 27001:2022 Control A5.15, NIST SP 800-53 Rev 5 AC-6 (Least Privilege), AICPA SOC 2 CC6.3.
