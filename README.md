<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create Virtual machine in Azure using Windows 10.
- Install/ Enable IIS in Windows.
- Create directory C:\PHP 
- Download and install [PHP Manager](https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view?usp=drive_link) [Rewrite Module](https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view?usp=drive_link)
- Download [php-7.3.8](https://drive.google.com/drive/folders/1yOk5ejp5Oe21USJfCgelyvdlJMwHRhxC?usp=drive_link) Unsip into C;\PHP
- Download and install [MySQL 5.5.62](https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view?usp=drive_link) Typical Setup-> Launch Config. Wizard (after install)-> Standard Config.-> Set password to something simple to remember.
- Open IIS as Admin, Register PHP within IIS, Restart IIS.
- Install [osTicket](https://drive.google.com/file/d/1VeVXKlzHDRjeaVUL99ptq7qYbrbXdFxJ/view?usp=drive_link). Extract and copy folder "upload" into c:\inetpub\wwwroot. Then rename "upload" to "osTicket"
- Enable extensions: php_imap.dll, php_intle.dll, php_opcache.dll
- Setup osTicket, then install [HeidiSQL](https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit?usp=drive_link) 

<h2>Pre-Installation Steps</h2>

<p>
<img src="https://i.imgur.com/9BooqYn.png" height="80%" width="80%" alt="Install/Enable IIS in Windows"/>
</p>
<p>
Install/Enable IIS on Windows. Go to control panel and select programs. Underneath Programs and features click on "Turn Windows features on or off". From here look for Internet Information Services and click the + to expand. Click the + next to World Wide Web Services. First click on the + next to Application Development Features, then click on the box next to CGI. Next click the + next to Web Management Tools, then click on the box next to IIS Management Console. Last click the box next to Common HTTP Features.
</p>
<br />

<p>
<img src="https://i.imgur.com/nBpTmzJ.png" height="80%" width="80%" alt="Download files and Setup IIS "/>
</p>
<p>
Download and install PHP Manager, Rewrite Module, VC_redist.x86.exe, MySQL 5.5.62. Create directory C:\PHP, then download PHP 7.3.8 and unzip into C:PHP. Open IIS Manager as Admin. Click PHP Manager, then select Register new PHP version. Choose file from C:PHP, file name "php-cgi". Now restart IIS.
</p>
<br />

<p>
<img src="https://i.imgur.com/slGmqI4.png" height="80%" width="80%" alt="Installing osTicket"/>
</p>
<p>
Download osTicket.Extract and copy "upload" folder to c:\inetpub\wwwroot, then rename "upload" to "osTicket". Open IIS Manager as Admin, on the left side click on Sites-> Defalut-> osTicket, then on the right side click on "Browse *:80". Go bak to IIS Manager click on Sites-> Default-> osTicket. From here click on PHP Manager, then at the bottom click on Enable or Disable an Extension. We are going to enable "php_imap.dll", "php_intl.dll", "php_opcache.dll". Then refresh the browser. Go to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php the rename to C:\inetpub\wwwroot\osTicket\ost-config.php. Right click on ost-config.php, then click on properties-> Security->Advanced. Disable inheritance and remove all. Add new permissions to Everyone, and giving full control.
<br />

<p>
<img src="https://i.imgur.com/nUDAEWY.png" height="80%" width="80%" alt="Setting Up osTicket"/>
</p>
<p>
Setup osTicket. Fill out information until it requires MySQL info. Download and install HeidiSQL, then launch. Click on the create button to create a new session. Put in password (Password1) then connect to session. Create database called "osTicket". Now fill in the rest of the info on osTicket installer. Click install now. Login from http:\\localhost\osTicket\scp\login.php.
