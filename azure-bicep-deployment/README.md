# Azure Infrastructure Deployment using Bicep

## Project Overview

This project demonstrates how to deploy Azure infrastructure using **Bicep**, a modern Infrastructure as Code (IaC) language developed by Microsoft.

Instead of creating resources manually in the Azure portal, infrastructure is defined as code and deployed using the **Azure CLI**.

---

# Architecture

Developer
↓
Bicep Template
↓
Azure Resource Manager
↓
Azure Resource Deployment

---

# Services Used

| Service                | Purpose                          |
| ---------------------- | -------------------------------- |
| Azure Resource Manager | Infrastructure deployment engine |
| Azure Bicep            | Infrastructure as Code language  |
| Azure Storage Account  | Example deployed resource        |

---

# Resource Deployed

| Resource        | Type      |
| --------------- | --------- |
| Storage Account | StorageV2 |

---

# Bicep Template

```bicep
param storageAccountName string = 'bicepstor${uniqueString(resourceGroup().id)}'

resource storageAccount 'Microsoft.Storage/storageAccounts@2023-01-01' = {
  name: storageAccountName
  location: resourceGroup().location
  sku: {
    name: 'Standard_LRS'
  }
  kind: 'StorageV2'
  properties: {
    accessTier: 'Hot'
  }
}
```

---

# Deployment Command

```bash
az deployment group create \
--resource-group bicep-demo-rg \
--template-file main.bicep
```

---

# Result

The Bicep template successfully deployed a **Storage Account** in Azure using Infrastructure as Code.

---

# Key Learning

* Infrastructure as Code with Azure Bicep
* Azure CLI resource deployment
* Automated cloud infrastructure provisioning
* Azure Resource Manager architecture

---

# Author

Anurag
Linux Engineer | Cloud & DevOps Learning
