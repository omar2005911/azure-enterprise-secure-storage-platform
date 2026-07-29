# Azure Enterprise Secure Storage Platform

> A production-style Azure Storage project demonstrating secure storage architecture using Microsoft Azure networking, identity, monitoring, governance, and security best practices.

![Azure Enterprise Secure Storage Platform](architecture/azure-storage-architecture1.png)

---

## 📖 Project Overview

The **Azure Enterprise Secure Storage Platform** is a production-style cloud project designed to demonstrate how to build, secure, monitor, and govern an enterprise Azure Storage environment using Microsoft Azure services and security best practices.

The project focuses on implementing a **private, identity-based storage architecture** that eliminates public exposure while providing secure administrative access, centralized monitoring, backup and recovery, governance, and threat protection.

Instead of deploying a basic Storage Account, this project simulates how an enterprise organization would design and secure critical business data in Azure.

---

## 🎯 Project Objectives

* Design a secure enterprise Azure Storage architecture.
* Eliminate public access using Azure Private Endpoint.
* Implement identity-based authorization with Microsoft Entra ID and Azure RBAC.
* Secure administrative access through Azure Bastion.
* Protect business data using backup and recovery features.
* Monitor storage activity with Azure Monitor and Log Analytics.
* Detect threats using Microsoft Defender for Storage.
* Enforce governance through Azure Policy and Resource Locks.
* Demonstrate Azure security best practices aligned with the AZ-104 certification.

---

## 🏢 Business Scenario

A company needs a secure cloud storage platform to host business documents and application data.

The solution must:

* Prevent direct public access to storage resources.
* Allow administrators to securely manage storage resources.
* Protect data against accidental deletion.
* Provide temporary, secure access for external users.
* Continuously monitor storage usage and activities.
* Detect suspicious or malicious behavior.
* Enforce organizational security policies.
* Support backup and recovery for critical data.

This project implements a secure Azure solution that satisfies all of these requirements.

---

## 🏗️ Solution Architecture

The solution is built using the following Azure services:

* Microsoft Entra ID
* Azure Storage Account
* Azure Blob Storage
* Azure File Share
* Azure Virtual Network (VNet)
* Azure Bastion
* Azure Virtual Machine
* Azure Private Endpoint
* Azure Private DNS Zone
* Azure RBAC
* Managed Identity
* Azure Backup
* Recovery Services Vault
* Azure Monitor
* Log Analytics Workspace
* Microsoft Defender for Storage
* Azure Policy
* Azure Resource Lock

## 🚀 Azure Services Implementation

This project integrates multiple Azure services to build a secure, enterprise-ready storage platform.

| Azure Service                      | Purpose                                                                                                 |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------- |
| **Azure Storage Account**          | Central storage service for enterprise data.                                                            |
| **Azure Blob Storage**             | Stores unstructured data such as documents, images, and application files.                              |
| **Azure File Share**               | Provides SMB-based shared file storage.                                                                 |
| **Azure Virtual Network (VNet)**   | Isolates network resources and enables private communication.                                           |
| **Azure Private Endpoint**         | Provides secure private connectivity to the Storage Account without exposing it to the public internet. |
| **Azure Private DNS Zone**         | Resolves the Storage Account's private endpoint using private IP addresses.                             |
| **Azure Bastion**                  | Enables secure browser-based RDP access to the management VM without assigning a public IP.             |
| **Azure Virtual Machine**          | Acts as the secure management workstation for administering the Storage Account.                        |
| **Microsoft Entra ID**             | Provides centralized authentication and identity management.                                            |
| **Azure RBAC**                     | Implements least-privilege authorization for users, groups, and managed identities.                     |
| **Managed Identity**               | Allows the VM to securely access Azure resources without storing credentials.                           |
| **Azure Backup**                   | Protects Azure File Share data through scheduled backups.                                               |
| **Recovery Services Vault**        | Stores and manages backup and recovery points.                                                          |
| **Azure Monitor**                  | Collects metrics and diagnostic data from Azure resources.                                              |
| **Log Analytics Workspace**        | Centralizes log collection and enables operational monitoring.                                          |
| **Microsoft Defender for Storage** | Detects suspicious activities and enhances storage security posture.                                    |
| **Azure Policy**                   | Enforces organizational security and compliance requirements.                                           |
| **Azure Resource Lock**            | Prevents accidental deletion of critical resources using a CanNotDelete lock.                           |
| **Shared Access Signature (SAS)**  | Grants secure, time-limited access to storage resources without exposing account keys.                  |

## 🛡️ Security Implementation

Security was the primary focus throughout this project. Multiple Azure security features were implemented to build a production-ready storage environment following Microsoft's recommended best practices.

### Network Security

* Public Network Access disabled for the Storage Account.
* Azure Private Endpoint configured to provide private connectivity.
* Azure Private DNS Zone integrated for private name resolution.
* Azure Virtual Network (VNet) used to isolate resources.
* Network Security Group (NSG) applied to the virtual machine subnet.
* Azure Bastion deployed to provide secure browser-based RDP access without exposing the VM to the public internet.

### Identity & Access Security

* Microsoft Entra ID used for centralized authentication.
* Azure Role-Based Access Control (RBAC) implemented using the principle of least privilege.
* System Assigned Managed Identity enabled for the management virtual machine.
* Shared Access Signature (SAS) configured to provide secure, time-limited access to Blob Storage.

### Storage Security

* Secure Transfer Required (HTTPS only) enabled.
* Minimum TLS version set to 1.2.
* Encryption at rest enabled.
* Anonymous public access disabled.

### Threat Protection

* Microsoft Defender for Storage enabled to detect suspicious activities and enhance the security posture of the Storage Account.

### Governance

* Azure Policy assigned to enforce:

  * Disable Public Network Access
  * Require Secure Transfer (HTTPS)
  * Enforce Minimum TLS Version 1.2

* Azure Resource Lock (CanNotDelete) applied to prevent accidental deletion of the Storage Account.

## 💾 Data Protection & Backup

To ensure business continuity and protect against accidental deletion or data loss, multiple Azure data protection features were implemented.

### Blob Storage Protection

The following protection mechanisms were enabled for Azure Blob Storage:

* Blob Soft Delete
* Container Soft Delete
* Blob Versioning
* Blob Change Feed

These features allow deleted or modified data to be recovered while maintaining a complete history of blob changes.

### Lifecycle Management

Azure Storage Lifecycle Management was configured to automatically manage blob data throughout its lifecycle. This helps optimize storage costs by applying automated actions based on predefined rules.

### Azure File Share Backup

Azure Backup was configured to protect the Azure File Share.

The backup solution includes:

* Recovery Services Vault
* Backup Policy
* Recovery Points
* On-demand Backup

This provides reliable recovery options in the event of accidental deletion, corruption, or other data loss scenarios.

## 📊 Monitoring & Alerting

The monitoring solution includes:

* Azure Monitor
* Diagnostic Settings
* Log Analytics Workspace
* Storage Metrics
* Storage Logs
* Metric Alert Rule
* Action Group
* Email Notification

---

## 🏛️ Governance & Compliance

The following governance controls were implemented:

* Azure Policy

  * Disable Public Network Access
  * Require Secure Transfer (HTTPS)
  * Enforce Minimum TLS Version 1.2
* Azure Resource Lock (CanNotDelete)

---

## 🧪 Validation & Testing

The following scenarios were successfully validated:

* Private Endpoint connectivity
* Azure Bastion remote access
* Microsoft Entra ID authentication
* RBAC authorization
* Managed Identity access
* SAS token access
* Azure File Share backup
* Azure Monitor alert generation
* Azure Policy compliance
* Resource Lock protection

---

## 📸 Screenshots

| Feature                        | Screenshot |
| ------------------------------ | ---------- |
| Architecture Diagram           | ✅          |
| Storage Account                | ✅          |
| Private Endpoint               | ✅          |
| Azure Bastion                  | ✅          |
| Managed Identity               | ✅          |
| RBAC                           | ✅          |
| Blob Protection                | ✅          |
| Azure Backup                   | ✅          |
| Microsoft Defender for Storage | ✅          |
| Azure Policy                   | ✅          |
| Azure Monitor Alert            | ✅          |
| Resource Lock                  | ✅          |

---

## 🛠️ Skills Demonstrated

* Azure Storage
* Azure Networking
* Azure Security
* Microsoft Entra ID
* Azure RBAC
* Managed Identity
* Azure Private Link
* Azure Backup
* Azure Monitor
* Microsoft Defender for Storage
* Azure Policy
* Azure Governance

---

## 📚 References

* Microsoft Learn
* Azure Architecture Center
* Azure Well-Architected Framework
