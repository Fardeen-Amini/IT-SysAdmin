# IT-SysAdmin Project
# Windows Server 2022 Domain Controller Lab

In this project, I simulated a real-world System Administrator environment using Hyper-V, Windows Server 2022, and physical office computers. 
My goal was to create a fully functional Domain Controller, connect real PCs to the domain, and manage users through Active Directory.


---

## 🌐 Network Overview

- **Server IP:** `10.4.0.30`
- **Subnet Mask:** `255.255.255.0`
- **Default Gateway:** `10.4.0.1`
- **DNS (on Server):** 10.4.0.30
- **Alternate DNS (on PCs):** 8.8.8.8
- **Switch Type:** Hyper-V External Switch (A Hyper-V External Switch connects my VMs to the physical network through adapter)

---

## 🛠️ Setup Steps

### 1. Created Hyper-V VM
- Installed **Windows Server 2022**
- Assigned External Switch to VM for LAN access

### 2. Configured Server Network
- Static IP: `10.4.0.30`
- DNS: Server points to itself (10.4.0.30)
- Alternate DNS: `8.8.8.8`

### 3. Installed Server Roles
- Installed **Active Directory Domain Services**
- Installed **DNS Server**

### 4. Promoted to Domain Controller
- Created domain: `fardeen.local`

### 5. Configured Real Office PCs
- Set static IPs (no DHCP in office)
- Set DNS:
  - Preferred: `10.4.0.30` (server)
  - Alternate: `8.8.8.8` (Google DNS)
- Joined PCs to domain `fardeen.local`

### 6. Create Domain User
- In ADUC: Created user `testuser`
- Assigned password
- Enabled "must change password at next login"

### 7. Test Domain Join
- Logged into a PC with: `FAR\testuser`
- Success: Logged in, policies applied, server can manage the PC

---

## 📷 Screenshots

- `Screenshots/ipconfig-server.png`: Shows server IP setup
- `Screenshots/domain-joined.png`: PC joined to domain
- `Screenshots/ad-users.png`: Domain user creation

---

## 📌 Notes

- No DHCP server used. Static IPs are manually set.
- External switch ensures server and PCs are on the same physical LAN.
- PCs retain internet access by setting alternate DNS to `8.8.8.8`.

---

## 🧠 What I Learned

- Setting up and promoting a Windows Server to a DC
- Managing DNS and Domain structure
- Joining real PCs to a domain safely
- Remote access and basic GPO management
