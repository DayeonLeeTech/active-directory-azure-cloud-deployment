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
