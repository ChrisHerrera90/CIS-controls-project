# CIS Controls Version 8.1 Implementation Project for a SaaS Based Online Business
This is a project walkthrough of a complete CIS Controls implementation that I designed for a real small-sized business (business name redacted for privacy) built on the GoHighLevel Platform (Elite360)

**Note:** Due to the fact that this business built all of their digital assets on a SaaS platform, not all CIS controls will be applicable for this project since I do not have access to GoHighLevel/Elite360 IT infrastructure. Therefore, the CIS Controls Framework has been adapted for SaaS usage instead of infrastructure hardening. 

## 🔒 Security Disclosure
This project contains anonymized configurations and data for demonstration purposes only. No real customer, business, or platform credentials are included in this repository.

---

# Technology Utilized
- GoHighLevel (Elite360)

---


# Table of Contents

- [CIS Control 1: Inventory and Control of Assets](#vulnerability-management-policy-draft-creation)
- [CIS Control 2: Inventory and Control of Software Assets)](#step-2-mock-meeting-policy-buy-in-stakeholders)
- [CIS Control 4: Secure Configuration of Enterprise Assets and Software](#step-3-policy-finalization-and-senior-leadership-sign-off)
- [CIS Control 5: Account Management](#step-4-mock-meeting-initial-scan-permission-server-team)
- [CIS Control 8: Audit Log Management](#step-5-initial-scan-of-server-team-assets)
- [CIS Control 10: Malware Defenses](#step-6-vulnerability-assessment-and-prioritization)
- [CIS Control 14: Security Awareness and Skills Training](#step-7-distributing-remediations-to-remediation-teams)

---

### CIS Control 1: Inventory and Control of Assets

This phase focuses on drafting a Vulnerability Management Policy as a starting point for stakeholder engagement. The initial draft outlines scope, responsibilities, and remediation timelines, and may be adjusted based on feedback from relevant departments to ensure practical implementation before final approval by upper management.  
[Draft Policy](https://docs.google.com/document/d/1CLSWm1_9JL1oUqgyNNwtPXW6FzXJ7ddVnSAUQTyqC8I/edit?usp=drive_link)

---

### CIS Control 2: Inventory and Control of Software Assets

In this phase, a meeting with the server team introduces the draft Vulnerability Management Policy and assesses their capability to meet remediation timelines. Feedback leads to adjustments, like extending the critical remediation window from 48 hours to one week, ensuring collaborative implementation.

---

### CIS Control 4: Secure Configuration of Enterprise Assets and Software

After gathering feedback from the server team, the policy is revised, addressing aggressive remediation timelines. With final approval from upper management, the policy now guides the program, ensuring compliance and reference for pushback resolution.  
[Finalized Policy](https://docs.google.com/document/d/1rvueLX_71pOR8ldN9zVW9r_zLzDQxVsnSUtNar8ftdg/edit?usp=drive_link)


---

### CIS Control 5: Account Management

The team collaborates with the server team to initiate scheduled credential scans. A compromise is reached to scan a single server first, monitoring resource impact, and using just-in-time Active Directory credentials for secure, controlled access.  

---

### CIS Control 8: Audit Log Management

In this phase, an insecure Windows Server is provisioned to simulate the server team's environment. After creating vulnerabilities, an authenticated scan is performed, and the results are exported for future remediation steps.  

![image](https://github.com/user-attachments/assets/48f7768f-13f8-458f-9f8c-41886431bca1)

[Scan 1 - Initial Scan PDF](https://drive.google.com/file/d/1RBPVj_azKJMwmRZ8QILlb4hxIjQU3wQ7/view?usp=drive_link)

---

### CIS Control 10: Malware Defenses

We assessed vulnerabilities and established a remediation prioritization strategy based on ease of remediation and impact. The following priorities were set:

1. Third Party Software Removal (Firefox)
2. Windows OS Secure Configuration (SMBv1 Disable)
3. Windows OS Secure Configuration (Protocols & Ciphers)
4. Windows OS Updates

---

### CIS Control 14: Security Awareness and Skills Training

The server team received remediation scripts and scan reports to address key vulnerabilities. This streamlined their efforts and prepared them for a follow-up review.  

![image](https://github.com/user-attachments/assets/66ae7a83-55ca-4597-8070-aee18eb33d13)


[Remediation Email](https://github.com/joshmadakor1/lognpacific-public/blob/main/misc/remediation-email.md)

---

By implementing CIS Controls, organizations can stay ahead of emerging threats and ensure long-term security resilience.
