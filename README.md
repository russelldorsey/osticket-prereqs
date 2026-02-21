<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Create an Azure Virtual Machine Windows 10
- Install/Enable IIS in Windows with CGI
- Create the directory C:\PHP
- Open IIS as an Admin
- Register PHP from within IIS
- Install osTicket v1.15.8
- Install HeidiSQL
- Continue Setting Up osTicket
- Installation Complete
- Clean Up

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First, create a Microsoft Azure account if you do not already have one. Once your account is set up, sign in and use the search bar at the top of the portal to search for Virtual Machines. Select Virtual Machines, then click Create.

Under Project Details, select Create new in the Resource group section. Enter a name for your resource group. You can choose any name. For example, I named mine osTicket because I am using this virtual machine for osTicket.

Next, under Instance Details, enter a name for your Virtual Machine. You can choose any name. I used osTicket-vm.

For Region, select the location closest to you.

Under Image, select Windows 10 Version 22H2 x64 Gen2. This option should allow you to choose the D2s_v3 size, which includes 2 vCPUs and 8 GiB of memory.

If that size is not available, try selecting a different Region and/or Image until you find a virtual machine size similar to 2 vCPUs and 8 GiB of memory.

Next, create a username and password for the virtual machine. You may choose any username and password you prefer.

Make sure to check the Licensing box.

Finally, click Review + Create, then click Create again.

Your virtual machine will now begin deploying.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
