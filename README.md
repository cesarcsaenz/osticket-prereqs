<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>


<h1>osTicket - The Installation Process</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.
<br>


<h2>Environments and Technologies Used</h2>

- Microsoft Azure
- Microsoft Remote Desktop
- Internet Information Services (IIS)
<br />

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)
<br />

<h2>List of Prerequisites</h2>

- In Azure: Create a Resource Group & a Windows 10 Virtual Machine with 2-4 CPUs 
- Install & Enable IIS in Windows 
- Download & Install PHP Manager for IIS
- Download & Install URL Rewrite Module
- Download PHP 7.3.8
- Download & Install VCRedist
- Download & Install MySQL 5.5.62
- Download & Install Heidi SQL
- Install osTicket v1.15.8
- [Link to Installation Files](https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
<br />

<h2>Installation Steps</h2>
<h3>1. CREATE A RESOURCE GROUP AND A VIRTUAL MACHINE IN AZURE</h3>

- Go to azure.portal.com and create a new virtual machine (VM). 
- Select Windows 10 22H2 as your image and a VM size of at least 4vcpus to ensure faster processing speeds.

<img height="50%" width="50%" alt="VM Creation 2" src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/8eef9c33-783e-4202-a31d-d9f39da291ee">

<br>

- Once your VM has been deployed copy its Public IP address.

   <img align = "top" height = "50%" width="50%" alt="Get Public IP Address" src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/f52f213e-977b-4ca9-88d6-60846feb26ff">

-  Connect to the VM through remote desktop.
  
      <img align = "top" height = "50%" width="50%" alt="remote desktop" src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/e406c82d-d3cf-4ad6-b97c-594906ff3287">



<h3>2. INSTALL / ENABLE IIS IN WINDOWS WITH CGI, COMMON HTTP FEATURES</h3>

<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/34b44a9d-7f2a-4c6e-91d4-3149430dc90e" height="50%" width="50%" alt="Turn Windows features on/off"/>


- After you created a Resource group and a Windows 10 VM with 2-4 CPUs in Azure, connect to Microsoft Remote Desktop (Mac users) with your Windows 10 VM Public IP & credentials you created during its set up in Azure.

- In Windows, go to Control Panel > Programs > Programs & Features, and Turn Windows features on and off.

<br>


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/3ee087a4-fd9b-4c03-b076-735d1b2f2fb4" height="40%" width="40%" alt="Enable IIS"/> </p>
<br>

<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/ae9d57f5-13bb-4ea5-a387-75ac2f900701" height="40%" width="40%" alt="Enable IIS"/>

Before installing osTicket, you need IIS because osTicket is a web-based application. IIS (Internet Information Services) is the needed software that allows your computer to serve and display web pages on the internet.

Check mark Internet Information Services to enable it. Then, click on Web Management Tools > Application Development Features. Check CGI and Common Features to enable them as well.  
<br>


<h3>3. INSTALL PHP MANAGER FOR IIS</h3>

<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/5721a70c-fbdc-43f8-8323-86dec98464bb" height="50%" width="50%" alt="Install PHP Manager for IIS"/>

- Download and install PHP Manager for IIS. (PHPManagerForIIS_V1.5.0.msi)

- PHP Manager for IIS is a tool that helps Internet Information Services (IIS) work smoothly with PHP. It ensures that IIS can understand and process PHP code, making it compatible with osTicket since it's built using PHP.
<br>

<h3>4.INSTALL REWRITE MODULE</h3>

<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/cbaa7462-b9d0-4f84-85cf-f9edcbeae10c" height="50%" width="50%" alt="Install URL Rewrite Module"/>  


- Download and install URL Rewrite Module. (rewrite_amd64_en-US.msi)
</p>
<br />



<h3>5. CREATE A PHP FOLDER IN C:\</h3>


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/5cb20bb9-fcee-4cda-b5f5-9c5bf577f776" height="50%" width="50%" alt="PHP Folder on C:\"/>

- On your Windows local disk C:\, create a folder and name it "PHP". 
<br>


<img width="350" alt="image" src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/39b23b99-b916-4b79-b87a-bc20d79e0f19">

- Then, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip), and unzip its contents, by clicking "Extract all", into C:\PHP folder you've just created.  
<br>

<h3>6. INSTALL Microsoft Visual C++</h3> 

<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/c5e4876b-4aeb-4ddc-9bcc-9eccc80c0c96" height="50%" width="50%" alt="Visual C++ instal"/>

- Download and install Microsoft Visual C++ VC_redist.x86.exe.

- osTicket is built using certain components or libraries created with Visual C++. VCRedist ensures that your computer has all the right tools so that osTicket can run smoothly without missing anything.
<br>


<h3>7. INSTALL MySQL</h3>

<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/dd7fc845-ea57-41eb-8168-8a67480ee337" height="50%" width="50%" alt="MySQL instal"/>

- Download and install MySQL (mysql-5.5.62-win32.msi). osTicket needs a place to store and organize information.

- MySQL is the filing cabinet and management system that helps osTicket keep things in order. Installing MySQL before osTicket ensures that there's an organized place for osTicket to store and retrieve the information it needs to handle support tickets effectively.

- Choose "Typical Setup" and upon installation, choose "Standard Configuration".
<br />


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/916935b1-893e-4d71-8921-924ad8c473f2" height="50%" width="50%" alt="MySQL credentials"/>

- The standard configuration sets you up with a "root" username. You may add your own password.
<br />



<h3>8. OPEN IIS AND REGISTER PHP WITHIN IIS</h3>


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/440445fc-6e83-4c46-b5b2-bf64bc10043b" height="50%" width="50%" alt="Open IIS as Admin"/>

- Open IIS as an Admin. In the Windows search bar, type "IIS".
<br />


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/dbb56ea1-40df-4aee-a3e1-5135bea0ffea" height="50%" width="50%" alt="Register PHP within IIS"/>

- In IIS, click on PHP Manager > Register new PHP version.
<br>


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/ea17899f-45d5-45ed-b6b6-a6342cf5ca03" height="50%" width="50%" alt="Pull CGI PHP folder"/>


- You will be prompted to add a CGI with .exe extension.

- Select C:\PHP and you CGI file will appear. Click on it so IIS can register it.
<br>


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/727470ca-f1d3-49a1-b5e7-f98bbac81798" height="50%" width="50%" alt="Reload IIS"/>

- Go back to IIS' main page, click "Restart".  IIS will now have the new additions you've just made.
<br>


<h3>9. INSTALL osTICKET</h3>


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/5d64e32b-ec96-42c8-8034-839d23039573" height="70%" width="70%" alt="Install OsTicket"/>

<h4> You are now ready to install osTicket!</h4>

- Download and install osTicket v1.15.8. Then, move its "Upload" folder to your local disk C:\inetpub\wwwroot.
- Within C:\inetpub|wwwroot, rename "Uplaod" to "osTicket".

<br>


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/315e4462-d935-4ba9-b914-3db6871d4e49" height="50%" width="50%" alt="Reload IIS"/>

- Reload IIS with the new additions you've just made. Go back to IIS' main page, click "Restart".
<br>


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/0d2f265d-29ee-437f-b48a-b7925a9d3f65" height="70%" width="70%" alt="Launch osTicket"/>

- Now you are ready to launch osTicket! In the IIS Connections pane on the left (see arrow), click on sites > Default > osTicket.

- Then, to the right in the Actions pane, locate and click "Browse *:80".
<br />


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/8f75bed1-fd24-40e3-95d7-64fbe0ea7abd" height="50%" width="50%" alt="osTicket missing extensions"/>

- Here you are, in osTicket !!! Note that some extensions are not enabled. So we'll go back to IIS and enable them.
<br>



<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/8b9d9fc8-a644-4167-ad9b-303c717badb9" height="40%" width="40%" alt="Enabling .php extensions"/>

- Go back to IIS. Go to sites > Default > osTicket. Then, double-click on PHP Manager. You will see a list of both enabled and disabled .php extensions.

- Enable: php_imap.dll; php_intl.dll; php_opcache.dll. See the "enable" in the example section below.
<br>


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/981760be-b2b4-4241-a6b9-22a325898177" height="60%" width="60%" alt="Enabling .php extensions"/>

- Once you've enabled the missing extensions, refesh osTicket in your browser.
- Observe the changes.
<br>



<h3>10. RENAME "OST-SAMPLE CONFIG" FILE AND ASSIGN NEW PERMISSIONS TO "OST-CONFIG" FILE</h3>

<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/854698c9-6be2-407f-8522-1426a14aaebd" height="60%" width="60%" alt="Rename ost-sampleconfig to ost-config"/> 
 
- In your local disk C:\inetpub\wwwroot\osTicket\includ\ost-sampleconfig.php, right-click on the file and rename it "ost-config".
<br>



<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/481e9391-0078-4a0e-b6b2-1e2fa65a7362" height="50%" width="50%" alt="Assign Permissions of ost-config.php"/>

- At this stage, we can assign new permissions to our ost-config.php file we've just renamed.

- Right-click on the file > Properties > Security > Advanced. Then, "disable inheritance" > Remove All Permissions.
<br>


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/782f0283-9f9a-4e72-9af6-1e1083758560" height="50%" width="50%" alt="Assign Permissioms of ost-config.php"/> 


- Once you removed all inheritances, click on "Add" > Select a principal. Write "Everyone", then click on "Check Names".  


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/7aa08797-1cd7-48f5-9d8c-57658a55eb64" height="50%" width="50%" alt="Give full control to Everyone"/>

-Give full control to the group "Everyone". Now, everyone has access to the file.
<br>


<h3>11. CONTINUE SETTING UP osTICKET IN THE BROWSER</h3>

<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/44b3ee4f-673a-407b-8b30-663a4a2f450b" height="60%" width="60%" alt="Setting up osTicket in the browser"/>


- Go back to the osTicket page on your browser, click "Continue". You may now fill most information. 

- The default email address is the one that receives emails from customers. DO NOT PRESS INSTALL, yet. We need more SQL information before proceeding.
<br>


<h3>12. INSTALL HeidiSQL.</h3>


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/59cd2371-03e0-4760-9923-ae5a66b756c2" height="60%" width="60%" alt="Download and Install Heidi SQL"/>


- Download and install Heidi SQL. It provides a visual interface for managing and manipulating data in the database.
<br />


<h3>13. CREATE A NEW SESSION AND DATABASE IN HeidiSQL</h3>


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/9751676e-2235-48a5-976c-02955fbb96b2" height="50%" width="50%" alt="Create a new session Heidi"/>

- Open Heidi SQL and click "New" (bottom left corner) to create a new seesion. Enter your password used for MySQL and connect to the session. 
<br>


<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/6e9995fe-3e01-46d9-bfaa-34726be8901e" height="50%" width="50%" alt="Create a database in Heidi"/>

- Create a database called "osTicket". For this, right-click on the screen > create new > database. Name it "osTicket".
<br>


<h3>14. FINISH SETTIN UP osTICKET IN THE BROWSER</h3>

<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/595d3fa0-eb3a-4d1f-8cb0-1307c8d4b8a7" height="50%" width="50%" alt="Continuing osTicket set up"/>

- Go back to osTicket in your browser, you may not fill all the remaining SQL section. Then, click "Install Now!"
<br>

<h3>STEP 15. CONGRATULATIONS!</h3>

<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/c4a36926-810e-4f87-b150-460282e80c40" height="70%" width="70%" alt="Congrats, you're in!"/>

<h4>CONGRATULATIONS, YOU MADE IT!</h4>

You can also clean up now by:
- 1. Deleting the following file: C:\inetpub\wwwroot\osTicket\setup

- 2. Setting new permissions to "Read Only" to your "ost-config.php": C:\inetpub|wwwwroot|osTicket\include\ost-config.php
<br>



<img src="https://github.com/cesarcsaenz/osticket-prereqs/assets/153584649/7ee82da5-ad5a-49c0-a1bb-c7778c9b2f18" height="70%" width="70%" alt="osTicket help desk page"/>

<h4> You may browse to your help desk login page: http://localhost/osTicket/scp/login.php </h4>

<br>

Congratulations you have successfully installed osTicket on your Virtual Machine, Continue to the [osTicket: Post-Installation Configuration Tutorial](https://github.com/s-evelyn/osTicket-PostInstallConfig) 

