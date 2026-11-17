# Authentication Alert Investigation

**Classification:** Supervised operational task  
**Organization:** Halisans Technologies  
**Date:** 2026-11-30  
**My role:** Security Operations Center (SOC) Tier-1/2 Analyst  
**Status:** Completed

## 1. Problem and objective
Investigate Windows Security Event IDs 4624, 4625, and 4740 with Kusto Query Language (KQL) in Microsoft Sentinel and document investigative conclusions.

Authentication attacks (brute force, credential stuffing, password spraying) account for the vast majority of enterprise perimeter breaches. Rapid triage and correlation of event telemetry is critical to isolate compromised credentials before lateral movement occurs.

## 2. Scope, environment and authorization
- **Systems/data:** Microsoft Sentinel Log Analytics Workspace, Azure Arc connected Windows Server 2022 telemetry, Azure Monitor Agent (AMA).
- **Tools:** Microsoft Sentinel, KQL (Kusto Query Language), Windows Event Viewer, Jira Service Management.
- **Authorization:** Authorized SOC incident investigation environment within Halisans Cybersecurity Operations.

## 3. Methodology
1. Alert Ingestion & Triage: Ingested high-volume Windows security events and filtered noise using optimized KQL timestamp aggregations.
2. Hypothesis & Threshold Querying: Built KQL queries correlating multiple failed logons (Event ID 4625 >= 5 within 10 min) followed by successful logon (Event ID 4624) from an external IP range.
3. Incident Documentation: Extracted caller process names, target usernames, and workstation IP addresses to compile an incident triage report.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | High-Fidelity KQL Hunting Query (BruteForce_Spraying.kql) | Proves multi-event correlation syntax isolating suspicious source IPs. |
| E-02 | Incident Timeline & Telemetry Export | Validates sequence of 14 Event ID 4625 events followed by a single Event ID 4624 success. |
| E-03 | Jira SOC Triage Ticket with Analyst Disposition | Demonstrates structured documentation of containment actions and user account lock. |

## 5. Findings and analysis
Correlated 48 failed logon attempts across 8 distinct user accounts originating from a single anomalous external IP, confirming a horizontal password spray attack. One account exhibited a successful logon 4 minutes later.

## 6. Outcome and recommendations
- **Disposition / deliverable:** Classified as Confirmed True Positive Incident (Severity: High); compromised account quarantined and investigated.
- **Action taken or recommended:** Immediately initiated automated password reset in Entra ID, revoked active refresh tokens, and blocked offending IP at enterprise firewall.
- **Validation:** Confirmed via Sentinel telemetry that authentication attempts from the malicious IP ceased following firewall block.
- **Limitations:** Internal IP visibility was masked behind a load balancer; required X-Forwarded-For header inspection to isolate root caller.

## 7. Lessons learned
Correlating Event 4625 failure sub-status codes (e.g., 0xC000006A wrong password vs 0xC0000064 user does not exist) speeds triage by 40%.

## 8. References
Microsoft Sentinel Documentation on Windows Security Events, MITRE ATT&CK T1110.003 (Password Spraying).
