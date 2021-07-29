---
title: "Fix Transfer File With USB in Debian"
summary: Fix input/output error when transfer file.
date: 2021-07-29T11:31:45+08:00
draft: false
---

## Intro

This error happens when I run `jmtpfs <directory/>` command in Debian. The directory on the phone doesn't appear and gives an error message saying input/output error.

## Prerequisite

Requires some packages to be installed:

-   gmtp
-   libmtp
-   jmtpfs

And then it need directory to store the phone directory. For example, `MTP` directory.
The directory requires user permission with this command below.

```shell
sudo chown $user:$user <directory/>
```

## Solutions

Open the terminal and enter this command below while the USB cable is connected with the phone and computer.

```shell
jmtpfs <directory/>
```

When this command is running, it will gives an error message saying input/output error. To solve it, enter this command below.

```shell
fusermount -u <directory/>
```

And then, enter this command again.

```shell
jmtpfs <directory/>
```

---

## References

-   https://wiki.debian.org/mtp