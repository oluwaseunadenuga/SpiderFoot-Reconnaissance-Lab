## Project Overview
This hands-on lab demonstrates a complete vulnerability assessment workflow using **Nessus Essentials** (free/community edition) running on **Kali Linux**, targeting the deliberately vulnerable **Metasploitable 2** virtual machine.

The exercise covers:
- Defining scan scope and policy
- Configuring and launching an unauthenticated Basic Network Scan
- Monitoring execution
- Exporting structured results (CSV)
- Analysing, prioritising and reporting findings for remediation
All activities were performed in an isolated lab environment.

## Environment & Scope
- **Scanner**: Nessus Essentials (cloud-connected)
- **Operating System**: Kali Linux
- **Target**: Metasploitable 2 VM (single host)
- **Scan Type**: Basic Network Scan (unauthenticated)
- **In scope**: Network-reachable services, open ports, known CVEs, misconfigurations
- **Out of scope**: Authenticated scans, web application testing, production systems

<img width="1519" height="852" alt="Kali IP" src="https://github.com/user-attachments/assets/cdfa54fd-c7e4-42c4-bddd-d9434fde538f" />
<img width="1448" height="799" alt="Target machine" src="https://github.com/user-attachments/assets/d32b8ec9-c403-46ce-9e82-46e08c856221" />
<img width="1226" height="775" alt="Nessus Essentials" src="https://github.com/user-attachments/assets/23d0503c-b33a-42ec-8459-1e7958453990" />
<img width="1455" height="881" alt="Scan Template" src="https://github.com/user-attachments/assets/2c3324bd-6a11-48fa-a4d2-2b994d91a1e7" />

## Methodology
1. **Define scope and objectives**  
   Confirmed target IP and restricted scope to the lab VM only.

   <img width="1460" height="923" alt="Basic Scan" src="https://github.com/user-attachments/assets/c7f1e413-5198-4600-adf2-8777d7e418fe" />

2. **Select and configure scan type**  
   Choose the **Basic Network Scan** template (most appropriate for initial unauthenticated discovery).

3. **Run scan and monitor execution**  
 Launched scan → monitored real-time progress in the Nessus dashboard.

<img width="1918" height="688" alt="Vulnerability Scanning on Metasploitable host" src="https://github.com/user-attachments/assets/e8887808-21e3-44e2-980a-9918cec21ef4" />

4. **Review and export the full results**  
     
<img width="1237" height="735" alt="1" src="https://github.com/user-attachments/assets/94abb983-c058-4956-aa73-f470f97073bc" />

5. **Prioritise vulnerabilities and prepare a report**  
   Focused remediation effort on **Critical → High** issues first.
   
<img width="1228" height="784" alt="2" src="https://github.com/user-attachments/assets/f5df9e07-74da-4a48-ad94-1154f802b876" />
<img width="1231" height="707" alt="6b" src="https://github.com/user-attachments/assets/c78ab23d-3346-42e3-80f4-d28e69b15136" />
<img width="1230" height="748" alt="6d" src="https://github.com/user-attachments/assets/162830f0-e695-42ab-8de7-ab33093827f5" />

## Remediation Handoff & Key Takeaways
- Final deliverable included:
- Recommended remediation steps for critical/high items
These outputs simulate handover to an internal IT/security operations team.

## Skills Demonstrated
- Nessus Essentials policy creation & tuning
- Target scoping and constraint definition
- Real-time scan monitoring & result interpretation
- CSV export + spreadsheet-based vulnerability prioritisation
- Risk-based reporting suitable for technical & management audiences
- Controlled lab-based ethical vulnerability assessment

## Disclaimer
Performed **exclusively in a private lab environment** using Metasploitable 2 (a legal, purpose-built vulnerable target). No production systems, live networks, or unauthorised assets were involved.
Screenshots are included directly from the lab walkthrough for transparency and portfolio review.
Feel free to contact me for questions/collaboration.
Last updated: February 2026
