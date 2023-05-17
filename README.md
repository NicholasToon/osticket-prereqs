<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

In this tutorial, we will explore the step-by-step installation process for osTicket and the essential prerequisites required for a successful setup. The chosen platform for installation is an Azure VM (Virtual Machine). It is assumed that you already have a VM ready and have logged in using a remote desktop connection. If you haven't created a VM yet, kindly do so before proceeding to the next step. If you are unsure how to do so, then proceed to here. To begin, please click the provided link to access the <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">installation files. </a> 

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
<img src="https://i.imgur.com/HU0jjnj.png"/>
</p>
<p>
<h3>Install / Enable IIS in Windows WITH CGI</h3>

Under Control Panel -> Programs -> Turn Windows Features on or off -> Internet information services -> World Wide Web Services -> Application Development Features -> [X] CGI -> Press OK </h3>
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
Create new file in your directory C:\PHP
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
Install as Windows Service (make sure "Launch my sql server..."is checked)

 Example Credentials:

 Username: root
 
 Password: Password1
 
 Execute and Finish
</p>
<br />
