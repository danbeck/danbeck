---
layout: post
title:  Installing click packages from the command line
date:   2015-06-12 22:24:00
categories: ubuntu
---

## Installing a click package

Click packages are the new packaging format used in Ubuntu Touch. We show how to install such 
a click package on your (USB-connected) device with the command line.  

First, make sure that the developer mode is enabled: Settings > About Phone > Developer Mode.

To install a click package from the command line on your Ubuntu touch device, the file
must first be pushed to the device:

```bash
daniel@laptop:~$ adb push org.ubuntu.myapp_0.1.0_armhf.click /home/phablet/Downloads/
```


Then, login on the device and install the package: 

```bash
daniel@laptop:~$ adb shell
phablet@ubuntu-phablet:~# pkcon install-local --allow-untrusted \
Downloads/org.ubuntu.myapp_0.1.0_armhf.click 
```



## Using _phablet-shell_ instead of _adb shell_

The adb shell doesn't work correctly if the terminal size is less than 80x24. So let's use the 
_phablet-shell_ instead of the _adb shell_.
 
If you haven't already done it, also install phablet command line tools:

```bash
sudo apt-get install phablet-tools 
```

Because phablet-shell is based on ssh, we need to create a ssh public key:

```bash
ssh-keygen 
```

Finally, start the phablet-shell. Then, we can install the click package from the command line and enjoy
the usual terminal line wrapping experience:

```bash
phablet-shell
phablet@ubuntu-phablet:~# pkcon install-local --allow-untrusted \
Downloads/org.ubuntu.myapp_0.1.0_armhf.click
```
