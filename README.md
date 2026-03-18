# Vulnerability Assessment using Nessus Essentials

![Tool](https://img.shields.io/badge/Tool-Nessus%20Essentials-2ea44f?style=flat-square)
![Type](https://img.shields.io/badge/Scan-Basic%20Network%20Scan-0075ca?style=flat-square)
![Scope](https://img.shields.io/badge/Scope-Unauthenticated%20Lab%20Host-586069?style=flat-square)
![Status](https://img.shields.io/badge/Status-Complete-2ea44f?style=flat-square)
![Phases](https://img.shields.io/badge/Phases-5-6f42c1?style=flat-square)
![Environment](https://img.shields.io/badge/Environment-Controlled%20Lab-e36209?style=flat-square)

An end-to-end vulnerability assessment lab engagement covering scope definition, scan policy configuration, authenticated results export, risk-based prioritisation, and a structured remediation handoff report.

A hands-on vulnerability assessment project using **Nessus Essentials** (cloud-connected) to identify, analyse and prioritise security weaknesses on a lab network host. The engagement covers the complete end-to-end workflow: scope definition → scan configuration → execution → CSV export → risk-based prioritisation → remediation handoff.

This assessment was performed in a controlled lab environment for educational and portfolio purposes only. No production systems or real-world customer data were scanned or impacted.

---

## Table of Contents

- [Project Overview](#-project-overview)
- [Environment & Scope](#-environment--scope)
- [Methodology](#%EF%B8%8F-methodology)
- [Scan Configuration](#-scan-configuration)
- [Scan Execution & Results](#-scan-execution--results)
- [Findings Export & Structured Report](#-findings-export--structured-report)
- [Prioritised Vulnerabilities](#-prioritised-vulnerabilities-risk-based-view)
- [Remediation Handoff](#-remediation-handoff--recommendations)
- [Outcomes & Deliverables](#-outcomes--deliverables)
- [Tools & Technologies](#-tools--technologies)
- [Skills Demonstrated](#-skills-demonstrated)

---

## Project Overview

This project demonstrates hands-on vulnerability assessment competency using **Nessus Essentials** against a single lab virtual machine. The engagement replicates the initial vulnerability sweep a security analyst would conduct on a new asset, from scope agreement through to producing a prioritised findings report ready for IT remediation handoff.

The lab covers the complete vulnerability management lifecycle:

- ✅ Target scoping and rules of engagement definition
- ✅ Scan template selection and policy configuration
- ✅ Scan execution and dashboard monitoring
- ✅ CSV export and spreadsheet-based data structuring
- ✅ Risk-based prioritisation by severity and business impact
- ✅ Formal reporting and remediation handoff

---

## Environment & Scope

| Attribute | Detail |
|-----------|--------|
| **Scanner** | Nessus Essentials (cloud-connected) |
| **Scan Type** | Basic Network Scan (unauthenticated) |
| **Target** | Single lab VM — network-reachable over local network |
| **In Scope** | Network-reachable services, open ports, known CVEs, misconfigurations |
| **Out of Scope** | Web application logic, credentialed/authenticated scans, production systems |
| **Objective** | Identify network-level vulnerabilities; generate prioritised findings for IT team |

> The goal of this lab is to simulate how a security analyst performs an initial vulnerability sweep on a new asset and generates actionable outputs for remediation.

<img width="940" height="363" alt="image" src="https://github.com/user-attachments/assets/307e3a6c-a8ab-496a-bc93-01eb8144deb6" />

---

## Methodology

A structured five-phase approach was followed, aligned to standard vulnerability management lifecycle practices:

<details>

  <summary><strong>Phase 1 — Define Scope & Objectives</strong></summary>

- Confirmed target IP/hostname; verified only the lab host was in scope
- Agreed objective: identify network-level vulnerabilities and misconfigurations
- Documented rules of engagement and out-of-scope boundaries

</details>

<details>

  <summary><strong>Phase 2 — Select & Configure Scan Template</strong></summary>

- Created a new **Basic Network Scan** in Nessus Essentials
- Reviewed three available scan types:
  - **Basic Network Scan** ← selected
  - Advanced Scan
  - Web Application Scan
- Configured: general settings (name, description, target IP), port scanning (default TCP range), service detection, and performance options appropriate for a lab environment

<img width="940" height="389" alt="image" src="https://github.com/user-attachments/assets/5d46363c-d01a-4015-b916-07a3b9b2f263" />

<img width="940" height="383" alt="image" src="https://github.com/user-attachments/assets/d72da181-57c2-4798-8961-f0f0785d92e6" />


</details>

<details>
<summary><strong>Phase 3 — Run Scan & Monitor Execution</strong></summary>

- Launched the scan and monitored real-time progress from the Nessus dashboard
- Verified: successful scan completion, host discovery, vulnerability population
- Reviewed drill-down views showing per-plugin details, affected port and impacted host

</details>

<details>
<summary><strong>Phase 4 — Export & Structure Results</strong></summary>

- Exported full findings as **CSV** from Nessus
- Imported CSV into a spreadsheet to:
  - Normalise column names
  - Filter out purely informational findings (if required)
  - Sort and group by severity, plugin family, and affected port

</details>

<details>
<summary><strong>Phase 5 — Prioritise vulnerabilities & Prepare Remediation Report</strong></summary>

- Grouped findings by severity and potential business impact
- Highlighted **Critical** and **High** severity issues first (e.g. RCE, weak encryption, outdated services)
- Produced a prioritised report and remediation summary for the IT team

</details>

---

## Scan Configuration

Key configuration elements for the Basic Network Scan:

| Setting | Value |
|---------|-------|
| **Template** | Basic Network Scan |
| **Target** | Single Lab VM (IP/hostname) |
| **Scan Type** | Unauthenticated |
| **Port Range** | Default TCP |
| **Service Detection** | Enabled |
| **OS Detection** | Enabled |
| **Host Discovery** | Ping + TCP |
| **Export Format** | CSV |

```
Nessus Scan Templates Reviewed:
  [✓] Basic Network Scan     ← Selected
  [ ] Advanced Scan          ← Reviewed
  [ ] Web Application Scan   ← Reviewed
  [ ] Credentialed Scan      ← Out of scope
```

> Supporting screenshots in the repository illustrate:
> - The scan template selection screen
> - The target configuration page showing the defined scope
> - The detailed configuration tabs: General, Discovery, Port Scanning

<img width="940" height="388" alt="image" src="https://github.com/user-attachments/assets/bde92179-47c9-41c6-9b65-c176974e767c" />
<img width="940" height="385" alt="image" src="https://github.com/user-attachments/assets/97f77f25-c676-49f0-bbc7-e99184ebb877" />

---

## Scan Execution & Results

Once the configuration was saved, the Basic Network Scan was executed against the lab host.

During and after execution, the Nessus dashboard displayed:

- Host discovery and overall scan status (running → completed)
- Summary of vulnerabilities by severity: **Critical, High, Medium, Low**
- Drill-down views showing each plugin, affected port, and impacted host

**Scan Summary:**

| Severity | Count |
|----------|:-----:|
| 🔴 Critical | 2 |
| 🟠 High | 5 |
| 🔵 Medium | 11 |
| 🟢 Low | 9 |
| **Total** | **27** |

> Screenshots in the repository show:
> - The scan details page (status, duration, host count)
> - The vulnerability summary chart by severity
> - Example detailed finding views for individual plugins

<img width="940" height="496" alt="image" src="https://github.com/user-attachments/assets/86aa4814-d310-400b-bd5f-d7c9968996b3" />
<img width="940" height="503" alt="image" src="https://github.com/user-attachments/assets/60a974b5-e201-47bc-9baf-e1ec037e5753" />
<img width="940" height="498" alt="image" src="https://github.com/user-attachments/assets/b650db53-0c70-41f7-bc9c-6c501141b38c" />
<img width="940" height="487" alt="image" src="https://github.com/user-attachments/assets/e8eb701c-4d33-46e1-8868-43adf2d78722" />

---

## Findings Export & Structured Report

After scan completion:

### 1. CSV Export
The full set of Nessus findings was exported as a CSV file. The CSV contains columns including:

```
Plugin ID | Name | Severity | Description | Solution | Host | Port | Protocol | Plugin Family
```

### 2. Data Structuring
The CSV was imported into a spreadsheet to:
- Normalise column names
- Filter out informational findings (optional)
- Sort and group by severity and asset

### 3. Prioritised vulnerability view
 - A dedicated view/report was created to focus on:
 - Critical and High vulnerabilities first.
 - Medium/Low issues grouped by category (e.g. configuration hardening, informational).
- The screenshots in this section show the structured CSV displayed in tabular form and the prioritised vulnerability list derived from it.

<img width="940" height="336" alt="image" src="https://github.com/user-attachments/assets/482f72fd-83a9-4fc7-b234-d273af8ad9b0" />
<img width="940" height="407" alt="image" src="https://github.com/user-attachments/assets/77aa7678-e516-4e54-ac9d-982c263515d8" />

---

## 🎯 Prioritised Vulnerabilities (Risk-Based View)

Vulnerabilities were prioritised based on:

- **Technical severity** — as reported by Nessus (Critical, High, Medium, Low)
- **Potential impact** — on the host and business (e.g. remote code execution vs minor information disclosure)
- **Exploitability** — known exploits, network exposure, proof-of-concept availability

### Priority Tiers

**🔴 Critical — Immediate Action**
> Exploitable remote services allowing code execution or full host compromise. Treat as P1 — must be addressed before the host connects to any production network.

**🟠 High — Urgent**
> Weak or deprecated protocols, missing security patches on exposed services. Schedule remediation within the patch management SLA (typically 7–14 days).

**🔵 Medium — Scheduled**
> Misconfigurations, unnecessary access methods, hardening gaps. Address within the next maintenance window.

**🟢 Low / Informational — Routine**
> Minor findings, limited exploitability. Address as part of ongoing security hygiene and hardening cycles.

<img width="940" height="475" alt="image" src="https://github.com/user-attachments/assets/63dad99a-02ea-4fc9-b13f-0571edc0fb26" />

---

## Remediation Handoff & Recommendations

The final deliverables were positioned as artefacts for the IT remediation team:
- A structured CSV of all findings, ready for ingestion into a ticketing or tracking system.
- A prioritised vulnerability report highlighting the most critical issues and recommended order of remediation.
These outputs were positioned as artefacts for an IT remediation team to:
- Patch vulnerable services.
- Harden configurations.
- Disable unnecessary or legacy protocols.

This lab demonstrates the full workflow from scan configuration through to analysis and handoff, reflecting how a security analyst would operate in a real world vulnerability management process.


## Outcomes & Deliverables

| Deliverable | Description |
|-------------|-------------|
| **Structured CSV Export** | Normalised Nessus findings — Plugin ID, Severity, Host, Port, Protocol, Name, Synopsis, Solution, Plugin Family |
| **Prioritised Vulnerability Report** | Risk-sorted findings report with Critical/High issues first, Medium/Low grouped by category |
| **Scan Configuration Documentation** | Documented scan policy, template selection rationale, and configuration settings |
| **Remediation Recommendations** | Actionable, severity-ordered remediation steps with patch references and hardening guidance |

---

## Tools & Technologies

```
Scanner          Nessus Essentials (cloud-connected)
Scan Type        Basic Network Scan (unauthenticated)
Export Format    CSV
Data Processing  Microsoft Excel / Google Sheets
Lab Platform     VirtualBox / VMware
Target OS        Linux-based lab VM
Reference        NIST NVD (CVE lookup & severity validation)
Dashboard        Nessus Web UI (scan monitoring & results)
```

---

## Skills Demonstrated

![Vulnerability Assessment](https://img.shields.io/badge/Technical-Vulnerability%20Assessment-2ea44f?style=flat-square)
![Nessus](https://img.shields.io/badge/Tool-Nessus%20Essentials-2ea44f?style=flat-square)
![Scan Config](https://img.shields.io/badge/Technical-Scan%20Scoping%20%26%20Configuration-0075ca?style=flat-square)
![CVE](https://img.shields.io/badge/Technical-CVE%20Identification%20%26%20Analysis-0075ca?style=flat-square)
![CSV Export](https://img.shields.io/badge/Technical-Findings%20Export%20%28CSV%29-0075ca?style=flat-square)
![Data Structure](https://img.shields.io/badge/Technical-Data%20Structuring%20%26%20Normalisation-586069?style=flat-square)
![Prioritisation](https://img.shields.io/badge/GRC-Risk--Based%20Prioritisation-6f42c1?style=flat-square)
![Severity](https://img.shields.io/badge/GRC-Severity%20Classification-6f42c1?style=flat-square)
![Exploitability](https://img.shields.io/badge/GRC-Exploitability%20Analysis-6f42c1?style=flat-square)
![Remediation](https://img.shields.io/badge/Soft%20Skill-Remediation%20Reporting-e36209?style=flat-square)
![Handoff](https://img.shields.io/badge/Soft%20Skill-IT%20Team%20Handoff-e36209?style=flat-square)
![VM Lifecycle](https://img.shields.io/badge/Technical-Vulnerability%20Management%20Lifecycle-0075ca?style=flat-square)

---

## 📂 Repository Structure

```
📁 Vulnerability-Assessment-Nessus-Essentials/
│
├── README.md                          ← This file
├── findings.csv                       ← Full Nessus CSV export (normalised)
├── Prioritised-Vulnerability-Report.xlsx  ← Sorted findings by severity
├── Scan-Configuration-Notes.md        ← Documented scan policy & settings
├── Remediation-Handoff-Report.pdf     ← Formatted report for IT team
└── screenshots/
    ├── 01-scan-templates.png          ← Template selection screen
    ├── 02-scan-config.png             ← Target & general configuration
    ├── 03-port-settings.png           ← Port scanning configuration
    ├── 04-scan-running.png            ← Scan execution dashboard
    ├── 05-scan-completed.png          ← Completed scan with summary
    ├── 06-csv-export.png              ← Structured CSV in spreadsheet
    └── 07-priority-report.png         ← Prioritised vulnerability view
```

---

## 📬 Contact

If you have questions about this project or would like to discuss vulnerability management, Nessus, or cybersecurity more broadly:

- 🔗 **GitHub:** [@oluwaseunadenuga](https://github.com/oluwaseunadenuga)
- 💼 **LinkedIn:** [linkedin.com/in/oluwaseunadenuga](https://linkedin.com/in/oluwaseunadenuga)
- 📧 **Email:** Available via LinkedIn

---

<div align="center">




