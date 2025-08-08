# 🔒 Task 4: Setup and Use a Firewall on Linux (UFW)
---
🔐 Configure UFW on Kali Linux to block and allow traffic like a pro! 🚫 Block Telnet (port 23), ✅ allow SSH (port 22), and test rules using telnet. Learn how firewalls filter traffic 🔍 with simple commands and screenshots. Perfect for beginners! 🧑‍💻📸
---
## ✅ Objective
Configure and test basic firewall rules to allow or block traffic on a Linux system using **UFW (Uncomplicated Firewall)**.
---
## 🛠️ Tools Used
- Operating System: Kali Linux (or any Debian-based Linux)
- Firewall Tool: `ufw` (Uncomplicated Firewall)
- Test Tool: `telnet` (for testing blocked port)
---
## 📋 Steps Performed
1. **Open UFW (Uncomplicated Firewall)**  
Check if UFW is installed and enabled:  
`sudo ufw status`  
If not installed:  
`sudo apt update`  
`sudo apt install ufw -y`  
Enable it:  
`sudo ufw enable`  
📸 Screenshot: Firewall Enabled  
![Firewall Enabled](https://github.com/shindeharsh3399/Task-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/screenshots/01-ufw-enabled.png)
---
2. **List Current Firewall Rules**  
`sudo ufw status numbered`  
📸 Screenshot: UFW Rules List  
![UFW Rules List](https://github.com/shindeharsh3399/Task-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/screenshots/02-ufw-rules-list.png)
---
3. **Add a Rule to Block Inbound Traffic on Port 23 (Telnet)**  
`sudo ufw deny 23`  
📸 Screenshot: Rule Added to Block Port 23  
![Block Port 23](https://github.com/shindeharsh3399/Task-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/screenshots/03-block-port-23.png)
---
4. **Test the Rule by Connecting to Port 23**  
Install Telnet (if needed):  
`sudo apt install telnet -y`  
Test:  
`telnet localhost 23`  
Expected result: **Connection refused**  
📸 Screenshot: Telnet Test Blocked  
![Telnet Blocked](https://github.com/shindeharsh3399/Task-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/screenshots/04-telnet-blocked.png)
---
5. **Add a Rule to Allow SSH (Port 22)**  
`sudo ufw allow 22`  
📸 Screenshot: SSH Rule Added  
![Allow SSH](https://github.com/shindeharsh3399/Task-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/screenshots/05-allow-ssh.png)
---
6. **Remove the Test Block Rule (Restore Original State)**  
List rules with numbers:  
`sudo ufw status numbered`  
Delete the rule blocking port 23 (example deletes rule #1):  
`sudo ufw delete 1`  
📸 Screenshot: Rule Deleted  
![Rule Deleted](https://github.com/shindeharsh3399/Task-4-Setup-and-Use-a-Firewall-on-Windows-Linux/blob/main/screenshots/06-rule-deleted.png)
---
## 📌 Commands Used
```bash
sudo ufw enable
sudo ufw status numbered
sudo ufw deny 23
telnet localhost 23
sudo ufw allow 22
sudo ufw delete 1
```
## 🔍 Summary: How Firewalls Filter Traffic
Firewalls inspect incoming and outgoing network traffic based on defined rules. UFW is a front-end for `iptables` that simplifies managing firewall rules on Linux. Rules can allow or deny traffic based on ports, protocols, or IP addresses. Default UFW behavior is to deny all incoming traffic and allow all outgoing. For example, blocking port 23 (Telnet) prevents remote shell access, while allowing port 22 (SSH) ensures secure remote access remains functional.
---
## 📂 File Structure (Repo)
```
.
├── README.md
└── screenshots
    ├── 01-ufw-enabled.png
    ├── 02-ufw-rules-list.png
    ├── 03-block-port-23.png
    ├── 04-telnet-blocked.png
    ├── 05-allow-ssh.png
    └── 06-rule-deleted.png
```
