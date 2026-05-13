# Azure Active Directory: File Server Management & Security Groups Lab

![Azure](https://img.shields.io/badge/azure-%230072C6.svg?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Windows Server](https://img.shields.io/badge/Windows%20Server-0078D4?style=for-the-badge&logo=windows&logoColor=white)
![Active Directory](https://img.shields.io/badge/Active%20Directory-FFB900?style=for-the-badge&logo=windows&logoColor=black)
![Security](https://img.shields.io/badge/Security-Access%20Control-green?style=for-the-badge&logo=shield&logoColor=white)

---

## Introduction
This lab focuses on the implementation of **Network File Sharing** and **Role-Based Access Control (RBAC)** within a Windows-based enterprise environment. By configuring Shared Folder permissions and Active Directory Security Groups, this project demonstrates how to enforce the **Principle of Least Privilege (PoLP)**. Key objectives include managing NTFS and Share permissions, creating targeted security groups for departmental isolation (e.g., Accounting), and validating the impact of group membership changes on end-user access within an Azure-hosted domain.

---

## Technical Skills & Tools

* **Windows Server 2022:** Administering Shared Folders and NTFS permissions via File Explorer and Server Manager.
* **Active Directory Users and Computers (ADUC):** Provisioning Security Groups and managing user object memberships.
* **Access Control Management:** Implementing Role-Based Access Control (RBAC) to enforce data silos between departments.
* **Network Resource Discovery:** Utilizing the Universal Naming Convention (UNC) pathing (`\\DC-1\`) to map and test network shares.
* **Microsoft Azure:** Orchestrating communication between a Domain Controller (DC-1) and a Windows Client (Client-1) within a cloud-native Virtual Network.
---

## Part 1: Shared Resource Provisioning & Access Control
The first phase focused on establishing the infrastructure for network file sharing and defining the baseline security posture for various organizational folders. This demonstrates the practical application of NTFS and Share permissions to control data visibility.
* **Directory Creation:** Established a set of functional folders on the Domain Controller (DC-1) to simulate various access scenarios, including restricted, open-read, and departmental repositories.
* **Permission Mapping:** Configured specific access levels for "Domain Users" and "Domain Admins." This included verifying that users could read data in "read-access" but were restricted from making modifications, enforcing data integrity.
* **Infrastructure Verification:** Confirmed that the Domain Controller was successfully broadcasting these shares over the internal virtual network, making them discoverable via the Universal Naming Convention (UNC) path.

<p align="center">
  <img src="assets/ad-folder-sharing-permissions-config.png" height='500' width="800" alt="Folder Sharing and Permissions Configuration" />
</p>

---

## Part 2: Security Group Implementation & Departmental Isolation
The final phase demonstrated the power of **Role-Based Access Control (RBAC)** by creating a specific security group to manage departmental data access. This simulates the transition from generic "Domain User" access to restricted, job-specific permissions.
* **Security Group Provisioning:** Created the "ACCOUNTANTS" Security Group within Active Directory. This allows for administrative scalability, as permissions are managed at the group level rather than per individual user.
* **Membership Validation:** Conducted a "before-and-after" access test. Initially, the test user was denied access to the "accounting" share. After adding the user to the "ACCOUNTANTS" group on DC-1 and re-authenticating, access was successfully granted.
* **Access Auditing:** Verified that the user could now read and write to the departmental folder, confirming that the new security tokens were correctly issued by the Domain Controller upon the new login session.

<p align="center">
  <img src="assets/ad-group-members-validation.png" width="800" alt="Security Group Membership and Access Validation" />
</p>

---
