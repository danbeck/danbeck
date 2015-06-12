---
layout: post
title:  Installing click packages from the command line
date:   2015-06-12 22:24:00
categories: ubuntu
---

Click packages are the new packaging format used in Ubuntu Touch.

First, make sure that the developer mode is enables: Settings > About Phone > Developer Mode.

To install a click package from the command line on your Ubuntu touch device, the file
must first be pushed to the device:

```bash
daniel@laptop:~$ adb push org.ubuntu.myapp_0.1.0_armhf.click /home/phablet/Downloads/
```


Then, login to the device and install it: 

```bash
daniel@laptop:~$ adb shell
phablet@ubuntu-phablet:~# sudo -iu phablet
phablet@ubuntu-phablet:~# pkcon install-local --allow-untrusted Downloads/org.ubuntu.myapp_0.1.0_armhf.click 
```
