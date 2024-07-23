<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />




<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure
- Windows 10 Virtual Machine (VM) with 4 Virtual CPUs
- osTicket Installation Files


<h2>Installation Steps</h2>

<h3> Step 1: Create an Azure Virtual Machine (Windows 10 with 4 CPUs)</h3>

- Go [here](https://portal.azure.com/).

<h3> Step 2: Installation Files</h3>

- Go [here](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6) and download the installation files.

- These files will be needed to install osTicket and some dependencies.

<h3>Step 3: Install / Enable IIS in Windows WITH CGI and Common HTTP Features and IIS Management Console</h3>

- Right-click 'Start' (Windows logo) in the bottom left hand corner and select 'Run'. Type 'control' and press 'OK'.
- Click 'Programs' and select 'Turn Windows features on or off'.
- Scroll down to 'Internet Information Services' and clip the + symbol to expand.
- Expand 'World Wide Web Services'. Expand 'Application Developement Features' and click the box next to 'CGI' to turn feature on.
- Collapse 'Application Development Features' and expand 'Common HTTP Features'. Enable all of the features underneath and press 'OK' to apply changes.


<div align="center"><img src="https://github.com/user-attachments/assets/8f894229-465c-46ef-96f9-a0241ef86ad8"></div>

<div align="center"><img src="https://github.com/user-attachments/assets/e6cac2e8-8a62-4e54-b528-fdbeaa46a855"></div>




<h3>Step 4: Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) from the installation files.
</h3>

<h3>Step 5: Install the Rewrite Module (rewrite_amd64_en-US.msi) from the installation files.
</h3>

<h3>Step 6: Create the directory C:\PHP.
</h3>

<h3>Step 7: Download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) from the installation files and unzip the contents into C:\PHP.
</h3>

<h3>Step 8: Install VC_redist.x86.exe from the installation files.
</h3>

<h3>Step 9: Install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the installation files.</h3>

- Select Typical setup.
- Launch the configuration wizard after the install.
- Select the standard configuration.
- Select a password for the root account.

<h3>Step 10: Internet Information Services (IIS) Configuration</h3>

- Click on 'Start'(Windows logo) and type IIS into the search bar.
- Right-click 'Internet Information Services' and run as administrator.
- Double-click 'PHP Manager'. Click 'Register new PHP version'.
- Browse to the C:\PHP directory, select 'php-cgi' executable, and press OK.
- Click on the name of your server on the left hand side to go back. Then click 'Restart' on the right hand side to restart the server.

<div align="center"><img src="https://github.com/user-attachments/assets/c4ea48b6-e9f8-4d02-b667-f56b2f173236"></div>

<h3>Step 11: Install osTicket v1.15.8</h3>

- Download the zip file, extract, and copy the 'upload' folder to c:\inetpub\wwwroot.
- Within c:\inetpub\wwwroot, Rename 'upload' to 'osTicket'.
- Open IIS, click 'Restart' to restart the server.
- In IIS, look to the top left corner and go 'Sites'-> 'Default web Site' -> 'osTicket'.
- On the right, click 'Browse *:80'. This will bring up osTicket setup in your web browser.

<div align="center"><img src="https://github.com/user-attachments/assets/85e2301f-ddb7-4998-b0a1-43e21ee211e8)"></div>

<h3>Step 12: Enable Extensions in IIS</h3>

- Go back to IIS -> 'Site's -> 'Default Web Site' -> 'osTicket'
- Double-click 'PHP Manager'.
- Click 'Enable or Disable an Extension' at the bottom under PHP Extensions.
- Right-click and enable the following:
    - php_imap.dll
    - php_intl.dll
    - php_opcache.dll
- Refresh the osTicket site in your browser to observe the changes.

<h3>Step 13: Rename: 'ost-config.php'</h3>

- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
- Right-click 'ost-config.php'.
- Open 'Properties' -> 'Security' -> 'Advanced' -> 'Permissions'.
- Select 'Disable Inheritance' -> 'Remove all inherited permissions from this object'.
- Select 'Add' -> select 'Principal' -> type in 'everyone' > select 'Check Names' > select OK.
- Under 'Basic Permissions' click the box for 'Full control' and click 'OK' to apply.

<div align="center"><img src="https://github.com/user-attachments/assets/9ebf7796-12e2-408d-bcce-5a96777ff3ec)"></div>

<div align="center"><img src="https://github.com/user-attachments/assets/120510c9-48d6-4f8e-b0b7-0662f6619823"></div>

<div align="center"><img src="https://github.com/user-attachments/assets/3a9828e5-9b79-460d-9588-43b73567a780"></div>

<h3>Step 14: Continue setting up osTicket in Browser</h3>

- Go back to the browser and click Continue
  - Name: Whatever you want to call your help desk
  - Email: whatever email 
  - First Name: your first name
  - Last Name: your last name
  - Email Address: whichever email you want (needs to be different from the previous email)
  - Username: select a username 
  - Password: select a passowrd
 
<div align="center"><img src="https://github.com/user-attachments/assets/25a61db1-57ad-4607-a268-e2097e0d111c"></div>

<h3>Step 15: Install HeidiSQL from the installation files.</h3>

- Open HeidiSQL -> Select "New" at the bottom-left corner of the screen
   - User: root
   - Password: the password you selected when setting up MySQL
- Select 'Open'.
- On the left hand side, right-click 'Unnamed' -> select 'Create New' -> 'Database'
- Name it osTicket and select 'OK'.

<div align="center"><img src="https://github.com/user-attachments/assets/d86eb6c4-ff45-4cac-a51b-758be3763b98"></div>
<div align="center"><img src="https://github.com/user-attachments/assets/44687039-3b7f-43a1-a8c1-d74f99f5d0eb"></div>

<h3>Step 16: Continue setting up osTicket in Browser</h3>

- Go back to the browser
	- MySQL Database: osTicket (the one you just created in HeidiSQL)
	- MySQL Username: root
	- MySQL Password: the password you selected when setting up MySQL
	- Click 'Install Now'.

<div align="center"><img src="https://github.com/user-attachments/assets/b1fc524f-7462-4e9e-8f13-d29219b897ed"></div>

Congratulations! You have sucessfully installed osTicket and all of its pre-requisite files!


<h3>Step 17: Post-Installation Cleanup</h3>

- Go to C: > inetpub > wwwroot > osTicket > Setup
    - Delete the contents in the Setup folder
    - Afterwards, delete the Setup folder
- Go to C: -> Inetpub -> wwwroot -> osTicket -> Include
    - Right-click on 'ost-config.php'. 
    - Select 'Securities' > 'Advanced' > Click on "everyone" > edit to change permissions
	- Allow everyone to only have "Read and execute" permission, then select 'OK' -> 'Apply' -> 'OK'.


























