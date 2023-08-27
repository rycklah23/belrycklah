Hello My Name Is Belrycklah, an IT Professional 
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> 

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8

STEP ONE: Installation

 ![image](https://github.com/rycklah23/belrycklah/assets/142331371/79f71746-720a-4a95-b72b-1a65050a4268)
![image](https://github.com/rycklah23/belrycklah/assets/142331371/ca1028ae-1193-48ca-af4b-a23aaaa2ec67)

1.) The first thing you are going to do is create a virtual machine by going to https://portal.azure.com/. Then, setup your virtual machine with Windows 10 Pro, version 22H2, you will want to create a virtual machine with atleast 2 vcpus and 16 gbs of memory.

2.) Then you will want to conncet to Virtual Machine by using the public ip address the vm is setup with. You will connect using the remote desktop connection app.

3.) Once you have connected to your virtual machine you will want to go to your control panel. From the control panel open up programs. Select, Turn Windows features on and off.

![image](https://github.com/rycklah23/belrycklah/assets/142331371/c9095821-8454-4b4a-a8e4-790ff1ee8cc4)
![image](https://github.com/rycklah23/belrycklah/assets/142331371/62710623-50f5-444d-aaf2-704e32b767d8)

4.) You will want to install / enable IIS in Windows with CGI and Common HTTP Features

World Wide Web Services -> Application Development Features -> [X] CGI [X] Common HTTP Features
![image](https://github.com/rycklah23/belrycklah/assets/142331371/1d606955-7d01-45ca-8605-dddb13d14a86)
![image](https://github.com/rycklah23/belrycklah/assets/142331371/7e50f605-1787-4cac-8c95-632d9ec22f7b)

NOTE: Make sure all Common HTTP Features are checked.

To make sure the IIS is installed / enabled go to a browser of your choice and search for 127.0.0.1 It should look something like this.
![image](https://github.com/rycklah23/belrycklah/assets/142331371/e8769e7a-17bd-401b-bfcd-513c90bbd3e9)
![image](https://github.com/rycklah23/belrycklah/assets/142331371/fdc4d06b-f911-452b-ae6f-d99852090335)
![image](https://github.com/rycklah23/belrycklah/assets/142331371/958fed3f-151b-4838-b83b-7f052cbb0fe3)

5.) Now that the IIS is enabled, From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) Go through the install wizard and complete the install.

6.) Next from the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)

7.) Create a folder in the C drive called PHP.

8.) From the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP

! ATTENTION !! If this appears, choose to “Keep” the file:

9.) Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe from the installation files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe.

10.) Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) Run the setup wizard: Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration ->

Make the new root password: Password1

![image](https://github.com/rycklah23/belrycklah/assets/142331371/a1d8c93d-ab17-4845-911e-b32903ee4a5b)
![image](https://github.com/rycklah23/belrycklah/assets/142331371/16d639f9-8e19-46f6-8786-32e3e5d1e193)

11.) Now that we have the files downloaded and installed we will want to search for IIS in the windows search bar. Open IIS as an administrator. The program should look like this.

12.) We will now want to register PHP from within IIS. Click on PHP Manager

Register new PHP version.

![image](https://github.com/rycklah23/belrycklah/assets/142331371/51a67ae4-9903-4f7f-aa70-63c074869e1c)
![image](https://github.com/rycklah23/belrycklah/assets/142331371/85e9bf0e-7874-4680-8e8f-ae531ebadb11)
![image](https://github.com/rycklah23/belrycklah/assets/142331371/a175ed1c-077d-4b56-ac3f-1b153919fdd1)

You will want to provide a path to the php executable file (php-cgi.exe)). Go to C Drive -> PHP -> click on php-cgi file.
Restart the IIS server.

13.) Install osTicket v1.15.8 -Download osTicket from the Installation Files Folder -Extract and copy "upload" folder to c:\inetpub\wwwroot -Within c:\inetpub\root, Rename "upload" to "osTicket"

Reload IIS again.

14.) On IIS go to sites -> Default -> osTicket -On the right, click “Browse *:80”

![image](https://github.com/rycklah23/belrycklah/assets/142331371/a67542cd-ba9a-4113-a7f0-450b2aec5841)

![image](https://github.com/rycklah23/belrycklah/assets/142331371/0fd48262-ba92-4006-856c-0193fd669a51)

![image](https://github.com/rycklah23/belrycklah/assets/142331371/e6e0346c-dca9-487e-96f2-f0e1ab2defc4)

Some extensions are not enabled on the osTicket browser.

To enable the extensions: -Go back to IIS, sites -> Default -> osTicket -Double click PHP manager -Click "Enable or disable an extension"

We will want to enable three extensions from here.

1.) php_imap.dll
2.) php_intl.dll
3.) php_opcache.dll

![image](https://github.com/rycklah23/belrycklah/assets/142331371/64f2dc70-e480-49bf-b12b-ee7fe8492473)

![image](https://github.com/rycklah23/belrycklah/assets/142331371/76faae4e-1c7a-4521-92c3-98768b4789d1)

![image](https://github.com/rycklah23/belrycklah/assets/142331371/9592b497-651f-4b02-bc17-4d278a09a2e4)


![image](https://github.com/rycklah23/belrycklah/assets/142331371/fe0b187b-29b7-41b3-b19b-66cc009c4ec9)

15.) Once we have those extensions enabled in IIS, we are going to want to rename one of the files in our osTicket folder. Go into the file explorer and search for C;\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

We are going to rename the ost-sampleconfig.php to ost-config.php

Now that we have renamed the files, right click on the file and go to properties. From there click security, click on advance, and disable the inheritance. We will select Remove all inherited permissions from this object.

Now we will add new permissions.

Click Add
Then Select a principal
Then Type "Everyone" in the box
Make sure Full Control and all the other boxes are checked
Click Apply and Ok 
![image](https://github.com/rycklah23/belrycklah/assets/142331371/ed7bbe33-f4ae-45bb-9a92-c88c355d243d)
![image](https://github.com/rycklah23/belrycklah/assets/142331371/9272ba14-4fca-4e36-9391-755858875730)
![image](https://github.com/rycklah23/belrycklah/assets/142331371/0df6799b-d179-4cb3-8eaa-c2d70bdff0fe)
![image](https://github.com/rycklah23/belrycklah/assets/142331371/a7b83628-778e-487e-8d0f-991576c9be8e)
![image](https://github.com/rycklah23/belrycklah/assets/142331371/e4335681-ff65-4c59-b866-dd8b35a040f4)

Once that is done we will continue to setup osTicket in the browser. Click Continue on the osTicket browser page. Fill out the page as required except the Database Settings at the bottom of the page. We will get to that.

We will want to download and install HeidiSQL from the Installation Files.

When the program is open we will create a new session in it.

We want to make sure the username is root and the password is Password1.

Once we are connected to the session we will go back to the browser to finish setting everything up. Under the Database Settings in the browser the username will be root and the password will be Password1.

We will now create a new database within HeidiSQL. In Heidi right click on the left side where is says "Unnamed", select "create new", and then select "database". Name the new database osTicket. Once we have the new database setup go back to the osTicket browser and under MySQL Database type in osTicket.


![image](https://github.com/rycklah23/belrycklah/assets/142331371/cbd2e4a2-44f1-4bc5-aaa6-d2fadb99ab75)


![image](https://github.com/rycklah23/belrycklah/assets/142331371/0df64fa2-87d4-43cc-9691-120770bd48d5)


![image](https://github.com/rycklah23/belrycklah/assets/142331371/c5fc08d4-2387-4825-91d9-350ac486ef63)


![image](https://github.com/rycklah23/belrycklah/assets/142331371/2335b11a-0484-4d3d-98dc-f58d3f7ac854)

The last step is to do some clean up. We will want to delete the setup folder in our system. -Delete: C:\inetpub\wwwroot\osTicket\setup Only delete the setup folder and nothing else.

We then will want to set the permissions back to "Read" only in the ost-config.php file

The last step after that is to login to osTicket on the browser.

Congrats! You have now successfully installed and setup osTicket!

![image](https://github.com/rycklah23/belrycklah/assets/142331371/45c37763-081f-4782-ab5f-202ce6ebc199)


![image](https://github.com/rycklah23/belrycklah/assets/142331371/da314cca-abb6-43f3-b76a-45196ac85a4b)


 ![image](https://github.com/rycklah23/belrycklah/assets/142331371/9fd90170-dbe4-4c41-b790-52455d800c51)
