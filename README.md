# 🧠 Active Directory Lab Environment

A hands-on **Active Directory lab environment** built using **Oracle VM VirtualBox**, designed to simulate real-world IT support and system administration tasks.

This lab demonstrates how domain environments are configured and managed, including **user administration, group management, domain authentication, and PowerShell automation**.

---

## 🖥️ Lab Environment

**Virtualization Platform**

- Oracle VM VirtualBox

**Domain Controller**

- Windows Server
- Active Directory Domain Services (AD DS)
- DNS Server

**Client Machine**

- Windows 11
- Joined to the domain for authentication testing

---

## 🏗️ Lab Architecture

```
                Oracle VM VirtualBox
                       │
                       │
        ┌──────────────┴──────────────┐
        │                             │
        │                             │
 Windows Server                 Windows 11 Client
 Domain Controller              Domain Joined
 AD DS + DNS                    User Authentication
```

---

## ⚙️ Tasks Practiced in This Lab

### 👤 User Management

- Create new domain users
- Unlock locked accounts
- Reset user passwords
- Disable / enable user accounts

### 👥 Group Management

- Create security groups
- Add users to groups
- Remove users from groups
- Verify group memberships

### 🌐 Domain Operations

- Join Windows 11 machine to domain
- Verify domain authentication
- Test login using domain users
- Validate domain controller connectivity

---

## 💻 PowerShell Automation Examples

### Create Domain User

```powershell
Import-Module ActiveDirectory

New-ADUser `
-Name "LabUser1" `
-SamAccountName "LabUser1" `
-AccountPassword (ConvertTo-SecureString "Password123!" -AsPlainText -Force) `
-Enabled $true
```

### Unlock User Account

```powershell
Unlock-ADAccount -Identity LabUser1
```

### Reset User Password

```powershell
Set-ADAccountPassword `
-Identity LabUser1 `
-Reset `
-NewPassword (ConvertTo-SecureString "NewPassword123!" -AsPlainText -Force)
```

### Add User To Group

```powershell
Add-ADGroupMember `
-Identity "IT-Support" `
-Members LabUser1
```

---

## 📂 Repository Structure

```
active-directory-lab
│
├── README.md
│
├── architecture
│      lab-architecture.png
│
├── user-management
│      create-user.ps1
│      unlock-user.ps1
│      reset-password.ps1
│
├── group-management
│      add-user-to-group.ps1
│      remove-user-from-group.ps1
│
├── domain-operations
│      check-domain-controller.ps1
│      list-domain-users.ps1
│      domain-health-check.ps1
│
├── screenshots
│      ad-console.png
│      domain-joined-client.png
│      password-reset.png
│      group-membership.png
```

---

## 📸 Lab Screenshots

Screenshots demonstrating the environment and operations will be added here.

Examples:

- Active Directory Users and Computers console
- Domain joined Windows 11 machine
- User creation and password reset
- Group membership configuration

---

## 🧩 Skills Demonstrated

- Active Directory Administration  
- Domain Controller Setup  
- User & Group Management  
- Windows Server Management  
- PowerShell Automation  
- Domain Authentication  
- Virtual Lab Infrastructure

---

## 🎯 Purpose of This Lab

This lab environment was built to **practice real-world IT support tasks performed in enterprise environments** and to strengthen knowledge of **Active Directory administration and troubleshooting workflows**.

---

## 👨‍💻 Author

**Dhanush Achari**

IT Support | Infrastructure Troubleshooting | Windows Systems
