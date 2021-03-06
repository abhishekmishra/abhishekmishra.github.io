---
layout: post
title:  "Install gcloud-sdk and Docker on Ubuntu 16.04 on VirtualBox"
date:   2018-02-15 08:56:00 +0530
categories: gcloud-sdk docker ubuntu virtualbox
---

I use Windows 10 Home on my laptop, so docker integration is a challenge, espescially running all the builds written in shell scripts won't run nicely on Ubuntu on Windows or MSYS2.

So I've had to fallback on installing ubuntu on virtualbox, with docker and gcloud-sdk. I've documented the steps below.

## Get VirtualBox

[Download VirtualBox](https://www.virtualbox.org/wiki/Downloads)

## Install Ubuntu on VirtualBox

Get Xubuntu 16.04 ISO. Xubuntu is lightweight and provides a standard desktop. Ubuntu or other flavours should also work.

[Download Xubuntu LTS](https://xubuntu.org/download#lts)

### VirtualBox Guest Config

Config suggested for guest:
1. Min Disk: 30GB
2. RAM: 2GB
3. LVM Partitioning
4. Xubuntu desktop installer

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
Install instructions are here [Installl Docker CE on Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)

### Run docker as user
Add current user to docker group, and verify that it works

```
sudo usermod -aG docker $USER
```

Reboot ubuntu for changes to take effect.

```
sudo reboot
```

Verify that the changes work

```
docker run hello-world
```

See [Post-install step for linux](https://docs.docker.com/install/linux/linux-postinstall/) for further details.

### (Optional) Install Docker Compose

See instructions at [Install Docker Compose for Linux](https://docs.docker.com/compose/install/#install-compose)

## Install gcloud-sdk
Install instructions are here [Install gcloud-sdk on Ubuntu](https://cloud.google.com/sdk/docs/quickstart-debian-ubuntu)

## SSH/github setup
Use this gist to setup multiple keys if required.
[Github multiple ssh keys](https://gist.github.com/jexchan/2351996)

## (Optional) Install nodejs using package manager

```
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```
For details see instructions at [Install nodejs via package manager](https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions)

## Copy the VM before using it
Take a backup of the VM folder if you have space, so that you don't need to go through these steps again. You can just start from a clean copy where all tools are setup.