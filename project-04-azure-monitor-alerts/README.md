# 🚀 Project 4 – Azure Monitor Alerts (CPU Monitoring)

## 📌 Overview

This project demonstrates real-time monitoring of an Azure Virtual Machine using Azure Monitor.
An alert rule is configured to trigger when CPU usage exceeds a defined threshold, and notifications are sent via email.

---

## 🏗️ Architecture

```
Azure VM
   ↓
Azure Monitor
   ↓
Alert Rule (CPU > 70%)
   ↓
Action Group
   ↓
Email Notification
```

---

## 🛠️ Services Used

* Azure Virtual Machine
* Azure Monitor
* Metric Alerts
* Action Groups (Email Notification)

---

## ⚙️ Implementation Steps

1. Created an Azure Virtual Machine (Ubuntu).
2. Configured Azure Monitor alert rule.
3. Defined condition: **CPU usage > 70% (Average)**.
4. Created an Action Group for email notification.
5. Simulated high CPU load using `stress` tool.
6. Verified alert triggering and email delivery.

---

## 📊 Alert Configuration

| Setting     | Value              |
| ----------- | ------------------ |
| Metric      | Percentage CPU     |
| Aggregation | Average            |
| Threshold   | 70%                |
| Severity    | Medium             |
| Action      | Email Notification |

---

## 🧪 Testing

CPU load was generated using:

```bash
sudo apt install stress -y
stress --cpu 2 --timeout 120
```

---

## ✅ Result

* Alert triggered successfully when CPU exceeded threshold
* Email notification received
* Monitoring pipeline validated end-to-end

---

## 📸 Screenshots



---

## 🧠 Key Learnings

* Implemented real-time monitoring using Azure Monitor
* Understood alert rules and thresholds
* Configured automated notifications using Action Groups
* Simulated production-like failure scenario

---

## 💡 Use Case

This setup is commonly used in production environments to:

* Detect high CPU usage
* Notify DevOps teams instantly
* Prevent system downtime

---

## 🔥 Future Enhancements

* Auto VM restart on alert (self-healing system)
* Integration with Slack / Teams
* Log Analytics dashboard
