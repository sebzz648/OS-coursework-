# week5: Advanced Security and Monitoring Infrastructure (Week 5)

## Overview

In this phase, advanced security controls were implemented on the Ubuntu server to enhance system protection and establish monitoring capabilities. Mandatory Access Control, automatic security updates, intrusion prevention, and custom verification and monitoring scripts were deployed. All configuration tasks were performed remotely via SSH in compliance with administrative constraints.

---

## 1. Mandatory Access Control (AppArmor)

### Description
AppArmor is a Mandatory Access Control (MAC) framework that restricts application capabilities and limits the impact of compromised services. It was used to enforce security policies on system services, including SSH.

### Commands Executed
```bash
sudo aa-status
sudo systemctl enable apparmor
sudo systemctl start apparmor
<img width="532" height="503" alt="image" src="https://github.com/user-attachments/assets/01b0eb8d-e515-4a6c-aa36-9805d398f6ce" />

Automatic Security Updates
Description

Automatic security updates ensure the server receives critical patches without manual intervention, reducing exposure to known vulnerabilities.

Commands Executed
