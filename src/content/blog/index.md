---
title: "First things you need to do after installing Ubuntu Server on Raspberry Pi"
description: "Hit the ground running."
date: "2024-10-22"
---


The first thing we want to do after installing with each Ubuntu Server is to check for available updates and install them as soon as possible.
The updates often include security patches which are very important for the security of the new system.


## Check Ubuntu Server Version

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

## Update Ubuntu Server
In order to start updating a Ubuntu (or Debian) system is to update the `Package Repository Index`.