# Azure DNS A Record Configuration

## 📌 Project Overview

This project demonstrates how to configure **Azure DNS** and map a Virtual Machine's public IP address to a custom hostname using an **A record**.

The objective of this project is to understand how DNS zones work in Azure and how hostname-based access can be configured for cloud resources.

---

## 🛠 Services Used

* Microsoft Azure
* Azure DNS
* Azure Virtual Machine
* Linux (Ubuntu)

---

## 🏗 Architecture

Client
↓
Azure DNS Zone
↓
A Record Mapping
↓
Azure Virtual Machine

---

## ⚙️ Steps Performed

1. Created an Azure DNS Zone
2. Configured an **A Record** in the DNS zone
3. Mapped the VM public IP address to the DNS hostname
4. Verified DNS resolution using `nslookup`
5. Validated connectivity to the VM

---

## 🌐 DNS Configuration

DNS Zone:
cloudlabdemo123.xyz

Record Type:
A Record

Hostname:
backup-test-vm.cloudlabdemo123.xyz

Public IP:
20.235.202.166

---

## 🧪 DNS Resolution Test

```bash
nslookup backup-test-vm.cloudlabdemo123.xyz ns1-05.azure-dns.com
```

Expected Output:

```
Name: backup-test-vm.cloudlabdemo123.xyz
Address: 20.235.202.166
```

---

## 📸 Screenshots

---

## 🎯 Learning Outcome

* Understood Azure DNS zone configuration
* Learned how A records map hostnames to IP addresses
* Tested DNS resolution using authoritative name servers
* Practiced cloud networking fundamentals

---

## 🚀 Author

Anurag Utkarsh
Cloud & Linux Practice Project
Azure Networking Fundamentals
