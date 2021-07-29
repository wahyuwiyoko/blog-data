---
title: "Fix PHP Upload File Not Work in Linux"
summary: Fix move_uploaded_file() PHP function not work in Linux.
date: 2021-07-05T19:38:47+08:00
draft: false
---

## Intro

`move_uploaded_file()` PHP function may not work in Linux because temporary files not move it in to directory.
This happens because we not give permission to local directory (ex: LAMP directory is in `/var/www/html`).

## Solutions

We have to give `www-data` permission to user and group on `/var/www` with this command below.

```shell
sudo chown -R www-data:www-data /var/wwww
```

And then, give permission to read & write with this command below.

```shell
sudo chmod -R 777 /var/wwww
```