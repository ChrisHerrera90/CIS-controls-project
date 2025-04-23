# CIS Controls Version 8.1 Implementation Project for a SaaS Based Online Business
This is a project walkthrough of a complete CIS Controls implementation that I designed for a real small-sized business (business name redacted for privacy) built on the GoHighLevel Platform (Elite360). 

In this project, I performed an audit of an online coaching business utilizing the CIS Controls Version 8.1 framework. Once I completed the audit, I then provided steps for remediation in order to make this business compliant based on these controls.

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

📋 Asset Inventory Table

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


✅ Review Schedule
Asset inventory is reviewed monthly during our security operations check-in and updated after any major launch or integration change.


---

### 📋 CIS Control 2: Inventory and Control of Software Assets

In this control, we track and periodically review all third-party integrations, webhooks, and connected apps to eliminate unauthorized or unused services. The following table lists all third-party software, services, and integrations that interact with our GoHighLevel account to maintain visibility, control, and reduce risk from unauthorized or outdated applications.

🔌 Software Asset Inventory

| Software / Integration | Purpose                          | Data Accessed              | Owner              | Status     | Notes                                    |
|------------------------|----------------------------------|----------------------------|--------------------|------------|-------------------------------------------|
| Zoom                   | Hosts webinar based events       | Contact data, form entries | Operations Manager | Active     | Limited scope, API key stored securely    |
| Paypal                 | Payment processing               | Customer payment details   | Admin              | Active     | PCI-DSS compliant, 2FA enabled            |
| EventsCalendar.io      | Calendar of Event offerings      | Calendar events, funnels   | Marketing Team     | Active     | OAuth-based access                        |
| Mailgun / SMTP         | Email Marketing delivery         | Emails, lead names         | Marketing Team     | Active     | DKIM/SPF configured                       |
| Proton Mail            | Internal Staff Communication     | Emails, various client PII | Admin              | Active     | DKIM/SPF configured                       |
| Tettra                 | Internal staff documentaton      | SOPs                       | Admin              | Active     | 2fa enabled                   |

✅ Review Schedule:

All integrations and software connections are reviewed quarterly and after any major platform change. Inactive or high-risk connections are removed or replaced immediately.


---

### ⚙️ CIS Control 4: Secure Configuration of Enterprise Assets and Software

This control focuses on applying secure-by-default configurations within the GoHighLevel platform by disabling unused features, securing integrations, and removing default assets. These are the steps I took to implement this control:

🌐 Funnels, Websites, and Domains

I first ensured that all of the funnels, website pages and domains were SSL enabled in order to prevent web-facing vulnerabilities. Upon looking up the SSL status, the domain for the business did have an up to date SSL certificate:

![image](https://github.com/user-attachments/assets/a1cab15d-65b0-4a6e-b12a-61f6e7a9d0a0)

In addition, I went through all  42 of their funnels and identified any funnels that were no longer needed. The intent was to find any live funnels (and their forms, assets, etc.) that could potentially be exploited by bad actors. In the end, with the help of management, 24 funnels were identified as unnecessary and were deleted:

![image](https://github.com/user-attachments/assets/af459e21-a6f9-4294-a9d0-188c7f091863)

I did the same with all of their website's main public-facing pages and found none that needed to be deleted or altered.

📜 Backup and Recovery Plan

Due to the fact that the business is built on a third party SaaS platform, and that almost all of their critical digital assets are stored within it, it was imperative to implement a backup and recovery plan in the event of service shortages (which have happened in the past). The plan revolved on the following tasks:
- Exporting a list of contacts, leads, funnels, ad and email campaigns, transactions, audit logs, and other sensitive data on a monthly basis.
- Store this data in an encrypted cloud storage solution with 2FA (Dropbox Business in this case)
- Document the manual backup process as an SOP within the company's Tettra database for the operations manager.

---

### 👨‍💻 CIS Control 5: Account Management

This control focuses on implementing individual user accounts, enforce least-privilege access, and conduct regular reviews to remove inactive or unnecessary users. These are the steps I took to implement this control:

👥 User and Role Configuration

The first thing I reviewed was the actual User roles and permissions for all accounts in the GoHighLevel/Elite360 platform to implement the principle of "least priveledge" access. Upon pulling up the roster of accounts I found the following accounts and permissions (details redacted for privacy):

![image](https://github.com/user-attachments/assets/4627d863-7199-4668-bd06-c1f11b8af2d7)
 
In total, there were 6 accounts with the following user types:
- Owner as Admin
- Operations Manager as Admin
- Client Success Manager as User
- Marketing Team as Admin (single user)
- Sales Team as Admin (single user)
- Virtual assistant as User

Right off the bat, there were simply too many accounts with full "Admin" privileges, many of which did not need such a deep level of permission and access to perform their job duties. Upon reviewing this information with the owner of the business, it was decided that the user permissions/role should be changed as follows:
- Owner as Admin
- Operations Manager as Admin
- Client Success Manager as User
- Marketing Team as User
- Sales Team as User
- Virtual assistant was to  be DELETED since they no longer contracted with them

In addition, more granular permission controls where implemented for each account to further enforce "least priviledge" access. For example, the "Sales Team" Account permissions where limited to only have access to the following platform features: 
- Calendars
- Contacts
- Conversations
- Opportunities
- Payments (limited)
- Media
- Dashboard (limited)

![image](https://github.com/user-attachments/assets/c8e9895a-690d-4df1-9af3-4e8f712a068c)
![image](https://github.com/user-attachments/assets/7578bffa-e1cd-489f-9a85-452d90f13620)

---

### 🪪 CIS Control 8: Audit Log Management

This control focuses on exporting and reviewing available activity logs to track account changes, user access, and lead/customer data movement across the platform. These are the steps I took to implement this control:

Due to being limited to GoHighLevels' features, the only source of activity logs is their "Audit Logs" menu in the dashboard:

![image](https://github.com/user-attachments/assets/3ab3ac26-f18c-4915-b57d-3d3b9e8c2a2f)

📜 Log Database Storage

These logs provided a record of actions that each user account has made in the platform. Since logs are only stored for 60 days in the platform, I advised the business to export the platform's user activity logs every 30 days. They can then store this data into their encrypted Dropbox Business account.

---

### 👀 CIS Control 14: Security Awareness and Skills Training

This control focuses on educating the team members on secure CRM usage, PII handling, phishing recognition, recognizing suspicious file uploads and enforcing security policies for account and communication hygiene. For this control, I created a "Security Awareness Cheat Sheet" that will accompany a formal staff security awareness training program:

https://docs.google.com/document/d/1U_tRtP8UHE78mXSD-BfcWJ8aJAvzb09z8dENtcS9Zvo/edit?usp=sharing



---

By implementing these CIS Controls, this organization can stay ahead of emerging threats and ensure long-term security resilience.
