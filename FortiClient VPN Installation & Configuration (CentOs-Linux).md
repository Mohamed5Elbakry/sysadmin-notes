# 📄 FortiClient VPN Installation & Configuration (CentOS / Linux)
🔹 1. Overview

This guide explains how to install and configure Fortinet SSL VPN on CentOS using openfortivpn.

## 🔹 2. Requirements
CentOS / RHEL / Linux machine
Internet connection
VPN details:
Gateway IP: 196.168.x.x
Port: 10443
Username: (your account)
Password: (your password)
## 🔹 3. Install Required Packages
Step 1: Enable EPEL repository
sudo yum install epel-release -y
Step 2: Install openfortivpn
sudo yum install openfortivpn -y
## 🔹 4. Configure VPN
Step 1: Create config file
sudo nano /etc/openfortivpn/config
Step 2: Add configuration
host = 196.160.X.X
port = XXXXX
username = YOUR_USERNAME
trusted-cert = 4a9ac76216c7e9731e9edd27ba386bsssssssssssssssssssssssssssssssssss

🔹 Replace:

YOUR_USERNAME with your actual username
Step 3: Save file
Press CTRL + X
Press Y
Press Enter
## 🔹 5. Connect to VPN

Run:

sudo openfortivpn

Then enter your VPN password when prompted.

## 🔹 6. Verify Connection

Successful connection will show:

Tunnel is up and running.

You will also see:

VPN IP assigned (example: 192.168.x.x)
Interface ppp0 created
🔹 7. Test Connectivity
Ping internal server:
ping 192.168.x.x
Access services:
RDP (Windows servers)
SSH (Linux servers)
Web portals (vCenter, etc.)
##🔹 8. Disconnect VPN

Press:

CTRL + C
## 🔹 9. Troubleshooting
❌ Error: Specify a valid host:port
Config file missing or incorrect
❌ Certificate error

Use:

--trusted-cert <fingerprint>
❌ Cannot access servers

Check:

VPN connected
Correct IP
Firewall rules
## 🔹 10. Optional (Direct Command Method)

Instead of config file:

sudo openfortivpn gatwayip:port -u USERNAME \
--trusted-cert 4a9ac76216c7e9731e9edd27ba386b7sssssssssssssssssssssssssssssssssssssss
✅ Summary
Step	Action
1	Install openfortivpn
2	Configure VPN settings
3	Run sudo openfortivpn
4	Enter password
5	VPN connected
