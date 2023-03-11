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
To connect to the VM you'll have to utilize Remote Desktop Connection on Windows or Microsoft Remote Desktop on a Mac. On Windows, open the app and paste your VM's Public IP Address into the "Computer" section and select "Connect". On a Mac after you've opened the app, you'll have to select "Add PC" then enter the IP Address in the "PC Name" section. 
  
By the way, you can find the Public IP Address to your VM within the Essentials section of your VM. I also spoke about locating the Essentials in my <a href="https://github.com/brittanynalexander/Azure-VMs">Azure-VMs</a> tutorial. To recap, if the Virtual Machines icon is not on your home screen, you can simply search "virtual machines" in the search bar, click on it then click on your VM. I've named mine VM-osTicket. The Public IP Address will be at the very top on the right-hand side. 
  
After you've clicked "Connect" on your Remote Desktop app, you'll have to enter the credentials you created when creating your VM then click "Ok" or "Continue". You'll then be asked if you want to continue despite certificate errors, click "Yes". (The certificate will be the name of your VM and since the certificate isn't valid, Remote Desktop cannot verify it.)
</p>
<br />


<p>
<img src="https://i.imgur.com/1jtkDba.png" height="80%" width="80%" alt="VM Home Screen"/>
</p>
<p>
After clicking "Yes" from your Remote Desktop app, you will be connected to your VM! This is what the home screen should look like.
</p>
<br />


<p>
<img src="https://i.imgur.com/6BWoMxO.png" height="80%" width="80%" alt="IIS"/>
</p>
<p>
<img src="https://i.imgur.com/2ijUhzW.png" height="80%" width="80%" alt="CGI"/>
</p>
<p>
The first prerequisite to install will be Internet Information Services (IIS), which is a Microsoft web server that will allow the VM to serve websites. OsTicket runs off of a website so you'll have to install and configure IIS to actually run osTicket. 
  
To get to the Control Panel you can either search for it in the search bar next to the start menu, or you can right click the start menu, select "Run", then type "control panel". Select "Programs", then under "Promgrams and Features" select "Turn Windows Features On or Off". Turn IIS on by selecting the box next to it. Expand "Internet Information Services", expand "World Wide Web Services", expand "Application Development Features", select "CGI", then select "Ok".
  
We need to install CGI with IIS because CGI let's us install a PHP Manager. PHP is a programming language which osTicket runs off of, so we need to install a web server (ISS) with PHP.
</p>
<br />


<p>
<img src="https://i.imgur.com/Q2fnyKC.png" height="80%" width="80%" alt="Download PHP Manager"/>
</p>
<p>
<img src="https://i.imgur.com/pujBt2t.png" height="80%" width="80%" alt="Download and Install"/>
</p>
<p>
Next, we'll have to download and install a PHP Manager. You can simply Google "php manager download" for the link to do so. After that's done, double click your file and install it.
</p>
<br />


<p>
<img src="https://i.imgur.com/eEF5lSc.png" height="80%" width="80%" alt="Rewrite Module"/>
</p>
<p>
Next, we'll download and install a Rewrite Module. To my understanding, it essentially allows an IIS administrator to change URLS to a URL that users can remember easier, and search engines can find faster. Find a downloadable link, then download and install.
</p>
<br />


<p>
<img src="https://i.imgur.com/rJweSJi.png" height="80%" width="80%" alt="Local Hard Drive"/>
</p>
<p>
<img src="https://i.imgur.com/cIKEcXw.png" height="80%" width="80%" alt="PHP Directory"/>
</p>
<p>
Now we'll have to create a PHP directory (C:\PHP) on the local hard drive. Open your File Explorer app. Most desktops come with it pinned to the taskbar; it looks like a folder. You can always search "file explorer" in the search bar next to the start menu if the app isn't pinned. 
  
In the File Explorer, select "This PC" on the left hand side. The local hard drive will show as "Local Disk (C:)" on your desktop by the way, but for this tutorial in the VM, it will show as "Windows (C:)" if you chose Windows as your Operating System (OS). Double click on the local hard drive. Right click on an empty space, scroll down to "Run", then select "Folder". You can decide what to name it but I'll be naming the folder "PHP".
</p>
<br />


<p>
<img src="https://i.imgur.com/ZhOKImJ.png" height="80%" width="80%" alt="VM Home Screen"/>
</p>
<p>
Prior, we downloaded a PHP Manager. Now we'll download PHP, (a programming language that osTicket runs off of), and unzip those contents into the folder we just made, (C:\PHP). Unzipping is extracting contents in a file.
  
Google "PHP download", find a link, then proceed to do so. Once downloaded, it will be in the Downloads section in your File Explorer. Right click on the PHP file and select "Extract All". Paste the location of the folder to where you want to extract the file, which is "C:\PHP". Alternatively, you can select "Browse", double click on "This PC", double click on "Windows (C:)", select "PHP", click "Select Folder", then click "Extract". Now your PHP folder will have all the contents from the PHP file.
</p>
<br />


<p>
<img src="https://i.imgur.com/TSYC2Y4.png" height="80%" width="80%" alt="VM Home Screen"/>
</p>
<p>
The next installation will be a C++ redistributable which PHP requires. Google a downloadable link then download and install.
</p>
<br />


<p>
<img src="https://i.imgur.com/HITzYIC.png" height="80%" width="80%" alt="VM Home Screen"/>
</p>
<p>
MySQL Server will be the next installation needed. You know what to do, find the link then download and install it.
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
