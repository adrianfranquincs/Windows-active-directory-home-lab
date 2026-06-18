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

## Screenshots

1.0 Lab Environment

This section shows the VirtualBox lab environment with the Windows Server 2022 domain controller and Windows 10 client VM.

![VirtualBox Manager Showing Both VMs](Documentation/Sections%201.0-4.0/Section%201/VirtualBox%20Manager%20showing%20both%20VMs.png)

![Server VM Network Settings Adapter 1](Documentation/Sections%201.0-4.0/Section%201/Server%20VM%20network%20settings%20Adapter%201.png)

![Server VM Network Settings Adapter 2](Documentation/Sections%201.0-4.0/Section%201/Server%20VM%20network%20settings%20Adapter%202.png)

![Client VM Network Settings Adapter 1](Documentation/Sections%201.0-4.0/Section%201/3.%20Client%20VM%20network%20settings%20Adapter%201.png)

![Client VM Network Settings Adapter 2](Documentation/Sections%201.0-4.0/Section%201/3.%20Client%20VM%20network%20settings%20Adapter%202.png)


2.0 Server and Active Directory Setup

This section shows DC01 configured as the domain controller for homelab.local, with Active Directory users, OUs, and security groups.

![Domain Controller Proof](Documentation/Sections%201.0-4.0/Section%202/2.1%20Domain%20controller%20proof.png)

![Domain Name Proof](Documentation/Sections%201.0-4.0/Section%202/2.2%20Domain%20name%20proof.png)

![AD Structure Proof Alex](Documentation/Sections%201.0-4.0/Section%202/2.3%20AD%20structure%20proof_Alex.png)

![AD Structure Proof John](Documentation/Sections%201.0-4.0/Section%202/2.3%20AD%20structure%20proof_John.png)

![AD Structure Proof Marina](Documentation/Sections%201.0-4.0/Section%202/2.3%20AD%20structure%20proof_Marina.png)

![Group Proof](Documentation/Sections%201.0-4.0/Section%202/2.4%20Group%20proof.png)


3.0 Shared Folders and Permissions

This section shows the shared folder structure and NTFS permissions configured for department-based access control.

![Shared Folder Structure](Documentation/Sections%201.0-4.0/Section%203/3.1%20Shared%20folder%20structure.png)

![Share Path](Documentation/Sections%201.0-4.0/Section%203/3.2%20Share%20path.png)

![NTFS Permissions for Accounting](Documentation/Sections%201.0-4.0/Section%203/3.3%20NTFS%20permissions%20for%20Accounting%20(3).png)

![NTFS Permissions for HR](Documentation/Sections%201.0-4.0/Section%203/3.3%20NTFS%20permissions%20for%20HR%20(1).png)

![NTFS Permissions for IT](Documentation/Sections%201.0-4.0/Section%203/3.3%20NTFS%20permissions%20for%20IT.png)

4.0 Client Testing

This section shows the Windows 10 client joined to the domain and verifies that users can access only the correct department folders.

![Client Can Reach Domain Controller](Documentation/Sections%201.0-4.0/Section%204/4.1%20Client%20can%20reach%20the%20domain%20controller.png)

![Client Joined to Domain](Documentation/Sections%201.0-4.0/Section%204/4.2%20Client01%20is%20joined%20to%20the%20domain.png)

![Access Works for Correct User](Documentation/Sections%201.0-4.0/Section%204/4.3%20Access%20works%20for%20the%20correct%20user.png)

![Blocked Access for Wrong Folder](Documentation/Sections%201.0-4.0/Section%204/4.4%20Blocked%20access%20for%20the%20wrong%20folder.png)

![File Creation Test](Documentation/Sections%201.0-4.0/Section%204/4.5%20File%20creation%20test.png)

1. VirtualBox lab VMs
2. DC01 server/domain information
3. Active Directory OU structure
4. Users inside department OUs
5. Security groups
6. Group membership example
7. CompanyShares folder structure
8. Network share path
9. Folder permissions
10. Client joined to domain
11. DNS/ping test
12. Allowed access test
13. Denied access test

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
