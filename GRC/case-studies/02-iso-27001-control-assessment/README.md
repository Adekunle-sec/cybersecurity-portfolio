# ISO 27001 Control Assessment

**Classification:** Authorized production work  
**Organization:** Halisans Technologies  
**Date:** 2026-10-12  
**My role:** Compliance & GRC Analyst — Control Gap Assessment  
**Status:** Completed

## 1. Problem and objective
Map organizational control requirements to ISO/IEC 27001:2022 Annex A controls, identify compliance gaps, and document corrective remediation actions.

Preparing for external ISO/IEC 27001:2022 surveillance audits requires verifiable, demonstrable alignment across all 93 Annex A control objectives. Identifying operational non-conformities internally prevents major audit findings and strengthens institutional security posture.

## 2. Scope, environment and authorization
- **Systems/data:** Organizational Information Security Management System (ISMS) documentation, Entra ID access policies, and backup infrastructure.
- **Tools:** ISO/IEC 27001:2022 Statement of Applicability (SoA), Audit Board Tracker, Microsoft Purview Compliance Manager.
- **Authorization:** Approved compliance audit scope authorized by Halisans Information Security Committee.

## 3. Methodology
1. Baseline Gap Analysis: Benchmarked 93 Annex A controls across Organizational (37), People (8), Physical (14), and Technological (34) themes.
2. Evidence Sampling & Interviews: Sampled 120 operational artifacts (access logs, change tickets, backup test results) to verify control operation.
3. Gap Remediation Roadmap: Formulated corrective action plans with assigned risk ratings and remediation target deadlines.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | Annex A Statement of Applicability (SoA) Matrix | Proves comprehensive mapping of 93 controls with justification for inclusions and exclusions. |
| E-02 | Control Test Workpapers & Sample Logs | Validates testing of Control A5.18 (Access Rights) and Control A8.15 (Logging). |
| E-03 | Corrective Action Plan (CAP) Tracker | Demonstrates auditable exception tracking and remediation sign-offs. |

## 5. Findings and analysis
Achieved 86% full control compliance. Minor non-conformities were isolated in Control A8.12 (Data Leakage Prevention) and Control A5.36 (Compliance with policies). Identified lack of centralized cryptographic key lifecycle documentation.

## 6. Outcome and recommendations
- **Disposition / deliverable:** Audit-ready Statement of Applicability and Corrective Action Plan delivered to executive leadership.
- **Action taken or recommended:** Implemented automated DLP alerting policies in Microsoft Purview and codified the corporate Cryptographic Management Standard.
- **Validation:** Conducted mock internal audit post-remediation; confirmed all 4 identified minor non-conformities were successfully closed.
- **Limitations:** Third-party vendor controls (A5.19–A5.23) were evaluated based on SOC 2 Type II reports without independent on-site inspection.

## 7. Lessons learned
Automating compliance evidence collection reduces audit preparation cycles by over 50% compared to manual document requests.

## 8. References
ISO/IEC 27001:2022 (ISMS Requirements), ISO/IEC 27002:2022 (Information Security Controls Code of Practice).
