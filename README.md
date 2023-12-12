# Virtualbox Cheat Sheet
Virtualbox Cheat Sheet with the most needed stuff..
<br />
<br />


<br><br><br><br>





# Old versions
- https://www.virtualbox.org/wiki/Download_Old_Builds_6_1




<br><br><br><br>




# Performance
- Go to Nvidia 3D Settings and add VirtualBoxVM.exe to your list and enable everything (https://superuser.com/questions/779070/use-nvidia-gpu-from-virtualbox)




















<br><br>
 _____________________________________________________
 _____________________________________________________
<br><br>


# Kill active process
```bash
# get all the processes containing VB
ps -A | grep VB

# then kill all processes with the command
sudo kill <pid>
```


<br><br>

# Install

<br><br>

## Ubuntu
```bash
sudo apt install virtualbox

sudo usermod -G vboxusers -a $USER

# sign out and in again for group changes take effect
```






<br><br>
<br><br>


# Uninstall


<br><br>

## Linux
```bash
# method 1
sudo apt-get remove --purge virtualbox-6.1 

# method 2
sudo apt-get remove virtualbox-* --purge
```





































<br><br>
 _____________________________________________________
 _____________________________________________________
<br><br>


# Guest Additions

## Install Guest Additions Ubuntu

#### Step 1. Install required packages. 
Before installing  VirtualBox Guest Additions on Ubuntu 18.04 & ubuntu 20.04 we need to install some required packages. So open the terminal and run the following command:
```bash
sudo apt install linux-headers-$(uname -r) build-essential dkms
```  

#### Step 2. Install Guest Additions using virtual box.
In order To install VirtualBox Guest Additions on Ubuntu virtual machine, Got to VirtualBox  -  select the Devices from VirtualBox host application menu - click Insert Guest Additions CD image.
- Or download here (Check your vbox version before):
  - [https://download.virtualbox.org/virtualbox/7.0.6/](https://download.virtualbox.org/virtualbox/7.0.6/VBoxGuestAdditions_7.0.6.iso)

#### Step 3. 
This will open a pop up window and it will ask you to run it. Press Run button <br />
After pressing Run button it will install VirtualBox Guest Additions. Press enter to close the window.

On Linux you can go inside of the CD and then run in terminal:
```
autorun.sh
```


#### Step 4. Shut down. 



#### Step 5(VERY IMPORTANT)
In some cases people get black screen after boot up. To fix this DISBALE 3D acceleartion on virtualbox settings for this machine


#### Step 6.
Start virtual machine and check if copy and paste works to verify that Guest Additions was installed correctly.

<br><br>


## Deinstall Guest Additions if screen is black after boot
Press **alt + ctrl + f1** or **f2** to open terminal:
```bash
cd /opt/virtualbox folder here
sudo sh uninstall.sh
```  






<br><br><br><br>





# Extension pack

<br><br>
<br><br>

## Uninstall
```
VBoxManage extpack uninstall "Oracle VM VirtualBox Extension Pack" 
```

<br><br>
<br><br>

## Install
```
VBoxManage extpack install /Desktop/Oracle_VM_VirtualBox_Extension_Pack-6.1.38-153438.vbox-extpack
```

- https://www.oracle.com/virtualization/technologies/vm/downloads/virtualbox-downloads.html#extpack
- You can install via Settings > Extensions

<br><br>

## Error while installing extension pack
- If you got a error related to something as ACCES DENIED then run virtualbox as admin and try again

<br><br>

## VERR_FILE_NOT_FOUND - /usr/lib/virtualbox/ExtensionPacks/Oracle_VM_VirtualBox_Extension_Pack/linux.amd64/VBoxPuelMain.so: undefined symbol: RTUtf16NCmp.
- Download the extension pack that will match your virtualbox version
  - https://www.virtualbox.org/wiki/Download_Old_Builds_6_1























<br><br>

 _____________________________________________________

 _____________________________________________________

<br><br>

## Shared folder permissions
```bash
sudo adduser usernamehere vboxsf
# reboot after this
```  

































<br><br>

 _____________________________________________________

 _____________________________________________________

<br><br>

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





































<br><br>

 _____________________________________________________

 _____________________________________________________

<br><br>

# Convert
**IMPORTANT**
You must remove virtualbox encryption before convert or it not work..


## Convert .vdmk to .vdi
```bash
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" clonehd --format vdi "Y:\Ubuntu 20.04 LTS v3\Ubuntu 20.04 LTS v3.vmdk" "Y:\convertarea\Ubuntu 20.04 LTS v3\Ubuntu 20.04 LTS v3.vdi"
```  











































<br><br>

 _____________________________________________________

 _____________________________________________________

<br><br>


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


































<br><br>

 _____________________________________________________

 _____________________________________________________

<br><br>

## Resize dynamic VM
```bash
# The resize number is MB
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" modifyhd "C:\Users\Administrator\VirtualBox VMs\Windows 7\Windows 7.vdi" --resize 200000
```  

## Convert fixed disc into dynamic
```bash
"C:\Program Files\Oracle\VirtualBox\VBoxManage.exe" clonehd "C:\Users\Administrator\VirtualBox VMs\Windows 7\Windows 7.vmdk" "C:\Users\Administrator\VirtualBox VMs\Windows 7\Windows 7 dynamic-DRIVE.vmdk" --variant Standard
```  







































<br><br>

 _____________________________________________________

 _____________________________________________________

<br><br>

# Shortcuts

## Leave scale mode
- Right Ctrl (Host Key) + c
