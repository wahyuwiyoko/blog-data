---
title: "Fix Black Screen Lock in Debian"
summary: In this post, I will tell you how to fix a black lock screen in Debian.
date: 2021-03-17T11:21:00+08:00
draft: false
---

## Intro

This issue may occur on computer that use Intel graphics.
This happens when I try to turn on the computer when it's locked, and the screen suddenly goes black.

## Solutions

Open the terminal and enter this command below.

```shell
sudo mkdir /etc/X11/xorg.conf.d
```

This command will create a new directory in `/etc/X11/`.

And then, enter this command below to create a new file: `20-intel.conf`

```shell
sudo nano /etc/X11/xorg.conf.d/20-intel.conf
```

Enter this code below.

```shell
Section "Device"
Identifier "Intel Graphics"
Driver "intel"
EndSection
```

And save it. To save it, press <kbd><kbd>CTRL</kbd>+<kbd>X</kbd></kbd>. And then press <kbd><kbd>Y</kbd></kbd> and press <kbd><kbd>Enter</kbd></kbd>.

After all of that, restart the computer.

---

## References

-   https://medium.com/the-blog-of-ehsan-nazim/debian-10-buster-xfce-black-screen-after-locking-screen-a2266e91791c
-   https://wiki.archlinux.org/index.php/Intel_graphics#Xorg_configuration