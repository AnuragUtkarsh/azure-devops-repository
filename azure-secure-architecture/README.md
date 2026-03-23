# Azure Secure Architecture Lab

This project demonstrates a **secure Azure cloud architecture** using multiple Azure services such as Application Gateway, Virtual Network, Key Vault, Managed Identity, Private Endpoint, and Storage Account.

The goal of this project is to design a **secure, production-style architecture** where sensitive resources are protected using identity-based authentication and private networking.

---

# Architecture Overview

This architecture includes the following components:

* Azure Application Gateway (Layer-7 Load Balancer)
* Backend Linux Virtual Machine
* Azure Key Vault for secret management
* Azure Storage Account
* Private Endpoint
* Virtual Network with multiple subnets
* Managed Identity authentication
* Private DNS resolution

The design ensures that **sensitive resources are not exposed to the public internet**.

---

# Architecture Diagram

![Architecture Diagram](architecture-diagram.png)

---

# Project Components

## 1. Azure Application Gateway

Application Gateway is used as a **Layer-7 load balancer** to route incoming HTTP traffic to backend servers.

Features used in this project:

* HTTP Listener
* Backend Pool
* Routing Rules
* Public IP frontend

Application Gateway securely manages and forwards client traffic to backend servers inside the Virtual Network.

---

## 2. Virtual Network

A Virtual Network was created to isolate all infrastructure resources.

Subnets created:

| Subnet Name    | Purpose             |
| -------------- | ------------------- |
| appgw-subnet   | Application Gateway |
| backend-subnet | Backend VM          |

Network segmentation helps improve security by isolating different components.

---

## 3. Backend Virtual Machine

A Linux VM acts as the backend server for this architecture.

Security features used:

* Managed Identity enabled
* Network Security Group
* Access through Application Gateway

The VM communicates securely with Azure services without storing credentials.

---

## 4. Azure Key Vault

Azure Key Vault is used to store sensitive information such as application secrets.

Example secret used in this project:

```
db-password
```

Secrets are accessed securely using **Managed Identity authentication** instead of storing credentials inside the VM.

---

## 5. Managed Identity

Managed Identity allows the VM to authenticate to Azure services **without storing passwords or credentials**.

The VM retrieves a token from the Azure metadata service and uses it to access the Key Vault.

Example token request:

```
TOKEN=$(curl -H Metadata:true \
"http://169.254.169.254/metadata/identity/oauth2/token?api-version=2018-02-01&resource=https://vault.azure.net" \
| jq -r '.access_token')
```

Retrieve secret from Key Vault:

```
curl https://secure-kv-demo.vault.azure.net/secrets/db-password?api-version=7.3 \
-H "Authorization: Bearer $TOKEN"
```

This is a **secure identity-based authentication method** recommended by Microsoft.

---

## 6. Azure Storage Account

A storage account was created to store data using Azure Blob Storage.

Security configuration:

* Private Endpoint enabled
* Public network access restricted
* Private DNS used for resolution

This ensures storage resources are only accessible from inside the Virtual Network.

---

## 7. Private Endpoint

Private Endpoint allows Azure services to be accessed using **private IP addresses inside the VNet**.

Benefits:

* No exposure to public internet
* Secure service communication
* Reduced attack surface

The Storage Account is accessed using private network connectivity.

---

## 8. Private DNS Zone

Private DNS ensures Azure services resolve to private IP addresses.

Example DNS resolution:

```
anuragaccount01.blob.core.windows.net
↓
anuragaccount01.privatelink.blob.core.windows.net
↓
10.x.x.x
```

This allows services inside the VNet to connect privately.

---

# Security Benefits Achieved

This architecture implements several Azure security best practices.

## Identity-based authentication

Managed Identity removes the need for storing credentials.

## Secure secret storage

Secrets are stored in Azure Key Vault instead of inside application code.

## Network isolation

Resources are deployed inside a Virtual Network.

## Private service access

Storage Account is accessed through Private Endpoint.

## Secure traffic routing

Application Gateway controls incoming web traffic.

---

# Screenshots

Screenshots of the deployment are included in the `screenshots` directory.

Examples:

* Architecture overview
* Virtual network configuration
* Application Gateway setup
* Backend VM configuration
* Key Vault secrets
* Private Endpoint configuration
* DNS resolution
* Secret retrieval using Managed Identity

---

---

# What This Project Demonstrates

This project demonstrates practical implementation of:

* Azure Networking
* Secure architecture design
* Application Gateway configuration
* Managed Identity authentication
* Azure Key Vault integration
* Private Endpoint architecture
* Private DNS resolution

These concepts are commonly used in **real-world enterprise cloud environments**.

---

# Author
Anurag Utkarsh
Anurag
Cloud & Linux Engineer
