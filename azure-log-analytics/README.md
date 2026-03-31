# Azure Monitor VM Monitoring Project

## Project Overview

This project demonstrates how to monitor an Azure Virtual Machine using **Azure Monitor and Log Analytics Workspace**.

The project collects VM telemetry data such as heartbeat logs, metrics, and system performance information using the **Azure Monitor Agent**.

These logs are stored and queried in **Log Analytics Workspace** using **Kusto Query Language (KQL)**.

---

# Architecture

Azure Virtual Machine
↓
Azure Monitor Agent
↓
Log Analytics Workspace
↓
Log Queries and Metrics Monitoring

---

# Services Used

| Service                 | Purpose                     |
| ----------------------- | --------------------------- |
| Azure Virtual Machine   | Compute resource to monitor |
| Azure Monitor           | Collect performance metrics |
| Log Analytics Workspace | Store and analyze logs      |
| Azure Monitor Agent     | Send telemetry data from VM |

---

# Resources Created

| Resource                | Name              |
| ----------------------- | ----------------- |
| Resource Group          | monitor-demo-rg   |
| Virtual Machine         | monitor-vm        |
| Log Analytics Workspace | monitor-workspace |

---

# Step 1 — Create Virtual Machine

A Linux virtual machine was deployed.

Configuration:

Name:
monitor-vm

Image:
Ubuntu

Region:
Central India

---

# Step 2 — Create Log Analytics Workspace

Workspace created to collect monitoring logs.

Name:
monitor-workspace

---

# Step 3 — Enable VM Monitoring

Monitoring was enabled using **VM Insights**, which automatically installs the Azure Monitor Agent.

Path:

Virtual Machine
→ Monitor
→ Insights
→ Enable

---

# Step 4 — Verify Agent Installation

Azure Monitor Agent installed automatically.

Path:

Virtual Machine
→ Extensions + Applications

Agent:

AzureMonitorLinuxAgent

---

# Step 5 — Run Log Query

Log Analytics allows querying logs using **Kusto Query Language (KQL)**.

Example query:

```kusto
Heartbeat
| take 10
```

This query retrieves heartbeat signals sent by the monitored VM.


**#SCREENSHOTS**
[images/AMAExtension.png]

# Example Output

The query returns heartbeat logs showing that the VM is actively sending monitoring data to Azure Monitor.

---

# Metrics Monitoring

Azure Monitor also provides performance metrics such as:

* CPU utilization
* Memory usage
* Network traffic
* Disk operations

These metrics can be visualized through graphs in the Azure Portal.

---

# Learning Outcome

This project demonstrates:

* Azure VM monitoring using Azure Monitor
* Log collection with Azure Monitor Agent
* Log storage and querying with Log Analytics
* Basic KQL query usage
* Infrastructure monitoring in cloud environments

---

# Author

Anurag
Linux Engineer | Azure & Cloud Infrastructure Enthusiast
