---
share: true
---
## The Hierarchical Structure of the Linux File System

The Linux file system is organized in a hierarchical tree-like structure, with the root directory (/) at the top. All other directories and files are contained within the root directory, which can be broken down into several subdirectories. Some of the key directories and their purposes include:

![[../assets/img/cf008e1d71b9cecc47bb315a8a80500a_MD5.png|cf008e1d71b9cecc47bb315a8a80500a_MD5]]

File Hierarchy Structure (FHS) in Linux

It follows a standard naming convention for directories and files. Directories are often named after their function or content, while files are named after their purpose. Here are some common directories and their functions:

1. **/bin (Essential User Binaries)**: The /bin directory contains essential system binaries that are required for the basic operation of the system, such as ls, cp, mv, and cat.
2. **/boot (Boot Loader Files)**: The /boot directory contains the files required for the boot loader to load the operating system. These files include the kernel, initial RAM disk, and boot loader configuration files.
3. **/dev (Device Files)**: The /dev directory contains device files that represent hardware devices and drivers. These files can be used to interact with hardware devices directly, such as USB drives, CD-ROMs, and printers.
4. **/etc (Configuration Files)**: The /etc directory contains configuration files for the system and applications installed on the system. These files include network configuration, user accounts, and system-wide configuration settings.
5. **/home (User Home Directories)**: The /home directory contains the home directories for individual users on the system. Each user has a subdirectory in the /home directory that contains their personal files and settings.
6. **/lib (Essential Shared Libraries)**: The /lib directory contains essential shared libraries that are required by system binaries and other applications on the system.
7. **/media (Removable Media)**: The /media directory is used for mounting removable media, such as USB drives, CD-ROMs, and DVDs.
8. **/mnt (Mount Point for File Systems)**: The /mnt directory is used for mounting other file systems, such as network file systems or other hard drives.
9. **/opt (Optional Software)**: The /opt directory is used for optional software installed on the system. This directory can be used for installing software that is not included in the system’s package manager.
10. **/proc (Process Information)**: The /proc directory contains virtual files that provide information about the system and running processes. These files can be used to monitor system performance and diagnose issues.
11. **/root (Home Directory for root User)**: The /root directory is the home directory for the root user, the system administrator. This directory contains the personal files and settings for the root user.
12. **/run (Runtime Data)**: The /run directory contains runtime data for the system and applications, such as system logs, process IDs, and other temporary files.
13. **/sbin (System Binaries)**: The /sbin directory contains system binaries that are required for system administration tasks, such as fdisk and iptables.
14. **/srv (Service Data)**: The /srv directory contains data for services provided by the system, such as websites and FTP servers.
15. **/tmp (Temporary Files)**: The /tmp directory is used for storing temporary files that are created and used by applications.
16. **/usr (User Binaries and Libraries)**: The /usr directory contains user binaries and libraries for the system, such as system administration tools and development libraries.
17. **/var (Variable Data)**: The /var directory contains variable data for the system, such as system logs, mailboxes, and spool files.

## Oh My Zsh

```sh
dnf install zsh

sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"


```

## LUKS
### Setup automatic unlock:
```bash
clevis luks bind -d /dev/mmcblkp3 tpm2 '{"pcr_ids":"1,7","key":"rsa"}'
systemctl enable clevis-luks-askpass.path
dracut --regenerate-all --force
```


### Regenerate
If automatic unlock does not work anymore it needs to be regenerated. First list the used slots:
```sh
clevis luks list -d /dev/nvme0n1p3
```

Then regenerate using slot
```sh
clevis luks regen -d /dev/nvme0n1p3 -s 1
```

### Change PCRs
To change PCRs you first need to delete the key and then re-add using the wanted PCRs.
List the used slots:

```sh
clevis luks list -d /dev/nvme0n1p3
```
Remove the slot:
```sh
clevis luks unbind -d /dev/nvme0n1p3 -s 1 -f
```

Note: `-f` will not ask for confirmation but is needed if there is no other slot set up.

After that re-add the key like above.

## OBS Virtual Cam
Install v4l2loopback
```sh
sudo dnf install https://download1.rpmfusion.org/free/fedora/rpmfusion-free-release-$(rpm -E %fedora).noarch.rpm
sudo dnf install v4l2loopback 
```

```sh
git clone https://github.com/umlaeute/v4l2loopback
```