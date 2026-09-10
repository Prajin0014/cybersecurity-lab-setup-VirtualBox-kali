# 🔐 Cybersecurity Lab Setup – VirtualBox & Kali Linux

## 📌 Project Overview

This project focuses on setting up a controlled cybersecurity lab using
VirtualBox and Kali Linux for hands-on learning and security testing.

## 🎯 Objectives

- Set up Kali Linux in VirtualBox
- Create a NAT Network
- Configure Kali's network settings
- Set up a shared folder
- Verify Internet connectivity
- Create a clean VM snapshot
- Document the setup and troubleshooting process

## ⚙️ Lab Configuration

| Component | Configuration |
|---|---|
| Virtualization | VirtualBox |
| Security OS | Kali Linux 2026.2 |
| Virtual Network | NAT Network |
| Network | 10.0.0.0/24 |
| Kali IP | 10.0.0.2/24 |
| Shared Folder | Downloads |
| Snapshot | Week 1 - Clean Lab Setup |

## 🛠️ Setup

### 1. VirtualBox and Kali Linux

Kali Linux was configured as a virtual machine in VirtualBox.

![VirtualBox Kali](./01-virtualbox-kali.png)

### 2. NAT Network

A NAT Network named `CyberLab` was created using:

`10.0.0.0/24`

![NAT Network](./02-nat-network.png)

### 3. Kali Network Configuration

Kali Linux was configured with the required IPv4 address:

`10.0.0.2/24`

![Kali IP](./03-kali-ip.png)

### 4. Shared Folder

A shared `Downloads` folder was configured between the host system and Kali Linux.

![Shared Folder](./04-shared-folder.png)

### 5. Internet Connectivity

Internet connectivity was verified using:

```bash
ping -c 4 8.8.8.8


GitHub: Prajin0014
