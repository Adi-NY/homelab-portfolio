# Microsoft 365 Business Setup with Exchange Online Email

## Why Microsoft 365? ##
The employees of the business were comfortable with using Microsoft SaaS such as Word, Excel, Outlook etc.
Business was interested in OneDrive Syncing and multi-device collaboration.

## Primary Challenge while setting up the environment ##
Due to the business wanting to test Microsoft 365, a Trial subscription was purchased. Later,
After the setup of Exchange Online, the Domain, and the Office 365 suite, the business decided to purchase an annual
subscription. This caused the same Microsoft account to have multiple licenses and since the Trial License
got inactivated, the Exchange Online Email Service immediately ceased, causing failed business email access.

## Resolution Approach
 - Verified if DNS Records (MX, SPF, DKIM) were healthy.
 - Installed PowerShell Microsoft Exchange Module via ```Install-Module ExchangeOnlineManagement```
 - Checked Mailbox status with ```Get-Mailbox user@company.com```
 - Mailbox returned deployed, so the licensure issue was shortlisted.
 - Internet Research showed, License needs to be reprovisioned and disconnected from Exchange Online
   for 30 mins to 1 hour and connected back.
 - License was reprovisioned and the mailbox was accessible within two hours.
 - Tested mail flow end-to-end before confirming resolution
 - Full functionality restored within 4 hours 

**Evidence:**
- Screenshot of Email sending failure evidence
- PowerShell screenshots guiding through the whole process
- Screenshot of DNS setup of the business in 365 Admin Center

**Resolution approach:**
- Identified the license corruption as root cause
- Re-provisioned licenses through M365 Admin Center
- Verified DNS records (MX, SPF, DKIM) were intact
- Tested mail flow end-to-end before confirming resolution
- Full functionality restored within 4 hours
