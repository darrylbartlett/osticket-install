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



