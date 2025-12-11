

# Week 1 — System Planning & Distribution Selection

This week focuses on planning the system deployment, choosing the server distribution, preparing the workstation, and documenting the initial network and system configuration.

---

## 1. System Architecture Diagram

Insert your diagram here (upload image to GitHub and link it).

Example:
![System Architecture Diagram](images/week1/diagram.png)

---

## 2. Distribution Selection Justification

I selected **Ubuntu Server 22.04 LTS** for my server.

### Reasons:
- Long-term support (5 years)
- Large community documentation
- Stable and widely used for servers
- Strong security features (AppArmor)
- Easy package management via `apt`
- Ideal for SSH-only administration

Alternative distributions considered include Debian and Rocky Linux, but Ubuntu Server provides the best balance for this coursework.

---

## 3. Workstation Configuration (Windows)

My workstation is a **Windows PC**.  
I use **Windows Terminal / PowerShell** to connect to the Ubuntu Server VM using SSH.

### Why Windows works well:
- Built-in SSH client  
- Easy integration with VirtualBox  
- Follows remote admin best practice (workstation → server)

---

## 4. Network Configuration

Ubuntu Server VM uses two network adapters:

### Adapter 1 — NAT  
- Provides internet access  
- Used for updates and package installation  

### Adapter 2 — Host-Only Adapter  
- Creates a private network between Windows and the VM  
- Used for SSH connections  

### Commands to verify network:
