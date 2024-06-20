<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
In this lab, I install the ticketing system osTicket from the ground up using neccessary installation files. I will outline the steps using pictures in this GitHub repository. <br />



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


1) Create a virtual machine by going to https://portal.azure.com/. Setup your virtual machine with Windows 10 Pro, version 22H2. Note, you will want to create a virtual machine with atleast 2 vcpus and 16 gbs of memory.

2) With the public IP address we will now connect to the VM using Remote Desktop Connection on our Windows computer. We will use the search bar at the bottom of the screen and type in Remote Desktop Connection and select it to open. Now paste the VM’s public IP address and click connect to initialize our remote connection. Note: The VM may take a moment to start up
 
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

  
3) Click on the “More choices” option and “Use a different account.” Now log in using the credentials we made when setting up the VM and click “Ok”


<p>
<img src="https://i.imgur.com/d0GqyIh.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://i.imgur.com/3DaExaS.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  
4) Enable Internet Information Services (IIS). To do this open the Control Panel -> Programs -> Turn Windows Features On or Off. 

 - We will then check Internet Information Services and expand it, expand World Wide Web Services, and Application Development Features. Check the CGI box. Now under Common HTTP Features check HTTP Redirection and WebDAV Publishing and click ok. Then IIS will be installed.


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
 
 
5) Test the connectivity to the web server which can be done by opening a web browser and type 127.0.0.1 and it should look like this
  
<p>
<img src="https://imgur.com/eICujoq.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
  
  
  
6) Now it’s time to make use of the installations, we will start with downloading and installing PHP Manager. Click Open File on the top right corner and install with default settings, agreeing to the License Agreement.
<p>
<img src="https://i.imgur.com/Qi3JgOy.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  
7) Install rewrite_amd64_en-US.msi and open the file using the same method. We will agree to the license agreement and click finish
<p>
<img src="https://i.imgur.com/x5ptpWe.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  
8) After a successful installation of Rewrite Module we will open up file explorer, go to This Pc > Windows (C:) and create a folder named PHP which we will use to extract the contents of the PHP zip file which can be found in This PC > Downloads
<p>
<img src="https://i.imgur.com/WbGdbVO.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>


9) After created we will download and install the Redist executable (.exe)
  
  !! ATTENTION !!
If this appears, choose to “Keep” the file:
  
<p>
<img src="https://imgur.com/xZv1Yhw.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
<p>
<img src="https://imgur.com/YwBhqo0.png" height="20%" width="20%" alt="Disk Sanitization Steps"/>
</p>
<p>


10) Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe from the installation files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe. 
<p>
<img src="https://i.imgur.com/4RO41Qx.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>


11) Download and install php-7.3.8, right click it and extract all into the PHP folder we just created in the C drive.

 - Download and install mysql-5.5.62, open the file, accept the agreement, do a typical install. Ensure “Launch the MySQL Instance Configuration Wizard” is checked and click finish.
 - Make sure to click standard configuration, install as windows service, and create a username and password for the root account. Next > Execute > Finish. This will install osTicket’s database to store data and tickets.

<p>
<img src="https://i.imgur.com/PdNVV4Q.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>


  
<p>
<img src="https://i.imgur.com/1lQnARR.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  
12) Go to the start menu and search for IIS, right click it and run as an administrator
 - Navigate to the PHP Manager button and double click to Register new PHP version. Path the install to the PHP folder we made within the C: drive, and click the PHP executable (.exe) and click ok
 - Give the server a quick restart and continue 

<p>
<img src="https://i.imgur.com/pjdn5c3.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

<p>
<img src="https://i.imgur.com/cMGFovJ.png" height="20%" width="20%" alt="Disk Sanitization Steps"/>
</p>
<p>

  
13) Download will be the osTicket zip file, open the file and drag the upload file into the C: > inetpub > wwwroot. Then rename upload to osTicket. Open IIS and give the server a restart.

  
<p>
<img src="https://i.imgur.com/UEpnaTM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  
14) Within IIS in the connections section open Sites > Default Web Site > osTicket and under Actions tab click Browse *:00 (http). This should take us to our osTicket homepage

  
<p>
<img src="https://i.imgur.com/TxSdyZl.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  
15) Go under the osTicket folder in the connections tab of IIS and click PHP manager > Enable or Disable extension. Enable the following extensions: php_imap.dll, php_intl.dll, php_opcache.dll

<p>
<img src="https://i.imgur.com/HARG5Pb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  
16) Navigate to This PC > C: > inetpub > wwwroot > osTIcket > include. Rename “ost-sampleconfig.php” to ost-config.php
 -Change the permissions of ost-config.php. Right click it, Properties > Security > Advanced > Disable inheritance > Remove all inherited permissions from this object > Apply.

  
<p>
<img src="https://i.imgur.com/7z5HBoV.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  
17) Add permissions > Select a principle > (type everyone into object name box) Check Names > Ok > Full control > Ok > Apply > Ok

18) Go to our browser > Continue. Now download and install HeidiSQL and run the executable and select the default configurations and finish.

19) Inside HeidiSQL click new, and enter the credentials and right click unnamed to create a new database

<p>
<img src="https://i.imgur.com/OjnEH7k.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

  
20) All that’s left is to clean up. Go to C: > inetpub > wwwroot > include ost-config.php > Properties > Security > Advanced > Everyone > Edit. Only have Read & execute and read enabled. Apply. 
<p>
<img src="https://i.imgur.com/dITLQKY.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
 
We have completed the prequisites and installation for osTicket!
  
<p>
<img src="https://i.imgur.com/pN5jDKa.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>

<h2>Lessons Learned</h2>
From this lab I was able to learn the use the depth you must go to create a ticketing system from the ground up. There are many steps and installations needed to form the database, however it creates a beautiful full fledged local ticketing system that will be used in future labs.

 - [osTicket: Post-Installation Configuration](https://github.com/ben-trainer/osTicket-post-install-cfg)
 - [osTicket: Resolving Tickets in a Ticketing System](https://github.com/ben-trainer/osTicket-lifecycle/tree/main)
