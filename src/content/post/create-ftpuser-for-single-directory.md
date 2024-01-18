---
title: "Create FTP User for single directory in linux"
description: "To create an FTP server on CentOS and set up a user with access to only one directory, you can use vsftpd (Very Secure FTP Daemon). Here's a step-by-step guide:"
publishDate: "18 Jan 2024"
tags: ["FTP", "Linux"]
draft: false
---

To create an FTP server on CentOS and set up a user with access to only one directory, you can use vsftpd (Very Secure FTP Daemon). Here's a step-by-step guide:

## Step 1: Install vsftpd

bashCopy code

```
sudo yum install vsftpd
```

## Step 2: Configure vsftpd

Edit the vsftpd configuration file:

bashCopy code

```
sudo nano /etc/vsftpd/vsftpd.conf
```

Make sure the following lines are set or added in the configuration file:

iniCopy code

```
anonymous_enable=NO
local_enable=YES
write_enable=YES
chroot_local_user=YES
allow_writeable_chroot=YES
```

Save and close the file.

## Step 3: Create an FTP User

Create a system user for FTP:

bashCopy code

```
sudo useradd -m ftpuser
sudo passwd ftpuser
```

## Step 4: Create a Directory for FTP Access

Create a directory that will be accessible by the FTP user:

bashCopy code

```
sudo mkdir /home/ftpuser/ftp
sudo chown ftpuser:ftpuser /home/ftpuser/ftp
```

## Step 5: Update SELinux Settings (if enabled)

If SELinux is enabled, you need to update the context of the FTP directory:

bashCopy code

```
sudo semanage fcontext -a -t public_content_t "/home/ftpuser/ftp(/.*)?"
sudo restorecon -Rv /home/ftpuser/ftp
```

## Step 6: Restart vsftpd Service

bashCopy code

```
sudo systemctl restart vsftpd
```

## Step 7: Test FTP Access

You can now use an FTP client to connect to your CentOS server using the FTP user credentials. The user will be restricted to the `/home/ftpuser/ftp` directory.

Make sure to replace "your_centos_ip" with your server's IP address.
