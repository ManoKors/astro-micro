---
title: "First things you need to do after installing Ubuntu Server on Raspberry Pi"
description: "Hit the ground running."
date: "2024-10-22"
---


The first thing we want to do after installing with each Ubuntu Server is to check for available updates and install them as soon as possible.
The updates often include security patches which are very important for the security of the new system.


## 1. Check Ubuntu Server Version

To check your Version of Ubuntu Server type

```sh
cat /etc/os-release
```
This command returns on my machine

```sh
PRETTY_NAME="Ubuntu 24.04 LTS"
NAME="Ubuntu"
VERSION_ID="24.04"
VERSION="24.04 LTS (Noble Numbat)"
VERSION_CODENAME=noble
ID=ubuntu
ID_LIKE=debian
HOME_URL="https://www.ubuntu.com/"
SUPPORT_URL="https://help.ubuntu.com/"
BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
UBUNTU_CODENAME=noble
LOGO=ubuntu-logo
```

## 2. Check for Updated
In order to start updating a Ubuntu (or Debian) system is to update the `Package Repository Index`. The command to update is 

```sh
sudo apt update
```
`sudo` is necessary if you are not logged in as root. The terminal asks for your password and gives you a list like this:

```sh
Hit:1 http://ports.ubuntu.com/ubuntu-ports noble InRelease
Get:2 http://ports.ubuntu.com/ubuntu-ports noble-updates InRelease [126 kB]
Hit:3 http://ports.ubuntu.com/ubuntu-ports noble-backports InRelease
Hit:4 http://ports.ubuntu.com/ubuntu-ports noble-security InRelease
Get:5 http://ports.ubuntu.com/ubuntu-ports noble-updates/main arm64 Packages [339 kB]
Get:6 http://ports.ubuntu.com/ubuntu-ports noble-updates/main Translation-en [86.9 kB]
Get:7 http://ports.ubuntu.com/ubuntu-ports noble-updates/restricted arm64 Packages [246 kB]
Get:8 http://ports.ubuntu.com/ubuntu-ports noble-updates/restricted Translation-en [47.8 kB]
Fetched 846 kB in 1s (838 kB/s)
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
46 packages can be upgraded. Run 'apt list --upgradable' to see them.
```

This synchronized with the server to see which update packages are available for installation. At the bottom it tells me that `46 packages can be upgraded`. 

## 3. Install the updates

```sh
sudo apt dist-upgrade
```
This returns:

```sh
mano@pi:~$  sudo apt dist-upgrade
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Calculating upgrade... Done
The following packages will be upgraded:
  apparmor apport apport-core-dump-handler cloud-init dhcpcd-base
  dracut-install flash-kernel initramfs-tools initramfs-tools-bin
  initramfs-tools-core landscape-common libapparmor1 libnss-systemd
  libopeniscsiusr libpam-modules libpam-modules-bin libpam-runtime
  libpam-systemd libpam0g libsystemd-shared libsystemd0 libudev1
  linux-firmware lxd-installer needrestart open-iscsi python3-apport
  python3-distupgrade python3-problem-report systemd systemd-dev
  systemd-resolved systemd-sysv systemd-timesyncd thin-provisioning-tools
  tzdata ubuntu-pro-client ubuntu-pro-client-l10n ubuntu-release-upgrader-core
  udev vim vim-common vim-runtime vim-tiny xkb-data xxd
46 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
Need to get 500 MB of archives.
After this operation, 1142 kB of additional disk space will be used.
Do you want to continue? [Y/n]
```

Ubuntu is offering me now to upgrade 46 packages. I enter `Y` to continue.


after this you should reboot

```sh
sudo reboot
```

```sh
hostname -I
```


ssh-copy-id -i ~/.ssh/id_rsa.pub mano@192.168.178.104


ssh 'mano@192.168.178.104'