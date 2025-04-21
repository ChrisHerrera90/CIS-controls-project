# CIS Controls Version 8.1 Implementation Project for a SaaS Based Online Business
This is a project walkthrough of a complete CIS Controls implementation that I designed for a real small-sized business built on the GoHighLevel Platform (Elite360)

**Note:** Due to the fact that this business built all of their digital assets on a SaaS platform, not all CIS controls will be applicable for this project since I do not have access to GoHighLevel/Elite360 IT infrastructure. Therefore, the CIS Controls Framework has been adapted for SaaS usage instead of infrastructure hardening.


---

<img width="1000" alt="image" src="https://github.com/user-attachments/assets/cfc5dbcf-3fcb-4a71-9c13-2a49f8bab3e6">

# Technology Utilized
- Tenable (enterprise vulnerability management platform)
- Azure Virtual Machines (Nessus scan engine + scan targets)
- PowerShell & BASH (remediation scripts)

---


# Table of Contents

- [Vulnerability Management Policy Draft Creation](#vulnerability-management-policy-draft-creation)
- [Mock Meeting: Policy Buy-In (Stakeholders)](#step-2-mock-meeting-policy-buy-in-stakeholders)
- [Policy Finalization and Senior Leadership Sign-Off](#step-3-policy-finalization-and-senior-leadership-sign-off)
- [Mock Meeting: Initial Scan Permission (Server Team)](#step-4-mock-meeting-initial-scan-permission-server-team)
- [Initial Scan of Server Team Assets](#step-5-initial-scan-of-server-team-assets)
- [Vulnerability Assessment and Prioritization](#step-6-vulnerability-assessment-and-prioritization)
- [Distributing Remediations to Remediation Teams](#step-7-distributing-remediations-to-remediation-teams)
- [Mock Meeting: Post-Initial Discovery Scan (Server Team)](#step-8-mock-meeting-post-initial-discovery-scan-server-team)
- [Mock CAB Meeting: Implementing Remediations](#step-9-mock-cab-meeting-implementing-remediations)
- [Remediation Round 1: Outdated Firefox Removal](#remediation-round-1-outdated-wireshark-removal)
- [Remediation Round 2: Disabling SMBv1 Vulnerability](#remediation-round-2-insecure-protocols--ciphers)
- [Remediation Round 3: Insecure Protocols & Ciphers](#remediation-round-3-guest-account-group-membership)
- [Remediation Round 4: Windows OS Updates](#remediation-round-4-windows-os-updates)
- [First Cycle Remediation Effort Summary](#first-cycle-remediation-effort-summary)

---

### Vulnerability Management Policy Draft Creation

This phase focuses on drafting a Vulnerability Management Policy as a starting point for stakeholder engagement. The initial draft outlines scope, responsibilities, and remediation timelines, and may be adjusted based on feedback from relevant departments to ensure practical implementation before final approval by upper management.  
[Draft Policy](https://docs.google.com/document/d/1CLSWm1_9JL1oUqgyNNwtPXW6FzXJ7ddVnSAUQTyqC8I/edit?usp=drive_link)

---

### Step 2) Mock Meeting: Policy Buy-In (Stakeholders)

In this phase, a meeting with the server team introduces the draft Vulnerability Management Policy and assesses their capability to meet remediation timelines. Feedback leads to adjustments, like extending the critical remediation window from 48 hours to one week, ensuring collaborative implementation.

---

### Step 3) Policy Finalization and Senior Leadership Sign-Off

After gathering feedback from the server team, the policy is revised, addressing aggressive remediation timelines. With final approval from upper management, the policy now guides the program, ensuring compliance and reference for pushback resolution.  
[Finalized Policy](https://docs.google.com/document/d/1rvueLX_71pOR8ldN9zVW9r_zLzDQxVsnSUtNar8ftdg/edit?usp=drive_link)


---

### Step 4) Mock Meeting: Initial Scan Permission (Server Team)

The team collaborates with the server team to initiate scheduled credential scans. A compromise is reached to scan a single server first, monitoring resource impact, and using just-in-time Active Directory credentials for secure, controlled access.  

---

### Step 5) Initial Scan of Server Team Assets

In this phase, an insecure Windows Server is provisioned to simulate the server team's environment. After creating vulnerabilities, an authenticated scan is performed, and the results are exported for future remediation steps.  

![image](https://github.com/user-attachments/assets/48f7768f-13f8-458f-9f8c-41886431bca1)

[Scan 1 - Initial Scan PDF](https://drive.google.com/file/d/1RBPVj_azKJMwmRZ8QILlb4hxIjQU3wQ7/view?usp=drive_link)





---

### Step 6) Vulnerability Assessment and Prioritization

We assessed vulnerabilities and established a remediation prioritization strategy based on ease of remediation and impact. The following priorities were set:

1. Third Party Software Removal (Firefox)
2. Windows OS Secure Configuration (SMBv1 Disable)
3. Windows OS Secure Configuration (Protocols & Ciphers)
4. Windows OS Updates

---

### Step 7) Distributing Remediations to Remediation Teams

The server team received remediation scripts and scan reports to address key vulnerabilities. This streamlined their efforts and prepared them for a follow-up review.  

![image](https://github.com/user-attachments/assets/66ae7a83-55ca-4597-8070-aee18eb33d13)


[Remediation Email](https://github.com/joshmadakor1/lognpacific-public/blob/main/misc/remediation-email.md)

---

### Step 8) Mock Meeting: Post-Initial Discovery Scan (Server Team)

The server team reviewed vulnerability scan results, identifying outdated software, insecure accounts, and deprecated protocols. The remediation packages were prepared for submission to the Change Control Board (CAB). 


---

### Step 9) Mock CAB Meeting: Implementing Remediations

The Change Control Board (CAB) reviewed and approved the plan to remove insecure protocols and cipher suites. The plan included a rollback script and a tiered deployment approach.  

---
### Step 10 ) Remediation Effort

#### Remediation Round 1: Outdated Firefox Removal

The server team used a PowerShell script to remove outdated Firefox. A follow-up scan confirmed successful remediation.  
[Firefox Removal Script](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/remediation-FireFox-uninstall.ps1)  

![image](https://github.com/user-attachments/assets/0e8ce5fe-7d59-4e94-ac30-19704263f613)


[Scan 2 - Third Party Software Removal PDF](https://drive.google.com/file/d/1n8a1I8-L_KdlOvn2bSQYzFyDFU7VsmcE/view?usp=sharing)


#### Remediation Round 2: SMBv1 Vulnerability Remediation

The server team used PowerShell scripts to remediate the SMBv1 vulnerability used by the Wannacry Ransomware. A follow-up scan verified successful remediation, and the results were saved for reference.  
[PowerShell: SMBv1 Remediation](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/remediation-SMBv1.ps1)


![image](https://github.com/user-attachments/assets/2e236f9e-8e7e-44e6-a358-f71d84b022e4)


[Scan 3 - Post SMBv1 remediation PDF](https://drive.google.com/file/d/1bVaznjkPWAqYYZoolYFRBbioUGx4rh4R/view?usp=sharing)


#### Remediation Round 3: Insecure Protocols & Ciphers

The server team used PowerShell scripts to remediate insecure protocols and cipher suites. A follow-up scan verified successful remediation, and the results were saved for reference.   
[PowerShell: Insecure Protocols and Ciphers Remediation](https://github.com/joshmadakor1/lognpacific-public/blob/main/automation/toggle-protocols.ps1)

![image](https://github.com/user-attachments/assets/2916034e-692b-4f0a-9447-0af7329e730b)

[Scan 4 - Post protocol and cipher remediation PDF](https://drive.google.com/file/d/1jVgikjfrV1YjOcL3QRT_oUB0Y82w22V7/view?usp=drive_link)


#### Remediation Round 4: Windows OS Updates

Windows updates were re-enabled and applied until the system was fully up to date. A final scan verified the changes  

![image](https://github.com/user-attachments/assets/0f08f1ef-8a42-4cd6-82f3-717c920a2976)

[Scan 5 - Post Windows Updates PDF](https://drive.google.com/file/d/1tmDjeHl5uiGitRwWy8kFRi33q-nGi1Zt/view?usp=drive_link)

---

### First Cycle Remediation Effort Summary

The remediation process reduced total vulnerabilities by approximately 89%, from 87 to 10. Critical vulnerabilities were resolved by the fifth scan (100%), and high vulnerabilities dropped by 91%. Mediums were reduced by 81%. In an actual production environment, asset criticality would further guide future remediation efforts.  

![image](https://github.com/user-attachments/assets/5bfa318d-f2ed-4ab2-9032-64ca844c7695)


[Remediation Data](https://docs.google.com/spreadsheets/d/1FTtFfZYmFsNLU6pm8nTzsKyKE-d2ftXzX_DPwcnFNfA/edit?gid=0#gid=0)

---

### On-going Vulnerability Management (Maintenance Mode)

After completing the initial remediation cycle, the vulnerability management program transitions into **Maintenance Mode**. This phase ensures that vulnerabilities continue to be managed proactively, keeping systems secure over time. Regular scans, continuous monitoring, and timely remediation are crucial components of this phase. (See [Finalized Policy](https://docs.google.com/document/d/1rvueLX_71pOR8ldN9zVW9r_zLzDQxVsnSUtNar8ftdg/edit?usp=drive_link) for scanning and remediation cadence requirements.)

Key activities in Maintenance Mode include:
- **Scheduled Vulnerability Scans**: Perform regular scans (e.g., weekly or monthly) to detect new vulnerabilities as systems evolve.
- **Patch Management**: Continuously apply security patches and updates, ensuring no critical vulnerabilities remain unpatched.
- **Remediation Follow-ups**: Address newly identified vulnerabilities promptly, prioritizing based on risk and impact.
- **Policy Review and Updates**: Periodically review the Vulnerability Management Policy to ensure it aligns with the latest security best practices and organizational needs.
- **Audit and Compliance**: Conduct internal audits to ensure compliance with the vulnerability management policy and external regulations.
- **Ongoing Communication with Stakeholders**: Maintain open communication with teams responsible for remediation, ensuring efficient coordination.

By maintaining an active vulnerability management process, organizations can stay ahead of emerging threats and ensure long-term security resilience.
