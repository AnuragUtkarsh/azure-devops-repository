# Azure Managed Identity with Key Vault Secret Access

## Project Overview

This project demonstrates how an **Azure Virtual Machine can securely retrieve secrets from Azure Key Vault using Managed Identity** without storing credentials such as passwords, client secrets, or API keys.

Managed Identity allows Azure resources to authenticate to Azure services through **Azure Active Directory (Azure AD)** automatically.

---

## Architecture

```id="archkv1"
Azure Virtual Machine
        │
        │ System Assigned Managed Identity
        ▼
Azure Active Directory (Token Issuance)
        │
        ▼
Azure Key Vault
        │
        ▼
Secret Retrieval
```

---

## Services Used

| Service               | Purpose                                    |
| --------------------- | ------------------------------------------ |
| Azure Virtual Machine | Compute resource used to access the secret |
| Managed Identity      | Provides secure identity for the VM        |
| Azure Key Vault       | Secure storage for secrets                 |
| Azure RBAC            | Authorization to allow secret access       |

---

## Resource Details

| Resource        | Name             |
| --------------- | ---------------- |
| Resource Group  | identity-rg      |
| Virtual Machine | identity-vm      |
| Key Vault       | identity-demo-kv |
| Secret          | demo-secret      |

---

## Step 1: Create Virtual Machine

A Linux VM was created and **System Assigned Managed Identity** was enabled.

Portal Path:

```id="kvstep1"
Virtual Machine
→ Identity
→ System Assigned
→ ON
```

---

## Step 2: Create Azure Key Vault

A Key Vault was deployed to securely store application secrets.

Configuration:

```id="kvstep2"
Name: identity-demo-kv
Region: Central India
Pricing Tier: Standard
```

---

## Step 3: Create Secret in Key Vault

Secret created:

```id="kvstep3"
Secret Name: demo-secret
Secret Value: helloanurag
```

Portal Path:

```id="kvstep3b"
Key Vault
→ Secrets
→ Generate / Import
```

---

## Step 4: Assign RBAC Permission

The VM Managed Identity was granted permission to access secrets.

Role assigned:

```id="kvstep4"
Key Vault Secrets User
```

Portal Path:

```id="kvstep4b"
Key Vault
→ Access Control (IAM)
→ Add Role Assignment
```

---

## Step 5: Generate Managed Identity Token

From inside the VM, an Azure AD access token was generated using the **Instance Metadata Service**.

```bash id="kvstep5"
TOKEN=$(curl -H Metadata:true \
"http://169.254.169.254/metadata/identity/oauth2/token?api-version=2018-02-01&resource=https://vault.azure.net" \
| jq -r '.access_token')
```

---

## Step 6: Retrieve Secret from Key Vault

```bash id="kvstep6"
curl https://identity-demo-kv.vault.azure.net/secrets/demo-secret?api-version=7.3 \
-H "Authorization: Bearer $TOKEN"
```

---

## Output

```json id="kvstep7"
"value": "helloanurag"
```

The VM successfully retrieved the secret from Azure Key Vault using Managed Identity authentication.

---

## Key Security Benefits

* No credentials stored in application code
* Automatic authentication via Azure AD
* Secure secret storage using Azure Key Vault
* Access controlled using Azure RBAC

---

## Learning Outcome

Through this project, the following Azure concepts were implemented:

* Managed Identity Authentication
* Azure AD Token Generation
* Azure Key Vault Secret Management
* RBAC Authorization
* Secure Secret Retrieval from Virtual Machines

---

## Screenshots

(images/Key-vaultoutput.png)

---

## Author

Anurag
Linux Engineer | Cloud & DevOps Enthusiast
