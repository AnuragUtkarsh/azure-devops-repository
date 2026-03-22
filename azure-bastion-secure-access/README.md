# Azure Bastion – Secure SSH Without Public IP

## 📌 Project Overview

This project demonstrates how to securely access an Azure Virtual Machine using **Azure Bastion** without exposing the VM to the internet through a public IP address.

Azure Bastion provides **browser-based SSH/RDP connectivity** directly from the Azure portal, improving security by eliminating the need for public IP exposure.

---

## 🛠 Services Used

* Microsoft Azure
* Azure Bastion
* Azure Virtual Machine
* Azure Virtual Network

---

## 🏗 Architecture

User Laptop
↓
Azure Portal
↓
Azure Bastion (Public Endpoint)
↓
Private Virtual Machine (10.0.0.4)

---

## ⚙️ Steps Performed

1. Created an Azure Virtual Machine
2. Removed the VM public IP address
3. Created a dedicated Bastion subnet **AzureBastionSubnet**
4. Deployed Azure Bastion in the virtual network
5. Connected to the private VM using Bastion SSH from the Azure portal

---

## 🔐 Security Benefit

Azure Bastion improves security by:

* Removing the need for public IP addresses
* Preventing direct SSH/RDP exposure to the internet
* Enabling secure access via the Azure portal

---

## 📸 Screenshots


---

## 🎯 Learning Outcome

* Learned how Azure Bastion works
* Implemented secure VM access without public IP
* Understood Azure networking and private connectivity
* Practiced cloud security best practices

---

## 🚀 Author
Anurag Utkarsh
Cloud Infrastructure Practice Project
Azure Networking & Security
