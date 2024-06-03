<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
In this lab, I install the ticketing system osTicket from the ground up using neccessary installation files. The lab is done in Windows 10 Pro 22H2 VM made on Microsoft Azure. I will outline the steps using pictures in this github repository. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- Internet Information Services (IIS)
- MySQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6


<h2>Installation Steps</h2>


1.) The first thing you are going to want to do is create a virtual machine by going to https://portal.azure.com/. Setup your virtual machine with Windows 10 Pro, version 22H2. Note, you will want to create a virtual machine with atleast 2 vcpus and 16 gbs of memory.

2.) With the public IP address we will now connect to the VM using Remote Desktop Connection on our Windows computer. We will use the search bar at the bottom of the screen and type in Remote Desktop Connection and select it to open. Now paste the VM’s public IP address and click connect to initialize our remote connection. Note: The VM may take a moment to start up
 
</p>
<br />

<p>
<img src="https://i.imgur.com/SBd2kxK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://i.imgur.com/0no6NJM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
3.) Once completed, we will click on the “More choices” option and “Use a different account.” Now log in using the credentials we made when setting up the VM and click “Ok”


<p>
<img src="https://i.imgur.com/d0GqyIh.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://i.imgur.com/3DaExaS.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
4.) To start we will need to enable Internet Information Services (IIS). To do this open the Control Panel -> Programs -> Turn Windows Features On or Off. 
We will then check Internet Information Services and expand it, expand World Wide Web Services, and Application Development Features. Check the CGI box. Now under Common HTTP Features check HTTP Redirection and WebDAV Publishing and click ok. Then IIS will be installed.


[X] CGI
[X] Common HTTP Features
  
<p>
<img src="https://i.imgur.com/kwYoh4V.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://i.imgur.com/wyBnhq6.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>


***NOTE*** Make sure all Common HTTP Features are checked.
 
 
Next is to test the connectivity to the web server which can be done by opening a web browser and type 127.0.0.1 and it should look like this
  
<p>
<img src="https://imgur.com/eICujoq.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
  
  
5.) Now it’s time to make use of the installations, we will start with downloading and installing PHP Manager. Click Open File on the top right corner and install with default settings, agreeing to the License Agreement.
<p>
<img src="https://i.imgur.com/Qi3JgOy.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  
6.) Now we are going to install rewrite_amd64_en-US.msi and open the file using the same method. We will agree to the license agreement and click finish
<p>
<img src="https://i.imgur.com/x5ptpWe.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
7.) After a successful installation of Rewrite Module we will open up file explorer, go to This Pc > Windows (C:) and create a folder named PHP which we will use to extract the contents of the PHP zip file which can be found in This PC > Downloads
<p>
<img src="https://i.imgur.com/WbGdbVO.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

8.) After created we will download and install the Redist executable (.exe)
  
  !! ATTENTION !!
If this appears, choose to “Keep” the file:
  
<p>
<img src="https://imgur.com/xZv1Yhw.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/YwBhqo0.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

9.) Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe from the installation files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe. 
<p>
<img src="https://i.imgur.com/4RO41Qx.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>


10.) Next step is to download and install php-7.3.8, right click it and extract all into the PHP folder we just created in the C drive.

Now download and install mysql-5.5.62, open the file, accept the agreement, do a typical install. Ensure “Launch the MySQL Instance Configuration Wizard” is checked and click finish. 
<p>
<img src="https://i.imgur.com/PdNVV4Q.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

Make sure to click standard configuration, install as windows service, and create a username and password for the root account. Next > Execute > Finish. This will install osTicket’s database to store data and tickets.
  
<p>
<img src="https://i.imgur.com/1lQnARR.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
With that done we will go to the start menu and search for IIS, right click it and run as an administrator

Navigate to the PHP Manager button and double click to Register new PHP version. Path the install to the PHP folder we made within the C: drive, and click the PHP executable (.exe) and click ok

<p>
<img src="https://i.imgur.com/pjdn5c3.png height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
11.) Now that we have the files downloaded and installed we will want to search for IIS in the windows search bar. Open IIS as an administrator.
  The program should look like this.
  
<p>
<img src="https://imgur.com/rgdZwmM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
12.) We will now want to register PHP from within IIS.
  Click on PHP Manager
  
<p>
<img src="https://imgur.com/vvTLNBH.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Register new PHP version.
  
<p>
<img src="https://imgur.com/qdbn5zQ.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
You will want to provide a path to the php executable file (php-cgi.exe)). 
  Go to C Drive -> PHP -> click on php-cgi file.
  
<p>
<img src="https://imgur.com/oJZ0gp9.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Restart the IIS server.
  
<p>
<img src="https://imgur.com/CJ3RUbG.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
13.) Install osTicket v1.15.8
  -Download osTicket from the Installation Files Folder
  -Extract and copy "upload" folder to c:\inetpub\wwwroot
  -Within c:\inetpub\root, Rename "upload" to "osTicket"
  
  Reload IIS again.
  
14.) On IIS go to sites -> Default -> osTicket
  -On the right, click “Browse *:80”
  
<p>
<img src="https://imgur.com/Yw55d5b.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Some extensions are not enabled on the osTicket browser.
  
<p>
<img src="https://imgur.com/eJIsGTn.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  To enable the extensions:
  -Go back to IIS, sites -> Default -> osTicket
  -Double click PHP manager
  -Click "Enable or disable an extension"
  
<p>
<img src="https://imgur.com/vvTLNBH.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/uigyKjb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  We will want to enable three extensions from here.
  
  1.) php_imap.dll
 
  2.) php_intl.dll
  
  3.) php_opcache.dll
  
<p>
<img src="https://imgur.com/cOem7Nb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
15.) Once we have those extensions enabled in IIS, we are going to want to rename one of the files in our osTicket folder.
  Go into the file explorer and search for C;\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
  
  We are going to rename the ost-sampleconfig.php to ost-config.php
  
  Now that we have renamed the files, right click on the file and go to properties.
  From there click security, click on advance, and disable the inheritance.
  We will select Remove all inherited permissions from this object.
  
  Now we will add new permissions.
  
  Click Add
  
<p>
<img src="https://imgur.com/VPZvOdo.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
Select a principal
  
<p>
<img src="https://imgur.com/PoGk34d.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
 Type "Everyone" in the box.
  
<p>
<img src="https://imgur.com/F4H3ppM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Make sure Full Control and all the other boxes are checked.
  
<p>
<img src="https://imgur.com/rbbGqwB.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Click Apply and Ok.
  
<p>
<img src="https://imgur.com/saRO3y5.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Once that is done we will continue to setup osTicket in the browser. Click Continue on the osTicket browser page.
  Fill out the page as required except the Database Settings at the bottom of the page. We will get to that. 
  
  We will want to download and install HeidiSQL from the Installation Files. 
  
<p>
<img src="https://imgur.com/i7a4gWC.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  When the program is open we will create a new session in it.
  
<p>
<img src="https://imgur.com/g5M1i61.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  We want to make sure the username is root and the password is Password1.
  
<p>
<img src="https://imgur.com/LEAZNOc.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Once we are connected to the session we will go back to the browser to finish setting everything up. Under the Database Settings in the browser the username will be root and the password will be Password1.
  
  We will now create a new database within HeidiSQL. In Heidi right click on the left side where is says "Unnamed", select "create new", and then select "database". Name the new database osTicket. Once we have the new database setup go back to the osTicket browser and under MySQL Database type in osTicket.
  
<p>
<img src="https://imgur.com/0rG1AJm.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  The last step is to do some clean up. We will want to delete the setup folder in our system. 
  -Delete: C:\inetpub\wwwroot\osTicket\setup
  Only delete the setup folder and nothing else.
  
  We then will want to set the permissions back to "Read" only in the ost-config.php file.
  
<p>
<img src="https://imgur.com/wFr0pkK.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/jsJOPyn.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  The last step after that is to login to osTicket on the browser.
  
<p>
<img src="https://imgur.com/uHVdDsx.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  Congrats! You have now successfully installed and setup osTicket!
