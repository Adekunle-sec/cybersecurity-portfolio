<p align="center">
  <img src="../cybersecurity-banner.svg" width="100%" alt="Cybersecurity Defense & Operations Portfolio" />
</p>

<p align="center">
  <a href="https://github.com/Adekunle-sec"><img src="https://img.shields.io/badge/Author%20Profile-Adekunle--sec-24292e?style=for-the-badge&logo=github&logoColor=white" /></a>
  <a href="https://www.linkedin.com/in/adekunle-olanrewaju-20261844b"><img src="https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="https://github.com/Adekunle-sec/cybersecurity-portfolio"><img src="https://img.shields.io/badge/Parent%20Portfolio-Cybersecurity%20Portfolio-38BDF8?style=for-the-badge&logo=shield&logoColor=white" /></a>
  <a href="mailto:tayour.ola@gmail.com"><img src="https://img.shields.io/badge/Email-Direct%20Inquiry-EA4335?style=for-the-badge&logo=gmail&logoColor=white" /></a>
</p>

---

# Adekunle Olanrewaju | Security Operations Center (SOC) Analyst

**Microsoft Sentinel | Microsoft Defender XDR | Threat Modeling | Incident Response & CTI**

📍 Lagos, Nigeria · [LinkedIn](https://www.linkedin.com/in/adekunle-olanrewaju-20261844b) · [tayour.ola@gmail.com](mailto:tayour.ola@gmail.com) · [GitHub Profile](https://github.com/Adekunle-sec)

---

## 🎯 Professional Profile

I am a **Security Operations Center (SOC) Analyst** with hands-on technical proficiency across cloud SIEM/XDR operations, threat modeling, security log analysis, and incident response workflows at **Halisans Technologies**. My portfolio documents verifiable security activities: data flow threat assessments, KQL detection queries, alert triage, automated response playbooks, and threat intelligence analysis mapped to the MITRE ATT&CK framework.

---

## 💼 Practical Experience | Halisans Technologies

**Role:** Security Operations Center (SOC) Analyst  
**Period:** 2026 – Present  
**Environment:** Supervised Cybersecurity Operations & Enterprise Defense Labs  

### 🛡️ Architectural Foundations & Operational Triad
- **The Core Triage Definitions:**
  - **Event:** Any baseline activity occurring across endpoints, servers, or directory services (e.g., standard user logon).
  - **Alert:** An automated system notification indicating an anomalous or threshold-breaching event (*"Hey, look at this!"*).
  - **Incident:** A verified security event confirmed by an analyst as a tangible threat requiring formal containment, remediation, and root-cause analysis.
- **Defense-in-Depth Architecture:**
  - **Microsoft Defender XDR:** The tactical security force on the ground inspecting local endpoints, user identities, and email channels to intercept and halt malicious activity at the point of origin.
  - **Microsoft Sentinel SIEM/SOAR:** The centralized surveillance command center aggregating feeds from Defender, network firewalls, Linux servers, and multi-cloud infrastructure for enterprise-wide correlation.
- **Hybrid Device Onboarding via Azure Arc & Azure Monitor Agent (AMA):**
  - *Linux Host Onboarding:* `chmod +x OnboardAzureArc.sh && sudo ./OnboardAzureArc.sh` (verification: `sudo azcmagent show`).
  - *Windows Host Onboarding:* `Set-ExecutionPolicy -ExecutionPolicy Bypass -Scope Process; .\OnboardAzureArc.ps1` (verification: `azcmagent show`).
  - *Data Collection Rules (DCR):* XPath telemetry filtering ingesting critical authentication events:
    `security!*[System[(EventID=4624 OR EventID=4625 OR EventID=4740)]]`
- **Kerberos Authentication Architecture:**
  - Deconstructed the ticket-granting security model: **Authentication Server (AS)** verifying client credentials to issue a **Ticket Granting Ticket (TGT)**, **Ticket Granting Server (TGS)** exchanging the TGT for service tickets, and secure client-service mutual authentication.
  - Aligned to **ISO/IEC 27001 Controls A8.15 & A8.16 (Logging and Monitoring)**.
- **Custom Threat Indicator Blocking:**
  - Automated threat mitigation via Microsoft Defender: `Settings -> Endpoints -> Indicators -> File hashes -> Add indicator -> Action: Block execution`.

---

## 🚀 Flagship Project: Student Login Portal | Threat Modeling & Risk Assessment

Located in **[`./threat-modeling-risk-assessment-saas/`](./threat-modeling-risk-assessment-saas/)**:

| Deliverable | Description | File Link |
|---|---|---|
| **Level-1 Data Flow Diagram (DFD)** | Visual architectural model of the Student Login Portal showing trust boundaries, 3 core processes, data stores, and external student entity. | [View DFD (`DFD.png`)](./threat-modeling-risk-assessment-saas/DFD.png) |
| **1,000-Row Threat Risk Register** | Quantitative and qualitative STRIDE risk register calculating CVSS v3.1 base scores, likelihood, and business impact. | [Download Register (`Threat_Risk_Register.xlsx`)](./threat-modeling-risk-assessment-saas/Threat_Risk_Register.xlsx) |
| **Risk Treatment Plan** | Actionable mitigation matrix detailing risk acceptance, avoidance, mitigation, designated owners, and residual risk. | [Download Plan (`Risk_Treatment_Plan.xlsx`)](./threat-modeling-risk-assessment-saas/Risk_Treatment_Plan.xlsx) |
| **Control Mapping Matrix** | Comprehensive cross-mapping of identified threats to ISO/IEC 27001:2022 Annex A and NIST SP 800-53 Rev 5 controls. | [Download Matrix (`Control_Mapping_Matrix.xlsx`)](./threat-modeling-risk-assessment-saas/Control_Mapping_Matrix.xlsx) |
| **OWASP Threat Dragon Report** | 24-page formal threat assessment report summarizing architectural weaknesses and mitigation roadmaps. | [View Report (`OWASP_Threat_Dragon_Report.pdf`)](./threat-modeling-risk-assessment-saas/OWASP_Threat_Dragon_Report.pdf) |

---

## 📂 Core SOC Case Studies

| Case Study | Focus & Objective | Key Evidence & Queries |
|---|---|---|
| **[01. Authentication Alert Investigation](./case-studies/01-authentication-alert-investigation/)** | Triage anomalous authentications and brute-force attempts across Windows Security Events (`4624`, `4625`) and Entra ID sign-in logs. | KQL authentication hunting queries, correlation tables, and incident disposition log. |
| **[02. Defender Endpoint Triage](./case-studies/02-defender-endpoint-triage/)** | Triage endpoint alerts in Microsoft Defender, analyzing suspicious PowerShell invocations and file modifications. | Defender incident summary, process execution timeline, and containment procedure. |
| **[03. Sentinel Automation Playbook](./case-studies/03-sentinel-automation-playbook/)** | Build automated SOAR playbooks using Azure Logic Apps triggered by Microsoft Sentinel incident generation. | Logic App workflow JSON, execution audit logs, and notification dispatch confirmation. |
| **[04. SOC Monitoring Dashboard](./case-studies/04-soc-monitoring-dashboard/)** | Design an interactive SOC monitoring dashboard in Microsoft Sentinel Workbooks tracking authentication failures and VIP risk. | Workbook KQL queries, data visualization layout, and refresh validation. |

---

## 🕵️ Threat Intelligence & Security Analysis

Located in **[`./threat-intelligence-and-detection/`](./threat-intelligence-and-detection/)**:

| Analysis Project | Focus | Reference |
|---|---|---|
| **Threat Intelligence Assessment** | Evaluated threat feeds (AlienVault OTX, SOCRadar, VirusTotal) for relevance against organizational assets. | [View Case Study](./threat-intelligence-and-detection/case-studies/01-threat-intelligence-assessment/) |
| **IoC-to-Detection Handoff** | Converted extracted file hashes, domain names, and IP indicators into operational KQL / Sigma rules. | [View Case Study](./threat-intelligence-and-detection/case-studies/02-ioc-to-detection-handoff/) |
| **MITRE ATT&CK Mapping** | Mapped adversary behaviors and observed TTPs (APT29, LockBit 3.0) against the MITRE ATT&CK enterprise matrix. | [View Case Study](./threat-intelligence-and-detection/case-studies/03-mitre-attandck-mapping/) |
| **Security Investigation Report** | Sanitized end-to-end incident investigation report detailing root cause analysis and post-incident hardening. | [View Case Study](./threat-intelligence-and-detection/case-studies/04-security-investigation-report/) |

---

## 🔬 Hands-On SOC Technical Labs

| Lab Environment | Description | Lab Directory |
|---|---|---|
| **Sentinel & Defender SOC Lab** | Multi-VM enterprise SIEM deployment with telemetry ingestion, alerting rules, and incident investigation. | [`./labs/01-sentinel-defender-soc-lab/`](./labs/01-sentinel-defender-soc-lab/) |
| **Threat Intelligence & Detection** | Threat intel ingestion pipeline and custom KQL analytic rule development mapped to MITRE tactics. | [`./labs/03-threat-intel-mitre-detection/`](./labs/03-threat-intel-mitre-detection/) |
| **SOAR Sentinel Playbooks** | Automated containment and incident enrichment playbooks leveraging Azure Logic Apps. | [`./labs/04-soar-sentinel-playbooks/`](./labs/04-soar-sentinel-playbooks/) |

---

## 🛠️ Technical Capabilities & Tooling

- **SIEM / XDR:** Microsoft Sentinel, Microsoft Defender for Endpoint, Log Analytics Workspaces, Splunk, Wazuh
- **Query Languages:** KQL (Kusto Query Language), PowerShell, Bash
- **Threat Modeling & Risk:** OWASP Threat Dragon, STRIDE framework, CVSS v3.1 scoring, DFD Level-0/1
- **Threat Intelligence:** AlienVault OTX, SOCRadar, VirusTotal, MITRE ATT&CK Enterprise Matrix, MISP
- **Automation / SOAR:** Azure Logic Apps, Sentinel Playbooks, Webhook integrations
- **ITSM & Ticketing:** Jira Service Management, ServiceNow ticketing workflows

---

## 🛡️ Evidence & Documentation Standards

Every case study in this repository adheres to verified enterprise documentation standards:
1. **Scenario & Authorization:** Strictly bounded within authorized corporate lab environments or approved operational scopes.
2. **Sanitized Evidence:** All IP addresses, hostnames, usernames, and tenant IDs are sanitized or synthetic to protect confidential infrastructure.
3. **Reproducibility:** Queries, scripts, and DFD models are included to allow peer review and replication.

---

## 📬 Contact & Links

- **LinkedIn:** [linkedin.com/in/adekunle-olanrewaju-20261844b](https://www.linkedin.com/in/adekunle-olanrewaju-20261844b)
- **Email:** [tayour.ola@gmail.com](mailto:tayour.ola@gmail.com)
- **GitHub:** [github.com/Adekunle-sec](https://github.com/Adekunle-sec)

---
*All operational and lab cases are verified, sanitized, and evidence-backed.*
