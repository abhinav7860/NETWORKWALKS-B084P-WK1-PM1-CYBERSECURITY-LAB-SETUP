 <div align="center">

# 🔐 Cybersecurity Lab Environment Setup

**Building a virtual cybersecurity testing laboratory using VirtualBox and Kali Linux**

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Batch-B084P-C00000?style=flat-square" />
  <img src="https://img.shields.io/badge/Week-01-0070C0?style=flat-square" />
  <img src="https://img.shields.io/badge/Project-WK1--PM1-404040?style=flat-square" />
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-C00000?style=flat-square" />
  <img src="https://img.shields.io/badge/Virtualization-VirtualBox-0070C0?style=flat-square" />
  <img src="https://img.shields.io/badge/Security%20OS-Kali%20Linux-E87500?style=flat-square" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square" />
  <img src="https://img.shields.io/badge/NetworkWalks-Cybersecurity-C00000?style=flat-square" />
</p>

---

## 📌 Project Overview

This project focuses on setting up a **cybersecurity testing laboratory** using VirtualBox and Kali Linux.

The objective is to create a controlled virtual environment for cybersecurity learning, network configuration, penetration testing practice, and future security testing activities.

The laboratory will use a dedicated NAT Network with the subnet `10.0.0.0/24`.

Kali Linux will be configured as the attacking machine with the required IP address `10.0.0.2/24` and internet connectivity.

The project is part of the NetworkWalks Cybersecurity Internship, Week 1 – Project Module 1.

---

## 🎯 Objectives

The main objectives of this project are to:

- Install and configure VirtualBox.
- Install 7-Zip for archive extraction.
- Setup Kali Linux as the attacking machine.
- Create a VirtualBox NAT Network using `10.0.0.0/24`.
- Configure Kali Linux with the required IP address.
- Enable clipboard sharing and drag-and-drop.
- Configure a shared `/downloads` folder from the host machine.
- Verify Kali Linux network connectivity.
- Verify internet access and DNS resolution.
- Take a clean snapshot of the configured virtual machine.
- Document the complete laboratory setup.

---

## 🛡️ Purpose of the Lab

The laboratory provides a controlled environment for cybersecurity learning and authorized security testing.

It can be used for future activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Network traffic analysis
- Security tool experimentation
- Ethical hacking practice
- Cybersecurity lab exercises

⚠️ **Important:** This laboratory is intended for educational purposes and authorized security testing only. Only test systems that you own or have explicit permission to assess.

---

## 🏗️ Lab Architecture

The laboratory will consist of a host operating system running VirtualBox, with Kali Linux configured as a virtual machine.

The Kali Linux VM will connect to a dedicated NAT Network.

### Network Architecture

```text
              Host Machine
               Windows 10
                    |
                    |
             Oracle VirtualBox
                    |
                    |
              NAT Network
             10.0.0.0/24
                    |
                    |
               Kali Linux
             Attacking VM
                    |
             IP: 10.0.0.2/24
                    |
             Internet Access
```

The host machine will provide the shared `/downloads` folder.

The configured virtual machine will serve as the baseline environment for future cybersecurity exercises.

### Lab Architecture Screenshot

![Lab Architecture](screenshots/01-lab-architecture.png)

---

## ⚙️ Lab Configuration

| Component | Required Configuration |
|---|---|
| Host Operating System | Windows 10 |
| Hypervisor | VirtualBox |
| Security Operating System | Kali Linux |
| Virtual Network | NAT Network |
| Network Subnet | 10.0.0.0/24 |
| Kali IPv4 Address | 10.0.0.2/24 |
| Clipboard Sharing | Enabled |
| Drag and Drop | Enabled |
| Shared Folder | Host `/downloads` |
| Internet Connectivity | Required |

### Network Configuration

```text
Network Type: NAT Network

Network Name: NatNetwork

IPv4 Network: 10.0.0.0/24

Kali Linux IP: 10.0.0.2/24

Gateway: [Actual configured gateway]

DNS: [Actual configured DNS]
```

The gateway and DNS values will be documented according to the actual working configuration.

---

# 🪜 Lab Setup Procedure

## Step 1. Install 7-Zip

Download and install 7-Zip on the host machine.

**Purpose:** Extract the downloaded Kali Linux virtual machine archive.

Download:

https://7-zip.org/download.html

### Screenshot

![7-Zip Installation](screenshots/02-7zip-installation.png)

---

## Step 2. Install VirtualBox

Download and install VirtualBox on the host machine.

VirtualBox will be used to create and manage the Kali Linux virtual machine.

Download:

https://virtualbox.org/wiki/Downloads

### Screenshot

![VirtualBox Installation](screenshots/03-virtualbox-installation.png)

---

## Step 3. Configure the NAT Network

Create a dedicated NAT Network in VirtualBox.

### Required Configuration

```text
Network Name: NatNetwork

IPv4 Prefix: 10.0.0.0/24

Network Type: NAT Network

DHCP: [Actual configuration]
```

The NAT Network will provide the virtual networking environment for Kali Linux.

### Screenshot

![NAT Network Configuration](screenshots/04-nat-network-configuration.png)

---

## Step 4. Download and Import Kali Linux

Download Kali Linux from the official website.

https://www.kali.org/get-kali/

Import the virtual machine into VirtualBox.

Configure the virtual network adapter to use the previously created NAT Network.

### Virtual Machine Configuration

```text
Operating System: Kali Linux

Network Adapter: Adapter 1

Attached To: NAT Network

Network Name: NatNetwork
```

### Screenshot

![Kali Linux Virtual Machine](screenshots/05-kali-linux-vm.png)

---

## Step 5. Configure the Kali Linux Network

Configure the Kali Linux network interface with the required IPv4 address.

### Required Configuration

```text
IPv4 Address: 10.0.0.2

Subnet Mask: 255.255.255.0

Network: 10.0.0.0/24

Gateway: [Actual configured gateway]

DNS Server: [Actual configured DNS]
```

The network configuration will be verified using Linux networking utilities.

### Screenshot

![Kali Network Configuration](screenshots/06-kali-network-configuration.png)

---

## Step 6. Configure Clipboard and Drag-and-Drop

Enable the following options in the Kali Linux virtual machine settings:

```text
Shared Clipboard: Bidirectional

Drag and Drop: Bidirectional
```

These features will allow supported clipboard and file-transfer interactions between the host and virtual machine.

### Screenshot

![Clipboard and Drag and Drop](screenshots/07-clipboard-drag-drop.png)

---

## Step 7. Configure the Shared Folder

Configure the host machine's `/downloads` folder as a shared folder in VirtualBox.

### Required Configuration

```text
Folder Name: downloads

Host Folder: [Actual host downloads folder]

Auto-Mount: [Actual configuration]

Make Permanent: [Actual configuration]
```

The shared folder will be used to transfer files between the host machine and Kali Linux.

### Screenshot

![Shared Folder Configuration](screenshots/08-shared-folder-configuration.png)

---

## Step 8. Verify Network Connectivity

Verify the Kali Linux IP configuration and network connectivity.

### Check IP Address

```bash
ip addr
```

### Check Routing Table

```bash
ip route
```

### Test Gateway Connectivity

```bash
ping -c 4 10.0.0.1
```

### Test Internet Connectivity

```bash
ping -c 4 8.8.8.8
```

### Test DNS Resolution

```bash
nslookup google.com
```

The gateway address must be replaced with the actual configured gateway if it differs.

### Screenshot

![Network Connectivity](screenshots/09-network-connectivity.png)

---

## Step 9. Take a Virtual Machine Snapshot

After completing the required configuration, create a clean snapshot of the Kali Linux virtual machine.

### Suggested Snapshot Name

```text
Kali-Linux-Clean-Lab-Setup
```

The snapshot will preserve the configured virtual machine as a baseline for future cybersecurity exercises.

### Screenshot

![Kali Linux Snapshot](screenshots/10-kali-snapshot.png)

---

# 🔎 Lab Verification

The following checks will be performed to verify the laboratory configuration.

| Test | Command | Expected Result |
|---|---|---|
| Check IP address | `ip addr` | Kali IP is 10.0.0.2/24 |
| Check routing | `ip route` | Correct network route displayed |
| Test gateway | `ping -c 4 10.0.0.1` | Successful replies if gateway is 10.0.0.1 |
| Test internet | `ping -c 4 8.8.8.8` | Successful replies |
| Test DNS | `nslookup google.com` | Domain resolves |
| Check shared folder | `ls` on mounted folder | Shared files accessible |
| Check snapshot | Restore snapshot | Baseline configuration restored |

### Verification Results

```text
Kali IP Address:
[Actual result]

Gateway:
[Actual result]

Internet Connectivity:
[Actual result]

DNS Resolution:
[Actual result]

Shared Folder:
[Actual result]

Snapshot:
[Actual result]
```

---

# 🐞 Problems Encountered & Solutions

Troubleshooting is an important part of configuring a cybersecurity laboratory.

## Problem 1. Kali Linux Internet Connectivity

### Problem

Kali Linux may experience internet connectivity issues after configuring the NAT Network and manually setting the IPv4 address.

### Investigation

The following configuration items should be checked:

- VirtualBox NAT Network configuration.
- Kali Linux network adapter configuration.
- IP address conflicts.
- Network interface status.
- Gateway configuration.
- DNS configuration.

### Solution

Follow the troubleshooting instructions provided in the NetworkWalks Week 1 assignment.

For the specific VirtualBox 7 and Kali Linux connectivity issue described in the assignment, the following commands are provided:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

sudo nmcli connection down "Wired connection 1"

sudo nmcli connection up "Wired connection 1"
```

The actual connection name must be verified before running the commands.

### Verification

```bash
ip addr

ip route

ping -c 4 8.8.8.8

nslookup google.com
```

### Result

[Document the actual issue, solution, and verification result.]

---

## Problem 2. VirtualBox Virtualization Error

### Problem

A virtual machine may fail to start if hardware virtualization is disabled or unavailable.

### Investigation

Check the VirtualBox error message and the system's virtualization configuration.

### Solution

If the issue is caused by disabled hardware virtualization:

1. Restart the computer.
2. Enter BIOS/UEFI settings.
3. Check the hardware virtualization setting.
4. Enable Intel VT-x or the corresponding supported virtualization option.
5. Save the configuration.
6. Restart the computer.
7. Start the virtual machine again.

### Verification

Confirm that VirtualBox starts the Kali Linux virtual machine successfully.

### Result

[Document whether this issue occurred and how it was resolved.]

---

# 💡 What I Learned

Through this project, I will develop practical knowledge of setting up a virtual cybersecurity testing environment.

### 1. Virtualization

Understanding how VirtualBox creates and manages virtual machines for cybersecurity learning.

### 2. Virtual Networking

Understanding NAT Network configuration and how virtual machines connect to a network.

### 3. IPv4 Configuration

Learning how IP addresses, subnet masks, gateways, and DNS settings affect network connectivity.

### 4. Kali Linux

Configuring Kali Linux as a virtual machine for future cybersecurity exercises.

### 5. Network Troubleshooting

Learning how to identify and troubleshoot network configuration and connectivity issues.

### 6. Virtual Machine Snapshots

Understanding the importance of maintaining a clean baseline before conducting security experiments.

### 7. Technical Documentation

Documenting configuration, screenshots, troubleshooting experiences, and verification results.

---

# 🔐 Security & Ethical Use

This laboratory is intended for cybersecurity education and authorized testing.

All security testing activities must be conducted only against systems that you own or have explicit permission to test.

The virtual environment will be used for learning, experimentation, and future cybersecurity exercises.

---

# 🔗 Tools & Resources

- **7-Zip:** https://7-zip.org/download.html
- **VirtualBox:** https://virtualbox.org/wiki/Downloads
- **Kali Linux:** https://www.kali.org/get-kali/
- **NetworkWalks:** https://networkwalks.com/

---

# 👤 Author

**Abhinav Sabu**

Cybersecurity Intern

NetworkWalks IT Solutions & Training

Batch: B084P

---

## 📌 Project Information

**Program:** NetworkWalks Cybersecurity Internship

**Week:** 01

**Project Module:** PM1

**Project:** Cybersecurity Lab Setup

**Repository:** GitHub
