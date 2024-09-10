---
title: Replace disk in RAID1 on Debian/Ubuntu
date: 2024-09-11 01:02:00 +/-0700
categories: [Linux, System]
tags: [hardware, mdadm]     # TAG names should always be lowercase
---

So, my 14 years old Hitachi 2Tb HDD finally kicked the bucket.

## Before replacing
First, I made sure I have working backups. `RAID1` is great, but it is **NOT** a backup!

Next is checking that `GRUB` is installed on both disks.   
(All commands here are executed as `root` user).
```sh
dpkg-reconfigure grub-pc
```

## Replace
Remove disk from `/dev/md0`
```sh
sync
mdadm --manage /dev/md0 --fail /dev/sdb1
mdadm --manage /dev/md0 --remove /dev/sdb1
```
Replace the disk and than copy partition table from an existing `sda` to a new one `sdb`.
```sh
sfdisk -d /dev/sda | sfdisk /dev/sdb
```
Add the new disk 
```sh
mdadm --manage /dev/md0 --add /dev/sdb1
```
The rebuilding process will take some time (More than 5 hours in my case=))

## Check
```sh
mdadm -D /dev/md0
```
or
```sh
cat /proc/mdstat
```