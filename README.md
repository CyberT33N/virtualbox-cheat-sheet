# Virtualbox Cheat Sheet
Virtualbox Cheat Sheet with the most needed stuff..
<br />
<br />
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
