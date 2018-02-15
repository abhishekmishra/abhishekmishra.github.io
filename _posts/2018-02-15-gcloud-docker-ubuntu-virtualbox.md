---
layout: post
title:  "Install gcloud-sdk and Docker on Ubuntu 16.04 on VirtualBox"
date:   2018-01-31 09:15:00 +0530
categories: gcloud-sdk docker ubuntu virtualbox
---

## Installing gcloud-sdk and Docker on Ubuntu 16.04 on VirtualBox

## VirtualBox Guest Config

Config suggested for guest:
1. Min Disk: 30GB
2. RAM: 2GB
3. LVM Partitioning
4. Xubuntu desktop installer

## Install Ubuntu on Virtualbox

## Post-install

### Enable shared clipboard Host-Guest and Reboot

Devices->Shared Clipboard->Host to Guest

### Install VirtualBox Guest Tools
1. Insert Guest Additions ISO
2. Run /media/am/VBox_.../autorun.sh

```
cd /media/am/VBox_.../
sudo ./autorun.sh
```

### Update and Upgrade
```
sudo apt-get update -y
sudo apt-get upgrade -y
```

## Install aptitude, vim, emacs etc.
```
sudo apt-get install aptitude vim emacs -y
```

## Install Docker
Install instructions are here https://docs.docker.com/install/linux/docker-ce/ubuntu/

## Install gcloud-sdk
Install instructions are here https://cloud.google.com/sdk/docs/quickstart-debian-ubuntu
