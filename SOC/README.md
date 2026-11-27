# Adekunle Olanrewaju | Security Operations Center (SOC) Analyst

**Microsoft Sentinel | Microsoft Defender | Threat Modeling | Detection & Incident Response**

📍 Lagos, Nigeria · [LinkedIn](https://www.linkedin.com/in/adekunle-olanrewaju-20261844b) · [tayour.ola@gmail.com](mailto:tayour.ola@gmail.com) · [GitHub Profile](https://github.com/Adekunle-sec)

---

## 🎯 Professional Profile

I am a **Security Operations Center (SOC) Analyst** with hands-on technical proficiency across cloud SIEM/XDR operations, threat modeling, security log analysis, and incident response workflows at **Halisans Technologies**. My portfolio documents verifiable security activities: data flow threat assessments, KQL detection queries, alert triage, automated response playbooks, and threat intelligence analysis mapped to the MITRE ATT&CK framework.

---

## 💼 Practical Experience | Halisans Technologies

**Role:** Security Operations Center (SOC) Analyst  
**Period:** 2026 – Present  
**Environment:** Supervised Cybersecurity Operations & Enterprise Defense Labs  

### Selected Responsibilities & Operational Activities
- **Threat Modeling & Attack Surface Analysis:** Conducted STRIDE architectural threat models for multi-tenant SaaS environments using OWASP Threat Dragon, formulating risk registers and ISO/NIST mitigation plans.
- **Authentication Alert Investigation:** Analyzed Windows security events (`4624`, `4625`, `4770`) and Entra ID sign-in logs using Kusto Query Language (KQL) to triage anomalous authentications.
- **Defender Endpoint Triage & Investigation:** Investigated Microsoft Defender XDR alerts, collected endpoint timeline evidence, assessed threat severity, and recommended host containment measures.
- **Sentinel SOAR Automation:** Architected automated incident triage and notification workflows in Azure Logic Apps triggered upon incident generation in Microsoft Sentinel.
- **Threat Intelligence & MITRE Mapping:** Evaluated OTX and threat feeds, extracting indicators of compromise (IoCs) and engineering detection rules mapped to MITRE ATT&CK tactics and techniques.

---

## 🚀 Flagship Project: Threat Modeling & Risk Assessment for a SaaS Product

| Subproject / Repository | Focus & Architecture | Evidence & Deliverables |
|---|---|---|
| **[Threat Modeling & Risk Assessment for a SaaS Product](./Threat-Modeling-and-Risk-Assessment-for-a-SaaS-Product/)**<br>*(Standalone repo: [threat-modeling-risk-assessment-saas](https://github.com/Adekunle-sec/threat-modeling-risk-assessment-saas))* | STRIDE threat modeling and quantitative risk assessment of an enterprise multi-tenant SaaS application running on Azure. | • [OWASP Threat Dragon DFD](./Threat-Modeling-and-Risk-Assessment-for-a-SaaS-Product/DFD.png)<br>• [1000-Row Threat Risk Register (XLSX)](./Threat-Modeling-and-Risk-Assessment-for-a-SaaS-Product/Threat_Risk_Register.xlsx)<br>• [Risk Treatment Plan (XLSX)](./Threat-Modeling-and-Risk-Assessment-for-a-SaaS-Product/Risk_Treatment_Plan.xlsx)<br>• [Control Mapping Matrix (ISO 27001 / NIST 800-53)](./Threat-Modeling-and-Risk-Assessment-for-a-SaaS-Product/Control_Mapping_Matrix.xlsx)<br>• [OWASP Threat Dragon Report (PDF)](./Threat-Modeling-and-Risk-Assessment-for-a-SaaS-Product/OWASP_Threat_Dragon_Report.pdf) |

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
| **Threat Intelligence Assessment** | Evaluated threat feeds (AlienVault OTX, SOC Radar) for relevance against organizational assets. | [View Case Study](./threat-intelligence-and-detection/case-studies/01-threat-intelligence-assessment/) |
| **IoC-to-Detection Handoff** | Converted extracted file hashes, domain names, and IP indicators into operational KQL / Sigma rules. | [View Case Study](./threat-intelligence-and-detection/case-studies/02-ioc-to-detection-handoff/) |
| **MITRE ATT&CK Mapping** | Mapped adversary behaviors and observed TTPs against the MITRE ATT&CK enterprise matrix. | [View Case Study](./threat-intelligence-and-detection/case-studies/03-mitre-attandck-mapping/) |
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

- **SIEM / XDR:** Microsoft Sentinel, Microsoft Defender for Endpoint, Log Analytics Workspaces
- **Query Languages:** KQL (Kusto Query Language), PowerShell, Bash
- **Threat Modeling & Risk:** OWASP Threat Dragon, STRIDE framework, CVSS v3.1 scoring, DFD Level-0/1
- **Threat Intelligence:** AlienVault OTX, VirusTotal, MITRE ATT&CK Enterprise Matrix, MISP
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
