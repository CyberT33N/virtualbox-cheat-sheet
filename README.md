# Virtualbox Cheat Sheet
Virtualbox Cheat Sheet with the most needed stuff..
<br />
<br />
<br />
<br />



# Guest Additions

## Install Guest Additions Ubuntu

#### Step 1. Install required packages. 
Before installing  VirtualBox Guest Additions on Ubuntu 18.04 & ubuntu 20.04 we need to install some required packages. So open the terminal and run the following command:
```bash
sudo apt install linux-headers-$(uname -r) build-essential dkms
```  

#### Step 2. Install Guest Additions using virtual box.
In order To install VirtualBox Guest Additions on Ubuntu virtual machine, Got to VirtualBox  -  select the Devices from VirtualBox host application menu - click Insert Guest Additions CD image.


#### Step 3. 
This will open a pop up window and it will ask you to run it. Press Run button <br />
After pressing Run button it will install VirtualBox Guest Additions. Press enter to close the window.


#### Step 4. Shut down. 



#### Step 5(VERY IMPORTANT)
In some cases people get black screen after boot up. To fix this DISBALE 3D acceleartion on virtualbox settings for this machine


#### Step 6.
Start virtual machine and check if copy and paste works to verify that Guest Additions was installed correctly.

<br />
<br />


## Deinstall Guest Additions if screen is black after boot
Press **alt + ctrl + f1** or **f2** to open terminal:
```bash
cd /opt/virtualbox folder here
sudo sh uninstall.sh
```  

<br />
<br />


 _____________________________________________________
 _____________________________________________________


<br />
<br />

## Shared folder permissions
```bash
sudo adduser usernamehere vboxsf
# reboot after this
```  

<br />
<br />


 _____________________________________________________
 _____________________________________________________


<br />
<br />

## Change UUID
```bash
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" internalcommands sethduuid "C:\Users\Administrator\VirtualBox VMs\Ubuntu 20.04 LTS v4\Ubuntu 20.04 LTS v4.vdi"
```  

## Start VM from terminal
```bash
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" startvm "OS X 10.11 El Capitan Retail" --x
```  

## list all VM
```bash
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" list vms
```  



<br />
<br />


 _____________________________________________________
 _____________________________________________________


<br />
<br />

# Convert
**IMPORTANT**
You must remove virtualbox encryption before convert or it not work..


## Convert .vdmk to .vdi
```bash
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" clonehd --format vdi "Y:\Ubuntu 20.04 LTS v3\Ubuntu 20.04 LTS v3.vmdk" "Y:\convertarea\Ubuntu 20.04 LTS v3\Ubuntu 20.04 LTS v3.vdi"
```  



<br />
<br />


 _____________________________________________________
 _____________________________________________________


<br />
<br />


## Reduce size of .vdi files
If you have .vmdk files then convert them first to .vdi <br />
<br />
First we remove empty space on our VM and after this we use the --compact argument on our .vdi file.

```bash
# Linux
sudo dd if=/dev/zero of=/EMPTY bs=1M  || echo "dd exit code $? is suppressed"
sudo rm -f /EMPTY
```  

```bash
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" modifyhd "Y:\convertarea\Ubuntu 20.04 LTS v3\Ubuntu 20.04 LTS v3.vdi" --compact
```  



<br />
<br />


 _____________________________________________________
 _____________________________________________________


<br />
<br />

## Resize dynamic VM
```bash
# The resize number is MB
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" modifyhd "C:\Users\Administrator\VirtualBox VMs\Windows 7\Windows 7.vdi" --resize 200000
```  

## Convert fixed disc into dynamic
```bash
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" clonehd "C:\Users\Administrator\VirtualBox VMs\Windows 7\Windows 7.vmdk" "C:\Users\Administrator\VirtualBox VMs\Windows 7\Windows 7 dynamic-DRIVE.vmdk" --variant Standard
```  


<br />
<br />


 _____________________________________________________
 _____________________________________________________


<br />
<br />

# Shortcuts

## Leave scale mode
- Right Ctrl (Host Key) + c
