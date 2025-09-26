# 🔥 Windows Firewall Configuration Task

This repository contains documentation and demonstration of configuring firewall rules in **Windows Defender Firewall with Advanced Security** using both **GUI** and **Command Prompt**.  
The task involved blocking inbound traffic on a specific port, testing the rule, and restoring the firewall to its original state.

---

## 📌 Overview
The goal of this task is to:
1. Open the firewall configuration tool.
2. List current firewall rules.
3. Add a rule to block inbound traffic on port **23 (Telnet)**.
4. Test the block by attempting to connect via Telnet.
5. Remove the test rule to restore original state.
6. Document all steps, screenshots, and results.

---

## 🛠️ Tools Used
- **Windows Defender Firewall with Advanced Security (GUI)**
- **Command Prompt (Administrator mode)**
- **Telnet Client** (enabled for testing)

---

## ⚙️ Commands Used

```powershell
# Show all firewall rules
netsh advfirewall firewall show rule name=all

# Add inbound block rule for Telnet (port 23)
netsh advfirewall firewall add rule name="Block Telnet" dir=in action=block protocol=TCP localport=23

# Enable Telnet client
dism /online /Enable-Feature /FeatureName:TelnetClient

# Test Telnet connection
telnet localhost 23

# Delete the Telnet block rule
netsh advfirewall firewall delete rule name="Block Telnet"
