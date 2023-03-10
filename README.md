<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>


<p>
<img src="https://i.imgur.com/hVsLVb1.png" height="80%" width="80%" alt="Creating VM"/>
</p>
<p>
Before doing anything pertaining to osTicket, you'll have to create a Resource Group and a Virtual Machine (VM). Please take a look at this tutorial, <a href="https://github.com/brittanynalexander/Azure-VMs">Azure-VMs</a>, as I walk you through exactly how to do that and how to connect to your VM using Remote Desktop. For the sake of this tutorial, let's review a couple of main steps. Of course you'll have to create the actual VM, name it and create credentials for signing in, as well as filling in and selecting other information. 
</p>
<br />


<p>
<img src="https://i.imgur.com/yktJPTL.png" height="80%" width="80%" alt="VM Connection"/>
</p>
<p>
To connect to the VM you'll have to utilize Remote Desktop Connection on Windows or Microsoft Remote Desktop on a Mac. On Windows, open the app and paste your VM's Public IP Address into the "Computer" section and hit "Connect". On a Mac after you've opened the app, you'll have to hit "Add PC" then enter the IP Address in the "PC Name" section. 
  
By the way, you can find the Public IP Address to your VM within the Essentials section of your VM. I also spoke about locating the Essentials in my <a href="https://github.com/brittanynalexander/Azure-VMs">Azure-VMs</a> tutorial. To recap, if the Virtual Machines icon is not on your home screen, you can simply search "virtual machines" in the search bar, click on it then click on your VM. I've named mine VM-osTicket. The Public IP Address will be at the very top on the right-hand side. 
  
After you've hit "Connect" on your Remote Desktop app, you'll have to enter the credentials you created when creating your VM then hit "Ok" or "Continue". You'll then be asked if you want to continue despite certificate errors, hit "Yes". (The certificate will be the name of your VM and since the certificate isn't valid, Remote Desktop cannot verify it.)
</p>
<br />


<p>
<img src="https://i.imgur.com/1jtkDba.png" height="80%" width="80%" alt="VM Home Screen"/>
</p>
<p>
After hitting "Yes" from your Remote Desktop app, you will be connected to your VM! This is what the home screen should look like.
</p>
<br />


<p>
<img src="https://i.imgur.com/6BWoMxO.png" height="80%" width="80%" alt="VM Home Screen"/>
</p>
<p>
<img src="https://i.imgur.com/2ijUhzW.png" height="80%" width="80%" alt="VM Home Screen"/>
</p>
<p>
The first prerequisite to install will be Internet Information Services (IIS), which is a Microsoft web server that will allow the VM to serve websites. OsTicket runs off of a website so you'll have to install and configure IIS to actually run osTicket. 
  
To get to the Control Panel you can either search for it in the search bar next to the start menu, or you can right click the start menu, select "Run", then type "control panel". Select "Programs", then under "Promgrams and Features" select "Turn Windows Features On or Off". Turn IIS on by selecting the box next to it. Expand "Internet Information Services", expand "World Wide Web Services", expand "Application Development Features", and select "CGI", then select "Ok". We need to install CGI with IIS because CGI let's us install a PHP Manager. PHP is a programming language which osTicket runs off of, so we need to install a web server (ISS) with PHP.
</p>
<br />


<p>
<img src="https://i.imgur.com/pujBt2t.png" height="80%" width="80%" alt="VM Home Screen"/>
</p>
<p>
Next, we'll have to download and install a PHP Manager. You can simply Google "php manager download" for the link to do so. After that's done, open and install it.
</p>
<br />


<p>
<img src="https://i.imgur.com/1jtkDba.png" height="80%" width="80%" alt="VM Home Screen"/>
</p>
<p>
After hitting "Yes" from your Remote Desktop app, you will be connected to your VM! This is what the home screen should look like.
</p>
<br />


<p>
<img src="https://i.imgur.com/1jtkDba.png" height="80%" width="80%" alt="VM Home Screen"/>
</p>
<p>
After hitting "Yes" from your Remote Desktop app, you will be connected to your VM! This is what the home screen should look like.
</p>
<br />
