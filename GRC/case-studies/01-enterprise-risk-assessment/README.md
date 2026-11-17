# Enterprise Risk Assessment

**Classification:** Supervised operational task  
**Organization:** Halisans Technologies  
**Date:** 2026-10-05  
**My role:** Lead GRC Analyst — Risk Assessment & Threat Modeling  
**Status:** Completed

## 1. Problem and objective
Maintain an enterprise risk register with likelihood, impact, asset owners, treatment strategies, and residual risk scoring.

Without a structured, centralized enterprise risk register, organizational units operated with fragmented visibility into IT asset vulnerabilities, third-party vendor risks, and unmitigated single points of failure. Establishing quantitative and qualitative risk criteria was essential to prioritize remediation investments and satisfy executive audit committees.

## 2. Scope, environment and authorization
- **Systems/data:** Sanitized inventory of enterprise tier-1 IT assets, cloud services (Microsoft 365, Entra ID), and critical operational databases.
- **Tools:** Enterprise Risk Register (Excel/Sheets), Jira Service Management, NIST SP 800-30 Rev 1, ISO 31000 Framework.
- **Authorization:** Authorized operational scope under Halisans Technologies cybersecurity governance framework; all corporate identifiers redacted.

## 3. Methodology
1. Asset Identification & Criticality Scoring: Cataloged 42 primary IT assets and mapped dependencies against business impact thresholds.
2. Threat & Vulnerability Analysis: Evaluated threat actor profiles against internal control gaps to assign 5x5 Likelihood and Impact scores.
3. Treatment Strategy & Residual Scoring: Formulated treatment pathways (Mitigate, Transfer, Avoid, Accept) with designated asset owners and computed residual risk scores post-control verification.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | Sanitized 5x5 Risk Heatmap Matrix | Proves systematic risk stratification from Critical (Red) to Low (Green) across 18 evaluated scenarios. |
| E-02 | Risk Register Treatment Plan Excerpt | Validates assignment of designated control owners, mitigation timelines, and residual impact reductions. |
| E-03 | Executive Risk Briefing Summary | Demonstrates translation of technical vulnerabilities into C-suite operational risk metrics. |

## 5. Findings and analysis
Identified 3 Critical-tier risks centered on legacy unsegmented service accounts and external contractor API access. 12 Medium-tier risks were linked to incomplete quarterly entitlement recertification. Demonstrated that target control implementation would reduce overall enterprise risk exposure by 68%.

## 6. Outcome and recommendations
- **Disposition / deliverable:** Formally adopted Enterprise Risk Register v2.4 with board-approved risk acceptance criteria.
- **Action taken or recommended:** Prioritized immediate multi-factor authentication (MFA) enforcement on all administrative service interfaces and scheduled bi-weekly owner remediation reviews.
- **Validation:** Re-assessed residual risk scores post-mitigation; verified residual risk index dropped within acceptable tolerance thresholds.
- **Limitations:** Assessment relied on point-in-time threat telemetry; continuous real-time threat intelligence ingestion is required for dynamic risk scoring.

## 7. Lessons learned
Asset owners require standardized risk terminology; automated Jira ticket linking significantly improves owner remediation responsiveness.

## 8. References
ISO/IEC 27005:2022 (Information Security Risk Management), NIST SP 800-30 Rev 1, ISO 31000:2018.
