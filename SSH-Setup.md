
# Operating Systems Course Repository

📌 Overview
- This repository contains  coursework, experiments, notes, and projects related to the Operating Systems (OS) course.
- The goal of this repository is to document the  learning process and provide practical implementations of core OS concepts.
- Topics covered include process management, memory management, file systems, system calls, and various OS tools.


## Practicle-1
### Install the SSH client and server in Linux OS

## Ubuntu OS
Download ISO File: https://ubuntu.com/download
```
sudo apt update
sudo apt install openssh-client
sudo apt install openssh-server
sudo systemctl status ssh
```

## CentOS OS
Download ISO File: https://www.centos.org/download/
```
sudo yum update -y
sudo yum –y install openssh-server openssh-clients
sudo systemctl start sshd
sudo systemctl status sshd
sudo systemctl enable sshd    
```

# SSH Communication Between Host (PC) to Guest(VM) and Guest(VM) to Guest(VM)

- Create Two VMs, Ubuntu and CentOS
  
### Create Custom Host-only Network
- Go to VirtualBox → File → Tools → Host Network Manager
- Create Network
- IP address: 192.168.56.1
- Subnet mask: 255.255.255.0

### Network Adapter Settings in VM
Go to VirtualBox → Select VM → Settings → Network.
- Enable Adapter 1:
  - Attached to: NAT
- Enable Adapter 2:
  - Name: Select vboxnet0  or create a new one (see below).
  - Promiscuous mode: Allow All
  - Cable connected:  (checked)


### Create Network 
<img width="669" height="406" alt="image" src="https://github.com/user-attachments/assets/d25379ee-2157-4159-a8cb-5b254d06281b" />
<img width="962" height="682" alt="image" src="https://github.com/user-attachments/assets/683b4e35-0c34-4bc6-ba79-59cecd9315ba" />


![image](https://github.com/user-attachments/assets/84c50fdf-d0ef-4cd7-b394-252a556c74b7)

![image](https://github.com/user-attachments/assets/e78d53b5-b9d0-4aa1-a9e8-b9638bf01a98)

![image](https://github.com/user-attachments/assets/ee2e876f-1b0b-462e-a3f6-6a5513f04173)

# NOTE
Enable copy-paste and move functions in VM
Install this one
```
dnf install tar bzip2 kernel-devel-$(uname -r) kernel-headers perl gcc make elfutils-libelf-devel
```
For ubuntu 
```
sudo apt install build-essential dkms linux-headers-$(uname -r) -y
```
Add a guest addition CD, go to the VM and select `Devices' and add Guest Addition CD
![image](https://github.com/user-attachments/assets/5cd59d0d-95cc-48dc-a3d0-e00fee8de160)

GO to CD and open in the terminal and run the following command
```
sudo ./autorun.sh
```
![image](https://github.com/user-attachments/assets/2d5cdbd1-7fc7-432f-8c0c-9e70155bdf99)
If you got the error as follows, then run maunaaly
![image](https://github.com/user-attachments/assets/0c1d67f5-735e-49f4-8cbd-ac8fc72ba946)
Change to the root user and run the following commands
```
su
cd /run/media/<User>/VB*
./VBoxLinuxAdditions.run
```
Finally, the report machine.

## Install openssh-server. Install it on both VMs as defined above and start communication
to check the IP address
```
ifconfig
```

# Passwordless Communication 

