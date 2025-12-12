

# Week 1 — System Planning & Distribution Selection

This week focuses on planning the system deployment, choosing the server distribution, preparing the workstation, and documenting the initial network and system configuration.

---

## 1. System Architecture Diagram

<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/914edf79-c4e6-43ab-9a64-92d8f3ebb6fe" />


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

<img width="855" height="361" alt="image" src="https://github.com/user-attachments/assets/8e48ffd1-6707-4f15-aa8e-7d7959c80365" />


---

## 5. System Specification Evidence

Commands executed on the server:

<img width="488" height="24" alt="image" src="https://github.com/user-attachments/assets/c1ae76f4-5b67-4283-8a02-b266a73c02cb" />

### Memory information
<img width="329" height="37" alt="image" src="https://github.com/user-attachments/assets/c7812922-e0b5-4b1b-a689-ef9a8b673592" />

### Network interfaces
<img width="298" height="66" alt="image" src="https://github.com/user-attachments/assets/ce8d52c8-10b9-40ae-973f-741cc34e0584" />

## 6. Reflection for Week 1

This week, I learned how to structure a dual-system architecture using a Windows workstation and a headless Ubuntu Server. I set up VirtualBox networking, identified the server distribution, and captured server specifications using CLI commands. This formed the foundation for security hardening and performance analysis in later weeks.

---



