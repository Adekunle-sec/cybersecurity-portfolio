# MITRE ATT&CK Mapping

**Classification:** Supervised operational task  
**Organization:** Halisans Technologies  
**Date:** 2026-12-18  
**My role:** Cyber Threat Analyst — Behavioral Mapping  
**Status:** Completed

## 1. Problem and objective
Map observed adversary behaviors to MITRE ATT&CK techniques, distinguishing verified telemetry evidence from investigative assumptions.

Security teams frequently misattribute attacks or miss lateral movement stages because incidents are treated as disconnected alert dots. Mapping telemetry to MITRE ATT&CK establishes a structured threat narrative and exposes defensive blind spots.

## 2. Scope, environment and authorization
- **Systems/data:** Microsoft Sentinel, MITRE ATT&CK Navigator v14, Defender XDR incident telemetry.
- **Tools:** ATT&CK Navigator JSON, MITRE ATT&CK Matrix Mapping, KQL Advanced Hunting.
- **Authorization:** Authorized threat modeling scope under Halisans Cybersecurity Operations.

## 3. Methodology
1. Telemetry Dissection: Analyzed a multi-stage simulated intrusion across endpoint, identity, and network logs.
2. Technique Attribution: Mapped observed artifacts strictly to Tactics (Initial Access, Execution, Persistence, Privilege Escalation, Defense Evasion, Exfiltration).
3. Evidence Verification: Tagged each mapped technique with concrete telemetry evidence IDs, explicitly separating facts from unverified hypotheses.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | ATT&CK Navigator Heatmap Layer (intrusion_layer.json) | Proves visual coverage mapping across 8 distinct ATT&CK tactics and 14 sub-techniques. |
| E-02 | Telemetry Attribution Evidence Table | Validates mapping of certutil.exe to T1105 (Ingress Tool Transfer) with exact command-line string. |
| E-03 | Defensive Coverage Gap Matrix | Demonstrates identification of unmonitored techniques across Discovery and Credential Access tactics. |

## 5. Findings and analysis
Mapping revealed robust detection coverage across Initial Access (T1566) and Execution (T1059), but uncovered a major defensive visibility gap in Credential Access (T1003 OS Credential Dumping) where LSASS access was unlogged.

## 6. Outcome and recommendations
- **Disposition / deliverable:** Delivered comprehensive MITRE ATT&CK Intrusion Profile and Defensive Gap Assessment.
- **Action taken or recommended:** Enabled Audit Credential Validation GPO and deployed Defender Attack Surface Reduction (ASR) rule to block LSASS credential stealing.
- **Validation:** Re-tested LSASS access simulation; confirmed ASR rule successfully blocked injection and triggered high-severity telemetry.
- **Limitations:** Technique mapping is constrained by log retention policies and endpoint telemetry visibility; unmonitored systems create mapping voids.

## 7. Lessons learned
The MITRE ATT&CK framework should be used to guide telemetry collection priorities, not just as a post-incident reporting taxonomy.

## 8. References
MITRE ATT&CK Enterprise Matrix v14, NIST CSF 2.0 (DE.CM Detection Processes).
