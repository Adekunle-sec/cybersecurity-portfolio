# Defender Endpoint Triage

**Classification:** Authorized production work  
**Organization:** Halisans Technologies  
**Date:** 2026-12-04  
**My role:** SOC Analyst — Incident Response & Triage  
**Status:** Completed

## 1. Problem and objective
Review endpoint alerts in Microsoft Defender for Endpoint, collect permitted forensic artifacts, determine threat disposition, and execute containment.

Endpoint detection alerts must be triaged within minutes to determine whether an alert represents benign administrative activity or malicious execution (malware, living-off-the-land binaries). Rapid triage minimizes adversary dwell time and halts ransomware staging.

## 2. Scope, environment and authorization
- **Systems/data:** Microsoft Defender for Endpoint (MDE), Windows 11 Enterprise workstations, Live Response console.
- **Tools:** Defender for Endpoint XDR Portal, KQL Advanced Hunting, VirusTotal, Live Response CLI.
- **Authorization:** Authorized endpoint triage and containment authority granted by Halisans SOC Lead.

## 3. Methodology
1. Alert Ingestion & Process Tree Reconstruction: Analyzed alert execution trees in Defender, tracing parent-child process ancestry from WINWORD.EXE to powershell.exe.
2. Forensic Artifact Collection: Utilized MDE Live Response to extract process hashes, command-line arguments, and dropped temporary script payloads.
3. Disposition & Containment: Determined true positive status, isolated the affected workstation from the network via Defender XDR, and submitted hashes to threat analysis.

## 4. Evidence
| Evidence ID | Sanitized artifact | What it proves |
|---|---|---|
| E-01 | Defender XDR Process Tree Ancestry Diagram | Proves anomalous spawning of PowerShell with obfuscated base64 encoded parameters from an Office process. |
| E-02 | MDE Advanced Hunting KQL Script | Validates query tracking file creation events in %APPDATA% within 5 minutes of execution. |
| E-03 | Host Isolation Confirmation Snapshot | Demonstrates successful network containment of target endpoint preventing lateral connectivity. |

## 5. Findings and analysis
Identified an encoded PowerShell command attempting outbound C2 beaconing. MDE automated cloud analysis flagged payload hash as TrojanDownloader with a 68/72 VirusTotal score.

## 6. Outcome and recommendations
- **Disposition / deliverable:** True Positive High-Severity Incident; workstation isolated, malicious process terminated, and persistence keys purged.
- **Action taken or recommended:** Executed full automated antivirus scan via Defender, reimaged target workstation per IR playbook, and pushed global block indicator across all endpoints.
- **Validation:** Verified zero outbound network connections from isolated host and confirmed no credential harvesting occurred via LSASS memory dumping.
- **Limitations:** Live Response network restrictions prevented dynamic in-memory memory dump extraction across limited-bandwidth remote connections.

## 7. Lessons learned
Attack Surface Reduction (ASR) rules blocking Office applications from creating child processes would have proactively blocked this vector.

## 8. References
Microsoft Defender for Endpoint Triage Guide, MITRE ATT&CK T1059.001 (PowerShell), T1204.002 (Malicious File).
