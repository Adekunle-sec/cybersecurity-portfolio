# Audit Evidence & Exception Tracking

**Classification:** Authorized production work  
**Organization:** Halisans Technologies  
**Date:** 2026-10-27  
**My role:** Lead ITGC & Audit Readiness Analyst  
**Status:** Completed

## 1. Problem and objective
Build an audit evidence index, test IT General Control (ITGC) operational effectiveness, and track audit exceptions to verified closure.

During external audits, disorganized evidence retrieval and untracked control deficiencies lead to audit friction, scope expansion, and qualified audit opinions. An institutional evidence index ensures rapid retrieval and accountability.

## 2. Scope, environment and authorization
- **Systems/data:** Jira Service Management, Audit Evidence Repository, Active Directory change logs, SIEM audit trails.
- **Tools:** Audit Evidence Index (Excel/Sheets), Jira Exception Workflow, PowerShell Log Exporters.
- **Authorization:** Authorized internal audit readiness scope sanctioned by Halisans IT Governance.

## 3. Methodology
1. Evidence Taxonomy Architecture: Structured a standardized folder and indexing schema mapping directly to external audit control IDs.
2. ITGC Operational Testing: Executed walkthroughs and sample testing across Logical Access, Change Management, and Computer Operations.
3. Exception Lifecycle Management: Logged control exceptions in Jira, assigned remediation owners, established compensatory controls, and validated closure.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | Master Audit Evidence Index Spreadsheet | Proves systematic tracking of 64 distinct control artifacts with standardized hashing and timestamps. |
| E-02 | ITGC Sample Testing Worksheets | Validates testing of 25 emergency change tickets and 40 user deprovisioning requests. |
| E-03 | Exception Remediation Verification Sign-offs | Demonstrates verified closure of 7 initial control exceptions prior to formal audit cutoff. |

## 5. Findings and analysis
Identified 5 initial exceptions where emergency changes lacked retrospective approval documentation within the mandatory 48-hour window. 2 service accounts lacked documented business owners.

## 6. Outcome and recommendations
- **Disposition / deliverable:** Delivered 100% complete, verified Audit Evidence Binder to external audit team with zero open exceptions.
- **Action taken or recommended:** Re-engineered the Jira emergency change workflow to automatically lock ticketing until retrospective approvals are captured.
- **Validation:** Conducted 60-day post-audit sampling; confirmed 100% adherence to retrospective change approvals and service account ownership.
- **Limitations:** Evidence indexing is labor-intensive if manual; requires automated API integration with ticketing systems for enterprise scale.

## 7. Lessons learned
Treating audit readiness as a continuous monthly operational discipline eliminates end-of-year audit panic and audit findings.

## 8. References
ISACA ITGC Audit Guidelines, AICPA SOC 2 Trust Services Criteria, ISO/IEC 27001:2022 Control A5.35.
