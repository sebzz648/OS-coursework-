# week5: Advanced Security and Monitoring Infrastructure (Week 5)

## Overview

In this phase, advanced security controls were implemented on the Ubuntu server to enhance system protection and establish monitoring capabilities. Mandatory Access Control, automatic security updates, intrusion prevention, and custom verification and monitoring scripts were deployed. All configuration tasks were performed remotely via SSH in compliance with administrative constraints.

---

## 1. Mandatory Access Control (AppArmor)

### Description
AppArmor is a Mandatory Access Control (MAC) framework that restricts application capabilities and limits the impact of compromised services. It was used to enforce security policies on system services, including SSH.

### Commands Executed
sudo aa-status
sudo systmectl enable apparmor
sudo systemctl start apparmor
<img width="532" height="503" alt="image" src="https://github.com/user-attachments/assets/3c6da107-2e27-48c4-860a-75fb53b23e04" />
**Automatic security updates**

Automatic security updates ensure the server receives critical patches without manual intervention, reducing exposure to known vulnerabilities.

<img width="752" height="542" alt="image" src="https://github.com/user-attachments/assets/72510635-f59f-45a3-a274-9eeb5800228c" />

<img width="946" height="247" alt="image" src="https://github.com/user-attachments/assets/dcab2bb4-cea4-4d33-8b69-b9960c57ab37" />

this screenshot verifies that my automatic updtaes are actually enabled

<img width="209" height="28" alt="image" src="https://github.com/user-attachments/assets/b0c91543-e254-4e08-8de0-ad89c7c1da67" />

my configuration file

**configuring fail2ban for enhanced intrusion detection**

<img width="729" height="138" alt="image" src="https://github.com/user-attachments/assets/20eef9f7-edb7-4477-a662-2101341cd28d" />

