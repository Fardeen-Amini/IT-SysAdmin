# 🖥️ IT-SysAdmin Project  
## Windows Server 2022 Domain Controller Lab

In this project, I simulated a real-world System Administrator environment using **Hyper-V**, **Windows Server 2022**, and **physical office computers**.  
My goal was to create a fully functional **Domain Controller**, connect real PCs to the domain, and manage users through **Active Directory**.

---

## 🌐 Network Overview

- **Server IP:** `10.4.0.30`  
- **Subnet Mask:** `255.255.255.0`  
- **Default Gateway:** `10.4.0.1`  
- **DNS (on Server):** `10.4.0.30`  
- **Alternate DNS (on PCs):** `8.8.8.8`  
- **Switch Type:** Hyper-V External Switch (to bridge VM with physical network)

---

## 🛠️ Setup Steps

### 1. Created Hyper-V VM  
- Installed **Windows Server 2022**  
- Assigned an **External Switch** for LAN access

### 2. Configured Server Network  
- Set static IP: `10.4.0.30`  
- DNS: `10.4.0.30`, Alternate: `8.8.8.8`

### 3. Installed Server Roles  
- **Active Directory Domain Services (AD DS)**  
- **DNS Server**

### 4. Promoted Server to Domain Controller  
- Created domain: `fardeen.local`

### 5. Configured Real Office PCs  
- Manually assigned static IPs (no DHCP used)  
- DNS settings:
  - Preferred: `10.4.0.30`  
  - Alternate: `8.8.8.8`  
- Joined each PC to the domain `fardeen.local`

### 6. Created Domain User  
- In **Active Directory Users and Computers**, created user `testuser`  
- Enabled password change on first login

### 7. Tested Domain Join  
- Successfully logged into PC with: `FAR\testuser`

---

## 📷 Screenshots

### 🔧 Server IP Setup  
![Server IP Configuration](https://github.com/Fardeen-Amini/IT-SysAdmin/blob/main/Screenshots/ipconfig-server.jpg?raw=true)

### 🖥️ PC Joined to Domain  
![PC Joined to Domain](https://github.com/Fardeen-Amini/IT-SysAdmin/blob/main/Screenshots/Phsical%20PC%20Joined%20to%20Domain.jpg?raw=true)

> _Note: Additional screenshots like "domain-joined.png" and "ad-users.png" were mentioned — please upload and link them if you’d like those included._

---

## 📌 Notes

- No DHCP was used; all devices configured manually  
- External switch enabled server-to-PC LAN communication  
- Internet access preserved with Google's DNS (`8.8.8.8`)

---

## 🧠 What I Learned

- Installing and promoting a **Windows Server 2022** Domain Controller  
- Managing local DNS and custom domains  
- Safely joining physical PCs to a domain  
- Creating and managing users in **Active Directory**  
- Basic understanding of **Group Policy** and domain infrastructure

---

## 📫 Contact

Made by [Fardeen Amini](https://www.linkedin.com/in/fardeen-amini)  
GitHub: [github.com/Fardeen-Amini](https://github.com)
