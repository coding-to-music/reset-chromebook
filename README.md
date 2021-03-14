<p style="color: red; font-weight: bold">>>>>>  gd2md-html alert:  ERRORs: 0; WARNINGs: 1; ALERTS: 3.</p>
<ul style="color: red; font-weight: bold"><li>See top comment block for details on ERRORs and WARNINGs. <li>In the converted Markdown or HTML, search for inline alerts that start with >>>>>  gd2md-html alert:  for specific instances that need correction.</ul>


<p style="color: red; font-weight: bold">Links to alert messages:</p><a href="#gdcalert1">alert1</a>
<a href="#gdcalert2">alert2</a>
<a href="#gdcalert3">alert3</a>


<p style="color: red; font-weight: bold">>>>>> PLEASE check and correct alert issues and delete this message and the inline alerts.<hr></p>






# Reset Chromebook Create New Linux Environment




[TOC]


# March 2021 reset linux in chromebook, this is what I did:

``` Javascript
// back up the following directories
- .ssh
- .gitconfig
- .bash_history
- .bash_alias

// Reset the chromebook in the Chromebook settings

Restore the following directories and files
- .ssh
- .gitconfig
- .bash_history
- .bash_alias

// download the vscode deb file from here: 
// https://code.visualstudio.com/Download

// Unzip / untar / remove from deb packaging

    8  sudo apt install code_1.54.2-1615424848_amd64.deb


    9  sudo dpkg -i code_1.54.2-1615424848_amd64.deb

   10  sudo apt update
   11  apt list --upgradable
   12  sudo apt upgrade
   13  apt --fix-broken install
   14  sudo apt --fix-broken install
   15  sudo apt upgrade
   16  ll
   17  sudo apt-get install -f
   18  code --version
   19  sudo apt-get install apt-transport-https
   20  sudo apt install gnome-keyring
   21  code 
   22  mkdir ap
       apt list --installed

In root

Mkdir .ssh

Chmod 700 .ssh

Cd .ssh

// Create SSH public and private keys
// Store them here
// or copy them from backup
Chmod 600 each_private_key # the ones not with .pub suffix





```




# List of required items to install






*   set up .bashrc and .bash_alias
*   git
*   vscode
*   ssh keys
    *   netflify - no ssh keys
    *   digitalocean - no ssh keys
    *   github - changed ssh key
*   nvm
*   npm
*   yarn
*   set up mounted virtual storage




## **0 Installing Git for Linux**


Edit the file .bash_aliases and put the contents from GitHub




```
source ~/.bashrc
```




The above command is for Ubuntu and works on all Recent Ubuntu versions, tested from Ubuntu 




## **1 Installing Git for Linux**


Download and install Git for Linux:




```
sudo apt-get install git
```




The above command is for Ubuntu and works on all Recent Ubuntu versions, tested from Ubuntu 16.04 to Ubuntu 18.04 LTS (Bionic Beaver) and it's likely to work the same way on future versions.




## **2 Configuring GitHub**


Once the installation has successfully completed, the next thing to do is to set up the configuration details of the GitHub user. To do this use the following two commands by replacing "user_name" with your GitHub username and replacing "email_id" with your email-id you used to create your GitHub account.




```
git config --global user.name coding-to-music
git config --global user.email connors.tom@gmail.com
```




The following image shows an example of my configuration with my "user_name" being "akshaypai" and my "email_id" being "abc123@gmail.com"




## Chromebook is Debian




```
connorstom@penguin:~$ cat /etc/os-release
PRETTY_NAME="Debian GNU/Linux 10 (buster)"
NAME="Debian GNU/Linux"
VERSION_ID="10"
VERSION="10 (buster)"
VERSION_CODENAME=buster
ID=debian
HOME_URL="https://www.debian.org/"
SUPPORT_URL="https://www.debian.org/support"
BUG_REPORT_URL="https://bugs.debian.org/"
```






## Digitalocean is Ubuntu




### Install Git on the server


 sudo apt-get install git


Now git should be installed. To check use


 git --version


git version 2.19.1




## SSH Keys




### Create a directory for the public keys


In root


Mkdir .ssh


Chmod 700 .ssh


Cd .ssh


Create SSH public and private keys


Store them here


Chmod 600 private_key




### Create SSH Key for Github


Now you need to create your SSH key for Github


ssh-keygen -t rsa -C “connors.tom@gmail.com”


It will get saved to 


home/tom/.ssh/id_rsa                // this is the private key, very long paragraph


home/tom/.ssh/id_rsa.pub         // this is the public key,         short paragraph


Copy that key in that file. I would suggest using Win SCP to download the file similar to FTP


ssh-rsa 
7 lines long private key short paragraph this is what you will paste into GitHub and Digitalocean
e1f0vfsMPOANChLOUWbSJTtf4s4P2x6CAYCOQYcd “connors.tom@gmail.com”

-----BEGIN RSA PRIVATE KEY-----
really big long private key
-----END RSA PRIVATE KEY-----


Once you copy the key, sign into Github and goto “Settings->SSH and GPG Keys” and add and name the new key 






<p id="gdcalert1" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image1.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert2">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>




![alt_text](images/image1.png "image_tooltip")






## How to Install Node.js and npm on Ubuntu


[https://linuxize.com/post/how-to-install-node-js-on-ubuntu-18.04/](https://linuxize.com/post/how-to-install-node-js-on-ubuntu-18.04/)




## Check os version in Linux


The procedure to find os name and version on Linux:






1. Open the terminal application (bash shell)
2. For remote server login using the ssh: **<code>ssh user@server-name</code></strong>
3. Type any one of the following command to find os name and version in Linux: \
<strong><code>cat /etc/os-release \
lsb_release -a \
hostnamectl</code></strong>
4. Type the following command to find Linux kernel version: \
<strong><code>uname -r</code></strong>


Let us see all examples in detailed.




## /etc/os-release file


Type the following [cat command](https://www.cyberciti.biz/faq/linux-unix-appleosx-bsd-cat-command-examples/):




```
    $ cat /etc/os-release
```




Sample outputs:




```
NAME="Ubuntu"
VERSION="17.10 (Artful Aardvark)"
ID=ubuntu
ID_LIKE=debian
PRETTY_NAME="Ubuntu 17.10"
VERSION_ID="17.10"
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
VERSION_CODENAME=artful
UBUNTU_CODENAME=artful
```






## lsb_release command


The lsb_release command gives LSB (Linux Standard Base) and distribution-specific information on the CLI. The syntax is:




```
    $ lsb_release -a
```




Sample outputs:




```
LSB Version:        :core-4.1-amd64:core-4.1-noarch
Distributor ID:        CentOS
Description:        CentOS Linux release 7.4.1708 (Core) 
Release:        7.4.1708
Codename:        Core
```






## hostnamectl command


Use hostnamectl command to query and change the system hostname and related settings. Just type the following command to check OS name and Linux kernel version:




```
    $ hostnamectl
```




Sample outputs:




```
  Static hostname: nixcraft-www-42
         Icon name: computer-vm
           Chassis: vm
        Machine ID: beb217fbb4324b7d9959f78c279e6599
           Boot ID: 10f00cc5ca614b518a84d1793d0134bc
    Virtualization: qemu
  Operating System: Ubuntu 16.04.3 LTS
            Kernel: Linux 4.10.0-42-generic
      Architecture: x86-64
```






## uname command


Just print Linux kernel version, run:




```
    $ uname -r
```




Sample outputs:






<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image2.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>




![alt_text](images/image2.jpg "image_tooltip")




Another option is to type the following command:




```
    $ cat /proc/version
```




Sample outputs:




```
Linux version 3.10.0-693.11.6.el7.x86_64 (mockbuild@x86-041.build.eng.bos.redhat.com) (gcc version 4.8.5 20150623 (Red Hat 4.8.5-16) (GCC) ) #1 SMP Thu Dec 28 14:23:39 EST 2017
```






### **Installation instructions - node**


[https://github.com/nodesource/distributions/blob/master/README.md#debinstall](https://github.com/nodesource/distributions/blob/master/README.md#debinstall)


Node.js v15.x:




```
# Using Ubuntu (Digitalocean)
curl -sL https://deb.nodesource.com/setup_15.x | sudo -E bash -
sudo apt-get install -y nodejs


# Using Debian, as root  (Chromebook)
curl -sL https://deb.nodesource.com/setup_15.x | sudo bash -
sudo apt-get install -y nodejs
```






### **Installation instructions - yarn**




```
curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
     echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
     sudo apt-get update && sudo apt-get install yarn
```




connorstom@penguin:~$ node --version


v15.3.0


connorstom@penguin:~$ yarn --version


1.22.5




## **Installing Node.js and npm using NVM**


NVM (Node Version Manager) is a bash script used to manage multiple active Node.js versions. With NVM you can install and uninstall any specific Node.js version you want to use or test.


To install Node.js and npm using NVM on your Ubuntu system, perform the following steps:




### **1. Installing NVM (Node Version Manager) script**


To download and install the `nvm` script run:


Also check latest info from: [https://github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm)




```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.35.3/install.sh | bash
```




The command above will clone the NVM repository from Github to the `~/.nvm` directory:


The script clones the nvm repository to ~/.nvm, and attempts to add the source lines from the snippet below to the correct profile file (~/.bash_profile, ~/.zshrc, ~/.profile, or ~/.bashrc).




```
=> Close and reopen your terminal to start using nvm or run the following to use it now:


export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion
```




As the output above says, you should either close and reopen the terminal or run the commands to [add the path](https://linuxize.com/post/how-to-add-directory-to-path-in-linux/) to `nvm` script to the current shell session. You can do whatever is easier for you.


Once the script is in your `PATH`, verify that `nvm` was properly installed by typing:




```
nvm --version
0.34.0
```






### **2. Installing Node.js and npm**


Now that the `nvm` is installed you can install the latest available version of Node.js, by typing:




```
nvm install node
```




The output should look something like this:




```
Downloading and installing node v12.8.1...
Downloading https://nodejs.org/dist/v12.8.1/node-v12.8.1-linux-x64.tar.xz...
######################################################################### 100.0%
Computing checksum with sha256sum
Checksums matched!
Now using node v12.8.1 (npm v6.10.2)
Creating default alias: default -> node (-> v12.8.1)
```




Once the installation is completed, verify it by printing the Node.js version:




```
node --version
v12.8.1
```




Let’s install two more versions, the latest LTS version and version 8.10.0




```
nvm install --lts
nvm install 8.10.0
nvm install 10.20.0
```




To list installed Node.js versions type:




```
nvm ls
```




The output should look something like this:




```
->      v8.10.0
       v10.16.3
        v12.8.1
default -> node (-> v12.8.1)
node -> stable (-> v12.8.1) (default)
stable -> 12.8 (-> v12.8.1) (default)
iojs -> N/A (default)
unstable -> N/A (default)
lts/* -> lts/dubnium (-> v10.16.3)
lts/argon -> v4.9.1 (-> N/A)
lts/boron -> v6.17.1 (-> N/A)
lts/carbon -> v8.16.1 (-> N/A)
lts/dubnium -> v10.16.3
```




The entry with an arrow on the right (-> v8.10.0) is the Node.js version used in the current shell session and the default version is set to v12.8.1. Default version is the version that will be active when opening new shells.


You can change the currently active version with:




```
nvm use 10.16.3
Now using node v10.16.3 (npm v6.9.0)
```




If you want to change the default Node.js version use the following command:




```
nvm alias default 10.16.3
```






# Install Yarn


Before you start using Yarn, you'll first need to install it on your system. There are a growing number of different ways to install Yarn:




Operating system:




Debian / Ubuntu 




Version:




         Stable (1.22.5)         Release Candidate (1.22.0)         Nightly (1.23.0-20200928.1349)       




### Debian / Ubuntu


On Debian or Ubuntu Linux, you can install Yarn via our Debian package repository. You will first need to configure the repository:




```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt update && sudo apt install yarn
sudo apt update && sudo apt install apt-utils
```






### **Install build-essential Package**


[https://www.osetc.com/en/how-to-install-build-essential-on-ubuntu-16-04-18-04-linux.html](https://www.osetc.com/en/how-to-install-build-essential-on-ubuntu-16-04-18-04-linux.html)






---




The build-essential package is already available on the default Ubuntu repository. so you just need to install it with the apt install command. Before installing build-essential package, you need to update the Ubuntu repo index with the following command:




```
$ sudo apt update
```




Then type the following command to install build-essential package:




```
$ sudo apt install build-essential
```




Outputs:




```
devops@devops-osetc:~$ sudo apt install build-essential
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages were automatically installed and are no longer required:
libllvm6.0 x11proto-dri2-dev x11proto-gl-dev
Use 'sudo apt autoremove' to remove them.
The following NEW packages will be installed:
build-essential
0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
Need to get 4,758 B of archives.
After this operation, 20.5 kB of additional disk space will be used.
Get:1 http://mirrors.aliyun.com/ubuntu bionic/main amd64 build-essential amd64 12.4ubuntu1 [4,758 B]
Fetched 4,758 B in 1s (3,325 B/s)
Selecting previously unselected package build-essential.
(Reading database ... 231616 files and directories currently installed.)
Preparing to unpack .../build-essential_12.4ubuntu1_amd64.deb ...
Unpacking build-essential (12.4ubuntu1) ...
Setting up build-essential (12.4ubuntu1) ...
```




**Check GCC Version**


After the installation process is completed, you can confirm your installation by checking for GCC version with the following command:




```
$ gcc --version
```




Outputs:




```
devops@devops-osetc:~$ gcc --version
gcc (Ubuntu 7.3.0-27ubuntu1~18.04) 7.3.0
Copyright (C) 2017 Free Software Foundation, Inc.
This is free software; see the source for copying conditions. There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
```






### **Create C program, compile and run it**


Let’s write a simple C program as below:




```
#include <stdio.h>


int main()
{
    printf("Hell, World!\n ");
}
```




Save this program as test.c file in your Ubuntu system, and try to execute the following command to compile and execute it:




```
$ gcc -o test test.c
$ ./test
```




Outputs:




```
devops@devops-osetc:~$ gcc -o test test.c
devops@devops-osetc:~$ ./test
Hell, World!
```








---




You should know that how to install build-essential on your Ubuntu 14.04 or 16.04 or 18.04 Linux from this guide. And if you want to learn more about the build-essential, you can go the below [official web site](https://packages.ubuntu.com/xenial/build-essential) to checking the getting started guide directly.




### **Visual Studio Code on Linux**




### **VS Code install for Debian and Ubuntu based distributions**


[https://code.visualstudio.com/docs/setup/linux](https://code.visualstudio.com/docs/setup/linux)


The easiest way to install Visual Studio Code for Debian/Ubuntu based distributions is to download and install the [.deb package (64-bit)](https://go.microsoft.com/fwlink/?LinkID=760868), either through the graphical software center if it's available, or through the command line with:




```
sudo apt install ./<file>.deb


download the file from the website to downloads and move it to linux file system then run:


https://code.visualstudio.com/docs/setup/linux
https://github.com/nodesource/distributions/blob/master/README.md#debinstall


# If you're on an older Linux distribution, you will need to run this instead:
# sudo dpkg -i <file>.deb
# sudo apt-get install -f # Install dependencies
connorstom@penguin:~$ code --version
1.51.1
e5a624b788d92b8d34d1392e4c4d9789406efe8f
x64
```




Installing the .deb package will automatically install the apt repository and signing key to enable auto-updating using the system's package manager. Note that 32-bit and .tar.gz binaries are also available on the [VS Code download page](https://code.visualstudio.com/Download).


The repository and key can also be installed manually with the following script:




```
curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /usr/share/keyrings/
sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/vscode stable main" > /etc/apt/sources.list.d/vscode.list'
```




Then update the package cache and install the package using:




```
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install code # or code-insiders


sudo apt install gnome-keyring
```






## **Installing Visual Studio Code on Ubuntu**


[https://linuxize.com/post/how-to-install-visual-studio-code-on-ubuntu-18-04/](https://linuxize.com/post/how-to-install-visual-studio-code-on-ubuntu-18-04/)


To install Visual Studio Code on your Ubuntu system, follow these steps:






1. First, update the packages index and install the dependencies by typing:
2. `sudo apt update`
3. `sudo apt install software-properties-common apt-transport-https wget`
4. Next, import the Microsoft GPG key using the following [wget command](https://linuxize.com/post/wget-command-examples/):
5. `wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -`
6. And enable the Visual Studio Code repository by typing:
7. `sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"`
8. Once the [apt repository is enabled](https://linuxize.com/post/how-to-add-apt-repository-in-ubuntu/), install the latest version of Visual Studio Code with:
9. `sudo apt update`
10. `sudo apt install code`


That’s it. Visual Studio Code has been installed on your Ubuntu desktop and you can start using it.




## **Starting Visual Studio Code**


Now that VS Code is installed on your Ubuntu system you can launch it either from the command line by typing `code` or by clicking on the VS Code icon (`Activities -> Visual Studio Code`).


When you start VS Code for the first time, a window like the following should appear:

<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image3.jpg). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>

![alt_text](images/image3.jpg "image_tooltip")

You can now start installing extensions and configuring VS Code according to your preferences.

## **Updating Visual Studio Code**

When a new version is released you can update the Visual Studio Code package through your desktop standard Software Update tool or by running the following commands in your terminal:
```
sudo apt update
sudo apt upgrade