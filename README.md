# IT-SysAdmin Project  
# Windows Server 2022 Domain Controller Lab

In this project, I simulated a real-world System Administrator environment using **Hyper-V**, **Windows Server 2022**, and **physical office computers**.  
My goal was to create a fully functional **Domain Controller**, connect real PCs to the domain, and manage users through **Active Directory**.

---

## 🌐 Network Overview

- **Server IP:** `10.4.0.30`  
- **Subnet Mask:** `255.255.255.0`  
- **Default Gateway:** `10.4.0.1`  
- **DNS (on Server):** `10.4.0.30`  
- **Alternate DNS (on PCs):** `8.8.8.8`  
- **Switch Type:** Hyper-V External Switch (I used an external switch to connect my VM to the physical network through the host adapter)

---

## 🛠️ Setup Steps

### 1. Created Hyper-V VM  
- I installed **Windows Server 2022**  
- I assigned an **External Switch** to the VM to enable LAN access

### 2. Configured Server Network  
- I configured a static IP: `10.4.0.30`  
- I set the DNS to point to the server itself (10.4.0.30)  
- I added an alternate DNS: `8.8.8.8`

### 3. Installed Server Roles  
- I installed **Active Directory Domain Services**  
- I installed the **DNS Server** role

### 4. Promoted to Domain Controller  
- I promoted the server to a Domain Controller and created the domain: `fardeen.local`

### 5. Configured Real Office PCs  
- I manually set static IPs on each physical PC (since there was no DHCP in the office)  
- I set the DNS:
  - Preferred: `10.4.0.30` (server)
  - Alternate: `8.8.8.8` (Google DNS)  
- I joined the PCs to the domain `fardeen.local`

### 6. Created Domain User  
- In **Active Directory Users and Computers (ADUC)**, I created a user account named `testuser`  
- I assigned a password  
- I enabled the setting "User must change password at next login"

### 7. Tested Domain Join  
- I logged into a physical PC using: `FAR\testuser`  
- The login was successful; policies were applied, and I could manage the PC through the domain controller

---

## 📷 Screenshots

## 📷 Screenshots

### 🔧 Server IP Setup
![Server IP Configuration](Screenshots/ipconfig-server.png)

- `Screenshots/domain-joined.png`: PC joined to domain  
- `Screenshots/ad-users.png`: Domain user creation
 
- `Screenshots/domain-joined.png`: PC joined to domain  
- `Screenshots/ad-users.png`: Domain user creation

---

## 📌 Notes

- I didn’t use a DHCP server; all IPs were manually configured  
- The external switch allowed my server VM and physical PCs to communicate over the same LAN  
- Internet access was preserved on the PCs by using `8.8.8.8` as the alternate DNS

---

## 🧠 What I Learned

- How to install and promote a **Windows Server** to a **Domain Controller**  
- How to manage **DNS settings** and create a local domain  
- How to safely **join real PCs to a domain**  
- Basic experience with **Group Policy** and **user management** in Active Directory  
