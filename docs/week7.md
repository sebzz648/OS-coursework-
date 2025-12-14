Week 7 - Security and System Evaluation 

 
The first thing i did was install lynis by doing the following command on ubuntu sudo apt install lynis -y, after this a ran an lynis audit system.

Network security map 

from my workstation my nmap was -SS 192.168.56.101

<img width="298" height="84" alt="image" src="https://github.com/user-attachments/assets/de96c31e-e117-42ae-900b-6142bb7d1225" />

ssh Security verification

<img width="461" height="77" alt="image" src="https://github.com/user-attachments/assets/12491262-c797-4a7c-b607-5723f12d1094" />

### SSH Security Verification

SSH configuration was verified using the `sshd -T` command to inspect the effective runtime configuration. Initial verification showed password authentication enabled, which did not meet the coursework security requirements. Password-based authentication and root login were subsequently disabled, enforcing exclusive key-based access.

**Verification Command:**
sudo sshd -T | egrep 'passwordauthentication|permitrootlogin|pubkeyauthentication'

Post-remediation verification confirmed:

Password authentication disabled

Root login prohibited

Public key authentication enforced

This phase demonstrated how defence-in-depth security principles operate in practice. Conducting audits, applying remediations, and verifying results improved both system security and my understanding of professional infrastructure management. However i did find some cahllenges wich included editing my password authenticatin on nano howerver this was quickly resolved by editing my nano aswell as troubleshooting and validation
