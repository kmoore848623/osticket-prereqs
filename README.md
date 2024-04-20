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

<h3>Step 1: Create an Azure Virtual Machine (Windows 10 with 4 CPUs)</h3>

- Go [here](https://portal.azure.com/) and click on 'Resource groups' underneath Azure Services.

![Screenshot 2024-04-20 060710](https://github.com/kmoore848623/osticket-prereqs/assets/157086384/84dc2a56-ef25-4c7e-8e8e-6663e6b1c654)

- Click 'Create'.

![Screenshot 2024-04-20 060936](https://github.com/kmoore848623/osticket-prereqs/assets/157086384/6e2dca3c-f137-46a2-bcab-477272fc254e)

- Under Project details, name your Resource group.
- Under Resource details, select your preferred region.
- Click 'Review + Create' at the bottom left of your screen.

![Screenshot 2024-04-20 061303](https://github.com/kmoore848623/osticket-prereqs/assets/157086384/f7551b32-16ba-45da-a487-d6c4dc2213ae)

- Click 'Create' to create your resource group.

![Screenshot 2024-04-20 061703](https://github.com/kmoore848623/osticket-prereqs/assets/157086384/ce98924e-930f-4564-8de8-16929274c726)

- Go [here](https://portal.azure.com/) and click on 'Virtual machines' underneath Azure Services.

![Screenshot 2024-04-20 054952](https://github.com/kmoore848623/osticket-prereqs/assets/157086384/7aa5268b-5e4b-4c71-bc54-4c9dfac8ad06)

- Click 'Create'.
- Select 'Azure virtual machine'.

![Screenshot 2024-04-20 063018](https://github.com/kmoore848623/osticket-prereqs/assets/157086384/dae99beb-c6b5-471f-be99-1d6c69694049)

- Select the same resource group, region, and create a name for your virtual machine.
- Select your preferred image.

![Screenshot 2024-04-20 063407](https://github.com/kmoore848623/osticket-prereqs/assets/157086384/46a0de79-461d-4d4b-a3ee-d2509cbb96fc)

- Select your preferred size.
- Select an username and password for the Administator account.
- Click 'Next' twice to get to the Networking tab.

![Screenshot 2024-04-20 064335](https://github.com/kmoore848623/osticket-prereqs/assets/157086384/adc0e245-b186-453c-86c5-8c600a733abb)

- When creating a virtual machine, a network interface is created for you. By default it creates a virtual network, subnet, IP address,etc.
- Click 'Review + Create'.

![Screenshot 2024-04-20 064826](https://github.com/kmoore848623/osticket-prereqs/assets/157086384/e5c7caef-1677-4bf0-adc2-b6b3826a02ee)

- Click 'Create'. This will start the deployment of your virtual machine.

![Screenshot 2024-04-20 065413](https://github.com/kmoore848623/osticket-prereqs/assets/157086384/c6dc410a-2f99-4042-b1fa-c9693557cf5c)

























