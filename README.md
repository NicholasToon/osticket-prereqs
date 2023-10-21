![Image](https://i.imgur.com/6TcPxKI.png)

# osTicket - Prerequisites and Installation

*Always delete your resource groups and other environments in Azure to avoid incurring any unwanted charges on your free credits or actual money. Keep resources open at your own discretion.*

In this tutorial, we will guide you through the step-by-step installation process of osTicket and the essential prerequisites required for a successful setup. We've chosen Azure VM (Virtual Machine) as the platform for installation. It is assumed that you already have a VM ready and have logged in using a remote desktop connection. If you haven't created a VM yet, kindly do so before proceeding to the next step. If you are unsure how to do so, you can find instructions [here](https://github.com/NicholasToon/Creating-Resource-Groups-and-Deploying-Virtual-Machines-in-Azure). To begin, please click the provided link to access the [installation files](https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6).

(If you are having trouble downloading PHP 7.3.8, download and install Google Chrome and perform it from within there.)


![Image](https://i.imgur.com/7gna8d4.png"/>)

## Environments and Technologies Used

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection (RDC)
- Internet Information Services (IIS)
- MySQL

## Operating Systems Used 

- Windows 10 Pro (22H2)

## Installation Steps

![Image](https://i.imgur.com/TIe1QvB.png)

## Install / Enable IIS in Windows WITH CGI

Under **Control Panel** -> **Programs** -> **Turn Windows Features on or off** -> **Internet information services** ->  **Web Managment Tools** -> **[√] IIS Managment Console** -> **World Wide Web Services** -> Check boxes on <ins>**Common HTTP Features**, **Health and Diagnostics**, **Performance Features**, and **Security**</ins> -> **Application Development Features** -> **[√] CGI** -> Press **OK** (To conduct a preliminary test of your server, please open a new tab in your browser and enter 127.0.0.1. Upon doing so, you should be able to successfully load the default Internet Information Services webpage.)



![Image](https://i.imgur.com/HuphyFv.png")

From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi).

![Image](https://i.imgur.com/NroRYT8.png)

Create the directory C:\PHP

Open File Explorer -> This PC -> Windows (C:) Drive -> Right Click to add NEW FOLDER -> name it "PHP"

![Image](https://i.imgur.com/ag11MQq.png)

![image](https://i.imgur.com/fOKwoV9.png)

Unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into C:\PHP From the installation files.

Double-Click on PHP-7.3.8 -> Extract All -> Browse -> This PC -> Windows (C:) -> Click PHP -> Select Folder -> Extract.

![Image](https://i.imgur.com/ILcg219.png)

From the Installation Files, download and install VC_redist.x86.exe

![Image](https://i.imgur.com/EtXiK5q.png)

From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Install as Windows Service (make sure "Launch my sql server..."is checked) -> Execute -> Finish

 Example Credentials: (These will be used when we download, install, and launch HeidiSQL)

 Username: root
 
 Password: Password1

![Image](https://i.imgur.com/LDrudOO.png)
 
From the Installation Files, download and install Rewrite Module (rewrite_amd64_en-US.msi)

![Image](https://i.imgur.com/NFB05iU.png)
 
![Image](https://i.imgur.com/2WxwC73.png)
 
![Image](https://i.imgur.com/PxVuU6E.png)
 
![Image](https://i.imgur.com/NUWgQUe.png)
 
![Image](https://i.imgur.com/hiSPSYF.png")
 
![Image](https://i.imgur.com/8epjq5e.png)
 
Type "IIS" in the start menu, click **Run As Administrator**, select **PHP Manager** (Double-Click or select **Open Feature**), choose **Register a new PHP Version**, click "BROWSE," open the PHP Folder in the Directory, select "php-cgi" (ensure that the PHP executable is chosen in the file box), click **Open**, click **OK**, use the blue arrows in the top left to return home, select **PHP Manager**, and click **Restart** (You can restart the server without highlighting **Restart** as well).


![Image](https://i.imgur.com/WhT8AjW.png)
 
![Image](https://i.imgur.com/nw75Ifm.png)

Open osTicket v1.15.8 from your Installation Files Folder, extract and copy the "upload" folder to c:\inetpub\wwwroot via Browse. Within c:\inetpub\wwwroot, rename "upload" to "osTicket" (when you're placing the "upload" folder inside "c:\inetpub\wwwroot," make sure it's renamed as "osTicket" exactly, with no spaces. If it's not named correctly or has a space, you'll encounter a '404 page not found' error). Return and reload IIS (Open IIS, stop and start the server).

![Image](https://i.imgur.com/5LmJK6m.png)
 
Once the server has been effectively restarted, go to **Sites** -> **Default Web Site** -> (Double-Click) **osTicket** -> Browse on *80.

If you have done everything correctly, you should have landed on the osTicket webpage. If not, please double-check the steps or give the tutorial another try.
 

![Image](https://i.imgur.com/q7FWute.png)
  
NOTE: Some PHP extensions are disabled (indicated by red Xs). To enable PHP extensions, return to IIS.

![Image](https://i.imgur.com/wIxbfWQ.png)

**Default Web Site** -> **osTicket** -> **PHP Manager** (double-click) -> Click on **PHP Extensions**.

Scroll down list to find:

**Php_imap.dil**

**Php_intl.dil**

**Php_opache.dil**

Click **Enable Extensions** and then restart the server.
![Image](https://i.imgur.com/NhggCtk.png)
 
Before pressing "Continue" in osTicket, we will return to the Downloads folder to install HeidiSQL. After installation, HeidiSQL will launch. Let it install itself in the C: Drive for ease, and then press "Next" for the remaining options.

![Image](https://i.imgur.com/28qtUOW.png)

![Image](https://i.imgur.com/ZubiYLY.png)

Go to**New** -> Enter the password we created earlier for MySQL (e.g., Password1) -> **Open** -> Right-click **Unnamed** -> **Create New** -> **Database** (Name it osTicket) -> **OK**.

![Image](https://i.imgur.com/FlgO5Z5.png)

Rename ost-sampleconfig.php to ost-config.php

Windows (C:) Drive -> inetpub -> wwwroot -> osTicket -> include -> Right click on ost-sampleconfig.php and rename it to "ost-config.php"

![Image](https://i.imgur.com/NVQhD5Q.png)

![Image](https://i.imgur.com/Gv3GHNE.png)

Assigning Permissions:

Right-click on ost-config.php -> **Properties** -> **Security** -> **Advanced** -> **Disable Inheritance** -> **Remove all inherited permissions from this object** -> Select **Permissions** (It's next to Auditing and Effective Access) -> **Add** -> Select a Principal > Type: Everyone > **Check Names** > **OK** -> [√] Full control (It will check the other boxes as well, and that's okay) -> **OK**.

![Image](https://i.imgur.com/Pu7Dgs5.png)

We will now return to osTicket to complete the remaining prerequisites. Press "Continue" to proceed and fill in the HELP DESK information.

![Image](https://i.imgur.com/Jx6wON4.png)

Remember, when filling out the Help Desk information, we have already created a password and database for MySQL, and "root" will always be the username. Press "Install," and you will only need to proceed with the cleanup.

![Image]( https://i.imgur.com/Pu7Dgs5.png)
  
The cleanup phase is quite simple; we are going to delete the setup and change permissions back to read-only.

To delete setup folder go to: C:\inetpub\wwwroot\osTicket\setup highlight "setup" then delete it.

To change permissions go go to: Windows (C:) Drive -> wwwroot -> osTicket -> Include -> scroll down to find ost-config.php and Right click on Properties -> Security -> Advanced -> Click on Everyone -> Edit to Read only -> OK -> Apply

![Image](https://i.imgur.com/hLr5NCX.png)

![Image](https://i.imgur.com/dRuV2Rp.png)

Finally. Sign in to osTicket: http://localhost/osTicket/scp/login.php

## Congratulations, you have succssefully installed osTicket! For post-configuration click [here](https://github.com/NicholasToon/osTicket-Post-Installation-Configuration). Thank you for your time.

