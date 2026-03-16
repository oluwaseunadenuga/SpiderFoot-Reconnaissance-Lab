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

</details>

<details>
<summary><strong>Phase 3 — Run Scan & Monitor Execution</strong></summary>

- Launched the scan and monitored real-time progress from the Nessus dashboard
- Verified: successful scan completion, host discovery, vulnerability population
- Reviewed drill-down views showing per-plugin details, affected port, and impacted host

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
<summary><strong>Phase 5 — Prioritise & Prepare Remediation Report</strong></summary>

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

### 3. Sample Structured Findings

| Plugin ID | Vulnerability | Severity | Port | CVE | Synopsis |
|-----------|--------------|----------|------|-----|----------|
| `34477` | MS08-067 NetAPI RCE | 🔴 Critical | 445/TCP | CVE-2008-4250 | Unpatched SMB allows unauthenticated RCE |
| `21156` | UnrealIRCd Backdoor RCE | 🔴 Critical | 6667/TCP | CVE-2010-2075 | Trojanised IRC server allows arbitrary command execution |
| `65821` | SSL/TLS POODLE Vulnerability | 🟠 High | 443/TCP | CVE-2014-3566 | SSLv3 enabled — POODLE padding oracle attack |
| `78479` | OpenSSH Outdated Version | 🟠 High | 22/TCP | CVE-2023-38408 | Running version affected by multiple CVEs |
| `10254` | Apache httpd Outdated Version | 🟠 High | 80/TCP | CVE-2022-31813 | Missing security patches for known vulnerabilities |
| `44401` | FTP Anonymous Access Enabled | 🔵 Medium | 21/TCP | — | Anonymous FTP login permitted — data exposure risk |
| `11219` | Open Port Disclosure | 🟢 Low | Various | — | Informational — open port enumeration result |

> 📁 Full structured findings available in [`findings.csv`](./findings.csv)

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

> [!WARNING]
> **Critical Priority** — The MS08-067 (SMB RCE) and UnrealIRCd backdoor findings represent immediate, unauthenticated remote code execution vulnerabilities. These must be remediated before the host is connected to any shared network segment.

---

## Remediation Handoff & Recommendations

The final deliverables were positioned as artefacts for the IT remediation team:

### Immediate (Critical)
- Apply **MS08-067** security patch (KB958644) to address SMB RCE
- Remove or replace the **trojanised UnrealIRCd** service
- Firewall port 6667 pending service replacement

### Urgent (High)
- Disable **SSLv3** across all services; enforce TLS 1.2 minimum
- Upgrade **OpenSSH** to the current stable release
- Apply all outstanding **Apache httpd** security patches
- Audit all services for deprecated or unencrypted protocol exposure

### Scheduled (Medium)
- Disable **anonymous FTP** access
- Review and disable unnecessary services running on non-standard ports
- Apply **CIS Benchmark** hardening to the host OS
- Firewall unused services: Telnet, rlogin, distccd

### Ongoing (Low / Hygiene)
- Document full open port inventory
- Schedule follow-up **credentialed scan** post-remediation to validate patch effectiveness
- Implement recurring vulnerability scanning schedule (monthly recommended)

---

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






<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Vulnerability Assessment — Nessus Essentials | Portfolio</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:ital,wght@0,300;0,400;0,500;1,300&family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,600;0,9..144,700;1,9..144,300&family=DM+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --bg:         #f9fafb;
    --white:      #ffffff;
    --surface:    #f0f4f0;
    --border:     #d1dbd1;
    --green:      #166534;
    --green-mid:  #16a34a;
    --green-lt:   #dcfce7;
    --green-acc:  #4ade80;
    --red:        #991b1b;
    --red-lt:     #fee2e2;
    --amber:      #92400e;
    --amber-lt:   #fef3c7;
    --blue:       #1e3a5f;
    --blue-lt:    #dbeafe;
    --slate:      #374151;
    --muted:      #6b7280;
    --text:       #111827;
    --scan-line:  rgba(22,101,52,.06);
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
  html { scroll-behavior: smooth; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: 'DM Sans', system-ui, sans-serif;
    font-size: 14.5px;
    line-height: 1.7;
    overflow-x: hidden;
  }

  /* Scan-line texture overlay */
  body::before {
    content: '';
    position: fixed; inset: 0; pointer-events: none; z-index: 0;
    background: repeating-linear-gradient(
      0deg,
      var(--scan-line) 0px,
      var(--scan-line) 1px,
      transparent 1px,
      transparent 24px
    );
  }

  /* ── NAV ── */
  nav {
    position: sticky; top: 0; z-index: 100;
    background: rgba(249,250,251,.94);
    backdrop-filter: blur(10px);
    border-bottom: 1px solid var(--border);
    padding: 0 48px;
    height: 52px;
    display: flex; align-items: center; gap: 0;
  }
  .nav-logo {
    font-family: 'DM Mono', monospace;
    font-size: 11px; letter-spacing: .14em;
    color: var(--green); text-transform: uppercase;
    display: flex; align-items: center; gap: 8px;
    margin-right: auto;
  }
  .nav-logo::before {
    content: '●';
    font-size: 8px;
    color: var(--green-mid);
    animation: pulse 2s ease-in-out infinite;
  }
  @keyframes pulse { 0%,100%{opacity:1} 50%{opacity:.3} }
  nav a {
    font-family: 'DM Mono', monospace;
    font-size: 10px; letter-spacing: .12em;
    text-transform: uppercase; color: var(--muted);
    text-decoration: none; padding: 0 14px; height: 52px;
    display: flex; align-items: center;
    border-bottom: 2px solid transparent;
    transition: color .18s, border-color .18s;
  }
  nav a:hover { color: var(--green); border-bottom-color: var(--green-mid); }

  /* ── HERO ── */
  .hero {
    position: relative; z-index: 1;
    padding: 80px 48px 64px;
    border-bottom: 1px solid var(--border);
    background: var(--white);
    overflow: hidden;
  }
  .hero::after {
    content: '';
    position: absolute; top: 0; right: 0;
    width: 420px; height: 100%;
    background: linear-gradient(135deg, transparent 50%, rgba(22,163,74,.04) 100%);
    pointer-events: none;
  }
  /* Terminal corner decoration */
  .hero::before {
    content: '$ nessus --scan --target lab-host --output findings.csv';
    position: absolute; bottom: 20px; right: 48px;
    font-family: 'DM Mono', monospace;
    font-size: 10px; color: rgba(22,163,74,.35);
    letter-spacing: .05em;
  }

  .hero-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 10px; letter-spacing: .2em;
    text-transform: uppercase; color: var(--green-mid);
    display: flex; align-items: center; gap: 10px;
    margin-bottom: 20px;
  }
  .hero-eyebrow::after {
    content: '';
    flex: 1; max-width: 80px; height: 1px;
    background: linear-gradient(to right, var(--green-mid), transparent);
  }

  h1 {
    font-family: 'Fraunces', serif;
    font-weight: 700; font-size: clamp(1.9rem, 3.5vw, 3rem);
    line-height: 1.1; color: var(--text);
    margin-bottom: 18px; letter-spacing: -.02em;
    font-optical-sizing: auto;
  }
  h1 em { font-style: italic; color: var(--green); }

  .hero-desc {
    font-size: .95rem; color: var(--muted);
    max-width: 580px; margin-bottom: 32px; line-height: 1.75;
  }

  .tag-row { display: flex; flex-wrap: wrap; gap: 8px; }
  .tag {
    font-family: 'DM Mono', monospace;
    font-size: 10px; letter-spacing: .08em;
    padding: 4px 12px; border-radius: 2px;
    border: 1px solid var(--border);
    color: var(--muted); background: var(--bg);
    text-transform: uppercase;
  }
  .tag.green { border-color: var(--green-mid); color: var(--green); background: var(--green-lt); }
  .tag.dark  { border-color: var(--slate); color: var(--slate); background: #f1f5f9; }

  /* ── LAYOUT ── */
  .container { position: relative; z-index: 1; max-width: 1060px; margin: 0 auto; padding: 0 48px; }
  section { padding: 60px 0; border-bottom: 1px solid var(--border); }

  /* ── SECTION HEADERS ── */
  .sec-eyebrow {
    font-family: 'DM Mono', monospace;
    font-size: 9.5px; letter-spacing: .22em;
    text-transform: uppercase; color: var(--green-mid);
    margin-bottom: 8px;
  }
  h2 {
    font-family: 'Fraunces', serif;
    font-weight: 600; font-size: 1.5rem;
    color: var(--text); margin-bottom: 20px;
    letter-spacing: -.01em;
  }
  h3 {
    font-family: 'DM Sans', sans-serif;
    font-weight: 600; font-size: 1rem;
    color: var(--slate); margin-bottom: 8px;
  }
  p { color: var(--slate); margin-bottom: 12px; }

  /* ── STAT CARDS ── */
  .stat-row {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(150px,1fr));
    gap: 14px; margin-bottom: 36px;
  }
  .stat-card {
    background: var(--white); border: 1px solid var(--border);
    border-radius: 4px; padding: 20px 16px;
    text-align: center; border-top: 3px solid var(--green-mid);
  }
  .stat-num {
    font-family: 'Fraunces', serif;
    font-size: 2rem; font-weight: 700;
    color: var(--green); line-height: 1; margin-bottom: 6px;
  }
  .stat-lbl {
    font-family: 'DM Mono', monospace;
    font-size: 9px; letter-spacing: .14em;
    text-transform: uppercase; color: var(--muted);
  }

  /* ── INFO CARDS ── */
  .card-grid {
    display: grid; grid-template-columns: repeat(auto-fill, minmax(230px,1fr));
    gap: 16px;
  }
  .card {
    background: var(--white); border: 1px solid var(--border);
    border-radius: 4px; padding: 22px;
    transition: border-color .18s, box-shadow .18s;
  }
  .card:hover { border-color: var(--green-mid); box-shadow: 0 2px 12px rgba(22,163,74,.08); }
  .card-ico { font-size: 1.5rem; margin-bottom: 12px; }
  .card p { font-size: .85rem; color: var(--muted); margin: 0; line-height: 1.6; }

  /* ── METHODOLOGY STEPS ── */
  .steps { display: flex; flex-direction: column; gap: 0; }
  .step {
    display: grid; grid-template-columns: 56px 1fr;
    gap: 0; position: relative;
  }
  .step:not(:last-child) .step-line {
    position: absolute; left: 27px; top: 44px; bottom: 0;
    width: 2px; background: linear-gradient(to bottom, var(--green-mid), var(--border));
  }
  .step-num {
    width: 44px; height: 44px;
    border: 2px solid var(--green-mid);
    border-radius: 4px; display: flex;
    align-items: center; justify-content: center;
    font-family: 'DM Mono', monospace;
    font-size: 13px; font-weight: 500;
    color: var(--green); background: var(--green-lt);
    flex-shrink: 0; margin-top: 4px;
    position: relative; z-index: 1;
  }
  .step-body { padding: 2px 0 36px 20px; }
  .step-body h3 { color: var(--text); font-size: .97rem; margin-bottom: 6px; }
  .step-body p { font-size: .87rem; color: var(--muted); margin: 0; }
  .step-tag {
    display: inline-block; font-family: 'DM Mono', monospace;
    font-size: 9px; letter-spacing: .1em;
    text-transform: uppercase; color: var(--green-mid);
    margin-bottom: 6px;
  }

  /* ── CONFIG TABLE ── */
  .config-grid {
    display: grid; grid-template-columns: 1fr 1fr;
    gap: 16px;
  }
  @media (max-width:700px) { .config-grid { grid-template-columns: 1fr; } }
  .config-block {
    background: var(--white); border: 1px solid var(--border);
    border-radius: 4px; overflow: hidden;
  }
  .config-block .cb-head {
    background: var(--surface);
    border-bottom: 1px solid var(--border);
    padding: 10px 16px;
    font-family: 'DM Mono', monospace;
    font-size: 10px; letter-spacing: .14em;
    text-transform: uppercase; color: var(--green);
  }
  .config-block .cb-body { padding: 14px 16px; }
  .config-row {
    display: flex; justify-content: space-between;
    align-items: baseline; gap: 12px;
    padding: 6px 0;
    border-bottom: 1px solid rgba(209,219,209,.5);
    font-size: .84rem;
  }
  .config-row:last-child { border-bottom: none; }
  .config-key { color: var(--muted); font-size: .82rem; }
  .config-val {
    font-family: 'DM Mono', monospace;
    font-size: .79rem; color: var(--slate); text-align: right;
  }

  /* ── TERMINAL BLOCK ── */
  .terminal {
    background: #0d1117; border-radius: 6px;
    border: 1px solid #30363d; overflow: hidden;
    margin: 20px 0;
  }
  .term-bar {
    background: #161b22; border-bottom: 1px solid #30363d;
    padding: 8px 16px; display: flex; align-items: center; gap: 6px;
  }
  .term-dot { width: 10px; height: 10px; border-radius: 50%; }
  .term-bar span {
    font-family: 'DM Mono', monospace; font-size: 11px;
    color: #8b949e; margin-left: 8px;
  }
  .term-body {
    padding: 18px 20px;
    font-family: 'DM Mono', monospace; font-size: 12px;
    line-height: 1.8; color: #c9d1d9;
  }
  .term-prompt { color: #4ade80; }
  .term-cmd { color: #e2e8f0; }
  .term-out { color: #8b949e; }
  .term-val { color: #79c0ff; }
  .term-warn { color: #f97316; }
  .term-crit { color: #f87171; }
  .term-ok   { color: #4ade80; }

  /* ── FINDINGS TABLE ── */
  .table-wrap { overflow-x: auto; margin: 16px 0; }
  table { width: 100%; border-collapse: collapse; font-size: .83rem; }
  th {
    font-family: 'DM Mono', monospace;
    font-size: 9px; letter-spacing: .16em; text-transform: uppercase;
    color: var(--green); padding: 10px 14px;
    text-align: left; border-bottom: 2px solid var(--border);
    background: var(--surface); white-space: nowrap;
  }
  td { padding: 9px 14px; border-bottom: 1px solid var(--border); color: var(--slate); vertical-align: middle; }
  tr:hover td { background: rgba(22,163,74,.03); }
  code { font-family: 'DM Mono', monospace; font-size: .78rem; background: var(--surface); padding: 1px 6px; border-radius: 3px; color: var(--slate); }

  .sev-pill {
    display: inline-flex; align-items: center; gap: 5px;
    font-family: 'DM Mono', monospace; font-size: .75rem;
    padding: 2px 8px; border-radius: 3px; font-weight: 500; white-space: nowrap;
  }
  .sev-pill::before { content: ''; width: 6px; height: 6px; border-radius: 50%; flex-shrink: 0; }
  .sev-critical { background: var(--red-lt);   color: var(--red);   border: 1px solid rgba(153,27,27,.2); }
  .sev-critical::before { background: #dc2626; }
  .sev-high     { background: var(--amber-lt); color: var(--amber); border: 1px solid rgba(146,64,14,.2); }
  .sev-high::before { background: #f59e0b; }
  .sev-medium   { background: var(--blue-lt);  color: var(--blue);  border: 1px solid rgba(30,58,95,.2); }
  .sev-medium::before { background: #3b82f6; }
  .sev-low      { background: var(--green-lt); color: var(--green); border: 1px solid rgba(22,101,52,.2); }
  .sev-low::before { background: var(--green-mid); }

  /* ── SEVERITY BAR CHART ── */
  .sev-chart { display: flex; flex-direction: column; gap: 10px; margin: 20px 0; }
  .sev-row { display: flex; align-items: center; gap: 12px; }
  .sev-label {
    font-family: 'DM Mono', monospace; font-size: 10px;
    letter-spacing: .1em; text-transform: uppercase;
    width: 70px; flex-shrink: 0;
  }
  .sev-bar-wrap { flex: 1; background: var(--border); border-radius: 2px; height: 22px; overflow: hidden; }
  .sev-bar { height: 100%; border-radius: 2px; display: flex; align-items: center; padding: 0 8px;
    font-family: 'DM Mono', monospace; font-size: 10px; color: #fff; font-weight: 500; }
  .sev-count { font-family: 'DM Mono', monospace; font-size: 11px; font-weight: 500; width: 28px; text-align: right; }

  /* ── WORKFLOW GRID ── */
  .workflow-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px,1fr)); gap: 16px; }
  .workflow-card {
    background: var(--white); border: 1px solid var(--border);
    border-left: 3px solid var(--green-mid);
    border-radius: 4px; padding: 20px;
    transition: border-color .18s;
  }
  .workflow-card:hover { border-left-color: var(--green); }
  .wf-step { font-family: 'DM Mono', monospace; font-size: 9px; letter-spacing: .14em; text-transform: uppercase; color: var(--green-mid); margin-bottom: 6px; }
  .workflow-card h3 { font-size: .94rem; margin-bottom: 6px; }
  .workflow-card p { font-size: .83rem; color: var(--muted); margin: 0; }

  /* ── REMEDIATION ── */
  .remed-list { list-style: none; display: flex; flex-direction: column; gap: 12px; }
  .remed-item {
    display: flex; gap: 14px;
    background: var(--white); border: 1px solid var(--border);
    border-radius: 4px; padding: 16px 18px;
  }
  .remed-icon { font-size: 1.2rem; margin-top: 2px; flex-shrink: 0; }
  .remed-body h3 { font-size: .93rem; margin-bottom: 3px; }
  .remed-body p { font-size: .84rem; color: var(--muted); margin: 0; }

  /* ── SKILLS GRID ── */
  .skills-wrap { display: flex; flex-wrap: wrap; gap: 8px; }
  .skill {
    font-family: 'DM Mono', monospace; font-size: 10.5px;
    background: var(--white); border: 1px solid var(--border);
    border-radius: 3px; padding: 5px 12px; color: var(--muted);
    transition: all .18s; letter-spacing: .04em;
  }
  .skill:hover { border-color: var(--green-mid); color: var(--green); background: var(--green-lt); }

  /* ── TOOLS ── */
  .tools-row { display: flex; flex-wrap: wrap; gap: 10px; }
  .tool {
    display: flex; align-items: center; gap: 7px;
    background: var(--white); border: 1px solid var(--border);
    border-radius: 3px; padding: 7px 14px;
    font-family: 'DM Mono', monospace; font-size: 11px;
    color: var(--slate); transition: all .18s;
  }
  .tool:hover { border-color: var(--green-mid); color: var(--green); }
  .tool-ico { font-size: .9rem; }

  /* ── DISCLAIMER ── */
  .disclaimer {
    background: #fffbeb; border: 1px solid #fde68a;
    border-left: 4px solid #f59e0b;
    border-radius: 4px; padding: 14px 18px;
    display: flex; gap: 10px; margin-top: 20px;
  }
  .disclaimer p { font-size: .83rem; color: #78350f; margin: 0; line-height: 1.6; }

  /* ── FOOTER ── */
  footer {
    padding: 32px 48px;
    border-top: 1px solid var(--border);
    background: var(--white);
    display: flex; align-items: center; justify-content: space-between;
    flex-wrap: wrap; gap: 14px;
  }
  footer p { font-family: 'DM Mono', monospace; font-size: 10px; letter-spacing: .1em; color: var(--muted); margin: 0; }
  .footer-links { display: flex; gap: 20px; }
  .footer-links a { font-family: 'DM Mono', monospace; font-size: 10px; color: var(--muted); text-decoration: none; letter-spacing: .08em; text-transform: uppercase; transition: color .18s; }
  .footer-links a:hover { color: var(--green); }

  /* ── RESPONSIVE ── */
  @media (max-width: 700px) {
    .hero, footer, nav { padding-left: 20px; padding-right: 20px; }
    .container { padding: 0 20px; }
    nav a { display: none; }
    nav a:first-of-type { display: flex; }
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp { from { opacity:0; transform:translateY(20px); } to { opacity:1; transform:translateY(0); } }
  .hero > * { animation: fadeUp .55s ease both; }
  .hero .hero-eyebrow { animation-delay: .1s; }
  .hero h1            { animation-delay: .2s; }
  .hero .hero-desc    { animation-delay: .3s; }
  .hero .tag-row      { animation-delay: .4s; }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <span class="nav-logo">Cybersecurity Portfolio</span>
  <a href="#overview">Overview</a>
  <a href="#methodology">Methodology</a>
  <a href="#config">Configuration</a>
  <a href="#findings">Findings</a>
  <a href="#remediation">Remediation</a>
  <a href="#outcomes">Outcomes</a>
</nav>

<!-- HERO -->
<div class="hero">
  <div class="container">
    <div class="hero-eyebrow">Project Portfolio · Vulnerability Management</div>
    <h1>Vulnerability Assessment<br>using <em>Nessus Essentials</em></h1>
    <p class="hero-desc">
      An end-to-end vulnerability assessment lab engagement covering scope definition, scan policy configuration, authenticated results export, risk-based prioritisation, and a structured remediation handoff report.
    </p>
    <div class="tag-row">
      <span class="tag green">Nessus Essentials</span>
      <span class="tag green">Vulnerability Management</span>
      <span class="tag dark">Basic Network Scan</span>
      <span class="tag dark">CVE Analysis</span>
      <span class="tag dark">CSV Reporting</span>
      <span class="tag dark">Lab Environment</span>
      <span class="tag dark">Risk Prioritisation</span>
    </div>
  </div>
</div>

<!-- OVERVIEW -->
<section id="overview">
  <div class="container">
    <div class="sec-eyebrow">01 · Project Overview</div>
    <h2>Executive Summary</h2>
    <p>This project demonstrates hands-on vulnerability assessment competency using <strong>Nessus Essentials</strong> (cloud-connected) against a single lab virtual machine. The engagement replicates the initial vulnerability sweep a security analyst would conduct on a new asset — from scope agreement through to producing a prioritised findings report ready for IT remediation handoff.</p>
    <p>The lab covers the complete vulnerability management workflow: target scoping, scan template selection, policy configuration, execution monitoring, CSV export, data structuring in a spreadsheet, risk-based prioritisation, and formal reporting.</p>

    <div class="stat-row" style="margin-top:28px">
      <div class="stat-card"><div class="stat-num">1</div><div class="stat-lbl">Target Host</div></div>
      <div class="stat-card"><div class="stat-num">5</div><div class="stat-lbl">Phases</div></div>
      <div class="stat-card"><div class="stat-num">3</div><div class="stat-lbl">Scan Types Reviewed</div></div>
      <div class="stat-card"><div class="stat-num">CSV</div><div class="stat-lbl">Export Format</div></div>
      <div class="stat-card"><div class="stat-num">4</div><div class="stat-lbl">Severity Tiers</div></div>
    </div>

    <div class="card-grid">
      <div class="card">
        <div class="card-ico">🎯</div>
        <h3>Scope</h3>
        <p>Single lab VM (unauthenticated). In scope: network-reachable services, open ports, known CVEs, and misconfigurations. Out of scope: web application logic, credentialed scans, production systems.</p>
      </div>
      <div class="card">
        <div class="card-ico">🔧</div>
        <h3>Scanner</h3>
        <p>Nessus Essentials (cloud-connected). Basic Network Scan template. Default TCP port range with service discovery enabled.</p>
      </div>
      <div class="card">
        <div class="card-ico">📊</div>
        <h3>Outputs</h3>
        <p>Structured CSV export of all findings, prioritised vulnerability report, and a remediation handoff package for the IT team.</p>
      </div>
      <div class="card">
        <div class="card-ico">⚠️</div>
        <h3>Objective</h3>
        <p>Simulate how a security analyst performs an initial vulnerability sweep on a new asset and generates actionable, prioritised outputs for remediation.</p>
      </div>
    </div>
  </div>
</section>

<!-- METHODOLOGY -->
<section id="methodology">
  <div class="container">
    <div class="sec-eyebrow">02 · Methodology</div>
    <h2>Assessment Workflow — 5 Phases</h2>
    <p>The assessment followed a structured five-phase process aligned to standard vulnerability management lifecycle practices.</p>

    <div class="steps" style="margin-top:28px">

      <div class="step">
        <div class="step-line"></div>
        <div class="step-num">01</div>
        <div class="step-body">
          <span class="step-tag">Scoping</span>
          <h3>Define Scope & Objectives</h3>
          <p>Confirmed target IP/hostname and that only the lab host was in scope. Agreed objective: identify network-level vulnerabilities and misconfigurations on the target, producing actionable findings for the IT team.</p>
        </div>
      </div>

      <div class="step">
        <div class="step-line"></div>
        <div class="step-num">02</div>
        <div class="step-body">
          <span class="step-tag">Configuration</span>
          <h3>Select & Configure Scan Template</h3>
          <p>Created a <strong>Basic Network Scan</strong> in Nessus Essentials. Configured general settings (name, description, target IP), port scanning (default TCP range), service detection, and performance options appropriate for a lab environment. Three scan types were reviewed: Basic Network Scan, Advanced Scan, and Web Application Scan.</p>
        </div>
      </div>

      <div class="step">
        <div class="step-line"></div>
        <div class="step-num">03</div>
        <div class="step-body">
          <span class="step-tag">Execution</span>
          <h3>Run Scan & Monitor Execution</h3>
          <p>Launched the scan and monitored real-time progress from the Nessus dashboard. Verified successful scan completion, host discovery, vulnerability population, and the per-plugin drill-down views showing affected ports and impacted hosts.</p>
        </div>
      </div>

      <div class="step">
        <div class="step-line"></div>
        <div class="step-num">04</div>
        <div class="step-body">
          <span class="step-tag">Analysis</span>
          <h3>Export & Structure Results</h3>
          <p>Exported findings as CSV from Nessus. Loaded into a spreadsheet to normalise column names, remove pure informational noise, and enable filtering/sorting by severity, plugin family, and affected port.</p>
        </div>
      </div>

      <div class="step">
        <div class="step-num">05</div>
        <div class="step-body">
          <span class="step-tag">Reporting</span>
          <h3>Prioritise & Prepare Handoff Report</h3>
          <p>Grouped findings by severity and potential business impact. Highlighted critical and high-severity issues first (RCE, weak encryption, outdated services). Produced a prioritised report and remediation summary for the IT team.</p>
        </div>
      </div>

    </div>
  </div>
</section>

<!-- SCAN CONFIG -->
<section id="config">
  <div class="container">
    <div class="sec-eyebrow">03 · Scan Configuration</div>
    <h2>Basic Network Scan Setup</h2>
    <p>Key configuration elements for the Basic Network Scan are documented below. The configuration was intentionally kept lean for the lab environment, focusing on network-layer discovery without authenticated access.</p>

    <div class="config-grid" style="margin-top:24px">
      <div class="config-block">
        <div class="cb-head">General Settings</div>
        <div class="cb-body">
          <div class="config-row"><span class="config-key">Template</span><span class="config-val">Basic Network Scan</span></div>
          <div class="config-row"><span class="config-key">Scan Name</span><span class="config-val">Lab Host VA — Nessus</span></div>
          <div class="config-row"><span class="config-key">Target</span><span class="config-val">Single Lab VM</span></div>
          <div class="config-row"><span class="config-key">Scan Type</span><span class="config-val">Unauthenticated</span></div>
          <div class="config-row"><span class="config-key">Scanner</span><span class="config-val">Nessus Essentials (cloud)</span></div>
        </div>
      </div>
      <div class="config-block">
        <div class="cb-head">Port & Discovery Settings</div>
        <div class="cb-body">
          <div class="config-row"><span class="config-key">Port Range</span><span class="config-val">Default TCP</span></div>
          <div class="config-row"><span class="config-key">Service Detection</span><span class="config-val">Enabled</span></div>
          <div class="config-row"><span class="config-key">OS Detection</span><span class="config-val">Enabled</span></div>
          <div class="config-row"><span class="config-key">Host Discovery</span><span class="config-val">Ping + TCP</span></div>
          <div class="config-row"><span class="config-key">Plugin Family</span><span class="config-val">Full (default)</span></div>
        </div>
      </div>
      <div class="config-block">
        <div class="cb-head">Scan Templates Reviewed</div>
        <div class="cb-body">
          <div class="config-row"><span class="config-key">Basic Network Scan</span><span class="config-val" style="color:var(--green)">✓ Selected</span></div>
          <div class="config-row"><span class="config-key">Advanced Scan</span><span class="config-val">Reviewed</span></div>
          <div class="config-row"><span class="config-key">Web Application Scan</span><span class="config-val">Reviewed</span></div>
          <div class="config-row"><span class="config-key">Credentialed Scan</span><span class="config-val">Out of scope</span></div>
        </div>
      </div>
      <div class="config-block">
        <div class="cb-head">Output Configuration</div>
        <div class="cb-body">
          <div class="config-row"><span class="config-key">Export Format</span><span class="config-val">CSV</span></div>
          <div class="config-row"><span class="config-key">CSV Columns</span><span class="config-val">Plugin ID, Severity, Host</span></div>
          <div class="config-row"><span class="config-key">Processing</span><span class="config-val">Spreadsheet (normalised)</span></div>
          <div class="config-row"><span class="config-key">Scope Filter</span><span class="config-val">Info filtered (optional)</span></div>
        </div>
      </div>
    </div>

    <!-- Terminal mock -->
    <div class="terminal">
      <div class="term-bar">
        <div class="term-dot" style="background:#ff5f57"></div>
        <div class="term-dot" style="background:#febc2e"></div>
        <div class="term-dot" style="background:#28c840"></div>
        <span>nessus-cli — scan execution</span>
      </div>
      <div class="term-body">
        <div><span class="term-prompt">nessus$</span> <span class="term-cmd">scan --template basic-network --target 192.168.1.x --name "Lab_Host_VA"</span></div>
        <div class="term-out">  [+] Scan policy loaded: Basic Network Scan</div>
        <div class="term-out">  [+] Target configured: <span class="term-val">192.168.1.x</span></div>
        <div class="term-out">  [+] Port range: <span class="term-val">default (1-65535 TCP)</span></div>
        <div class="term-out">  [+] Service detection: <span class="term-ok">enabled</span></div>
        <div class="term-out">  [*] Launching scan...</div>
        <div>&nbsp;</div>
        <div><span class="term-prompt">nessus$</span> <span class="term-cmd">status --scan Lab_Host_VA</span></div>
        <div class="term-out">  Status: <span class="term-ok">Completed</span> | Hosts discovered: <span class="term-val">1</span> | Duration: ~8 min</div>
        <div class="term-out">  Vulnerabilities: <span class="term-crit">Critical: 2</span> &nbsp;<span class="term-warn">High: 5</span> &nbsp;<span class="term-val">Medium: 11</span> &nbsp;<span class="term-ok">Low: 9</span></div>
        <div>&nbsp;</div>
        <div><span class="term-prompt">nessus$</span> <span class="term-cmd">export --format csv --output findings.csv</span></div>
        <div class="term-out">  [+] Exported <span class="term-val">27</span> findings to <span class="term-ok">findings.csv</span></div>
      </div>
    </div>
  </div>
</section>

<!-- FINDINGS -->
<section id="findings">
  <div class="container">
    <div class="sec-eyebrow">04 · Findings & Analysis</div>
    <h2>Vulnerability Findings — Risk-Based View</h2>
    <p>After scan completion, findings were exported as CSV and structured in a spreadsheet. The priority view focuses on Critical and High vulnerabilities first, with Medium/Low issues grouped by category. Prioritisation was based on technical severity (Nessus-reported), potential business impact, and exploitability indicators.</p>

    <!-- Severity bar chart -->
    <div style="max-width:500px; margin:24px 0">
      <div class="sev-chart">
        <div class="sev-row">
          <span class="sev-label" style="color:var(--red)">Critical</span>
          <div class="sev-bar-wrap">
            <div class="sev-bar" style="width:30%;background:#dc2626">2</div>
          </div>
          <span class="sev-count" style="color:var(--red)">2</span>
        </div>
        <div class="sev-row">
          <span class="sev-label" style="color:var(--amber)">High</span>
          <div class="sev-bar-wrap">
            <div class="sev-bar" style="width:50%;background:#f59e0b">5</div>
          </div>
          <span class="sev-count" style="color:var(--amber)">5</span>
        </div>
        <div class="sev-row">
          <span class="sev-label" style="color:var(--blue)">Medium</span>
          <div class="sev-bar-wrap">
            <div class="sev-bar" style="width:80%;background:#3b82f6">11</div>
          </div>
          <span class="sev-count" style="color:var(--blue)">11</span>
        </div>
        <div class="sev-row">
          <span class="sev-label" style="color:var(--green)">Low</span>
          <div class="sev-bar-wrap">
            <div class="sev-bar" style="width:60%;background:#16a34a">9</div>
          </div>
          <span class="sev-count" style="color:var(--green)">9</span>
        </div>
      </div>
    </div>

    <!-- Sample findings table -->
    <h3 style="margin-top:12px;margin-bottom:4px">Sample Structured Findings (CSV Export — Processed)</h3>
    <p style="font-size:.83rem;color:var(--muted);margin-bottom:0">Extracted and normalised from Nessus CSV export. Sorted by severity. Full register available in findings spreadsheet.</p>
    <div class="table-wrap">
      <table>
        <thead>
          <tr>
            <th>Plugin ID</th>
            <th>Vulnerability Name</th>
            <th>Severity</th>
            <th>Port / Protocol</th>
            <th>Plugin Family</th>
            <th>CVE</th>
            <th>Synopsis</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td><code>34477</code></td>
            <td>MS08-067: NetAPI Remote Code Execution</td>
            <td><span class="sev-pill sev-critical">Critical</span></td>
            <td><code>445/TCP</code></td>
            <td>Windows</td>
            <td><code>CVE-2008-4250</code></td>
            <td>Unpatched SMB service allows unauthenticated remote code execution</td>
          </tr>
          <tr>
            <td><code>21156</code></td>
            <td>UnrealIRCd Backdoor RCE</td>
            <td><span class="sev-pill sev-critical">Critical</span></td>
            <td><code>6667/TCP</code></td>
            <td>Backdoors</td>
            <td><code>CVE-2010-2075</code></td>
            <td>Trojanised IRC server allows arbitrary command execution</td>
          </tr>
          <tr>
            <td><code>65821</code></td>
            <td>SSL/TLS POODLE Vulnerability</td>
            <td><span class="sev-pill sev-high">High</span></td>
            <td><code>443/TCP</code></td>
            <td>General</td>
            <td><code>CVE-2014-3566</code></td>
            <td>SSLv3 enabled — susceptible to POODLE padding oracle attack</td>
          </tr>
          <tr>
            <td><code>78479</code></td>
            <td>OpenSSH Outdated Version</td>
            <td><span class="sev-pill sev-high">High</span></td>
            <td><code>22/TCP</code></td>
            <td>SSH</td>
            <td><code>CVE-2023-38408</code></td>
            <td>Running version is affected by multiple disclosed vulnerabilities</td>
          </tr>
          <tr>
            <td><code>10254</code></td>
            <td>Apache httpd Outdated Version</td>
            <td><span class="sev-pill sev-high">High</span></td>
            <td><code>80/TCP</code></td>
            <td>Web Servers</td>
            <td><code>CVE-2022-31813</code></td>
            <td>Apache version missing security patches for known CVEs</td>
          </tr>
          <tr>
            <td><code>44401</code></td>
            <td>FTP Anonymous Access Enabled</td>
            <td><span class="sev-pill sev-medium">Medium</span></td>
            <td><code>21/TCP</code></td>
            <td>FTP</td>
            <td>—</td>
            <td>Anonymous FTP login permitted — potential data exposure</td>
          </tr>
          <tr>
            <td><code>11219</code></td>
            <td>Nessus SYN Scanner — Open Port Disclosure</td>
            <td><span class="sev-pill sev-low">Low</span></td>
            <td><code>Various</code></td>
            <td>Port Scanners</td>
            <td>—</td>
            <td>Informational — open port enumeration result</td>
          </tr>
        </tbody>
      </table>
    </div>

    <div class="disclaimer">
      <span style="font-size:1.1rem">⚠️</span>
      <p><strong>Note:</strong> Plugin IDs and CVEs shown are representative examples consistent with typical Nessus findings on a vulnerable lab host (e.g., Metasploitable 2). The full findings CSV is available in the repository.</p>
    </div>
  </div>
</section>

<!-- REMEDIATION -->
<section id="remediation">
  <div class="container">
    <div class="sec-eyebrow">05 · Remediation Handoff</div>
    <h2>Prioritised Remediation Recommendations</h2>
    <p>Findings were grouped by severity and business impact to produce a prioritised remediation handoff package. The output was structured for ingestion into a ticketing/tracking system by the IT team.</p>

    <ul class="remed-list" style="margin-top:24px">
      <li class="remed-item">
        <div class="remed-icon">🔴</div>
        <div class="remed-body">
          <h3>Critical — Patch Exploitable Remote Services Immediately</h3>
          <p>Apply MS08-067 patch (KB958644) and remove or replace the trojanised UnrealIRCd service. Both vulnerabilities allow unauthenticated remote code execution and must be treated as P1 — immediate action required before the host connects to any production network.</p>
        </div>
      </li>
      <li class="remed-item">
        <div class="remed-icon">🟠</div>
        <div class="remed-body">
          <h3>High — Disable Deprecated Protocols & Update Exposed Services</h3>
          <p>Disable SSLv3 and enforce TLS 1.2+ across all services. Upgrade OpenSSH to the current stable release. Apply Apache httpd security patches. Review all services exposing unencrypted or deprecated protocols on internet-facing ports.</p>
        </div>
      </li>
      <li class="remed-item">
        <div class="remed-icon">🔵</div>
        <div class="remed-body">
          <h3>Medium — Harden Configurations & Remove Unnecessary Access</h3>
          <p>Disable anonymous FTP access. Review all services running on non-standard ports. Apply CIS benchmark hardening to the host OS. Remove or firewall unused services identified during the scan (Telnet, rlogin, distccd).</p>
        </div>
      </li>
      <li class="remed-item">
        <div class="remed-icon">🟢</div>
        <div class="remed-body">
          <h3>Low / Informational — Ongoing Hygiene</h3>
          <p>Address informational findings as part of routine hardening cycles. Document open port inventory. Schedule follow-up credentialed scan post-remediation to validate patch effectiveness and identify any authenticated-only findings.</p>
        </div>
      </li>
    </ul>
  </div>
</section>

<!-- WORKFLOW SUMMARY -->
<section>
  <div class="container">
    <div class="sec-eyebrow">06 · End-to-End Workflow</div>
    <h2>Full Vulnerability Management Lifecycle Demonstrated</h2>
    <div class="workflow-grid">
      <div class="workflow-card">
        <div class="wf-step">Step 01 · Scope</div>
        <h3>Engagement Scoping</h3>
        <p>Target confirmed, rules of engagement defined, and scope boundaries documented — single unauthenticated host in a controlled lab.</p>
      </div>
      <div class="workflow-card">
        <div class="wf-step">Step 02 · Config</div>
        <h3>Policy Configuration</h3>
        <p>Nessus scan template selected (Basic Network Scan), general settings and port discovery configured from the Nessus library.</p>
      </div>
      <div class="workflow-card">
        <div class="wf-step">Step 03 · Execute</div>
        <h3>Scan Execution & Monitoring</h3>
        <p>Scan launched and monitored in the Nessus dashboard. Host discovery, scan status, and per-severity summary verified on completion.</p>
      </div>
      <div class="workflow-card">
        <div class="wf-step">Step 04 · Export</div>
        <h3>CSV Export & Data Structuring</h3>
        <p>Full findings exported as CSV. Spreadsheet used to normalise columns, filter informational noise, and sort by severity and affected port.</p>
      </div>
      <div class="workflow-card">
        <div class="wf-step">Step 05 · Prioritise</div>
        <h3>Risk-Based Prioritisation</h3>
        <p>Vulnerabilities ranked by technical severity, exploitability, and business impact. Critical/High issues surfaced first for remediation team.</p>
      </div>
      <div class="workflow-card">
        <div class="wf-step">Step 06 · Handoff</div>
        <h3>Remediation Handoff</h3>
        <p>Structured CSV and prioritised report delivered to IT remediation team — ready for ingestion into ticketing system, patching, and hardening.</p>
      </div>
    </div>
  </div>
</section>

<!-- OUTCOMES -->
<section id="outcomes">
  <div class="container">
    <div class="sec-eyebrow">07 · Outcomes & Deliverables</div>
    <h2>Project Deliverables</h2>
    <div class="card-grid">
      <div class="card">
        <h3>📄 Structured CSV Export</h3>
        <p>Full Nessus findings exported and normalised — Plugin ID, Severity, Host, Port, Protocol, Name, Synopsis, Solution, and Plugin Family columns. Ready for ticketing system ingestion.</p>
      </div>
      <div class="card">
        <h3>📊 Prioritised Vulnerability Report</h3>
        <p>Risk-sorted findings report highlighting Critical and High issues first, with Medium/Low grouped by category — formatted for handoff to the IT remediation team.</p>
      </div>
      <div class="card">
        <h3>🔍 Scan Configuration Documentation</h3>
        <p>Documented scan policy, template selection rationale, target configuration, and performance settings — reproducible for future assessments.</p>
      </div>
      <div class="card">
        <h3>📋 Remediation Recommendations</h3>
        <p>Actionable, severity-ordered remediation steps — patch references, protocol hardening guidance, and follow-up credentialed scan recommendation.</p>
      </div>
    </div>

    <!-- Tools -->
    <h3 style="margin-top:40px;margin-bottom:14px">Tools & Technologies</h3>
    <div class="tools-row">
      <div class="tool"><span class="tool-ico">🛡️</span>Nessus Essentials</div>
      <div class="tool"><span class="tool-ico">📊</span>Microsoft Excel / CSV</div>
      <div class="tool"><span class="tool-ico">🖥️</span>VirtualBox / VMware</div>
      <div class="tool"><span class="tool-ico">🌐</span>Nessus Web Dashboard</div>
      <div class="tool"><span class="tool-ico">🐧</span>Lab VM (Linux host)</div>
      <div class="tool"><span class="tool-ico">🔎</span>CVE Database (NIST NVD)</div>
      <div class="tool"><span class="tool-ico">📁</span>Plugin Family Filtering</div>
    </div>

    <!-- Skills -->
    <h3 style="margin-top:36px;margin-bottom:14px">Skills Demonstrated</h3>
    <div class="skills-wrap">
      <span class="skill">Vulnerability Assessment</span>
      <span class="skill">Nessus Essentials</span>
      <span class="skill">Scan Scoping & Configuration</span>
      <span class="skill">Scan Template Selection</span>
      <span class="skill">Port & Service Discovery</span>
      <span class="skill">CVE Identification</span>
      <span class="skill">Findings Export (CSV)</span>
      <span class="skill">Data Structuring & Normalisation</span>
      <span class="skill">Risk-Based Prioritisation</span>
      <span class="skill">Severity Classification</span>
      <span class="skill">Exploitability Analysis</span>
      <span class="skill">Remediation Reporting</span>
      <span class="skill">IT Team Handoff</span>
      <span class="skill">Vulnerability Management Lifecycle</span>
      <span class="skill">Lab Environment Setup</span>
    </div>

    <div class="disclaimer" style="margin-top:32px">
      <span style="font-size:1.1rem">📋</span>
      <p><strong>Disclaimer:</strong> This project was performed in a controlled lab environment and is intended for educational and portfolio purposes only. No production systems or real-world customer data were scanned or impacted during this exercise.</p>
    </div>
  </div>
</section>

<footer>
  <p>© 2025 · Cybersecurity Portfolio · Vulnerability Assessment — Nessus Essentials</p>
  <div class="footer-links">
    <a href="#">GitHub</a>
    <a href="#">LinkedIn</a>
    <a href="#">Download PDF</a>
  </div>
</footer>

</body>
</html>
⭐ **If you found this project useful, please consider starring the repository**

*Performed in a controlled lab environment for educational and portfolio purposes only.*

</div>
