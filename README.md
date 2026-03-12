# Active Directory Lab Environment

This repository documents a hands-on Active Directory lab built for practicing common IT support and system administration tasks.

The lab environment was created using **Oracle VM VirtualBox**, with Windows Server configured as a Domain Controller and a Windows 11 machine joined as a domain client.

---

## Lab Environment

Domain Controller  
• Windows Server  
• Active Directory Domain Services installed  
• DNS configured  

Client Machine  
• Windows 11  
• Joined to the domain for authentication testing

Virtualization Platform  
• Oracle VM VirtualBox

---

## Lab Architecture

Domain Controller → Manages users, groups, authentication  
Client Machine → Domain-joined workstation for testing

---

## Tasks Practiced

### User Management
• Create new domain users  
• Unlock locked accounts  
• Reset user passwords  

### Group Management
• Create security groups  
• Add users to groups  
• Verify group membership

### Domain Operations
• Join Windows 11 machine to domain  
• Test domain authentication  
• Verify user login from client machine

---

## PowerShell Automation Examples

Scripts included in this repository demonstrate automation of common Active Directory tasks.

Examples:

Create user

```
New-ADUser -Name "TestUser" -SamAccountName testuser -AccountPassword (ConvertTo-SecureString "Password123!" -AsPlainText -Force) -Enabled $true
```

Unlock user

```
Unlock-ADAccount -Identity testuser
```

Reset password

```
Set-ADAccountPassword -Identity testuser -Reset -NewPassword (ConvertTo-SecureString "NewPassword123!" -AsPlainText -Force)
```

Add user to group

```
Add-ADGroupMember -Identity "IT-Support" -Members testuser
```

---

## Skills Demonstrated

Active Directory Administration  
User and Group Management  
Domain Authentication  
PowerShell Automation  
Virtual Lab Setup using Oracle VM VirtualBox

---

## Purpose of This Lab

This lab was built to simulate real-world IT support tasks performed in enterprise environments and to practice troubleshooting and administration of Active Directory systems.

---

## Author

Dhanush Achari  
IT Support / Infrastructure Troubleshooting
