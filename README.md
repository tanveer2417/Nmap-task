Install Nmap
Download and install Nmap from the official website:
🔗 https://nmap.org/download.html

Find Your Local IP Range
Open Command Prompt or Terminal and find your local IP address using:

On Windows:

cmd
ipconfig

Then, determine your subnet (e.g., 192.168.1.0/24).

Run a TCP SYN Scan
Execute the following command to discover active hosts and open ports:

nmap -sS 192.168.1.0/24


Note on Active IP Addresses & Open Ports
Active IP Address:

192.168.0.106 is active on the local network.

Open TCP Ports on 192.168.0.106:

Port 135 (msrpc):
Microsoft Remote Procedure Call used for remote management and DCOM services.

Port 139 (netbios-ssn):
NetBIOS Session Service, used for legacy file and printer sharing.

Port 445 (microsoft-ds):
SMB over TCP, critical for Windows file/printer sharing; commonly targeted by exploits like EternalBlue.

Port 2179 (vmrdp?):
Likely used by Hyper-V for VM console access or remote management.

Port 2869 (http - Microsoft HTTPAPI 2.0):
UPnP service for device/service communication.

Port 5357 (http - Microsoft HTTPAPI 2.0):
UPnP related endpoint, typically for device management or discovery.

Operating System:
Detected as Microsoft Windows 10 (versions 1809 to 21H2).

SMB Security Details:
SMBv2 is enabled.

Network Latency:
Very low latency (~0.91 ms), indicating the host is on the local network.

Scan Command Used:
nmap -sS -sV -O 192.168.0.106

