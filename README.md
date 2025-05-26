# 🛡️ Nmap Reconnaissance and Enumeration Reports

This repository documents Nmap scan results against local network hosts for penetration testing and network auditing.

## 🧰 Setup Instructions

### 1️⃣ Install Nmap

Download and install Nmap from the official website:  
🔗 [https://nmap.org/download.html](https://nmap.org/download.html)

### 2️⃣ Find Your Local IP Range

On Windows (Command Prompt):
ipconfig

Determine your subnet range (e.g., `192.168.0.0/24`).

## 📊 Scan Report 1: OS Detection & Service Version Scan

**Target:** `192.168.0.106`

**Command:**

nmap -sS -sV -O 192.168.0.106

**Details:**

* **Operating System:** Microsoft Windows 10 (versions 1809 to 21H2)
* **SMB Version:** SMBv2 enabled
* **Network Latency:** \~0.91 ms (local network)

**Open Ports and Services:**

| Port | Service      | Description                                                     |
| ---- | ------------ | --------------------------------------------------------------- |
| 135  | msrpc        | Microsoft Remote Procedure Call – remote management, DCOM       |
| 139  | netbios-ssn  | NetBIOS Session Service – legacy file/printer sharing           |
| 445  | microsoft-ds | SMB over TCP – file/printer sharing; EternalBlue exploit target |
| 2179 | vmrdp?       | Likely Hyper-V VM console or remote management access           |
| 2869 | http         | Microsoft HTTPAPI 2.0 – UPnP service                            |
| 5357 | http         | Microsoft HTTPAPI 2.0 – UPnP device management/discovery        |

## 📊 Scan Report 2: TCP SYN Scan (Basic Port Discovery)

**Target:** `192.168.0.106`

**Command:**
nmap -sS 192.168.0.106

**Open TCP Ports:**

| Port | Service      | Description                                                     |
| ---- | ------------ | --------------------------------------------------------------- |
| 135  | msrpc        | Microsoft Remote Procedure Call – remote management, DCOM       |
| 139  | netbios-ssn  | NetBIOS Session Service – legacy file/printer sharing           |
| 445  | microsoft-ds | SMB over TCP – file/printer sharing; EternalBlue exploit target |
| 2179 | vmrdp?       | Likely Hyper-V VM console or remote management access           |
| 2869 | http         | Microsoft HTTPAPI 2.0 – UPnP service                            |
| 5357 | http         | Microsoft HTTPAPI 2.0 – UPnP device management/discovery        |

## 📊 Scan Report 3: Single Port Scan (DNS Port 53)

**Target:** `192.168.1.106`

**Command:**

```bash
nmap -sS 192.168.1.106
```

**Output:**

Starting Nmap 7.97 ( https://nmap.org ) at 2025-05-26 22:05 +0530
Nmap scan report for 192.168.1.106
Host is up (0.0086s latency).
Not shown: 999 filtered tcp ports (no-response)
PORT   STATE SERVICE
53/tcp open  domain

Nmap done: 1 IP address (1 host up) scanned in 8.60 seconds

**Summary:**

* Only port 53 (DNS) is open.
* Host is alive and responsive on the network.
* Further DNS enumeration recommended.

