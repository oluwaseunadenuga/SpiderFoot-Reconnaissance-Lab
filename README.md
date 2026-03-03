## Vulnerability Assessment using Nessus Essentials
## Overview

This project showcases hands-on vulnerability assessment skills using Nessus Essentials to identify, analyse and prioritise security weaknesses on a lab network host. 

The engagement covers end-to-end activities:
- Defining scope
- Configuring a scan policy
- executing a basic network scan
- Exporting structured results (CSV)
- producing a prioritised findings report that can be handed over to an IT remediation team.

All activities were performed in an isolated lab environment.

## Environment & Scope
- **Scanner**: Nessus Essentials (cloud-connected)
- **Target**: Single lab VM (test host) reachable over the network
- **Scan Type**: Basic Network Scan (unauthenticated)
- **In scope**: Network-reachable services, open ports, known CVEs, misconfigurations
- **Out of scope**: Web application logic testing, authenticated/credentialed scans, production systems, authenticated scans, web application testing, production systems

<img width="940" height="363" alt="image" src="https://github.com/user-attachments/assets/0c888ab3-9da2-446a-82d5-dabba92ecd86" />

## Methodology

1. **Define scope and objectives**  
- Confirm target IP/hostname and that only the lab host is in scope.
- Agree that the objective is to identify network-level vulnerabilities and misconfigurations

3. **Select and configure scan type**  
- Create a new Basic Network Scan in Nessus Essentials.
- Configure:
- General settings (name, description, target IP(s))
- Port scanning (default port range, service discovery)
- Performance and discovery options appropriate for a lab environment.

Supporting screenshots in the repository illustrate:

- The scan template selection screen (Basic Network Scan vs Advanced and Web Application scans).
- The target configuration page showing the defined scope.
- The detailed configuration tabs (General, Discovery, Port Scanning). 

 <img width="940" height="389" alt="image" src="https://github.com/user-attachments/assets/fe2d5926-4f10-48d3-a892-b3f12d3fd43b" />
 <img width="940" height="383" alt="image" src="https://github.com/user-attachments/assets/f6b91489-627a-4546-b3e4-7f2f452eb086" />

3. Choose the **Basic Network Scan** template (most appropriate for initial unauthenticated discovery).

4. **Run scan and monitor execution**
 - Launched scan → monitored real-time progress in the Nessus dashboard.
 - Verify that the scan completes successfully and that results are populated (hosts discovered, vulnerabilities found).

<img width="940" height="496" alt="image" src="https://github.com/user-attachments/assets/932a4f63-f37c-4409-8441-f134f318095e" />
<img width="940" height="503" alt="image" src="https://github.com/user-attachments/assets/3b1de789-2703-42a3-a1c2-b1ab1b5986a1" />
<img width="940" height="498" alt="image" src="https://github.com/user-attachments/assets/ff2bafdb-120e-4af0-8d2f-2a55d389a7e1" />
<img width="940" height="487" alt="image" src="https://github.com/user-attachments/assets/2891c4d1-5f07-44de-97d3-2d374240d199" />


5. **Export and structure results**  
  - Export the findings as CSV from Nessus.
  - Load the CSV into a spreadsheet to:
  - Clean and standardise fields (e.g., plugin ID, severity, host, port, protocol, name, synopsis, solution).
  - Enable filtering and sorting by severity, plugin family, or affected port.

<img width="940" height="336" alt="image" src="https://github.com/user-attachments/assets/f5975954-dd99-45f2-b058-430d1b34f8ec" />
<img width="940" height="407" alt="image" src="https://github.com/user-attachments/assets/cdbfeb0b-1d13-408a-afc1-9cc45e8598a3" />

6. **Prioritise vulnerabilities and prepare a report**  
- Group findings by severity and potential business impact.
- Highlight critical and high-severity issues first (e.g., remote code execution, weak encryption, outdated services).
- Produce a prioritised report and summary for the remediation team.

<img width="940" height="475" alt="image" src="https://github.com/user-attachments/assets/29bcb8ee-f5fa-4f7b-98be-bd586c9ccadb" />
   
## Remediation Handoff & Key Takeaways
- Final deliverable included:
- Recommended remediation steps for critical/high items

These outputs simulate handover to an internal IT/security operations team.
-	Patch vulnerable services.
-	Harden configurations.
-	Disable unnecessary or legacy protocols.


## Skills Demonstrated
- Vulnerability assessment using Nessus Essentials
- Scan scoping and configuration (templates, targets, ports)
- Interpreting and exporting Nessus findings
- Structuring vulnerability data in CSV/spreadsheet form
- Risk-based prioritisation of vulnerabilities
- Communicating findings and next steps to remediation teams. The prioritised vulnerabilities report was summarised and sent to the Remediation IT team for patching and resolution.

## Disclaimer
This project was performed in a controlled lab environment and is intended for educational and portfolio purposes only. No production systems or real-world customer data were scanned or impacted during this exercise.
