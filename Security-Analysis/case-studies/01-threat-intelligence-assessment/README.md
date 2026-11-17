# Threat Intelligence Assessment

**Classification:** Supervised operational task  
**Organization:** Halisans Technologies  
**Date:** 2026-12-13  
**My role:** Cyber Threat Intelligence (CTI) Analyst  
**Status:** Completed

## 1. Problem and objective
Select relevant AlienVault OTX and SOCRadar threat intelligence pulses, validate indicator fidelity, and assess local infrastructure relevance.

Raw threat intelligence feeds flood security operations with thousands of generic indicators of compromise (IOCs). Without contextual validation and relevance scoring, analysts waste hundreds of hours investigating irrelevant external noise.

## 2. Scope, environment and authorization
- **Systems/data:** AlienVault OTX, SOCRadar Dark Web Monitoring, VirusTotal Enterprise, Microsoft Sentinel.
- **Tools:** MISP, OTX Python SDK, VirusTotal API, KQL Threat Intelligence Indicators table.
- **Authorization:** Authorized CTI research environment within Halisans Cybersecurity Operations.

## 3. Methodology
1. Adversary Profiling: Identified active ransomware campaigns (LockBit 3.0, BlackCat) targeting technology and logistics sectors.
2. Indicator Extraction & Scoring: Ingested 180 IOCs (SHA-256 hashes, C2 IPs, malicious domains), filtering out indicators older than 30 days or with confidence scores < 75.
3. Local Relevance Mapping: Queried internal SIEM telemetry to cross-reference extracted indicators against internal enterprise endpoints and proxy logs.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | Curated Threat Intelligence Pulse Report | Proves tactical analysis of LockBit 3.0 ransomware TTPs and validated file hash signatures. |
| E-02 | KQL Telemetry Cross-Referencing Query (Search_IOCs.kql) | Validates historical searching across 90 days of internal DNS and proxy traffic. |
| E-03 | Indicator Ingestion Confirmation Log in Sentinel | Demonstrates successful push of 45 high-fidelity IOCs into the Sentinel ThreatIntelligenceIndicator table. |

## 5. Findings and analysis
Confirmed that 85% of public indicators in general feeds had zero relevance to our Microsoft-centric hybrid environment. Identified 1 historical DNS query matching a known LockBit command-and-control domain from a decommissioned testing host.

## 6. Outcome and recommendations
- **Disposition / deliverable:** Produced vetted High-Fidelity Threat Advisory Briefing with 45 actionable indicators.
- **Action taken or recommended:** Deployed automated blocking rules on enterprise perimeter firewalls and Defender for Endpoint for all 45 validated indicators.
- **Validation:** Re-tested firewall proxy filters with synthetic non-destructive lookup queries; confirmed immediate block disposition.
- **Limitations:** Threat actor rapid infrastructure turnover means IP-based indicators decay within 48 to 72 hours; behavioral detection is superior.

## 7. Lessons learned
Focusing on TTPs (Techniques) rather than static IOCs (hashes/IPs) provides substantially longer-lasting defensive value (Pyramid of Pain).

## 8. References
David Bianco Pyramid of Pain, AlienVault OTX Pulse Documentation, MITRE ATT&CK Group G0096.
