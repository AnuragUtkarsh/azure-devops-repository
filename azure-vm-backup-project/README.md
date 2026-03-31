# Azure VM Backup Project

## 📌 Project Overview
This project demonstrates how to configure automated backup for an Azure Virtual Machine using **Azure Backup** and **Recovery Services Vault**.

The goal of this project is to protect virtual machines from data loss by implementing a scheduled backup policy.

---

## 🛠 Services Used

- Azure Virtual Machine
- Azure Backup
- Recovery Services Vault
- Backup Policy

---

## 🏗 Architecture

User
   │
Azure Virtual Machine
   │
Azure Backup
   │
Recovery Services Vault

---

## ⚙️ Steps Performed

1. Created a Resource Group
2. Deployed an Azure Virtual Machine
3. Created a Recovery Services Vault
4. Enabled backup for the VM
5. Applied default backup policy
6. Triggered manual backup job

---

## 📊 Result

Backup was successfully configured for the Azure Virtual Machine.

- Backup policy applied
- Backup job executed
- VM protected in Recovery Services Vault

---
## Project Screenshots

### VM Overview

![VM Overview](images/overview-vm.png)

### Recovery Services Vault Overview

![Vault Overview](images/vault-overview.png)

### Vault Deployment

![Vault Deployment](images/vault-deployement.png)

### Backup Pre-checks

![Backup Prechecks](images/backup-prechecks.png)

### Backup Progress

![Backup Progress](images/backup-progess2.png)

### Backup Status

![Backup Status](images/backupstatus.png)

### File Uploaded to VM

![File Uploaded](images/file-uploaded.png)

### Deleted File Before Restore

![Deleted for Backup](images/deleted-for-backup.png)


## 🎯 Learning Outcome

- Learned how Azure Backup works
- Configured Recovery Services Vault
- Protected Azure VM using backup policies
- Triggered and monitored backup jobs
