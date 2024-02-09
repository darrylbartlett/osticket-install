<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure for creating a Virtual Machine
- Remote Desktop Connection
- Internet Information Services (IIS)

<h2>Operating System Used</h2>

- Windows 10 Pro (22H2)

<h2>List of Prerequisites</h2>

- Creation of an Azure Virtual Machine (VM) with Windows 10 Pro
- Connecting to the VM using Remote Desktop Connection - the public IP address for the VM is used as the Computer Name, along with the username and password entered as part of the VM setup
- Installation files for osTicket – the following files were downloaded for this example:
  - osTicket
  - PHP Manager for IIS
  - PHP
  - Rewrite Module
  - VC Redistributable
  - MySQL
  - HeidiSQL
<br />

<h2>Installation Steps</h2>

<h3>Enable IIS in Windows</h3>
<p>Open Control Panel and select Programs and Features.</p>
<p>On the left menu, click on 'Turn Windows features on or off'.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/7b71ffbb-56be-42d4-8c11-8a44279a625e"/>
</p>
<br />

<p>In the Windows Features box, scroll down and click on the ‘+’ beside Internet Information Services to expand its options.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/597cdc97-3b04-4a27-b329-d40ff45c1301"/>
</p>
<br />

<p>Click on the ‘+’ beside World Wide Web Services to see its options and do the same next to Application Development Features.</p>
<p>Select the checkbox for CGI.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/d4a6c388-8fa1-47ab-abb2-982a620811f7"/>
</p>
<br />

<p>Scroll down to Common HTTP Features, click its ‘+’ and select all the options.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/4ef2753d-d1ad-48b8-accd-566bc6d0c893"/>
</p>
<br />

<p>Next, under Internet Information Services, click the ‘+’ to expand its options and select the checkbox for IIS Management Console.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/bf4c1207-d1f2-4f73-b108-960686ea87b0"/>
</p>
<br />

<p>Click the OK button to apply all the changes.</p>
<p>To see if the changes are working, go to an Internet browser and type 127.0.0.1 in the address bar. 
A blue Internet Information Services page should be displayed.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/326923c2-46b6-4db3-85b8-e6dae90a7719"/>
</p>
<br />

<p>After confirming, close the Control Panel and associated screens.</p>
<br />


<h3>Install PHP Manager for IIS</h3>
<p>Install PHP Manager for IIS using the default options.</p>
<br />


<h3>Install Rewrite Module</h3>
<p>Install Rewrite Module using the default options.</p>
<br />

<p>In File Explorer, create a folder called PHP on the C: drive.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/fa1d2a5f-3d15-41ad-89ab-3efc102530b2"/>
</p>
<br />


<h3>Unzip the PHP zip file</h3>
<p>The PHP download will be in a zip file. Unzip/Extract the contents into C:\PHP.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/97054c00-1618-440d-b8dd-f38572cb5cca"/>
</p>
<br />


<h3>Install VC Redistributable</h3>
<p>Install VC Redistributable using the default options.</p>
<br />


<h3>Install MySQL</h3>
<p>Use the following criteria while going through the install (use the defaults for everything else):</p>

- At the ‘Choose Setup Type’ screen, select Typical. Click Install.
- The checkbox for ‘Launch the MySQL Instance Configuration Wizard’ should be selected. Click Finish and continue the installation.

<p>During the MySQL Server Instance Configuration Wizard install use the following criteria (use the defaults for everything else):</p>

- For the configuration type, select the Standard Configuration option and continue the installation.
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/b2776b57-460d-46ab-8bda-880ecac9c698"/>
</p>

- For the security options, use Modify Security Settings by entering a password in the New root password and Confirm fields (this password won’t be used, it’s only mandatory for the install). Click Next. 
<p>
<img src="![image](https://github.com/darrylbartlett/osticket-install/assets/159499839/fbdf44a5-14e1-4cea-806c-c0fbf1cfe67c"/>
</p>

<p>On the next screen, click Execute to finish the installation.</p>
<br />


<h3>Register PHP in IIS</h3>
<p>Open Internet Information Services (IIS) as an Administrator (Run as administrator).</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/45e1bd2e-b50d-48c7-aa18-12e072bce53e"/>
</p>

<p>Open PHP Manager.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/981aae85-706d-48d0-a51c-2d7a9dd67d47"/>
</p>

<p>Select Register new PHP version.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/b92fb317-bcd6-4720-8476-e9b63a74efc0"/>
</p>

<p>Enter or look for the path C:\PHP\php-cgi.exe and click OK.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/c0bd1742-9ab9-4515-9494-17bdba1161b4"/>
</p>

<p>On the left side of the screen under Connections, expand Sites and select Default Web Site.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/475ca4cd-1195-4dcd-914b-13fe75f67c69"/>
</p>

<p>On the right side of the screen under Actions, click on Restart to stop and start the IIS server.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/9981619f-baaa-4b23-8094-7e9a1f92d337"/>
</p>

<p>Close the IIS screen.</p>
<br />


<h3>Install osTicket</h3>
<p>The osTicket download will be in a zip file. Open the contents of the zip file.</p>
<p>Copy the upload folder into c:\inetpub\wwwroot.</p>
</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/b766ec72-fa95-40bf-a681-6829e1068440"/>
</p>

<p>In c:\inetpub\wwwroot, rename the upload folder to osTicket.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/0f91a63b-90f0-4382-b3f1-38f62f8402ff"/>
</p>

<p>Reopen IIS as an Administrator.</p>
<p>On the right under Actions, click on Restart to stop and start the server.</p>
<p>On the left under Connections, expand Sites and Default Web Site. Click on osTicket.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/1c84dea6-281a-4dd5-b87e-7b97727b0573"/>
</p>

<p>On the right under Actions, click on 'Browse *:80 (http)'.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/b7290d96-a6ab-4188-863a-026efec0dc5f"/>
</p>

<p>An osTicket install window will open in the browser.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/8b5d8efe-067f-43d3-9c7e-fcd1f1665211"/>
</p>

<p>This osTicket window shows there are extensions not enabled.</p>
<p>In IIS, with osTicket still selected on the left of the screen, open PHP Manager.</p>
<p>At the bottom of the screen, select 'Enable or disable and extension'.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/de8e57c4-bd99-4380-b57a-63a9ffbb596a"/>
</p>

<p>Right-click on the following extensions in the list and select Enable:</p>

-	php_imap.dll
-	php_intl.dll
-	php_opcache.dll

<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/544caa30-f87a-4ba2-baa4-bef97759e614"/>
</p>

<p>Go back to the Internet browser and refresh the osTicket install screen. Verify the changes.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/b67765e9-ae49-4973-837d-46893c975478"/>
</p>

<p>Click the Continue button.</p>
<br />


<h3>Update the Configuration File</h3>
<p>The osTicket screen shows there is a configuration file missing.</p>
</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/74ed13cc-92d4-4e9f-a11e-e6899eaaaee9"/>
</p>

<p>Go to C:\inetpub\wwwroot\osTicket\include</p>
<p>Find the ost-sampleconfig.php file. Rename it to ost-config.php</p>
<p>Refresh the osTicket screen in the browser. The screen now shows the configuration file is not writable.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/2d2f78dd-9562-41bd-81ae-225a941a6f16"/>
</p>

<p>The ost-config.php file needs its permissions updated.</p>
<p>Right-click on ost-config.php and select Properties from the sub-menu.</p>
<p>Select the Security tab.</p>
<p>Click on the Advanced button.</p>
<p>In the Advanced Security Settings window, click the 'Disable inheritance' button.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/6d8059f0-8a07-40a8-b723-9be6e0f7b2c6"/>
</p>

<p>Select Remove all inherited permissions from this object.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/eb2ca4a7-843e-4174-bd21-96e779ce1c00"/>
</p>

<p>Select the Add button.</p>
<p>At the top of the Permission Enty screen, click on 'Select a principal'.</p>
<p></p>In the Enter the object name to select box, type in 'everyone' and click on Check Names. Click OK.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/1f3e783c-f6db-4aaa-a96d-37899d76465c"/>
</p>

<p>Under 'Basic permissions', select the checkbox beside 'Full control'. Click OK.</p>
<p>On the Advanced Security Settings screen, click on the Apply button. Click OK.</p>
<p>Click OK on the Properties window.</p>
<p>Refresh the osTicket install screen in the browser. It should now show the osTicket Basic Installation screen. osTicket is ready to finish the setup.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/411bc589-8779-480b-9bf9-8a70eb9f48ad"/>
</p>

<p>Under System Settings, enter a Helpdesk Name and a Default Email.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/181c18a5-f514-43bb-95c3-cc749e75510c"/>
</p>
<br />


<h3>Install HeidiSQL</h3>
<p>Install HeidiSQL using the default options.</p>
<br />

<p>Open HeidiSQL.</p>
<p>At the bottom left corner, click the New button to create a new session.</p>
<p>The User is root.</p>
<p>Enter a password.</p>
<p>Click the Open button to connect to the session.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/ade5addf-b609-4145-99f4-b4aa067ce573"/>
</p>

<p>On the left side of the screen, right-click on the empty area and select Create new and then Database.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/e957b874-8bc8-4e91-a443-c8e3c49eaf57"/>
</p>

<p>In the Create database box, enter osTicket in the Name field and click OK.</p>
<p>osTicket will show on the left-side of the screen.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/01ba741c-cd10-41c1-9404-2d321cc816e9"/>
</p>
<br />


<h3>Continue Setting Up osTicket Basic Installation in the Browser</h3>
<p>Fill out the information for the Admin User.</p>
<p>For the Database Settings, enter the following:</p>

-	MySQL Database: osTicket
-	MySQL Username: root
-	Create a password for the MySQL Password

<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/04e1b681-680f-4a3f-92f1-4155c27a06ee"/>
</p>

<p>Click Install Now.</p>
<p>The browser window should show Congratulations.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/4dab483f-fa30-4ec1-ac71-f2fa7ebc36d5"/>
</p>
<br />

<h3>Delete the Setup Folder</h3>
<p>Go to C:\inetpub\wwwroot\osTicket</p>
<p>Find the setup folder and delete it.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/240cd8b3-c093-4d42-acc6-7f0bee6e21ca"/>
</p>

<p>From the osTicket folder, select the include folder and find the ost-config.php file.</p>
<p>Right-click on the file and select Properties from the sub-menu.</p>
<p>Select the Security tab.</p>
<p>Click on the Advanced button.</p>
<p>Click on Everyone. Select the Edit button.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/ffde0bf9-57fd-4271-a135-8092abfe0188"/>
</p>

<p>Uncheck the following:</p>

-	Full control
-	Modify
-	Write

<p>Only 'Read & execute' and Read should be checked. Click OK.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/53889dee-41a2-477e-931f-3232c74840c0"/>
</p>

<p>Select Apply and then click OK.</p>
<p>Click OK on the Properties box.</p>
<br />


<h3>Helpdesk Admin/Agent Login Page</h3>
<p>This is where the Administrator and helpdesk agents will login.</p>
<p><a href="http://localhost/osTicket/scp/login.php"> osTicket Admin and Agent Login </a></p>
<p>Login with the Admin username and password to configure things like Roles, Departments, Teams, Agents, Users, and SLA’s.</p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/66d7e54c-f531-4dfc-86e9-3f8ddec60b5a"/>
</p>
<br />


<h3>User Login Page</h3>
<p>This is where users will submit their tickets.</p>
<p><a href="http://localhost/osTicket/"> osTicket User Login </a></p>
<p>
<img src="https://github.com/darrylbartlett/osticket-install/assets/159499839/8cb8b37b-215a-4efc-b441-2af470786c41"/>
</p>
<br />
