<h1>Active Directory Home Lab</h1>

<h2>Description</h2>
The project involves setting up a Basic Home Lab Running Active Directory (Oracle VirtualBox) and adding users using PowerShell.
<br />


<h2>Utilities and Languages Used</h2>

- <b>Oracle VirtualBox</b>
- <b>PowerShell</b> 


<h2>Environments Used </h2>

- <b>Windows Server 2025</b> 
- <b>Windows 10</b> 

<h2>Program walk-through:</h2>

# 🖥️ Windows Server & Client Virtual Lab Setup Guide

This guide covers the steps to build a virtual lab using **Oracle VirtualBox** with **Windows Server 2025** and **Windows 10** client, simulating a domain environment using Active Directory.

---

## 📦 Virtual Machine Setup

### 1. Download & Install VirtualBox
- Get VirtualBox from: [https://www.virtualbox.org](https://www.virtualbox.org)

### 2. Create a Virtual Network in VirtualBox
- Go to **File > Host Network Manager**.
- For server, it neds two network adapters, using NAT Network for internet, and Internal Network for network.
- For client, use only Internal Network for network. 

### 3. Create Two Virtual Machines
- **VM 1: Server**
  - OS: Windows Server 2025 (64-bit)
  - RAM: At least 2 GB
- **VM 2: Client**
  - OS: Windows 10 (64-bit)
  - RAM: At least 2 GB

---

## 🧰 Windows Server 2025 Configuration

### 1. Installation
- Download from [Microsoft Evaluation Center](https://www.microsoft.com/en-us/evalcenter/)
- Mount ISO and install on the server VM.

### 2. Basic Setup
- Set a **static IP address** before promoting to Domain Controller 
- Rename the machine (e.g., `Server01`, `DC`).

### 3. Install & Configure Active Directory Domain Services (AD DS)
- Promote server to a **Domain Controller** (e.g., `example.local`or `mydomain.com`).
- Install DNS during promotion.
- Reboot after setup.

### 4. Active Directory Tasks
- Create **Organizational Units (OUs)**.
- Create new users, e.g. a-mtse (a = admin, m=Mike (First Name), tse = Tse (Surname).
- Promote a user, e.g. a-mtse, to **Domain Admin**.
- Practice:
  - Creating/deleting OUs
  - Creating/deleting users
  - Resetting passwords
  - Disabling/enabling users

### 5. Install Routing and Remote Access
- Enable **NAT (Network Address Translation)**.
- Add a second network adapter if needed.

### 6. Set Up DHCP Server
- Add the **DHCP role**.
- Create a **DHCP scope**.
- Configure DHCP options (e.g., default gateway, DNS server).
- Authorize DHCP server in AD.
- Add IP address of server/router // Configure DHCP options including default gateway (server's IP) and DNS server (server's IP).

---

## 🧑‍💻 Active Directory Tasks

- ✅ Creating Active Directory Users  
- 🔁 Resetting User Passwords  
- 🗂️ Creating and Deleting Organizational Units  
- ❌ Deleting and Disabling Users  
- 🛡️ Creating and Linking GPOs (Group Policy Objects)

---

## 💻 Windows 10 Client Setup

### 1. Install Windows 10 in VM
- Download ISO from: [https://www.microsoft.com/en-gb/software-download/windows10](https://www.microsoft.com/en-gb/software-download/windows10)

### 2. Configure Networking
- Use the same **VirtualBox network** as the server (i.e. Internal Network).
- Set to get IP from DHCP.

### 3. Join Domain
- Right-click **This PC > Properties > Change settings**.
- Click **Change...**, then join domain (e.g., `example.local` or `mydomain.com`).
- Use domain admin credentials to authorize.

### 4. Verify
- Log in with domain user.
- Check **IP address leases** on DHCP server.

---

## ✅ Final Checklist

- [x] VirtualBox installed and VMs created  
- [x] Windows Server 2025 installed and configured  
- [x] Active Directory Domain configured  
- [x] NAT and DHCP set up  
- [x] Client joined to domain successfully  
- [x] Active Directory tasks tested

---

> 💡 This setup is ideal for practicing Windows Server skills, Active Directory management, and domain-based networking in a safe environment.




<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
