# CIS Controls Version 8.1 Implementation Project for a SaaS Based Online Business
This is a project walkthrough of a complete CIS Controls implementation that I designed for a real small-sized business (business name redacted for privacy) built on the GoHighLevel Platform (Elite360). 

In this project, I performed an audit of an online coaching business utilizing the CIS Controls Version 8.1 framework. Once I completed the audit, I then provided steps for remediation in order tp make this business compliant based on these controls.

**Note:** Due to the fact that this business built all of their digital assets on a SaaS platform, not all CIS controls will be applicable for this project since I do not have access to the GoHighLevel/Elite360 IT infrastructure. Therefore, the CIS Controls Framework has been adapted for SaaS usage instead of infrastructure hardening. 

## 🔒 Security Disclosure
This project contains anonymized configurations and data for demonstration purposes only. No real customer, business, or platform credentials are included in this repository.

---

# Technology Utilized
- GoHighLevel (Elite360)

---


# Table of Contents

- [CIS Control 1: Inventory and Control of Assets](#cis-control-1-inventory-and-control-of-assets)
- [CIS Control 2: Inventory and Control of Software Assets](#step-2-mock-meeting-policy-buy-in-stakeholders)
- [CIS Control 4: Secure Configuration of Enterprise Assets and Software](#step-3-policy-finalization-and-senior-leadership-sign-off)
- [CIS Control 5: Account Management](#step-4-mock-meeting-initial-scan-permission-server-team)
- [CIS Control 8: Audit Log Management](#step-5-initial-scan-of-server-team-assets)
- [CIS Control 10: Malware Defenses](#step-6-vulnerability-assessment-and-prioritization)
- [CIS Control 14: Security Awareness and Skills Training](#step-7-distributing-remediations-to-remediation-teams)

---

### 📋 CIS Control 1: Inventory and Control of Assets

This control is about maintaining an up-to-date inventory of all the business' GoHighLevel sub-accounts, domains, websites, and client-facing assets to reduce shadow IT and manage attack surface exposure. These are the steps I took to implement this control:

In order to identify all critical assets for inventory, I went through the following areas of the business GoHighLevel dashboard:
- Contacts (email list and leads)
- Payments (customer transaction history, invoice templates and contracts)
- Sites (includes websites, funnels, and form templates)
- Marketing (includes email templates)
- Memberships (community platform for customers)
- Media Storage (includes client PDFs, website images, event documents, audio recordings)
- Settings (domain settings, encryption and security)

![image](https://github.com/user-attachments/assets/3e92bc0f-a605-4447-90c4-ec9141fa3b67)


The file below contains a sample structured inventory of all business-critical assets inside the GoHighLevel platform to support visibility, risk reduction, and secure configuration practices. To protect the privacy of the business, and to simplify the inventory for demonstration purposes, I have anonymized and condensed many of the items.

## 📋 Asset Inventory Table

| Asset Type      | Name/Label              | Purpose                            | Owner       | Status     | Notes                                
|------------------|--------------------------|-------------------------------------|-------------|------------|--------------------------------
| Elite360 Account | Main Business Account    | Website + Funnel + CRM for Business | Admin User      | Active  | MFA enabled        
| Domain           | www.client1.com          | Public-facing website              | Admin User       | Active  | SSL enabled      
| 17 Funnels       | Event Add Ons            | Upsell funnels                     | Marketing Team   | Active  | Reviewed 2025-04-17         
| 2 Funnels        | Consultations            | 1 on 1 Coaching sales              | Marketing Team   | Active  | Reviewed 2025-04-17
| 10 Funnels       | Distant Sessions         | Online Group Coaching sales        | Marketing Team   | Active  | Reviewed 2025-04-17 
| 9 Funnels        | 2 Day Online Events      | Coaching Event Sales               | Marketing Team   | Active  | Reviewed 2025-04-18 
| 2 Funnels        | In Person Coaching Sessions  | 1 on 1 Coaching sales          | Marketing Team   | Active  | Reviewed 2025-04-18 
| 2 Funnels        | Consultations            | 1 on 1 Coaching sales              | Marketing Team   | Active  | Reviewed 2025-04-18 
| 14 Email Templates | Email Templates        | Marketing Campaigns                | Marketing Team   | Active  | Reviewed 2025-04-21 
| Lead List        | Email List               | Marketing Campaigns                | Marketing Team   | Active  | Reviewed 2025-04-21 
| Transaction History | Payment history       | Accounting                         | Admin User       | Active  | PCI compliant
| 32 File Uploads  | PDF files for funnels    | Downloadable assets on funnel      | Admin User       | Active  | No sensitive data
| 67 Image Uploads | PNG files                | Images for website/funnels         | Admin User       | Active  | No sensitive data
| Coomunity Portal | Membership Community     | Community Portal for VIP Members   | Admin User       | Active  | No sensitive data
| User Account     | john.doe@domain.com      | Owner/Founder                      | Admin (Owner)    | Active  | Least privilege confirmed
| User Account     | john.doe@domain.com      | Operations Manager                 | Admin            | Active  | Least privilege confirmed
| User Account     | john.doe@domain.com      | Sales Rep                          | User             | Active  | Least privilege confirmed
| User Account     | john.doe@domain.com      | Marketing Manager                  | User             | Active  | Least privilege confirmed
| User Account     | john.doe@domain.com      | Client Success Manager             | User             | Active  | Least privilege confirmed
| Workflow 1        | Onboarding Automation   | Event Registrees are sent to onboarding page | Marketing Team   | Active    | Logs reviewed
| Workflow 2        | Add to email list       | Newsletter opt in joins email list           | Marketing Team   | Active    | Logs reviewed
| Workflow 3        | New purchases           | Alerts staff of new purchase/registration    | Marketing Team   | Active    | Logs reviewed
| Workflow 4        | New contact form        | Alerts staff of new contact form submission  | Marketing Team   | Active    | Logs reviewed
| 40 Forms          | Questionnaires | Onboarding intake forms for events/sessions | Admin User  | Active  | PII sanitized, reCAPTCHAenable

## ✅ Review Schedule
Asset inventory is reviewed monthly during our security operations check-in and updated after any major launch or integration change.


---

### 📋 CIS Control 2: Inventory and Control of Software Assets

In this control, we track and periodically review all third-party integrations, webhooks, and connected apps to eliminate unauthorized or unused services. These are the steps I took to implement this control:

---

### ⚙️ CIS Control 4: Secure Configuration of Enterprise Assets and Software

This control focuses on applying secure-by-default configurations within the GoHighLevel platform by disabling unused features, tightening permissions, and removing default assets. These are the steps I took to implement this control:


---

### 👨‍💻 CIS Control 5: Account Management

This control focuses on implementing individual user accounts, enforce least-privilege access, and conduct regular reviews to remove inactive or unnecessary users. These are the steps I took to implement this control:

---

### 🪪 CIS Control 8: Audit Log Management

This controls focuses on exporting and reviewing available activity logs to track account changes, user access, and lead/customer data movement across the platform. These are the steps I took to implement this control:

---

### 🛡️ CIS Control 10: Malware Defenses

This control focuses on training staff to recognize suspicious messages or uploads and ensure only vetted files and assets are shared or received via the GoHighLevel-Elite360 platform. These are the steps I took to implement this control:


---

### 👀 CIS Control 14: Security Awareness and Skills Training

This control focuses on educating the team members on secure CRM usage, PII handling, phishing recognition, and enforce security policies for account and communication hygiene. For this control, I created a training manual on best security practices that team members can study and reference:


---

By implementing these CIS Controls, this organization can stay ahead of emerging threats and ensure long-term security resilience.
