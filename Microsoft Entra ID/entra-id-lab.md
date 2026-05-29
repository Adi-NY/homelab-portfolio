# Microsoft Entra ID (Azure AD) Lab
## Cloud Identity and Access Management

## Overview
Built a fully functional Microsoft Entra ID environment 
using a dedicated Azure tenant (AdiITLab) to develop 
hands-on experience with cloud-based identity management, 
access control, and security policies. This lab simulates 
a real-world enterprise environment including user 
lifecycle management, group administration, conditional 
access, MFA enforcement, and device management.

## Environment
| Component | Details |
|-----------|---------|
| Platform | Microsoft Azure |
| Service | Microsoft Entra ID (formerly Azure AD) |
| Tenant | AdiITLab.onmicrosoft.com |
| Lab Type | Cloud Identity Management |
| Users Created | Multiple test users across departments |

---

## What I Built

### 1. User Lifecycle Management
- Created user accounts in Entra ID with proper 
  display names, UPNs, and department assignments
- Created Microsoft 365 licensed user accounts 
  with cloud mailbox provisioning
- Configured password enforcement policies 
  requiring complexity and expiration
- Performed password resets on user accounts 
  following security best practices
- Verified user device overview showing 
  registered devices per user

**Screenshots:** Entra_User_Creation.png,
Entra_Create_365_User_Account.png,
Entra_Password_Enforce.png,
Entra_Resetting_a_User_Account_Passwo.png,
Entra_User_Device_Overview.png

---

### 2. Group Management — Static and Dynamic
- Created Security groups and Microsoft 365 
  groups for department-based access control
- Implemented dual-group strategy per department:
  Security group for resource access control,
  Microsoft 365 group for team collaboration
- Added members to groups using both direct 
  assignment and alternative bulk methods
- Created a Dynamic Security Group with 
  membership rules based on user location 
  (NYC branch) — automatically assigns users 
  to the group when their location attribute 
  matches the defined rule
- Reviewed Group Overview showing full 
  membership and group properties

**Dynamic Group Rule:**
(user.officeLocation -contains "NYC")

This rule automatically adds any user whose 
office location contains NYC to the group — 
eliminating manual group management for 
location-based access control.

**Screenshots:** Entra_Group_Overview.png,
Entra_Add_Member_to_Group.png,
Entra_Alt_way_to_add_members.png,
Entra_Dynamic_Group_Creation.png,
Entra_Dynamic_Membership_logic_setup.png

---

### 3. Role Assignment
- Assigned administrative roles to specific 
  users following least privilege principles
- Configured role assignments to grant only 
  the permissions required for each user's 
  function
- Verified role assignments reflected 
  correctly in user properties

**Screenshot:** Entra_Role_Assignment.png

---

### 4. Multi-Factor Authentication (MFA)
**Per-User MFA:**
- Reviewed per-user MFA status across all accounts
- Identified users with MFA enabled vs disabled
- Understood distinction between enabled, 
  enforced, and disabled MFA states

**Conditional Access MFA (Modern Approach):**
- Created Conditional Access policy requiring 
  MFA for all users across all cloud applications
- Configured policy in Report Only mode first 
  for impact assessment before enforcement
- Enabled policy to enforce MFA organization-wide
- Verified MFA enforcement in effect on 
  user account
- Captured MFA status showing not registered 
  state for new user — simulating real onboarding 
  scenario where user must register MFA 
  on first login

**Why Conditional Access over Per-User MFA:**
Microsoft recommends Conditional Access as the 
modern standard for MFA enforcement because it 
allows granular policy control — applying MFA 
only under specific conditions (location, device 
compliance, risk level) rather than blanket 
per-user enforcement.

**Screenshots:** Entra_Conditional_Access_MFA_Policy.png,
Entra_MFA_status_not_registrated.png,
Entra_Account_MFA_in_effect.png

---

### 5. Password Policy and Account Security
- Configured client-side password policy 
  and verified it was in effect on user accounts
- Simulated account lockout scenario by 
  exceeding failed login attempts
- Reviewed account lockout status in 
  Entra ID admin center
- Unlocked account and reset password 
  following security procedures

**Screenshots:** Entra_Client_Password_policy_in_effect.png,
Entra_Account_Lockout.png

---

### 6. Security Monitoring — Sign-in Logs
- Accessed Sign-in logs to review 
  authentication activity across the tenant
- Identified and reviewed failed password 
  sign-in attempts in audit logs
- Demonstrated ability to investigate 
  suspicious authentication activity — 
  a critical skill in HIPAA-regulated 
  and compliance-aware environments

**Real World Application:**
In a healthcare environment, monitoring 
sign-in logs is essential for detecting 
unauthorized access attempts to systems 
containing protected health information (PHI). 
Failed login patterns can indicate 
brute force attacks or compromised credentials.

**Screenshots:** Entra_Signin_logs.png,
Entra_Failed_password_Sign_in_logs.png

---

### 7. Self-Service Password Reset (SSPR)
- Configured Self-Service Password Reset 
  for selected users
- Selected authentication methods users 
  can use to verify identity during reset
- Verified SSPR working in effect — 
  users can reset their own passwords 
  without IT intervention
- Reduces IT helpdesk ticket volume for 
  password reset requests — one of the 
  most common IT support tasks

**Screenshots:** Entra_Selected_Self_Password_reset.png,
Entra_Self_Password_Reset_in_effect.png

---

### 8. Device Management — Entra ID Join
- Connected a Windows client PC to the 
  Azure tenant via Entra ID Join
- Entra ID Join registers the device 
  directly to the cloud directory — 
  no on-premise domain controller required
- Verified device appeared in user's 
  device overview after join
- Demonstrated understanding of difference 
  between traditional AD domain join 
  (on-premise) and Entra ID Join (cloud-native)

**Entra ID Join vs Traditional Domain Join:**
| Feature | Traditional AD | Entra ID Join |
|---------|---------------|---------------|
| Infrastructure | On-premise DC required | Cloud only |
| Best for | Legacy enterprise | Modern/remote workforce |
| Management | Group Policy | Intune/Conditional Access |
| Identity | Local AD | Microsoft 365 identity |

**Screenshot:** Entra_Connecting_PC_to_Domain.png

---

## Skills Demonstrated
- Cloud identity and access management
- User lifecycle — creation, modification, 
  password reset, device overview
- Static and Dynamic group management 
  with attribute-based rules
- Role assignment with least privilege principles
- MFA enforcement via Conditional Access 
  (modern) and Per-User (legacy)
- Security monitoring through sign-in 
  and audit logs
- Account lockout identification and recovery
- Self-Service Password Reset configuration
- Entra ID device join and management
- Understanding of cloud vs on-premise 
  identity architecture

## Real World Application
| Lab Task | Real World Scenario |
|----------|-------------------|
| Dynamic group by location | Auto-assign NYC branch staff to correct access groups |
| Conditional Access MFA | Enforce MFA for all staff accessing patient systems |
| Sign-in log monitoring | Detect unauthorized access to PHI systems |
| SSPR configuration | Reduce helpdesk tickets for password resets |
| Account lockout recovery | Staff locked out before clinic hours |
| Entra ID Join | Deploy new workstation without on-premise DC |
| Role assignment | Grant helpdesk staff limited admin permissions |

## Lessons Learned
- Dynamic groups eliminate manual membership 
  management — critical for organizations 
  with frequent staff changes
- Conditional Access is superior to Per-User 
  MFA because it allows policy-based 
  enforcement with granular conditions
- Sign-in logs are the first place to check 
  during a suspected security incident — 
  failed attempts, unusual locations, 
  and off-hours access are key indicators
- SSPR significantly reduces helpdesk 
  password reset volume — one of the most 
  common IT support requests in any organization
- Entra ID Join is the modern replacement 
  for traditional domain join in 
  cloud-first organizations

## Screenshots
All screenshots labeled descriptively and 
available in the screenshots folder.
Total screenshots: 21
