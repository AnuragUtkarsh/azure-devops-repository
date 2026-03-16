## Architecture

Internet → Public IP → Azure Load Balancer → Backend Pool → Ubuntu VMs → NGINX

## Services Used

- Azure Virtual Machine
- Azure Load Balancer
- Public IP Address
- Network Security Group
- Ubuntu Server
- NGINX Web Server

## Infrastructure Setup

1. Created two Ubuntu Virtual Machines
2. Installed NGINX on both servers
3. Created Azure Load Balancer
4. Configured Frontend Public IP
5. Added both VMs to Backend Pool
6. Configured Health Probe (HTTP port 80)
7. Created Load Balancing Rule

## Commands Used

SSH into VM
