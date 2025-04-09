<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# 🎫 osTicket - Prerequisites and Installation Guide

This walkthrough provides step-by-step instructions to install the open-source help desk ticketing system, **osTicket**, using a Windows 10 Virtual Machine in Microsoft Azure. You'll also install and configure several necessary components like IIS, PHP, MySQL, and more.

---

## 🧰 Tools and Technologies Used

- Microsoft Azure (Virtual Machines / Compute)
- Remote Desktop Protocol (RDP)
- Internet Information Services (IIS)

---

## 💻 Operating System Used

- Windows 10 (21H2)

---

## ✅ Prerequisites

- Microsoft Azure account
- Windows 10 Virtual Machine (with 4 vCPUs)
- osTicket installation files ([Download here](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6))

---

## 🛠️ Installation Steps

### ☁️ Step 1: Create an Azure Virtual Machine (Windows 10, 4 CPUs)

- Follow the Azure VM creation tutorial [here](https://github.com/kmoore848623/Azure-VM).

---

### 📂 Step 2: Download Installation Files

- Download the necessary files from [this Google Drive link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6).

---

### 🌐 Step 3: Install/Enable IIS with Required Features

- Open Control Panel > Programs > Turn Windows features on or off
- Enable:
  - CGI (under Application Development Features)
  - All Common HTTP Features
  - IIS Management Console

![IIS Features Screenshot](https://github.com/user-attachments/assets/8f894229-465c-46ef-96f9-a0241ef86ad8)

---

### 🧩 Step 4–9: Install Prerequisites

4. Install PHP Manager (PHPManagerForIIS_V1.5.0.msi)  
5. Install URL Rewrite Module (rewrite_amd64_en-US.msi)  
6. Create directory `C:\PHP`  
7. Extract PHP 7.3.8 to `C:\PHP`  
8. Install `VC_redist.x86.exe`  
9. Install MySQL 5.5.62 and configure root password  

---

### ⚙️ Step 10: Configure IIS for PHP

- Register PHP in PHP Manager
- Select `php-cgi` in `C:\PHP`
- Restart IIS

![PHP Manager](https://github.com/user-attachments/assets/c4ea48b6-e9f8-4d02-b667-f56b2f173236)

---

### 🚀 Step 11: Install osTicket

- Extract the osTicket `upload` folder to `C:\inetpub\wwwroot\osTicket`
- Restart IIS
- Browse to: Sites > Default Web Site > osTicket > Browse *:80

![osTicket Setup](https://github.com/user-attachments/assets/85e2301f-ddb7-4998-b0a1-43e21ee211e8)

---

### 🔧 Step 12: Enable Required PHP Extensions

- Enable:
  - `php_imap.dll`
  - `php_intl.dll`
  - `php_opcache.dll`

---

### 🔐 Step 13: Configure File Permissions

- Rename:
  - From: `ost-sampleconfig.php`
  - To: `ost-config.php`
- Set full control permissions for "Everyone"

![Permissions Screenshot](https://github.com/user-attachments/assets/9ebf7796-12e2-408d-bcce-5a96777ff3ec)

---

### 🧑‍💻 Step 14: Finish Setup in Browser

- Fill out helpdesk and admin details

![Final Setup Screenshot](https://github.com/user-attachments/assets/25a61db1-57ad-4607-a268-e2097e0d111c)

---

### 🗃️ Step 15: Create Database in HeidiSQL

- Connect as root
- Create a new database named `osTicket`

![HeidiSQL Screenshot](https://github.com/user-attachments/assets/d86eb6c4-ff45-4cac-a51b-758be3763b98)

---

### 🏁 Step 16: Complete Web-Based Setup

- Enter:
  - MySQL Database: `osTicket`
  - Username: `root`
  - Password: *your root password*

![Install Now Screenshot](https://github.com/user-attachments/assets/b1fc524f-7462-4e9e-8f13-d29219b897ed)

---

### 🧹 Step 17: Post-Installation Cleanup

- Delete contents of `C:\inetpub\wwwroot\osTicket\setup`
- Modify `ost-config.php` permissions to read-only

---

🎉 Congratulations! You have successfully installed osTicket and its full stack of prerequisites on a cloud-hosted Windows 10 VM.
