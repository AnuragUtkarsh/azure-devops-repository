# Azure Private Endpoint Project

## Project Overview

This project demonstrates how to secure Azure Storage by using **Azure Private Endpoint**.

Private Endpoints allow Azure resources to be accessed **privately through a Virtual Network instead of the public internet**. This improves security by preventing direct internet exposure.

In this project, a Storage Account was connected to a Virtual Network using a Private Endpoint and verified through DNS resolution and connectivity tests.

---

# Architecture

Client VM (Virtual Network)
↓
Private Endpoint (Private IP)
↓
Azure Storage Account

Public Internet Access → Blocked

---

# Azure Services Used

| Service               | Purpose                     |
| --------------------- | --------------------------- |
| Azure Storage Account | Object storage service      |
| Virtual Network       | Private network environment |
| Private Endpoint      | Secure private connectivity |
| Private DNS Zone      | Internal DNS resolution     |

---

# Resources Created

| Resource         | Name                              |
| ---------------- | --------------------------------- |
| Resource Group   | private-endpoint-rg               |
| Storage Account  | anuragaccount01                   |
| Virtual Machine  | storage-private-vm01              |
| Virtual Network  | monitor-vm-vnet                   |
| Private Endpoint | storage-private-endpoint          |
| Private DNS Zone | privatelink.blob.core.windows.net |

---

# Implementation Steps

## 1 Disable Public Network Access

Public network access was disabled on the storage account to prevent direct internet access.

---

## 2 Create Private Endpoint

A private endpoint was created connecting the storage account to the virtual network subnet.

---

## 3 Configure Private DNS

Azure automatically created a Private DNS zone to resolve the storage account endpoint to a private IP address.

---

## 4 Verify DNS Resolution

From the VM inside the VNet:

```bash
nslookup anuragaccount01.blob.core.windows.net
```

Output resolved to a private IP address.

---

## 5 Test Connectivity

Connectivity to the storage endpoint was tested using:

```bash
curl -I https://anuragaccount01.blob.core.windows.net
```

---

# Screenshots



---

# Learning Outcomes

This project demonstrates:

* Azure Private Endpoint configuration
* Private DNS integration
* Secure storage access without public exposure
* VNet-based service connectivity

---

# Author

Anurag
Linux Engineer | Cloud & DevOps Learner
