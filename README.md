# 🔐 Cybersecurity Lab Setup – VirtualBox & Kali Linux

## 📌 Project Overview

This project focuses on setting up a controlled cybersecurity testing and learning environment using Oracle VirtualBox and Kali Linux.

The purpose of this lab is to create a reusable environment for practicing cybersecurity concepts, networking, troubleshooting, and future security testing activities.

The lab was configured with a custom NAT Network, a Kali Linux virtual machine, a shared folder between the host and virtual machine, Internet connectivity, and a clean VM snapshot.

---

## 🎯 Objectives

The main objectives of this project were:

- Set up Kali Linux as a virtual machine using VirtualBox.
- Create and configure a custom NAT Network.
- Configure the lab network using the `10.0.0.0/24` subnet.
- Configure Kali Linux network connectivity.
- Verify the assigned IP address.
- Configure a shared folder between the host system and Kali Linux.
- Verify Internet connectivity from Kali Linux.
- Create a clean VM snapshot for future lab activities.
- Document the setup and troubleshooting process.

---

## 🧰 Lab Environment

| Component | Configuration |
|---|---|
| Virtualization Platform | Oracle VirtualBox |
| Operating System | Kali Linux 2026.2 |
| Virtual Network | NAT Network |
| NAT Network Name | CyberLab |
| IPv4 Network | `10.0.0.0/24` |
| Kali Linux IP | `10.0.0.2/24` |
| Shared Folder | Downloads |
| Host Shared Folder Path | `C:\Downloads` |
| Snapshot | Week 1 - Clean Lab Setup |

---

## 🏗️ Lab Architecture

```text
                    Host System
                        │
                        │
                  Oracle VirtualBox
                        │
                        │
                  ┌──────────────┐
                  │   CyberLab   │
                  │  NAT Network │
                  │ 10.0.0.0/24  │
                  └───────┬──────┘
                          │
                          │
                   ┌──────▼──────┐
                   │ Kali Linux  │
                   │   2026.2    │
                   │ 10.0.0.2/24 │
                   └─────────────┘
                          │
                          │
                    Internet Access

Host C:\Downloads
        │
        │ Shared Folder
        ▼
/media/sf_Downloads
       Kali Linux
⚙️ Setup Process
1. Kali Linux Virtual Machine

Kali Linux 2026.2 was configured as a virtual machine inside Oracle VirtualBox.

The VM configuration included:

Kali Linux 2026.2
2048 MB allocated memory
2 processors
Virtual disk
Network Adapter 1
Intel PRO/1000 MT Desktop network adapter
CyberLab NAT Network
Screenshot

2. NAT Network Configuration

A custom NAT Network named CyberLab was created in VirtualBox.

The network was configured using:

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

A secondary address, 10.0.0.3/24, was also visible on the interface.

Screenshot

4. Shared Folder Configuration

A shared folder was configured in VirtualBox to allow files to be accessed between the host system and Kali Linux.

The configuration used:

Shared Folder Name: Downloads
Host Path: C:\Downloads
Access: Full
Auto Mount: Yes

This provides a convenient way to transfer files between the host system and the cybersecurity lab.

Screenshot

5. Shared Folder Verification

After configuring the shared folder, it was verified from inside Kali Linux.

The following command was used:

ls /media/sf_Downloads

The command displayed files from the shared Windows Downloads folder.

This confirmed that the shared folder was accessible from Kali Linux.

Screenshot

6. Internet Connectivity Test

Internet connectivity was tested from the Kali Linux terminal.

The following command was used:

ping -c 4 8.8.8.8

The test was successful:

4 packets transmitted
4 packets received
0% packet loss

This confirmed that Kali Linux was able to reach an external IP address through the configured virtual network.

Screenshot

🐞 Problem Encountered and Troubleshooting

During the initial connectivity testing, a DNS resolution problem was encountered.

When testing connectivity using a domain name, the terminal returned:

Temporary failure in name resolution

To investigate the issue, connectivity was tested directly against an IP address:

ping -c 4 8.8.8.8

The test succeeded with:

4 packets transmitted
4 packets received
0% packet loss

This showed that basic network connectivity was working while DNS name resolution had initially encountered an issue.

After troubleshooting the network configuration, connectivity was successfully verified.

What I Learned From This Issue

This troubleshooting process helped me understand that:

Basic Internet connectivity and DNS resolution are different things.
Testing an IP address can help determine whether network connectivity is working.
A domain-name resolution failure does not necessarily mean the entire network connection is unavailable.
Network troubleshooting should be performed step by step.
💾 VM Snapshot

After completing the initial lab configuration, a VirtualBox snapshot was created.

The snapshot was named:

Week 1 - Clean Lab Setup

The snapshot provides a clean restore point before performing future cybersecurity experiments.

If a future configuration causes problems, the virtual machine can be restored to this clean state.

Screenshot

📸 Complete Evidence

The following screenshots document the main stages of the lab setup.

1. Kali Linux Virtual Machine

2. NAT Network Configuration

3. Shared Folder Configuration

4. Kali Linux IP Configuration

5. Internet Connectivity

6. Shared Folder Verification

7. VM Snapshot

📚 What I Learned

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

Some of the commands used during the setup were:

ifconfig
ip addr
ping -c 4 8.8.8.8
ls /media/sf_Downloads
🔐 Security and Ethical Use

This lab is intended for:

Cybersecurity education
Hands-on learning
Testing in an authorized environment
Practicing networking and security concepts

All security testing should only be performed on systems that I own or where I have explicit authorization to test.

No unauthorized systems, networks, or services should be targeted.

🚀 Future Lab Work

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

📂 Repository Structure
cybersecurity-lab-setup-VirtualBox-kali/
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
✅ Project Completion Checklist
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
