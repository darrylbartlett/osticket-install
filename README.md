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


