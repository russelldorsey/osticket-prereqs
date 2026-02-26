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
- Install files PHP Manager and rewrite amd64
- Create the directory C:\PHP
- Unzip PHP 7.3.8 into the directory C:\PHP
- Install files VC_redist.x86 and MySQL 5.5 62
- Open IIS as an Admin
- Register PHP from within IIS
- Reload IIS
- Install osTicket v1.15.8
- Reload IIS
- Continue Setting Up osTicket
- Installation Complete
- Clean Up

<h2>Installation Steps</h2>

<p>
<img width="2191" height="1410" alt="Screenshot 2026-02-21 115911" src="https://github.com/user-attachments/assets/c4a0499f-dff4-4bda-be7f-6b6518346dc2" />
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
<img width="1120" height="661" alt="Screenshot 2026-02-21 130853" src="https://github.com/user-attachments/assets/b6516249-c058-4926-b951-79107f78e870" />
</p>
<p>
Log in to your virtual machine (osticket-vm) using Remote Desktop. Once you are inside the VM, download the osTicket-Installation-Files.zip file and save it to your desktop. After the download is complete, right-click the file and select Extract All to unzip it. When finished, you should see a folder on your desktop named osTicket-Installation-Files. This folder contains the files you will use to install osTicket and its required dependencies.

Next, install and enable IIS with CGI. Open the Control Panel and select Programs, then click Turn Windows features on or off. Expand Internet Information Services, then expand World Wide Web Services, followed by Application Development Features. Check the box labeled CGI, then click OK to complete the installation.
</p>
<br />

<p>
<img width="1123" height="631" alt="Screenshot 2026-02-21 133637" src="https://github.com/user-attachments/assets/69fc3986-3eaf-43f9-b6fd-27aab4e57761" />
</p>
<p>
Open the osTicket-Installation-Files folder on your desktop. First, locate the file named PHPManagerForIIS_V1.5.0.msi and double-click it to begin the installation. Follow the prompts to complete the installation of PHP Manager for IIS.

Next, in the same osTicket-Installation-Files folder, find the file named rewrite_amd64_en-US.msi. Double-click this file and follow the installation steps to install the Rewrite Module.
</p>
<br />

<p>
<img width="1123" height="632" alt="Screenshot 2026-02-21 134436" src="https://github.com/user-attachments/assets/d48db8d1-06b6-4784-9432-3ec64873de34" />
</p>
<p>
Open the Start menu, search for File Explorer, and open it. Click This PC, then under Devices and drives, double-click the Windows (C:) drive. Inside the C: drive, right-click in an empty area, select New, then click Folder. Rename the new folder PHP. This creates a new directory located at C:\PHP.
</p>
<br />

<p>
<img width="1120" height="630" alt="Screenshot 2026-02-21 143107" src="https://github.com/user-attachments/assets/9af3925d-7891-4fcc-8c97-22650b544585" />
</p>
<p>
Open the osTicket-Installation-Files folder on your desktop, locate the zip file named php-7.3.8-nts-Win32-VC15-x86 and right-click it, then select Extract All. Before clicking Extract, choose Browse to select a destination for the files. Search for and select the C:\PHP folder that you created earlier. Once the correct folder is selected, click Extract to unzip the files into the C:\PHP directory.
</p>
<br />

<p>
<img width="1123" height="633" alt="Screenshot 2026-02-21 145034" src="https://github.com/user-attachments/assets/a83c9ec3-35a5-47e4-af93-0c723cb7af14" />
</p>
<p>
Open the osTicket-Installation-Files folder on your desktop and locate the file named VC_redist.x86.exe. Double-click the file and follow the prompts to complete the installation.

Next, in the same folder, find mysql-5.5.62-win32.msi and double-click it to begin installing MySQL 5.5.62. Choose the Typical Setup option during installation. After the installation finishes, make sure to select Launch Configuration Wizard. In the Configuration Wizard, choose Standard Configuration. When prompted, set the username to root and the password to root, then complete the setup. Normally, you would create a more secure username and password. However, for practice purposes in osTicket, using root makes it easier to remember.
</p>
<br />

<p>
<img width="784" height="640" alt="Screenshot 2026-02-21 151301" src="https://github.com/user-attachments/assets/0254b1c2-f721-4983-af47-150eb0bbda79" />
</p>
<p>
Open the Start menu and search for IIS. When it appears in the search results, right-click it and select Run as administrator or on the right side select the same, Run as administrator. This will open the IIS Manager and display the osTicket-vm Home screen.
</p>
<br />

<p>
<img width="955" height="1026" alt="Screenshot 2026-02-21 153027" src="https://github.com/user-attachments/assets/93c1aa90-a057-4d9c-ad56-90618fa5cdd0" />
</p>
<p>
Register PHP from within IIS Manager. From the osTicket-vm Home screen, double-click PHP Manager. Then select Register new PHP version. In the Register new PHP version window, click the 3 dots. Then double-click the PHP folder, double-click the php-cgi application, and select OK.

</p>
<br />

<p>
<img width="957" height="1036" alt="Screenshot 2026-02-21 155601" src="https://github.com/user-attachments/assets/3e6e2908-0767-461e-acb7-da4899666dfd" />
</p>
<p>
To reload IIS Manager, go to the osTicket-vm Home screen. On the left side under Connections, right-click the osTicket-vm(osTicket-vm\labuser) folder and select Stop. Wait a few seconds, then right-click it again and select Start. You can also restart IIS Manager from the right side of the screen under Actions. In the Manage Server section, click Stop, wait a few seconds, and then click Start to restart the server.
</p>
<br />

<p>
<img width="1122" height="810" alt="Screenshot 2026-02-21 161624" src="https://github.com/user-attachments/assets/c9b4137c-0ce5-4fe1-b0be-a7311fa36bdf" />
</p>
<p>
To install osTicket v1.15.8, open the osTicket-Installation-Files folder and locate the zip file named osTicket-v1.15.8.zip. Right-click the zip file and select Extract All to unzip it. After the files are extracted, open the extracted folder and copy the upload folder into it. Next, navigate to C:\inetpub\wwwroot and paste the upload folder into that directory. Once it has been pasted, rename the upload folder to osTicket. Be sure to type osTicket exactly as shown, with no spaces and the correct capitalization.
</p>
<br />

<p>
<img width="957" height="1036" alt="Screenshot 2026-02-21 155601" src="https://github.com/user-attachments/assets/02b93031-3781-4dc2-9f37-ad1073008149" />
</p>
<p>
Reload IIS Manager again using the same following steps. Go to the osTicket-vm Home screen. On the left side under Connections, right-click the osTicket-vm(osTicket-vm\labuser) folder and select Stop. Wait a few seconds, then right-click it again and select Start. You can also restart IIS Manager from the right side of the screen under Actions. In the Manage Server section, click Stop, wait a few seconds, and then click Start to restart the server.
</p>
<br />

<p>
<img width="1918" height="1037" alt="Screenshot 2026-02-26 101256" src="https://github.com/user-attachments/assets/4975ce60-7adc-433a-a709-03e8f2686994" />
</p>
<p>
Next, load the osTicket site. Open IIS Manager and, under Connections, expand the osTicket-vm (osTicket-vm\labuser) folder. Then expand the Sites folder, then expand the Default Web Site folder, and click on osTicket. Then on the right side of IIS Manager, under Manage Folder, under Browse Folder, click on Browse *:80 (http). This will open the osTicket Installer page in Microsoft Edge.
</p>
<br />

<p>
<img width="1916" height="1032" alt="Screenshot 2026-02-26 114923" src="https://github.com/user-attachments/assets/73b4df55-cb6a-4a0b-b8a5-5521d79eafb6" />
</p>
<p>
Notice that some extensions are not enabled. Return to IIS Manager, expand the Sites folder, then expand the Default Web Site folder, and click on osTicket. Double-click PHP Manager, then click on Enable or disable an extension. On the right side of ISS Manager under Actions, click Enable for the following extensions: php_imap.dll, php_intl.dll, and php_opcache.dll. After enabling these extensions, refresh the osTicket Installer site in Microsoft Edge and observe the changes.
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
