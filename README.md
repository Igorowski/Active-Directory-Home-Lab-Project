# Active Directory Home Lab Project

## Overview

This project demonstrates the deployment of a basic enterprise-style Active Directory environment using Oracle VirtualBox. The lab was designed to simulate a small business network infrastructure with centralized user management, DHCP services, NAT/Routing configuration, and domain-joined client machines.

The environment was built to strengthen practical IT Support and System Administration skills relevant to Helpdesk and Junior IT roles.

---

# Technologies Used

* Windows Server 2019
* Windows 10 Pro
* Oracle VirtualBox
* Active Directory Domain Services (AD DS)
* DHCP Server
* Routing and Remote Access (NAT)
* PowerShell

---

# Environment Architecture

## Virtual Machines

| Machine | Operating System    | Purpose                        |
| ------- | ------------------- | ------------------------------ |
| DC      | Windows Server 2019 | Domain Controller / DHCP / NAT |
| CLIENT1 | Windows 10 Pro      | Domain-Joined Client           |

## Network Configuration

* External Adapter (NAT) — Internet Access
* Internal Adapter — Internal Lab Network
* Domain Name: `mydomain.com`

---

# Lab Topology

<img width="1300" height="1000" alt="ADDS2" src="https://github.com/user-attachments/assets/a5337783-f8b2-4282-8e09-fd8f09d5b0ac" />

---

# Project Objectives

* Deploy and configure Active Directory Domain Services
* Create and manage domain users and groups
* Configure DHCP services for internal clients
* Configure NAT/Routing for internet access
* Join Windows 10 client machine to the domain
* Practice basic IT administration and troubleshooting tasks

---

# Domain Controller Setup

## Creating the Domain Controller VM

A Windows Server 2019 virtual machine was created in Oracle VirtualBox with:

* Allocated CPU, RAM, and storage resources
* NAT adapter for external connectivity
* Internal adapter for lab communication

<img width="523" height="366" alt="image" src="https://github.com/user-attachments/assets/fdfacfab-d433-4ef9-a5c7-7209e5ea265d" />

<img width="824" height="310" alt="image" src="https://github.com/user-attachments/assets/1ca4ae9f-4806-4a05-8d16-90dd66cf61b5" />

<img width="829" height="311" alt="image" src="https://github.com/user-attachments/assets/4321c67a-0401-4e31-b30e-cdedbf8fd0d5" />

---

## Installing Windows Server 2019

Windows Server 2019 Desktop Experience edition was installed to provide a graphical management interface.

<img width="698" height="512" alt="image" src="https://github.com/user-attachments/assets/73640174-fa92-423b-b44b-bd7163f3f53b" />

Guest Additions were also installed to improve virtual machine usability and performance.

<img width="302" height="239" alt="image" src="https://github.com/user-attachments/assets/bfa76d97-300b-42e4-b35a-a07f8a74ea6c" />

---

# Network Configuration

The Domain Controller was configured with:

* One external adapter connected to the home network
* One internal adapter for client communication
* Static internal IP addressing
* DNS configured to point to itself

<img width="517" height="72" alt="image" src="https://github.com/user-attachments/assets/835e2b80-5c64-4bb2-90f4-7691f52ff2d8" />

<img width="399" height="450" alt="image" src="https://github.com/user-attachments/assets/0e23b773-a073-4708-88fa-212f8db4d9a3" />

---

# Active Directory Deployment

Active Directory Domain Services were installed using Server Manager.

The server was promoted to a Domain Controller with a newly created forest:

`mydomain.com`

<img width="476" height="320" alt="image" src="https://github.com/user-attachments/assets/2a8099a4-c562-4114-962d-d3556077e6d4" />

<img width="788" height="566" alt="image" src="https://github.com/user-attachments/assets/be926e0f-249a-4d64-afd9-2cae40e17895" />

<img width="597" height="480" alt="image" src="https://github.com/user-attachments/assets/d83d8132-8d97-495d-ab7d-6c7ea6d9279d" />

<img width="416" height="442" alt="image" src="https://github.com/user-attachments/assets/98369db4-10e4-4fee-9b1d-d904a247759d" />

<img width="572" height="562" alt="image" src="https://github.com/user-attachments/assets/5d1c0d8d-42b6-4364-b29e-7f33c1611fc4" />

---

# User and Organizational Unit Management

An Organizational Unit (OU) structure was created for administrative organization.

A domain administrator account was created and assigned to the `Domain Admins` group.

<img width="787" height="590" alt="image" src="https://github.com/user-attachments/assets/af48d62f-84d9-42e7-ac1e-f8a6c70b32c1" />

<img width="754" height="527" alt="image" src="https://github.com/user-attachments/assets/c2bc333b-8457-4f3a-9438-bee077e646a2" />

The administrator account was successfully used to authenticate into the domain environment.

<img width="499" height="623" alt="image" src="https://github.com/user-attachments/assets/bd179b22-1209-460a-ae90-93f6d06cd99d" />

---

# NAT and Routing Configuration

Routing and Remote Access Services (RRAS) were configured to provide internet access for internal lab clients.

NAT was enabled using the public-facing network adapter.

<img width="778" height="560" alt="image" src="https://github.com/user-attachments/assets/b9acb4de-308f-4d20-8a6f-c126d90870fd" />

---

# DHCP Configuration

A DHCP scope was configured to dynamically assign IP addresses to client machines within the internal network.

DHCP Scope:

* Range: `172.16.0.100 - 172.16.0.200`

<img width="1093" height="615" alt="image" src="https://github.com/user-attachments/assets/3f1a4e5c-33b6-44ab-b44f-10c48dcc399a" />

<img width="519" height="424" alt="image" src="https://github.com/user-attachments/assets/3cfbfc1d-9648-40ee-ba39-c3847399b8b3" />

<img width="515" height="424" alt="image" src="https://github.com/user-attachments/assets/d4c221d7-5617-4c4c-af9f-d83462ec795c" />

After configuration, the DHCP server was authorized and verified.

<img width="395" height="355" alt="image" src="https://github.com/user-attachments/assets/932f93a9-e459-459e-80e6-48c63759c5f8" />

---

# PowerShell Automation

For demonstration purposes, a PowerShell script was used to automate bulk user creation.

The script imported user data from a text file and generated multiple Active Directory accounts automatically.

<img width="1341" height="627" alt="image" src="https://github.com/user-attachments/assets/28828519-5995-45cb-b08f-d873516de5aa" />

<img width="801" height="731" alt="image" src="https://github.com/user-attachments/assets/1fa077eb-fd9f-422a-8bbe-18d9f931d546" />

This demonstrated:

* Basic PowerShell administration
* Bulk user provisioning
* Active Directory automation workflows

---

# Client Machine Deployment

A Windows 10 client virtual machine was created and connected to the internal network.

The client machine was:

* Renamed
* Joined to the domain
* Assigned an IP address via DHCP

<img width="1160" height="868" alt="image" src="https://github.com/user-attachments/assets/dc5210be-b9fb-4066-b219-521d57d60a0a" />

<img width="956" height="518" alt="image" src="https://github.com/user-attachments/assets/22929758-739f-460c-816d-9135638140bf" />

<img width="1049" height="831" alt="image" src="https://github.com/user-attachments/assets/c3eb84ae-85bf-4ce8-9f33-f66fce53255a" />

---

# DHCP Lease Verification

The client lease was successfully visible within the DHCP management console.

<img width="743" height="526" alt="image" src="https://github.com/user-attachments/assets/b6e9cf55-0e7f-49e0-9fa2-9f3295f85db7" />

<img width="1031" height="703" alt="image" src="https://github.com/user-attachments/assets/dd617cec-2b39-4431-90dd-47800639f765" />

The domain user account was successfully able to authenticate on the client machine.

---

# Troubleshooting and Challenges

During the lab deployment several issues were encountered and resolved:

| Issue                               | Resolution                                      |
| ----------------------------------- | ----------------------------------------------- |
| NAT configuration option greyed out | Restarted RRAS service and VM                   |
| Internal/External adapter confusion | Verified adapters using IPv4 addressing         |
| PowerShell execution restrictions   | Modified execution policy temporarily           |
| Client domain join issues           | Verified DNS and internal adapter configuration |

---

# Skills Demonstrated

* Active Directory Administration
* User and Group Management
* DHCP Configuration
* NAT/Routing Configuration
* Windows Server Administration
* Windows 10 Client Administration
* Virtualization with Oracle VirtualBox
* Basic PowerShell Automation
* Network Troubleshooting
* Domain Management

---

# Future Improvements

Planned improvements for this environment:

* Group Policy Objects (GPO)
* Shared folders and permissions
* File server deployment
* Remote Desktop administration
* Security hardening
* Additional client machines

---

# References

## Video Resources

* [https://youtu.be/MHsI8hJmggI](https://youtu.be/MHsI8hJmggI)
* [https://youtu.be/85-bp7XxWDQ](https://youtu.be/85-bp7XxWDQ)

Special thanks to:

* Andy Malone MVP
* Josh Madakor

Their educational content was used as guidance while building this lab environment.
