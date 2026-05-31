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

Add screenshots here in order:

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
