# IOC-to-Detection Handoff

**Classification:** Authorized production work  
**Organization:** Halisans Technologies  
**Date:** 2026-12-16  
**My role:** Detection Engineer & Threat Analyst  
**Status:** Completed

## 1. Problem and objective
Translate a validated threat hypothesis into a high-performance KQL detection rule and formal SOC operational handoff package.

A major vulnerability in threat intelligence programs is the handoff gap between CTI analysts and SOC detection engineers. Without structured translation, threat data languishes in reports rather than shielding enterprise assets in real time.

## 2. Scope, environment and authorization
- **Systems/data:** Microsoft Sentinel, Microsoft Defender XDR, Azure DevOps Git Repository.
- **Tools:** KQL (Kusto Query Language), Sentinel Analytic Rule Designer, Jira Service Desk, YAML Rule Templates.
- **Authorization:** Authorized detection engineering workflow approved by Halisans Lead SOC Architect.

## 3. Methodology
1. Hypothesis Formulation: Deconstructed observed T1053.005 (Scheduled Task Creation) persistence mechanisms used by ransomware threat actors.
2. KQL Rule Authoring: Programmed an analytic rule filtering ProcessCreationEvents where schtasks.exe is invoked with /create and suspicious parameters by non-SYSTEM accounts.
3. Handoff Documentation & Testing: Authored comprehensive SOC triage runbook detailing false positive baselines, escalation paths, and containment steps.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | Production KQL Analytic Rule Code (Detect_Schtasks_Persistence.kql) | Proves robust logic filtering known administrative scheduled tasks while catching anomalous executions. |
| E-02 | SOC Triage Operational Runbook | Validates clear step-by-step guidance for Tier-1 analysts handling rule triggers. |
| E-03 | Analytic Rule Performance & False Positive Test Log | Demonstrates 0 false positive alerts across 14 days of historical production telemetry. |

## 5. Findings and analysis
Historical query analysis showed that generic schtasks monitoring triggered 35 false alarms per day from routine software updaters. The tuned rule filtered benign paths while preserving 100% detection of user-context task creation.

## 6. Outcome and recommendations
- **Disposition / deliverable:** Analytic rule merged into production Sentinel SIEM with active alerting status.
- **Action taken or recommended:** Conducted training walkthrough with Tier-1 SOC analysts on interpreting scheduled task payload strings.
- **Validation:** Simulated task creation via test harness; verified Sentinel spawned High-severity incident within 90 seconds.
- **Limitations:** Adversaries utilizing API-based task registration (ITaskService) bypass command-line schtasks.exe detection; requires event ID 4698 telemetry.

## 7. Lessons learned
A detection rule is only as good as its accompanying SOC triage playbook; technical logic without response instructions causes analyst burnout.

## 8. References
MITRE ATT&CK T1053.005 (Scheduled Task), SigmaHQ Detection Rules, Microsoft Sentinel Analytic Rule Best Practices.
