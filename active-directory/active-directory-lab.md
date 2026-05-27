# Active Directory Home Lab
## On-Premise Windows Server Environment

## Overview
Built a fully functional Active Directory domain environment 
using VirtualBox and Windows Server 2019 to develop hands-on 
experience with enterprise identity and access management. 
This lab simulates a real-world organizational IT environment 
including domain setup, user and group management, GPO 
configuration, remote access, and client machine integration.

## Environment
| Component | Details |
|-----------|---------|
| Server OS | Windows Server 2025 |
| Client OS | Windows 11 |
| Domain | adiit.lab |
| Lab Type | Local Active Directory |

## What I Built

### 1. Domain Setup and DNS Configuration
- Configured DNS to enable domain name resolution 
  across the environment
- Successfully promoted server to Domain Controller
- Verified domain connectivity from the client machine
- Established a stable client-to-domain connection
## IT is important to note down that Active Directory heavily relies on DNS to setup domains
**Screenshots:** AD_DNS_setup_to_access_domain.png, 
AD_Successfull_Domain_Connection.png

---

### 2. Organizational Unit Structure
- Created a branch and department-based OU hierarchy to reflect 
  real organizational structure
- Structured OUs to enable department-level 
  GPO application

**Screenshot:** AD_OU_Creation.png, AD_OU_Structure.png

---

### 3. User Account Management
- Created user accounts within appropriate OUs
- Configured user properties including department, 
  job title, and contact information
- Updated user information post-creation to simulate 
  real HR change requests
- Configured login restrictions to control 
  when and where users can authenticate

**Screenshots:** AD_User_Creation.png, 
AD_User_Info_Update.png, AD_Login_Restrict_Setup.png

---

### 4. Security Group Management
- Created security groups for department-level 
  access control
- Assigned users to appropriate security groups
- Implemented Role Based Access Control (RBAC) 
  principles through group membership
- Resolved duplicate naming conflict during 
  group assignment. Also identified and corrected 
  naming convention issue

**Screenshots:** AD_Group_Creation.png, 
AD_Group_Assign.png, 
AD_Group_User_Security_Permissions.png,
AD_Group_Assign_Duplicate_Name.png

---

### 5. Group Policy Objects (GPO)
- Created and configured Password Policy GPO:
  - Minimum password length enforcement
  - Password complexity requirements
  - Password history settings
- Created Account Lockout Policy GPO:
  - Lockout threshold configuration
  - Lockout duration settings
  - Reset counter configuration
- Linked GPOs to appropriate OUs for 
  targeted policy application

**Screenshots:** GPO_Password_Policy.png, 
GPO_Account_Lockout_policy.png

---

### 6. Account Lockout and Recovery
- Simulated client-side account lockout scenario
- Located locked account in Active Directory 
  Users and Computers
- Unlocked account and configured temporary 
  password following security best practices
- Verified user could authenticate successfully 
  after unlock

**Screenshots:** Client_Account_Lockout.png,
AD_Account_Lockout.png, Unlock_Account.png,
Setup_Temporary_Password.png

---

### 7. Remote Desktop Protocol (RDP) Setup
- Assigned RDP access permissions to specific users
- Configured Remote Desktop settings on client machine
- Allowed remote connections through system properties
- Verified remote connectivity between server 
  and client

**Screenshots:** AD_Assign_RDU_to_user.png,
AD_Allow_Remote_connection_on_client.png

---

### 8. Client Machine Domain Join
- Configured client machine network settings 
  to point to AD DNS server
- Successfully joined Windows 11 client to 
  adiit.lab domain
- Verified domain authentication from client machine
- Logged in as domain user from client machine

**Screenshots:** User1_Network_Setup.png,
AD_Connect_Client_to_Domain.png,
AD_Logging_in_as_user.png,
AD_login_as_client.png,
AD_Client_logged_in.png

---

### 9. Roles and Delegation
- Configured role delegation to grant specific 
  administrative permissions to non-admin users
- Applied principle of least privilege, 
  users receive only permissions required 
  for their function

**Screenshot:** AD_Roles_Delegation.png

---

### 10. SYSVOL Logon Script
- Configured SYSVOL logon script for automated 
  drive mapping on user login
- Script deployed through Group Policy to 
  apply consistently across domain users
- Simulates real enterprise onboarding automation

**Screenshot:** SYSVOL_Logon_script_setup.png

---

## Skills Demonstrated
- Active Directory domain setup and DNS configuration
- Organizational Unit design and hierarchy
- User account lifecycle management
- Security group creation and RBAC implementation
- GPO creation  password and lockout policies
- Account lockout identification and recovery
- Remote Desktop Protocol configuration and access
- Client machine domain join and authentication
- Role delegation and least privilege principles
- SYSVOL logon script deployment
- Troubleshooting , resolved duplicate group 
  naming conflict during 

## Real World Application
Every task completed in this lab maps directly to 
day-to-day IT support responsibilities:

| Lab Task | Real World Scenario |
|----------|-------------------|
| User creation | New employee onboarding |
| Account unlock | Staff locked out |
| Password reset | User forgot credentials |
| GPO configuration | Enforcing security policy across org |
| RDP setup | Remote IT support for staff |
| Domain join | Setting up a new workstation |
| Role delegation | Junior IT staff helping with specific tasks |
| Logon script | Automating drive mapping for new hires |

## Lessons Learned
- DNS configuration is the foundation of AD  
  without correct DNS the entire domain 
  communication fails
- GPO inheritance requires careful OU planning  
  applying policies at the wrong level affects 
  unintended users
- Duplicate group naming causes assignment failures  
  naming conventions must be established before 
  deployment
- Least privilege through role delegation is more 
  secure than granting full admin rights for 
  limited tasks
- SYSVOL logon scripts significantly reduce manual 
  onboarding steps in a real environment

## Screenshots
All screenshots are labeled and available in the 
screenshots folder with descriptive filenames 
indicating exactly what each image demonstrates.
