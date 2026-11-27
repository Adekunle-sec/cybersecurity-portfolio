# SOC Monitoring Dashboard

**Classification:** Authorized production work  
**Organization:** Halisans Technologies  
**Date:** 2026-12-10  
**My role:** SIEM Content Developer & Data Analyst  
**Status:** Completed

## 1. Problem and objective
Create Microsoft Sentinel interactive workbook queries, visualize telemetry trends, explain security metrics, and record validation results.

SOC leaders and analysts require real-time, consolidated operational visibility into threat trends, analyst performance metrics, and log ingestion volumes. Interactive visual workbooks bridge technical telemetry with operational oversight.

## 2. Scope, environment and authorization
- **Systems/data:** Microsoft Sentinel Workbooks, Log Analytics Workspace, Azure Monitor.
- **Tools:** KQL (Kusto Query Language), Sentinel Workbooks UI, JSON Visualization Engine.
- **Authorization:** Approved dashboard development charter under Halisans Cybersecurity Operations.

## 3. Methodology
1. Metric Definition & Stakeholder Alignment: Defined core KPIs: Mean Time to Triage (MTTT), Alert Volume by Severity, Geographically Anomalous Logins, and EPS (Events Per Second).
2. KQL Query Optimization: Programmed 12 optimized KQL visual tiles using bin(), render timechart, summarize count(), and dynamic parameter filtering.
3. Workbook Layout & Drill-Through Design: Structured tabbed navigation enabling analysts to toggle between Executive KPI Overview, Authentication Analytics, and Threat Hunting tiles.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | Sentinel Workbook KQL Query Codebase | Proves advanced multi-table join and aggregation queries across SigninLogs and SecurityEvent. |
| E-02 | High-Resolution Dashboard Screenshot | Validates visual presentation of time-series authentication trends, alert heatmaps, and geographic flow maps. |
| E-03 | Analyst Usability & Performance Validation Sign-off | Demonstrates sub-2-second query load performance across 30 days of historical telemetry. |

## 5. Findings and analysis
Uncovered that 62% of security alerts were generated during non-business hours (11 PM - 5 AM), highlighting the need for automated off-hours SOAR response. Identified an unmonitored domain controller experiencing 4x normal log volume.

## 6. Outcome and recommendations
- **Disposition / deliverable:** Adopted as the primary operational dashboard for Halisans Tier-1 and Tier-2 SOC shift handovers.
- **Action taken or recommended:** Configured automated weekly PDF report generation dispatched directly to CISO and SOC Management.
- **Validation:** Validated metrics against raw Log Analytics queries; confirmed 100% mathematical parity across alert counters and MTTT calculations.
- **Limitations:** Workbook rendering performance degrades if querying raw, unindexed custom log tables spanning > 90 days without pre-aggregation.

## 7. Lessons learned
Parameterizing time ranges and subscription selectors ensures dashboards remain fast, responsive, and reusable across multiple workspaces.

## 8. References
Microsoft Sentinel Workbooks Documentation, KQL Best Practices for Azure Monitor.
