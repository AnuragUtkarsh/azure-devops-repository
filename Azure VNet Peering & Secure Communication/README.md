# 🌐 Project 06 - Azure VNet Peering & Secure Communication

## 📌 Overview

This project demonstrates secure communication between two Azure Virtual Networks using VNet Peering and Network Security Groups (NSG).

---

## 🏗️ Architecture

* VNet01: `10.0.0.0/16`
* VNet02: `10.1.0.0/16`
* VM1 in VNet01
* VM2 in VNet02

---

## 🔗 VNet Peering

* Established bidirectional peering between VNet01 and VNet02
* Enabled private communication using Azure backbone network

---

## 🔐 Security Implementation (NSG)

* Restricted SSH access:

  * Source: `10.0.0.0/16`
  * Destination: VM2
  * Port: `22`
* Restricted ICMP (Ping) access
* Removed open access (Any → Any)

---

## 🧪 Testing

### ✅ SSH Test

ssh azureuser@10.1.0.4
```

### ✅ Ping Test

ping 10.1.0.4
```

---

## 📸 Screenshots


---

## 💡 Key Learnings

* VNet Peering enables private communication across VNets
* NSG acts as a firewall to control traffic
* Even with peering, NSG rules can block or allow traffic
* Implemented least privilege access (secure design)

---

## 🚀 Conclusion

Successfully configured secure communication between VNets using peering and NSG rules, simulating a real-world production networking scenario.
