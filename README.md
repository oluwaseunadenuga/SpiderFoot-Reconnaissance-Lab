# APT Breach: Analysing the impact on information security
<img width="1152" height="768" alt="image" src="https://github.com/user-attachments/assets/9abe98ec-8829-4c61-b6b5-30315450ae0d" />

## INTRODUCTION
This project focuses on investigating a cyberattack by APT34 and producing a comprehensive report documenting the findings and outlining key recommendations to improve a client's cybersecurity posture.

<img width="1000" height="750" alt="image" src="https://github.com/user-attachments/assets/93c86d1d-d95b-489a-88bc-55bf745eb839" />

## PROBLEM STATEMENT
A leading tech corporation client experienced a sophisticated cyberattack by the notorious Advanced Persistent Threat (APT) group APT34. The attack, believed to be sponsored by a foreign government, has left the organisation's network compromised and valuable customer data and intellectual property have been stolen.

## OBJECTIVES
- Conduct an initial investigation into APT34 and evaluate the potential impact of the attack on the organisation.
- Produce a comprehensive report documenting my findings and outlining key recommendations to improve the organisation's cybersecurity posture.

## TASKS
- Utilise various Open-source Intelligence(OSINT)tools and techniques to gather information on APT34
- Apply the MITRE ATT&CK Framework to identify and categorise to develop a comprehensive defence strategy to protect the client's networks and systems against future attacks.
- Provide answers to the following questions
- What is their history?
- Which nation/state are they associated with?
- Do they target specific industries?
- What are their motives?
- What are the TTPs they use to conduct their attacks?
- What security measures could the client implement to defend against cyberattacks conducted by this APT?

## OSINT TOOLS
OSINT tools used to gather information on APT34
- Mandiant Security Blog: https://www.mandiant.com/resources/blog
- CrowdStrike: https://www.crowdstrike.com 
- Recorded Future: https://www.recordedfuture.com
- CyberScoop: https://www.cyberscoop.com
- Dark Reading: https://www.darkreading.com
- The CyberWire: https://thecyberwire.com
- SecureWorks - https://www.secureworks.com 
- ThreatConnect - https://www.threatconnect.com 
- Kaspersky Lab: https://www.kaspersky.com
- Symantec Threat Intelligence: https://www.symantec.com/threat-intelligence

## MITRE ATT&CK Framework (https://attack.mitre.org/)
This is a widely used tool for categorising and identifying cyber threats.
- Cybersecurity and Infrastructure Security Agency (CISA): https://www.cisa.gov
- US-CERT: https://www.us-cert.gov

# Comprehensive Cybersecurity Assessment: APT34 (OilRig)

## Executive Summary
This report provides actionable insights into APT34 (OilRig), an advanced persistent threat (APT) group linked to Iran. The findings outline the group's history, tactics, targets and motivations, along with a comprehensive defense strategy. The goal is to enhance the client’s security posture and mitigate risks associated with APT34 attacks.

## 1.0 Overview of APT34
**History**

APT34 has been active since at least 2014, conducting cyber-espionage campaigns that primarily target organisations in the Middle East and occasionally in other regions. Known for its sophisticated and persistent attacks, APT34 uses custom malware, phishing and web shells to achieve its objectives.

## Nation/State Association
APT34 is widely attributed to Iran, with operations aligning closely with the nation’s strategic and geopolitical goals.

## Targeted Industries
The group targets:
- Government agencies
- Financial institutions 
- Energy companies 
- Telecommunications
- Defense contractor
- Critical infrastructures 

## Motives
APT34’s primary motive is espionage. The group seeks to collect:
- Sensitive information to support state objectives
- Gain strategic advantages in geopolitical conflicts
- Disrupt adversarial operations in key sectors

## 2.0 APT34 Tactics, Techniques and Procedures (TTPs)
**Using the MITRE ATT&CK Framework, APT34’s TTPs include:**

Tactic/**                    **Techniques**
- Initial Access:          Spear-phishing links (T1566.001), exploiting public-facing applications (T1190)**
- Execution:	              PowerShell scripting (T1059.001), execution of malicious payload(T1203)**.
- Persistence:	            Web shells (T1505.003), account manipulation (T1098)**.
- Privilege Escalation:	   Exploiting vulnerabilities for elevated privileges (T1068)**.
- Defense Evasion:	        Obfuscated scripts (T1027), credential dumping (T1003)**.
- Command and Control:	    HTTPS or DNS tunneling for encrypted C2 communication (T1071.001)**.
- Exfiltration:             Data staging and exfiltration over encrypted channels (T1048.002).**

## Tools Associated with APT34
- PoisonFrog: A backdoor for remote access
- PowBat: A PowerShell-based tool
- TwoFace: A web shell

## 3.0 Defense Strategy Against APT34
To mitigate risks, the following multi-layered security measures are recommended:

**A. Network Security**
1.	**Network Segmentation**: Restrict access between critical systems and general networks.
2.	**Intrusion Detection and Prevention Systems (IDPS)**: Deploy systems to detect and block unusual traffic patterns and known APT34 signatures.
3.	**DNS Filtering:** Block known malicious domains associated with APT34’s infrastructure.

**B. Endpoint Security**
1.	**Endpoint Detection and Response (EDR)**: Monitor endpoints for suspicious activity.
2.	**Regular Patching**: Ensure timely updates of software to address vulnerabilities.
3.	**Application Whitelisting**: Prevent unauthorised execution of applications or scripts.

**C.Identity and Access Management (IAM)**
1.	**Multi-Factor Authentication (MFA)**: Enforce MFA for all critical accounts.
2.	**Least Privilege Access**: Apply the principle of least privilege to minimise access.
3.	**Account Monitoring**: Monitor for unusual login attempts or privilege escalations.

**D. Email Security**
1.	**Anti-Phishing Solutions**: Use tools to detect and block phishing emails.
2.	**User Training:** Educate employees to recognise and report phishing attempts.

**E. Threat Intelligence and Monitoring**
1.	**Threat Feeds**: Monitor threat intelligence feeds for Indicators of Compromise (IOCs) related to APT34.
2.	**Penetration Testing:** Simulate attacks to identify vulnerabilities in defences.

**F. Incident Response and Recovery**
1.	**Incident Response Plan**: Develop and routinely test an incident response plan.
2.	**Backup Strategy**: Maintain offline backups to mitigate the impact of data theft or destruction.

**G. Continuous Monitoring and Analytics**
1.	**SIEM Solutions**: Implement Security Information and Event Management (SIEM) systems to centralise and correlate logs.
2.	**Behavioural Analytics**: Leverage analytics to detect anomalies indicative of APT-style attacks.

## 4.0 CONCLUSION AND RECOMMENDATIONS
APT34’s sophisticated tactics and nation-state backing make it a persistent and formidable threat. The client should:
- Implement the recommended defence strategies to strengthen their security posture.
- Regularly update and test their defenses based on emerging threat intelligence.
- Foster a culture of security awareness among employees to reduce human error.

By adopting these measures, the client can significantly reduce the risk of successful APT34 attacks and enhance resilience against future threat targets. Top Wastage Causes.
  
## THANK YOU
