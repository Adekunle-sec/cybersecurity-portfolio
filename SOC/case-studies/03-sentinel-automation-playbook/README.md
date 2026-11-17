# Sentinel Automation Playbook

**Classification:** Supervised operational task  
**Organization:** Halisans Technologies  
**Date:** 2026-12-07  
**My role:** SOAR & Automation Engineer  
**Status:** Completed

## 1. Problem and objective
Document incident-created triggers, automated ownership routing, testing workflows, and safety validation safeguards in Azure Logic Apps.

High alert volumes overwhelm Tier-1 SOC analysts with repetitive manual tasks (assigning tickets, notifying analysts, looking up IP reputations). Developing automated SOAR playbooks slashes response latency from hours to seconds.

## 2. Scope, environment and authorization
- **Systems/data:** Microsoft Sentinel, Azure Logic Apps (Consumption), Microsoft Teams, Jira Service Management.
- **Tools:** Azure Logic Apps Designer, Sentinel Automation Rules, JSON Schema, REST APIs.
- **Authorization:** Authorized SOAR development environment approved by Halisans Security Operations.

## 3. Methodology
1. Trigger & Logic Architecture: Designed an automated playbook triggered on Sentinel Incident Creation filtering for High/Medium severities.
2. Enrichment & Multi-Channel Routing: Extracted incident entities (IPs, accounts), queried VirusTotal API for IP reputation, posted rich adaptive cards in Microsoft Teams, and spawned Jira tracking tickets.
3. Containment Safeguard Implementation: Configured interactive Teams confirmation buttons requiring explicit analyst approval before triggering automated host network isolation.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | Logic App Workflow Designer JSON Definition | Proves structured conditional branching, error handling, and API integration in Azure. |
| E-02 | Teams Adaptive Card Notification Snapshot | Validates presentation of enriched threat telemetry, severity tags, and interactive action buttons. |
| E-03 | Automated End-to-End Test Execution Log | Demonstrates end-to-end execution runtime of 4.2 seconds from incident trigger to ticket creation. |

## 5. Findings and analysis
Manual triage previously consumed 14 minutes per incident just in preliminary ticketing and analyst dispatch. Playbook execution completed initial enrichment and notification in 4.2 seconds.

## 6. Outcome and recommendations
- **Disposition / deliverable:** Production-ready SOAR Playbook deployed across Sentinel Incident Automation Rules.
- **Action taken or recommended:** Activated playbook across all Sentinel alert rules and established a fallback notification channel for failed API responses.
- **Validation:** Simulated 10 synthetic incident alerts across test subscriptions; verified 100% successful trigger, enrichment, and ticket synchronization.
- **Limitations:** Rate limits on free-tier external threat intelligence APIs require exponential backoff retries in Logic Apps.

## 7. Lessons learned
Always implement human-in-the-loop approval gates before automating destructive actions (e.g., account deactivation or firewall block).

## 8. References
Microsoft Sentinel SOAR Documentation, Azure Logic Apps Workflow Definition Language.
