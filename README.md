# Windows IT Support Home Lab

## Project Overview

This project is a small Windows IT support home lab built with VirtualBox, Windows Server 2022, and a Windows 10 client VM. The goal was to simulate a basic company environment with Active Directory, domain users, security groups, shared folders, and department-based permissions.

## Lab Environment

- Virtualization: Oracle VM VirtualBox
- Server: Windows Server 2022
- Client: Windows 10 Pro
- Domain Controller: DC01
- Domain: homelab.local
- Server Lab IP: 192.168.56.10
- Client: CLIENT01

## What I Configured

- Installed and configured Windows Server 2022
- Promoted the server to a Domain Controller
- Created the domain homelab.local
- Installed Active Directory Domain Services and DNS
- Created Organizational Units for IT, HR, and Accounting
- Created domain users and security groups
- Joined a Windows 10 Pro client to the domain
- Created shared folders for each department
- Applied NTFS permissions using security groups
- Tested access from the client using domain user accounts

## Active Directory Structure

- Employees
  - IT
  - HR
  - Accounting
- Groups
  - IT_Users
  - HR_Users
  - Accounting_Users

## Permission Testing

Each department folder was configured so only the correct department group could access it.

| User | Group | Allowed Folder | Blocked Folders |
|---|---|---|---|
| Marina Garcia | HR_Users | HR | IT, Accounting |
| Alex Brown | IT_Users | IT | HR, Accounting |
| John Smith | Accounting_Users | Accounting | HR, IT |

## Skills Practiced

- Windows Server administration
- Active Directory user and group management
- Domain Controller setup
- DNS configuration
- Windows domain joining
- NTFS permissions
- Shared folder management
- Basic help desk troubleshooting
- Access control testing
- Documentation

# Screenshots


# 1.0 Lab Environment


This section documents the virtual lab environment used for the Active Directory project. The lab used one Windows Server 2022 virtual machine as the domain controller and one Windows 10 virtual machine as the client workstation.

VirtualBox Manager Showing Both VMs

![VirtualBox Manager Showing Both VMs](Documentation/Sections%201.0-4.0/Section%201/VirtualBox%20Manager%20showing%20both%20VMs.png)

This screenshot shows both virtual machines used in the lab: the Windows Server 2022 domain controller and the Windows 10 client.


* Server VM Network Adapter 1

![Server VM Network Settings Adapter 1](Documentation/Sections%201.0-4.0/Section%201/Server%20VM%20network%20settings%20Adapter%201.png)

This screenshot shows the first network adapter for the Windows Server VM configured as NAT.


* Server VM Network Adapter 2

![Server VM Network Settings Adapter 2](Documentation/Sections%201.0-4.0/Section%201/Server%20VM%20network%20settings%20Adapter%202.png)

This screenshot shows the second network adapter for the Windows Server VM configured as a Host-Only Adapter.


* Client VM Network Adapter 1

![Client VM Network Settings Adapter 1](Documentation/Sections%201.0-4.0/Section%201/3.%20Client%20VM%20network%20settings%20Adapter%201.png)

This screenshot shows the first network adapter for the Windows 10 client VM configured as NAT.


* Client VM Network Adapter 2

![Client VM Network Settings Adapter 2](Documentation/Sections%201.0-4.0/Section%201/3.%20Client%20VM%20network%20settings%20Adapter%202.png)

This screenshot shows the second network adapter for the Windows 10 client VM configured as a Host-Only Adapter.

---

# 2.0 Server and Active Directory Setup

This section documents the Windows Server and Active Directory configuration. DC01 was configured as the domain controller for the homelab.local domain.

* Domain Controller Proof

![Domain Controller Proof](Documentation/Sections%201.0-4.0/Section%202/2.1%20Domain%20controller%20proof.png)

This screenshot shows DC01 listed in Server Manager, confirming that the Windows Server VM was configured and managed as the main server in the lab.


* Domain Name Proof

![Domain Name Proof](Documentation/Sections%201.0-4.0/Section%202/2.2%20Domain%20name%20proof.png)

This screenshot shows the server properties with the domain listed as homelab.local.


* Active Directory Structure - Alex Brown

![AD Structure Proof Alex](Documentation/Sections%201.0-4.0/Section%202/2.3%20AD%20structure%20proof_Alex.png)

This screenshot shows Alex Brown placed inside the IT organizational unit.


* Active Directory Structure - John Smith

![AD Structure Proof John](Documentation/Sections%201.0-4.0/Section%202/2.3%20AD%20structure%20proof_John.png)

This screenshot shows John Smith placed inside the Accounting organizational unit.


* Active Directory Structure - Marina Garcia

![AD Structure Proof Marina](Documentation/Sections%201.0-4.0/Section%202/2.3%20AD%20structure%20proof_Marina.png)

This screenshot shows Marina Garcia placed inside the HR organizational unit.


* Security Groups Proof

![Security Groups Proof](Documentation/Sections%201.0-4.0/Section%202/2.4%20Group%20proof.png)

This screenshot shows the security groups created for Accounting, HR, and IT.

---

# 3.0 Shared Folders and NTFS Permissions


This section documents the shared folder structure and access control configuration.

* Shared Folder Structure

![Shared Folder Structure](Documentation/Sections%201.0-4.0/Section%203/3.1%20Shared%20folder%20structure.png)

This screenshot shows the CompanyShares folder with separate Accounting, HR, and IT folders.


* Network Share Path

![CompanyShares Network Share Path](Documentation/Sections%201.0-4.0/Section%203/3.2%20Share%20path.png)

This screenshot shows the network share path: \\DC01\CompanyShares.


* IT Folder NTFS Permissions

![IT Folder NTFS Permissions](Documentation/Sections%201.0-4.0/Section%203/3.3%20NTFS%20permissions%20for%20Accounting%20(3).png)

This screenshot shows NTFS permissions applied to the IT folder using the IT_Users security group.


* HR Folder NTFS Permissions

![HR Folder NTFS Permissions](Documentation/Sections%201.0-4.0/Section%203/3.3%20NTFS%20permissions%20for%20HR%20(1).png)

This screenshot shows NTFS permissions applied to the HR folder using the HR_Users security group.


* Accounting Folder NTFS Permissions

![Accounting Folder NTFS Permissions](Documentation/Sections%201.0-4.0/Section%203/3.3%20NTFS%20permissions%20for%20IT.png)

This screenshot shows NTFS permissions applied to the Accounting folder using the Accounting_Users security group.

---

### 4.0 Client Testing


This section documents the Windows 10 client testing.

* Client Can Reach the Domain Controller

![Client Can Reach Domain Controller](Documentation/Sections%201.0-4.0/Section%204/4.1%20Client%20can%20reach%20the%20domain%20controller.png)

This screenshot shows the Windows 10 client successfully pinging the domain controller.


* Client Joined to the Domain

![Client01 Joined to Domain](Documentation/Sections%201.0-4.0/Section%204/4.2%20Client01%20is%20joined%20to%20the%20domain.png)

This screenshot shows CLIENT01 joined to the homelab.local domain.


* Access Works for Correct User

![Access Works for Correct User](Documentation/Sections%201.0-4.0/Section%204/4.3%20Access%20works%20for%20the%20correct%20user.png)

This screenshot shows a domain user successfully accessing the correct department folder.


* Blocked Access for Wrong Folder

![Blocked Access for Wrong Folder](Documentation/Sections%201.0-4.0/Section%204/4.4%20Blocked%20access%20for%20the%20wrong%20folder.png)

This screenshot shows Windows denying access when the user tries to open an unauthorized department folder.


* File Creation Test

![File Creation Test](Documentation/Sections%201.0-4.0/Section%204/4.5%20File%20creation%20test.png)

This screenshot shows the user creating or editing a test file inside the allowed department folder.



## Result

The lab successfully simulates a small company Active Directory environment. Domain users can log into the Windows 10 client and access only the department folders assigned to their security groups.

Section descriptions:

## 1.0 Lab Environment

This section shows the virtual lab setup. I used VirtualBox with two VMs: a Windows Server 2022 domain controller and a Windows 10 Pro client workstation.

## 2.0 Server and Active Directory Setup

This section shows the server configuration. DC01 was set up as the domain controller for `homelab.local`, with Active Directory and DNS installed. I also created OUs, users, and security groups for IT, HR, and Accounting.

## 3.0 Shared Folders and Permissions

This section shows the shared folder setup. I created `\\DC01\CompanyShares` with separate folders for IT, HR, and Accounting. Access was controlled using AD security groups and NTFS permissions.

## 4.0 Client Testing

This section shows the Windows 10 client joined to the domain. I tested domain login, DNS connectivity, and folder access to confirm users could only open the department folders they were assigned to.
