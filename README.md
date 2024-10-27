# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial provides a step-by-step guide on the prerequisites and installation process of osTicket, an open-source help desk ticketing system. To begin, we need to create a Virtual Machine (VM) using the Microsoft Azure Portal. Afterwards, we will utilize the Remote Desktop Connection to access our newly created VM. Please note that if you are using a Mac, you will need to install Microsoft Remote Desktop. To simplify the process, I have included all the necessary installation files for osTicket. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Virtual Machine
- [osTicket Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
- [Remote Desktop](https://apps.apple.com/us/app/microsoft-remote-desktop/id1295203466?mt=12) 


<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/P90vtKL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To start, we will proceed with the installation and enabling of IIS (Internet Information Services) in Windows. Additionally, we will enable CGI and Common HTTP Features. Please follow the steps below:

   - Navigate to the Control Panel on your Windows system.
   - Click on "Programs and Features."
   - Locate and select "Turn Windows features on or off."
   - A window will appear displaying a list of features. Scroll down and find "Internet Information Services (IIS)." Check the box next to it to enable IIS.
   - Expand the "Internet Information Services (IIS)" option.
   - Expand "World Wide Web Services."
   - Expand "Application Development Features."
   - Enable CGI by checking the box next to it.
   - Also, ensure that all the features for "Common HTTP Features" are enabled.

By following these steps, you will successfully install and enable IIS in Windows, including CGI and the necessary features for Common HTTP Features.
</p>
<br />

<p>
<img src="https://i.imgur.com/UofjXtm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Please follow these instructions to proceed with the next steps:

  Navigate to the location where the installation files are provided.
    I recommend downloading all of the files as a zip file for easier handling. To do this, right-click on the installation 
  files located next to "Shared with me" and click on "Download."
    Once the zip file is downloaded, extract its contents to a desired location on your system.

Now, we will proceed with the installation of PHP Manager for IIS and Rewrite Module:

   - Locate the downloaded files and find the installer for PHP Manager for IIS.
   - Double-click on the installer to start the installation process.
   - Follow the on-screen instructions to complete the installation of PHP Manager for IIS.
   - Repeat the following steps for Rewrite Module.

</p>
<br />

<p>
<img src="https://i.imgur.com/OQGGXyR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
  
   - Create a new folder on the C:\ drive by right-clicking on an empty space and selecting "New" -> "Folder." Name the folder "PHP".

   - Now, navigate back to the location where you downloaded the files. Locate the PHP 7.3.8 files.

   - Select all the contents of the PHP 7.3.8 folder and move them into the newly created PHP folder on the C:\ drive.

   - After moving the files, find the "VC_redist.x86.exe" file and start the installation process by double-clicking on it. Follow the on-screen instructions to complete the installation.
   - Next, locate the downloaded files for MySQL 5.5.62. Start the installation process by running the installer.

   - During the installation of MySQL 5.5.62, choose the "Typical Setup" option.

   - In the Configuration Wizard, select the "Standard Configuration" option.

   - Create a password for the MySQL database. Since this is a lab environment, you can choose a password like "Password1" for simplicity.
</p>
<br />

<p>
<img src="https://i.imgur.com/wWAeIpM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To proceed with the remaining steps, please follow the instructions provided:

1. Open IIS (Internet Information Services) as an administrator. You can do this by searching for "IIS" in the Windows Start menu, right-clicking on "Internet Information Services (IIS) Manager," and selecting "Run as administrator."

2. Register PHP from within IIS:
   - In the IIS Manager, select the server name in the left-hand navigation pane.
   - Double-click on "Handler Mappings."
   - In the Actions pane on the right-hand side, click on "Add Module Mapping."
   - Fill in the following information in the dialog box:
     - Request Path: *.php
     - Module: FastCgiModule
     - Executable: C:\PHP\php-cgi.exe (Path to your PHP installation)
     - Name: PHP_via_FastCGI
   - Click "OK" to save the module mapping.

3. Reload IIS:
   - Open IIS Manager.
   - Stop the server by clicking on the "Stop" button in the Actions pane on the right-hand side.
   - Start the server by clicking on the "Start" button in the Actions pane.

4. Install osTicket v1.15.8:
   - Download osTicket from the Installation Files Folder.
   - Extract the contents of the downloaded file.
   - Copy the "upload" folder to "C:\inetpub\wwwroot" directory.
   - Within the "C:\inetpub\wwwroot" directory, rename the "upload" folder to "osTicket".

5. Reload IIS:
   - Open IIS Manager.
   - Stop the server by clicking on the "Stop" button in the Actions pane on the right-hand side.
   - Start the server by clicking on the "Start" button in the Actions pane.

6. Go to sites -> Default -> osTicket:
   - In IIS Manager, expand the server name in the left-hand navigation pane.
   - Expand "Sites" and then select "Default Web Site."
   - Under "Default Web Site," find the "osTicket" folder and click on it.
   - On the right-hand side, click on "Browse *:80".

By following these steps, you will have successfully completed the installation and configuration of osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/CFXDCql.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   
Note that some extensions are not enabled
   
   Go back to IIS Manager.
   
   Navigate to sites -> Default -> osTicket.
   
   Double-click on PHP Manager.
   
   In the PHP Manager window, click on "Enable or disable an extension."
   Enable the following extensions by checking the corresponding 
   checkboxes:
   
      - php_imap.dll
      - php_intl.dll
      - php_opcache.dll
   
   Click "Apply" or "OK" to save the changes.
    Refresh the osTicket site in your browser to observe the changes.

</p>
<br />

<p>
<img src="https://i.imgur.com/Q9vXAmf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To continue setting up osTicket and perform the necessary actions, please follow these steps:

1. Rename the file:
   - Open File Explorer and navigate to "C:\inetpub\wwwroot\osTicket\include\".
   - Locate the file "ost-sampleconfig.php".
   - Rename it to "ost-config.php".

2. Assign permissions to "ost-config.php":
   - Right-click on "ost-config.php" and select "Properties".
   - In the "Security" tab, click on "Disable inheritance" and choose "Remove all inherited permissions from this object".
   - Click on "Add" to add new permissions.
   - In the "Select Users or Groups" window, type "Everyone" and click "Check Names".
   - Select "Everyone" and click "OK".
   - Check the box for "Full control" under the "Allow" column for the "Everyone" group.
   - Click "OK" to save the changes.

3. Continue setting up osTicket in the browser:
   - Open your preferred browser and access the osTicket site.
   - Click on "Continue" to proceed with the setup.
   - Provide a name for the Helpdesk.
   - Specify the default email address that will receive emails from customers.

4. Download and install HeidiSQL:
   - From the installation files, download HeidiSQL.
   - Run the installer and follow the on-screen instructions to complete the installation.

5. Open HeidiSQL and create a new session:
   - Launch HeidiSQL.
   - Create a new session by clicking on the "New" button.
   - Enter the following details:
     - Network type: MySQL (TCP/IP).
     - Hostname/IP: localhost.
     - User: root.
     - Password: Password1 (assuming you used this password during the MySQL installation).
   - Click on "Save" to save the session.

6. Connect to the session and create the "osTicket" database:
   - Select the session you just created from the list.
   - Click on "Open" to connect to the session.
   - Once connected, click on the "SQL" tab.
   - In the SQL editor, enter the following command: `CREATE DATABASE osTicket;`
   - Press F9 or click on the "Execute" button to run the command and create the database.

By following these steps, you will have renamed the configuration file, assigned permissions, continued setting up osTicket in the browser, and created the "osTicket" database using HeidiSQL.
</p>
<br />

<p>
<img src="https://i.imgur.com/YZ7Eea7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
    In the osTicket setup page in your browser, provide the following MySQL database details:
   
    - MySQL Database: osTicket
    - MySQL Username: root
    - MySQL Password: Password1 (assuming you used this password during the MySQL installation)

  Click on "Install Now!" to initiate the installation process.
   
</p>
<br />

<p>
<img src="https://i.imgur.com/sTQEDd6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Congratulations! With these steps completed, osTicket should be successfully installed without any errors. This installation process involved downloading and installing various files, enabling required features, and creating a database to be used with the osTicket software.
</p>
<br />
