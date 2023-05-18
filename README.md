<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

In this tutorial, we will explore the step-by-step installation process for osTicket and the essential prerequisites required for a successful setup. The chosen platform for installation is an Azure VM (Virtual Machine). It is assumed that you already have a VM ready and have logged in using a remote desktop connection. If you haven't created a VM yet, kindly do so before proceeding to the next step. If you are unsure how to do so, then proceed to here. To begin, please click the provided link to access the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> INSTALLATION FILES. </a> 

(If you are having trouble downloading PHP 7.3.8, download and install Google Chrome and perform it from within there.)

<h2>
<p>
<img src= "https://i.imgur.com/7gna8d4.png"/>
</p>
 <h/2>


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- MySQL

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/TIe1QvB.png"/>
</p>
<p>
<h3>Install / Enable IIS in Windows WITH CGI</h3>

Under Control Panel -> Programs -> Turn Windows Features on or off -> Internet information services ->  Web Managment Tools -> [√] IIS Managment Console -> World Wide Web Services -> Check boxes on <ins>Common HTTP Features, Health and Diagnostics, Performance Features, and Security</ins> -> Application Development Features -> [√] CGI -> Press OK (To conduct a preliminary test of your server, please open a new tab in your browser and enter 127.0.0.1. Upon doing so, you should be able to successfully load the default Internet Information Services webpage.)




 </h3>
</p>
<br />

<p>
<img src="https://i.imgur.com/HuphyFv.png"/>
</p>
<p>
From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
</p>
<br />

<p>
<img src= "https://i.imgur.com/NroRYT8.png"/>
</p>
<p>
Create the directory C:\PHP

 Open File Explorer -> This PC -> Windows (C:) Drive -> Right Click to add NEW FOLDER -> name it "PHP"
</p>
<br />

<p>
<img src= "https://i.imgur.com/ag11MQq.png"/>
</p>
<p>

<p>
<img src= "https://i.imgur.com/fOKwoV9.png"/>
</p>
<p>

Unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into C:\PHP From the installation files

Double-Click on PHP-7.3.8 -> Extract All -> Browse -> This PC -> Windows (C:) -> Click PHP -> Select Folder -> Extract
</p>
<br />

<p>
<img src="https://i.imgur.com/ILcg219.png"/>
</p>
<p>
From the Installation Files, download and install VC_redist.x86.exe
</p>
<br />

<p>
<img src="https://i.imgur.com/EtXiK5q.png"/>
</p>
<p>
From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Install as Windows Service (make sure "Launch my sql server..."is checked) -> Execute -> Finish

 Example Credentials:

 Username: root
 
 Password: Password1
</p>
<br />

<p>
<img src="https://i.imgur.com/LDrudOO.png"/>
</p>
<p>
From the Installation Files, download and install Rewrite Module (rewrite_amd64_en-US.msi)
</p>
<br />

<p>
<img src="https://i.imgur.com/NFB05iU.png"/>
</p>
<p>
 
 <p>
<img src="https://i.imgur.com/2WxwC73.png"/>
</p>
<p>
 
 <p>
<img src="https://i.imgur.com/PxVuU6E.png"/>
</p>
<p>
 
 <p>
<img src="https://i.imgur.com/NUWgQUe.png"/>
</p>
<p>
 
 <p>
<img src="https://i.imgur.com/hiSPSYF.png"/>
</p>
<p>
 
 <p>
<img src="https://i.imgur.com/8epjq5e.png"/>
</p>
<p>
 
Type IIS in start menu -> Click on Run As Administrator -> Select PHP Manager (Double-Click or Select Open Feature -> Select Register new PHP Version -> Click BROWSE -> Open PHP Folder in Directory -> Select php-cgi (make sure php executable is chosen in file box) -> Open -> OK -> Use blue arrows in the top left to return home -> Select PHP Manager -> Click RESTART
</p>
<br />

 <p>
<img src="https://i.imgur.com/WhT8AjW.png"/>
</p>
<p>
 
  <p>
<img src="https://i.imgur.com/nw75Ifm.png"/>
</p>
<p>

Open osTicket v1.15.8 from your Installation Files Folder -> Extract and copy “upload” folder to c:\inetpub\wwwroot via Browse -> Within c:\inetpub\wwwroot, Rename “upload” to “osTicket” (when you're putting the "upload" folder inside of "c:\inetpub\wwwroot", make sure it's renamed exactly "osTicket" with no spaces. If it's not named correctly or has a space, you'll get a "404 page not found") -> Return and Reload IIS (Open IIS, Stop and Start the server)

  <p>
<img src="https://i.imgur.com/5LmJK6m.png"/>
</p>
<p>
 
 Once the server has been effectively restarted -> Sites -> Default Web Site -> (Double-Click) osTicket -> Browse *80
 
If you did everything correctly, you should have landed on the osTicket webpage. If not, just double-check the steps or give the tutorial another go.
 

<p>
<img src= "https://i.imgur.com/q7FWute.png"/>
</p>
  
NOTE: some php extensions are disabled (with red Xs) to enable php extensions go back to IIS 

<p>
<img src= "https://i.imgur.com/wIxbfWQ.png"/>
</p>

Sites -> Default Web Site -> osTicket -> php manager (double-click) -> Click on PHP extensions

Scroll down list to find:

Php_imap.dil

Php_intl.dil

Php_opache.dil

click enable extensions and Restart the server

<p>
<img src= "https://i.imgur.com/NhggCtk.png"/>
</p>
Before pressing continue in osTicket, we will return to the Downloads folder to install HeidiSQL ->
After Installation, HeidiSQL will launch

<p>
 <img src= https://i.imgur.com/28qtUOW.png />
</p>

<p>
 <img src= https://i.imgur.com/ZubiYLY.png />
</p>

New -> Enter password we created earlier for mysql (example: Password1)-> Open -> Right Click Unamed -> Create New -> Database (Name it osTicket) -> OK

<p>
 <img src= https://i.imgur.com/FlgO5Z5.png />
</p>

Rename ost-sampleconfig.php to ost-config.php

Windows (C:) Drive -> inetpub -> wwwroot -> osTicket -> include -> Right click on ost-sampleconfig.php and rename it to ost-config.php


