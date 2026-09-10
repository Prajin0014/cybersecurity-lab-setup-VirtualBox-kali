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

⚙️ Setup Process
1. Kali Linux Virtual Machine

Kali Linux 2026.2 was configured as a virtual machine inside Oracle VirtualBox.

The VM was configured with:

Kali Linux 2026.2
2048 MB allocated memory
2 processors
Virtual disk
Network Adapter 1
Intel PRO/1000 MT Desktop network adapter
CyberLab NAT Network

The VirtualBox configuration can be seen below.

Screenshot

2. NAT Network Configuration

A custom NAT Network named CyberLab was created in VirtualBox.

The network was configured with:

Network Name: CyberLab
IPv4 Prefix: 10.0.0.0/24
DHCP: Enabled

The /24 subnet provides the address range used by the virtual lab.

Screenshot

3. Kali Linux Network Configuration

After connecting Kali Linux to the CyberLab NAT Network, the network interface was checked using:

ifconfig

and:

ip addr

The eth0 interface showed:

inet 10.0.0.2/24

This confirmed that Kali Linux had the expected IP address on the lab network.

A secondary address, 10.0.0.3/24, was also visible on the interface as a DHCP-assigned address.

The required lab IP, 10.0.0.2/24, was successfully present.

Screenshot

📁 4. Shared Folder Configuration

A shared folder was configured in VirtualBox to allow files to be accessed between the host system and Kali Linux.

The configuration used:

Shared Folder Name: Downloads
Host Path: C:\Downloads
Access: Full
Auto Mount: Yes

This provides a convenient way to transfer files into the cybersecurity lab environment.

Screenshot

5. Shared Folder Verification

After configuring the shared folder, it was verified from inside Kali Linux.

The following command was used:

ls /media/sf_Downloads

The command displayed files from the shared Windows Downloads folder.

This confirmed that the shared folder was accessible from Kali Linux.

Screenshot

🌐 6. Internet Connectivity Test

Internet connectivity was tested from the Kali Linux terminal.

The following command was used:

ping -c 4 8.8.8.8

The test was successful:

4 packets transmitted
4 packets received
0% packet loss

This confirmed that Kali Linux was able to reach an external IP address through the configured virtual network.

Screenshot

🐞 7. Problem Encountered and Troubleshooting

During the initial connectivity testing, a DNS resolution problem was encountered.

When testing connectivity using a domain name, the terminal returned:

Temporary failure in name resolution

This indicated that although network connectivity could be available, DNS name resolution was not working correctly at that point.

To investigate the issue, connectivity was tested directly against Google's public DNS IP address:

ping -c 4 8.8.8.8

The test succeeded with:

4 packets transmitted
4 packets received
0% packet loss

This helped distinguish between general network connectivity and DNS resolution.

After troubleshooting the network configuration, connectivity was successfully verified.

What I learned from this issue

This troubleshooting process helped me understand that:

An Internet connection and DNS resolution are related but different functions.
Testing an IP address can help determine whether basic network connectivity is working.
Domain-name failures do not always mean the entire network connection is unavailable.
Basic network troubleshooting should be performed step by step instead of assuming the entire configuration is broken.
📸 8. Complete Evidence

The following screenshots document the main stages of the lab setup:

1. VirtualBox and Kali Linux VM

2. CyberLab NAT Network

3. Shared Folder Configuration

4. Internet Connectivity

5. Kali Linux IP Configuration

6. Shared Folder Verification

7. Clean VM Snapshot

💾 9. VM Snapshot

After completing the initial lab configuration, a VirtualBox snapshot was created.

The snapshot was named:

Week 1 - Clean Lab Setup

The purpose of the snapshot is to provide a clean restore point before performing future cybersecurity experiments.

If a future lab configuration causes problems, the virtual machine can be restored to this clean state instead of rebuilding the entire environment.

Screenshot

📚 10. What I Learned

Through this project, I gained hands-on experience with:

Virtual machines and virtualization
Oracle VirtualBox
Kali Linux
NAT Networks
IPv4 addressing
CIDR notation
Network interface configuration
Internet connectivity testing
DNS troubleshooting
VirtualBox shared folders
VM snapshots
Basic Linux commands
Technical documentation

Some of the most useful commands used during the setup were:

ifconfig
ip addr
ping -c 4 8.8.8.8
ls /media/sf_Downloads
🔐 11. Security and Ethical Use

This lab is intended for:

Cybersecurity education
Hands-on learning
Testing in an authorized environment
Practicing networking and security concepts

All security testing should only be performed on systems that I own or where I have explicit authorization to test.

No unauthorized systems, networks, or services should be targeted.

🚀 12. Future Lab Work

This environment will serve as a foundation for future cybersecurity practice.

Possible future activities include:

Setting up additional virtual machines
Practicing network scanning in the lab
Learning reconnaissance techniques
Exploring security tools available in Kali Linux
Performing controlled vulnerability-testing exercises
Building isolated Capture The Flag (CTF) environments
Practicing security monitoring and analysis

All future testing will remain within controlled and authorized environments.

📂 13. Repository Structure
cybersecurity-lab-setup-virtualbox-kali/
│
├── README.md
│
├── Screenshot (90).png
├── Screenshot (91).png
├── Screenshot (92).png
├── Screenshot (93).png
├── Screenshot_2026-09-09_02_31_00.png
├── Screenshot_2026-09-09_02_31_01.png
└── Screenshot_2026-09-10_03-10-02.png
✅ 14. Project Completion Checklist
 Kali Linux virtual machine configured
 VirtualBox NAT Network created
 CyberLab network configured
 10.0.0.0/24 subnet configured
 Kali Linux IP verified
 Shared folder configured
 Shared folder access verified
 Internet connectivity tested
 DNS issue identified and troubleshooted
 Clean VM snapshot created
 Project screenshots documented
 Project documentation added to GitHub
📝 Conclusion

This project gave me practical experience in building a controlled cybersecurity lab using VirtualBox and Kali Linux.

The setup helped me understand the basics of virtual networking, IP addressing, shared resources, connectivity testing, DNS troubleshooting, and VM snapshots.

Having a reusable lab environment will make it easier to continue practicing cybersecurity concepts through future hands-on projects.

👤 Author

Prajin PK

GitHub: Prajin0014

