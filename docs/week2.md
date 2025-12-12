
Week 2 — Security Planning and Testing Methodology

This week focuses on designing a security baseline and defining a performance testing methodology for the Ubuntu Server environment.
for week 2 i will be using the following monitoring tools:
top — live CPU and memory usage

htop — enhanced process viewer (if installed)

vmstat — CPU, memory, I/O metrics

iostat — disk I/O throughput

free -h — memory statistics

df -h — storage usage

sar — historical performance logging

Network Monitoring

ping — latency and packet loss

iperf3 — bandwidth and throughput

ss -tulnp — inspect open ports and services
Testing approach
I will evaluate system performance under different workload types.

 **Baseline Measurements**

Observe idle CPU, memory, and disk usage

Tools: top, vmstat 1, free -h, iostat

2. CPU Stress Test
sudo apt install stress-ng
stress-ng --cpu 2 --timeout 60s


Monitor with top and vmstat.

3. Memory Stress Test
stress-ng --vm 1 --vm-bytes 75% --timeout 60s

4. Disk I/O Test
stress-ng --hdd 1 --timeout 60s


Monitor with iostat.

5. Network Performance Test
iperf3 -s    # server
iperf3 -c <server-ip>    # client

 **Data to Be Collected**

The following metrics will be recorded during testing:

CPU utilisation (%)

RAM usage (%)

Disk read/write performance

Network latency and throughput

Load average

System bottlenecks

Graphs and tables will be generated in Week 6.

 **Security Configuration Checklist**

A full security baseline will be implemented across SSH, firewall, user accounts, and system services.

**SSH Hardening Checklist**
Task	Status
Disable root login	Planned
Disable password authentication	Planned
Enable key-based authentication	Planned
Change default SSH port	Planned
Restrict SSH to workstation IP	Planned
Enforce strong cryptographic ciphers	Planned

Commands (to implement later):

sudo nano /etc/ssh/sshd_config
sudo systemctl restart ssh

 **Firewall Configuration (UFW)**
Rule	Purpose
Deny all incoming traffic	Reduce attack surface
Allow outgoing traffic	Required for updates
Allow SSH from workstation only	Restrict remote access
Log blocked connections	Security visibility

Commands (to implement later):

sudo apt install ufw
sudo ufw default deny incoming
sudo ufw default allow outgoing
sudo ufw allow from <workstation-ip> to any port 22
sudo ufw enable

 **Mandatory Access Control (AppArmor)
**
Ubuntu uses AppArmor to enforce application-level security.

Security tasks:

Ensure AppArmor is active

Enforce all profiles

Review AppArmor security logs

Commands:

sudo apparmor_status
sudo aa-enforce /etc/apparmor.d/*

** Automatic Security Updates**

Enable unattended upgrades:

sudo apt install unattended-upgrades
sudo dpkg-reconfigure unattended-upgrades


This ensures the system receives security patches without manual intervention.

** User Privilege Management**

Tasks include:

Create a non-root administrative user

Restrict unnecessary sudo privileges

Apply least-privilege principles

Audit /etc/sudoers for secure configuration

Commands:

sudo adduser adminuser
sudo usermod -aG sudo adminuser
sudo visudo

 **Network Security Controls**

Tasks:

Segregate server using Host-Only networking

Disable unused services

Perform regular port scans using nmap

Install and configure fail2ban

Command:

sudo apt install fail2ban

## 3. Threat Model

This threat model identifies key risks to the system and mitigation strategies.

Threat 1 — Brute-Force SSH Attacks

Attackers attempt to guess SSH credentials.

Mitigations:

Disable password login

Enforce key-based authentication

Install fail2ban

Change SSH port

Restrict SSH to workstation IP

Threat 2 — Privilege Escalation

A compromised user account attempts to gain root access.

Mitigations:

Strong sudo policies

Least privilege access

Logging and auditing user actions

Enforce AppArmor profiles

Threat 3 — Misconfigured Firewall

Open or unnecessary ports expose the system to attacks.

Mitigations:

Default deny incoming policy

Only allow required services

Regular firewall audits
