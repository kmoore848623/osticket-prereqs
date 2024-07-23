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

- Right-click Windows logo in the bottom left hand corner and select 'Run'. Type 'control' and press 'OK'.
- Click 'Programs' and select 'Turn Windows features on or off'.
- Scroll down to 'Internet Information Services' and clip the + symbol to expand.
- Expand 'World Wide Web Services'. Expand 'Application Developement Features' and click the box next to 'CGI' to turn feature on.
- Collapse 'Application Development Features' and expand 'Common HTTP Features'. Enable all of the features underneath and press 'OK' to apply changes.


![os1](https://github.com/user-attachments/assets/8f894229-465c-46ef-96f9-a0241ef86ad8)

![os2](https://github.com/user-attachments/assets/e6cac2e8-8a62-4e54-b528-fdbeaa46a855)




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


- osTicket Installation Files [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
	- Download Web Platform Installer > select Download Anyway > at the top right, select Open File
	- Follow the prompt to install Web Platform Installer
	- Open the Web Platform Installer

<p align="center">
<img src="https://i.imgur.com/0On2vKd.png" height="80%" width="80%" alt="Azure Free Account"/> <img src="https://i.imgur.com/V4p94mP.png" height="80%" width="80%" alt="Azure Free Services"/>
</p>

- Once Web Platform Installer is open, go to the top right of the screen and search for MySQL 5.5
- Go to MySQL Windows 5.5 and click Add
- Go to the top right again and search for PHP
	- Adjust the list to Sort by "name"
- Add all simple versions of x86 PHP up until 7.3
- Select Install at the bottom of the screen and it will tell you to create a username and password to complete the installation

<p align="center">
<img src="https://i.imgur.com/uWAVcRG.png" height="80%" width="80%" alt="Azure Free Account"/> <img src="https://i.imgur.com/MQmZfht.png" height="80%" width="80%" alt="Azure Free Services"/>
</p>


  - Username: root
  - Password: Password1
- Follow the prompt to complete the installation
- You might get a message stating that "some products have failed to install"
	- Ignore that message and select Finish
- Download and install the following from within the lab files: [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
  - PHP Version 7.3.8
  - PHP Manager 1.5.0 for IIS 10
  - Microsoft Visual C++ 2009 Redistributable Package


<p align="center">
<img src="https://i.imgur.com/zAPFRmU.png" height="70%" width="70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/DUiyQdt.png" height="70%" width="70%" alt="Azure Free Services"/>
</p>


<h3>Step 4: Install osTicket v1.15.8</h3>
     
- Download osTicket (download from within lab files: [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6))
- Right-click on the file and select Extract All
	- Open the new osTicket folder
		- Copy the Upload folder into C:\inetpub\wwwroot
		- Rename â€œUploadâ€ to â€œosTicketâ€


<p align="center">
<img src="https://i.imgur.com/BpL8IJE.png" height="80%" width="80%" alt="Azure Free Account"/> <img src="https://i.imgur.com/xSJD7yk.png" height="80%" width="80%" alt="Azure Free Services"/>
</p>
 
     

<h3>Step 5: Restart the IIS Server
</h3>

- Search for Internet Information Services (IIS) and select Open
	- Select Restart on the right-hand side 
- On the left side of the screen, select Virtualmachine > Sites > Default Website > osTicket
- On the right side of the screen, click â€œBrowse *:80â€
	- This should open osTicket in your web browser
- Before continuing, head back to IIS
- Open IIS


<p align="center">
<img src="https://i.imgur.com/OpBkwwj.png" height="80%" width="80%" alt="Azure Free Account"/> <img src="https://i.imgur.com/XNVSNia.png" height="80%" width="80%" alt="Azure Free Services"/>
</p>

<h3>Step 6: Enable Extensions in IIS
</h3>

- Go back to IIS > Sites > Default Web Site > osTicket
- Double-click PHP Manager
- Click â€œEnable or Disable an Extensionâ€ at the bottom of the screen under PHP Extensions
- Right-click and enable the following
    - php_imap.dll (Might be already enabled)
    - php_intl.dll
    - php_opcache.dll

 
     
 <p align="center">
<img src="https://i.imgur.com/GQfPOU8.png" height="80%" width="80%" alt="Azure Free Account"/> <img src="https://i.imgur.com/iCK6vst.png" height="80%" width="80%" alt="Azure Free Services"/>
</p>

<h3>Step 7: Refresh the osTicket Site in Your Browser
</h3>

- Refresh the osTicket site adn observe the change
	- Intl Extension should now have a green checkmark next to it


<p align="center">
<img src="https://i.imgur.com/ByfN2Fd.png" height="80%" width="80%" alt="Azure Free Account"/>



<h3>Step 8: Rename</h3>
 
- Open Windows Explorer and select C: > inetpub > wwwroot > osTicket > include
	- Rename the following file:
		- From: ost-SAMPLEconfig.php
		- To: ost-config.php


<p align="center">
<img src="https://i.imgur.com/DDTR8CD.png" height="80%" width="80%" alt="Azure Free Account"/>

<h3>Step 9: Assign Permissions to ost-config.php</h3>

- Right-click ost-config.php 
- Open Properties > Security > Advanced > Permissions 
- Select Disable Inheritance > Remove all inherited permissions from this object 

<p align="center">
<img src="https://i.imgur.com/pcFvK9d.png" height="80%" width="80%" alt="Azure Free Account"/>

- Afterwards, select Add > select Principal > type in "everyone" > select Check Names > select OK
	- Allow everyone full control (check all boxes) > Select apply > OK

<p align="center">
<img src="https://i.imgur.com/vUlpzTb.png" height="70%" width=70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/WZrk1F7.png" height="80%" width="80%" alt="Azure Free Services"/>
</p>

  
<h3>Step 10: Continue Setting Up osTicket in Browser</h3>

- Go back to the browser and click Continue
  - Name: Helpdesk
  - Email: whichever email you want
  - First Name: your first name
  - Last Name: your last name
  - Email Address: whichever email you want (needs to be different from the Helpdesk's default email)
  - Username: user_admin 
  - Password: Password1 
  
<p align="center">
<img src="https://i.imgur.com/1GfpPLs.png" height="80%" width="80%" alt="Azure Free Account"/>

<h3>Step 11: Download and Install HeidiSQL</h3>

- Head to osTicket Installation Files [link](https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
	- Download and install HeidiSQL
- Open HeidiSQL > Select "New" at the bottom-left corner of the screen
   - User: root
   - Password: Password
- Select Open
- On the left side, right-click Unnamed > select Create New > Database
- Name it â€œosTicketâ€ and select OK

 <p align="center">
<img src="https://i.imgur.com/mDBWQ5k.png" height="70%" width="70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/ADJYQyB.png" height="70%" width="70%" alt="Azure Free Services"/>
</p>

<h3>Step 12: Continue Setting Up osTicket by Filling Out the Fields</h3>

- Go back to the browser
	- MySQL Database: osTicket (the one you just created in HeidiSQL)
	- MySQL Username: root
	- MySQL Password: Password1
	- Finally, click Install Now

<p align="center">
<img src="https://i.imgur.com/Npqj9Us.png" height="80%" width="80%" alt="Azure Free Account"/>


ðŸŽ‰Congratulations! You have sucessfully installed osTicket adn all of its pre-requisite files!ðŸŽ‰

<p align="center">
<img src="https://i.imgur.com/F52ypHn.png" height="80%" width="80%" alt="Azure Free Account"/>

<h3>Tips!</h3>

- To create tickets as a user: http://localhost/osTicket/
- To log in as an Admin or helpdesk professional: http://localhost/osTicket/scp

<h3>Step 13: Post-Intallation Cleanup</h3>

- Go to C: > inetpub > wwwroot > osTicket > Setup
    - Delete the contents in the Setup folder
    - Afterwards, delete the Setup folder
- Go to C: > Inetpub > wwwroot > osTicket > Include
    - Right-click on ost-config.php 
    - Select Securities > Advanced > Click on "everyone" > edit to change permissions
	- Allow everyone to only have "Read and execute" permission, then select OK > Apply > OK
	
 <p align="center">
<img src="https://i.imgur.com/wucT3UN.png" height="70%" width="70%" alt="Azure Free Account"/> <img src="https://i.imgur.com/cPSx6VL.png" height="70%" width="70%" alt="Azure Free Services"/>
</p>	


Click [here](https://github.com/roslyndwilliams/post-install-config) to move on to part 2 of this tutorial!

























