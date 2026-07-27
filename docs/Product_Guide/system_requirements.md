# System requirements

---

Ensure that your environment meets the following requirements before installing Equify.

---

## Infrastructure

- Provision a minimum of 5 servers for low-to-medium traffic (100K to 1M messages per day).
- For this configuration, the data retention period is 35 days (mandatory).
- For high-volume deployments, provision 10 servers with distributed components.
- Use one of the following operating systems:

    - Rocky Linux 8.10
    - Windows Server 2025 (x64)

- Ensure that CPU, memory, and storage meet the required specifications for each server role.

---

## Server / VM requirements

Provision servers or virtual machines based on the following specifications:

| Purpose                       | Qty | CPU      | Memory | Disk Type | Disk Size (RAID 10) | OS                              |
|-------------------------------|-----|----------|--------|----------|---------------------|----------------------------------|
| Message Queue and Delivery Report Management   | 4   | 32 Core  | 64 GB  | SSD      | 1 TB                | Linux / Windows Server 2025 x64  |
| Middleware and Supporting Applications         | 2   | 32 Core  | 128 GB | SSD      | 1 TB                | Linux / Windows Server 2025 x64  |
| In/Out DB and Transaction Logger DB            | 2   | 32 Core  | 64 GB  | SSD      | 2 TB                | Linux / Windows Server 2025 x64  |
| Monitoring and Analytics                       | 2   | 32 Core  | 32 GB  | SSD      | 1 TB                | Linux / Windows Server 2025 x64  |

## Access requirements

#### Linux

- Sudo/root privileges for installing & config the Equify
- Required users & groups with restricted permissions (optional)
- Internet access or internal YUM mirror for package installation
- If required, Enable ports for applications/resources

#### Windows

- Admin privileges for installing & config the Equify
- Required users & groups with restricted permissions
- If required, Enable Firewall ports for applications/resources

---

## Software requirements

Install the following components:

- Java runtime: OpenJDK 21
- Application framework: Spring Boot 3.x

---

## Frontend requirements 

- Node.js 22.15.1 or later
- Equify GUI 10.9.2 or later

---

## Core components

- Kafka 4.0
- Redpanda 3.2.2
- MySQL 8.4
- ClickHouse 25.10.2.65
- Redis 8.0.3
- Vault 1.20.2
- Debezium plugin 3.2.0 (optional)

---

## Web and application servers

- Web Server: Nginx 1.14.1
- Application Server: Tomcat 10.x

---

## System Tools & Utilities

#### Required tools for Linux

yum-utils, epel-release, net-tools, sendmail, vim, wget, atop, htop, telnet, zip, iptraf-ng, traceroute, nano, rsync, sysstat, rpm, tcpdump, tar, java-21-openjdk-devel, jq, bc

#### Required tools for Windows

- NSSM for running Java/Kafka/Equify as a Windows service.
- Configure each service for automatic restart.
- Ensure proper user permissions (service account with Admin privileges for
startup, restricted rights for runtime).

---

## Domain Requirements

Four subdomains are required for below functionalities

- GUI
- Internal Data Base Configuration,
- Analytics
- Webhook to receive delivery reports.

---

## Identity Provider (IdP)

An IdP that supports OIDC is required.
Examples: Microsoft Entra ID (Azure AD), Okta, Key cloak, Auth0

---

## FTP Requirement

One FTP server for uploading the application JAR

Required below details:

- FTP Host/IP
- FTP Username & Password
- Folder with Read/Write access

---

## DLR API Requirement

- Webhook of Equify needs to be configured at Service Providers system to receive
- Delivery reports on Equify platform.

---

## Application Mapping (Linux/Windows)


Use the following mapping to understand how components are distributed across servers:

| S. No. | Hostname  | Applications and resources                                      |
|--------|-----------|------------------------------------------------------------------|
| 1      | Server-1  | Kafka-Node1, Redis-Node1                                        |
| 2      | Server-2  | Kafka-Node2, Redis-Node2                                        |
| 3      | Server-3  | Kafka-Node3, Redis-Node3                                        |
| 4      | Server-4  | Vault-Node1, ClickHouse-Node1                                   |
| 5      | Server-5  | Vault-Node2, ClickHouse-Node2                                   |
| 6      | Server-6  | Vault-Node3, MySQL (Master) DB, DB Config apps, UI              |
| 7      | Server-7  | MySQL (Slave) DB, DB Connector apps, DB Connector API apps      |
| 8      | Server-8  | DLR Webhook apps, DLR Processor microservices                   |
| 9      | Server-9  | Dispatcher apps                                                 |
| 10     | Server-10 | Middleware apps, Retry apps                                     |

---

## Pre-installation checklist

Complete the following checks before you begin the installation.

=== "Linux"

    Verify that the following requirements are met:

    - Provision 10 servers or virtual machines  
    - Verify hardware specifications  
    - Install Rocky Linux 8.10 with the latest kernel  
    - Install required system tools  
    - Install MySQL and ClickHouse  
    - Set up the Kafka cluster  
    - Configure the Redis high-availability (HA) cluster  
    - Install Node.js and GUI dependencies  
    - Install and configure Nginx  
    - Provide OIDC identity provider (IdP) details  
    - Provide FTP access  
    - Complete DLR API configuration  
    - Update BIOS and firmware  

=== "Windows"

    Verify that the following requirements are met:

    - Provision 10 servers or virtual machines  
    - Verify hardware specifications  
    - Install and patch Windows Server 2025 Datacenter  
    - Ensure required Windows system tools are available  
    - Install Java (OpenJDK 21 or 25)  
    - Configure the Kafka cluster (KRaft mode)  
    - Configure the Redis high-availability (HA) cluster  
    - Install MySQL  
    - Install ClickHouse  
    - Install Node.js and GUI dependencies (if applicable)  
    - Install and configure Nginx  
    - Provide OIDC identity provider (IdP) details  
    - Provide file transfer access (SMB or FTP, as applicable)  
    - Complete DLR API configuration  
    - Configure Windows Firewall rules  
    - Apply antivirus exclusions (Kafka and database data paths)  
    - Update BIOS and firmware  

---

## Network & Security Requirements

- **Firewall Rules / Ports**: Provide an explicit list of required inbound/outbound ports for
Kafka, Redis, MySQL, ClickHouse, Vault, and Nginx.
- **VLAN / Subnet details**: Specify network segmentation if the servers are deployed across separate networks (for example, DB
network vs application network).
- **SSL/TLS Requirements**: Configure certificates for Nginx and any inter-service
communication.

---

## Backup & Disaster Recovery

- Provision N+1 servers if you plan to implement a disaster recovery (DR) setup.
- Define backup frequency and retention policies for MySQL and ClickHouse.
- Define backup locations for application configurations (Vault and UI settings).
- Document recovery order for services and define failover procedures.

---

## What to do next

- Proceed with the [Installation guide](installation.md)
- Learn initial setup in [Getting started](getting_started.md)

<div class="home-support-banner">
  <div class="support-left">
    <h2 class="support-title">Need some help?</h2>
    <p class="support-desc">
      Communication at scale isn’t always simple. Get instant help from our
      <a href="https://equence.com/contact.html">support team</a>, or browse the
      <a href="../../faq/#faq">FAQ</a> for quick answers.
    </p>
    <div class="support-legal">
      <a href="https://equence.com/terms.html">Terms of service</a>
      <a href="https://equence.com/privacy-policy.html">Privacy Policy</a>
      <span>© 2026 Equify. All rights reserved.</span>
    </div>
  </div>
  <div class="support-right">
    <div class="support-icon-cluster">
      <div class="support-icon-bubble support-icon-bubble--1">🎧</div>
      <div class="support-icon-bubble support-icon-bubble--2">💬</div>
      <div class="support-icon-bubble support-icon-bubble--3">🛡️</div>
    </div>
  </div>
</div>