---
layout: post
title:  Installing click packages from the command line
date:   2015-06-12 22:24:00
categories: ubuntu
---


Click packages are the new packaging format used in Ubuntu Touch. We show how to install such 
a click package on your (USB-connected) device with the command line. In a second part, we
show how to use the _phablet shell_ instead of the _adb shell_.

## Installing a click package
The developer mode must be enabled for all the following steps: Settings > About Phone > Developer Mode.

Push the click file to your device:

```bash
daniel@laptop:~$ adb push org.ubuntu.myapp_0.1.0_armhf.click /home/phablet/Downloads/
```


Now, we can login on the device and install the package: 

```bash
daniel@laptop:~$ adb shell
phablet@ubuntu-phablet:~# pkcon install-local --allow-untrusted \
Downloads/org.ubuntu.myapp_0.1.0_armhf.click 
```

The _adb shell_ doesn't work correctly if the terminal size is less than 80x24: the line wrapping
bug makes it hard to enter long commands like the ones above. Instead, a better solution is to use
the _phablet shell_.

## Using _phablet-shell_ instead of _adb shell_

We install and configure the _phablet-tools_ as follows:

```bash
sudo apt-get install phablet-tools 
```

Because phablet-shell is based on ssh, we need to create a ssh public key:

```bash
ssh-keygen 
```

We are done! Start the phablet-shel and install the click package like above:

```bash
phablet-shell
phablet@ubuntu-phablet:~# pkcon install-local --allow-untrusted \
Downloads/org.ubuntu.myapp_0.1.0_armhf.click 
```
