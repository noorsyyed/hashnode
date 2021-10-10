## Install and Run multiple instances of Microsoft Teams on Windows

With the tremendous growth of collaboration tools and communicating software platforms like Microsoft Teams, Slack etc. Such tools became ubiquitous with the advent of pandemic, not just the tech companies but non tech companies started to rely on these platforms for effective team collaboration and productivity. This exponential growth paved way to have many people manage their account in multiple tenants.  If somebody like be is part of multiple organizations which may pertain to the clients or parent and partner companies, they find it difficult to manage multiple account in single instance of Teams on PCs, Macs & Linux, because managing multiple account is not present on these platforms. However, Teams on Android and iOS have seamless multiple tenant support.

Tap on profile in teams on mobile to switch Organization & Account


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1633805149838/fzoc4PxLF.png)

While on the other hand slack is much mature compared to teams when it comes to multi tenancy. It has the concept of workspaces and users can switch between them effortlessly.

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1633804355986/FVq445k9o.png)

Even on mobile switching and adding a new workspace is seamless

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1633804480528/aMZkLhFky.png)

We have workarounds to tackle desktop Teams incompetency to handle multiple accounts.  And in this post, I'm going to discuss two such workarounds


1. Install Teams site [https://teams.microsoft.com/](https://teams.microsoft.com/)  as an app in Microsoft Edge browser.


- Head over to above Teams site and login

- Once logged in click on the settings and more option **(...)** in the browser top bar

- From the menu select Apps and then **Install this site as an app**


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1633806189626/VlbjZRIm0.png)


- Give a name to the app and install. You can even select options as shown below. 

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1633806355389/wnpienRB4V.png)

This gives you feasibility to open another Teams instance on desktop beside desktop version of Teams. And can opt to have browser notifications turned on for the Teams app site to stay on top of everything.


2. Another way to have multiple instances of Teams running on windows, which is more a nerdy way is to install Linux GUI app on Windows Subsystem for Linux (WSL).  This is every fascinating and magical way to run Teams on windows. Process is as follows

For more details on WSL you can go [here](https://docs.microsoft.com/en-us/windows/wsl/about), explaining WSL is out of the scope of this post. But if anybody wants to a level down to understand it, they can get in touch with me I would love to explain. For now I'm just leaving Microsoft Docs like above and a very good article from [ Steve Pronovost](https://github.com/spronovo)  who works in the WSL team 
 [https://devblogs.microsoft.com/commandline/wslg-architecture/](https://github.com/microsoft/wslg) 

**WSL2 **is now part of windows and ***only available in Windows 10, Version 1903, Build 18362 or higher***

For our Teams GUI app to work we need to have **WSLg** 

%[https://github.com/microsoft/wslg]
 It is in preview and will generally be available in upcoming windows version.
One of the prerequisites for WSLg is
> 
Windows 10 Insider Preview build 21362+

The purpose of this project is to 
> 
enable support for running Linux GUI applications (X11 and Wayland) on Windows in a fully integrated desktop experience.

WSLg is part of latest WSL, so to update WSL to latest version run below command


```
wsl update
``` 

To install Teams on Linux we need to have one of the distributions of Linux installed on windows. To see installed Linux distributable run below command


> 
-v is for verbose


```
wsl --list -v
``` 

To see all the available online distributions which can be installed run

```
wsl --list --online
``` 
 
![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1633878316310/AOKLR7a0r.png)

We will install latest distro of ubuntu

```
wsl --install -d ubuntu
``` 
Once it is installed you will be asked to set username and password

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1633878874811/Hu0lFkJvyz.png)
Now we need download Teams package from [http://packages.microsoft.com](http://packages.microsoft.com) 


```
sudo wget http://packages.microsoft.com/repos/ms-teams/pool/main/t/teams/teams_1.4.00.7556_amd64.deb
``` 
Once it is retrieved, install 

```
sudo dpkg -i teams_1.4.00.7556_amd64.deb
``` 
once done, just type and enter

```
$ teams
``` 

And it will Teams app Linux window. 
And you can have it running side by side your windows Teams app. You can chat, call people, have meetings, upload files (it will open Linux folder explorer, isn't is awesome, I loved it).

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1633879551598/SoQvv8tV5.png)

Limitations I saw are, you cannot have screensharing and turn camera on because it is not detected.

I hope this post helps people out there who have multiple Teams accounts and want to run multiple instances of Teams on windows at the same time. Please leave your comments for any feedback and queries, I would love to hear from you guys and do share it in your circle. 