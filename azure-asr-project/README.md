# 🚀 Azure Site Recovery (ASR) – Disaster Recovery Project

## 📌 Project Overview

This project demonstrates how to implement **Disaster Recovery (DR)** in Azure using **Azure Site Recovery (ASR)**.
A virtual machine is replicated from one region to another to ensure business continuity during failures.

---

## 🎯 Objective

* Configure cross-region disaster recovery
* Replicate VM from **Central India → Southeast Asia**
* Perform **Test Failover** without impacting production
* Validate DR readiness

---

## 🏗️ Architecture

This project follows a **cross-region disaster recovery architecture** using Azure Site Recovery:

* **Source Region:** Central India

  * Virtual Machine (Ubuntu 22.04)
  * Running application (Nginx)

* **Target Region:** Southeast Asia

  * Replica VM created during failover
  * Separate Virtual Network for isolation

* **Recovery Services Vault (Southeast Asia):**

  * Manages replication and failover
  * Stores replication metadata and policies

* **Replication Flow:**

  * Data continuously replicated from source VM to target region
  * Recovery points maintained (RPO based)

* **Failover Process:**

  * Test Failover creates a temporary VM in target region
  * Actual Failover switches production to target region

### 🔁 Flow Summary

Source VM (Central India)
↓
Azure Site Recovery (Vault - Southeast Asia)
↓
Replica VM (Southeast Asia)

### 🎯 Key Design Highlights

* Cross-region high availability
* No downtime testing using Test Failover
* Isolated failover network
* Cost optimization using cleanup

---

## ⚙️ Technologies Used

* Microsoft Azure
* Azure Virtual Machines
* Azure Site Recovery (ASR)
* Recovery Services Vault

---

## 🪜 Implementation Steps

### 1. Create Source VM

* OS: Ubuntu 22.04 LTS
* Region: Central India

### 2. Create Recovery Services Vault

* Region: Southeast Asia

### 3. Enable Replication

* Source: Central India VM
* Target: Southeast Asia

### 4. Configure Replication

* Target Resource Group
* Virtual Network
* Replication Policy

### 5. Verify Replication

* Status: **Protected**
* Health: **Healthy**
* RPO monitored

### 6. Perform Test Failover

* Validate VM boot in target region
* Ensure application availability

### 7. Cleanup Test Failover

* Remove test resources to avoid cost

---

## 📸 Screenshots



## 🧠 Key Learnings

* Difference between **Failover vs Test Failover**
* Importance of **cross-region DR**
* Understanding **RPO (Recovery Point Objective)**
* Azure automation in DR setup
* Cost management with cleanup

---

## 🔥 Real-World Use Case

Organizations use ASR to:

* Ensure high availability
* Recover from region outages
* Maintain business continuity

---

## ⚠️ Important Notes

* Source and target regions must be different
* Supported OS is required for replication
* Cleanup is necessary to avoid extra costs

---

## 🚀 Future Enhancements

* Automate failover using runbooks
* Add monitoring and alerts
* Implement multi-VM replication

---

## 👨‍💻 Author

Anurag Utkarsh
Azure | Linux | DevOps Engineer 🚀
