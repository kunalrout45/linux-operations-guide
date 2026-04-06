# Linux Filesystem Guide

## 📌 What is a Filesystem?
A filesystem is how data is stored and organized on disk. It controls:
- How files are named
- How data is stored
- How access is managed

---

## 📂 Linux Directory Structure

Linux follows a hierarchical structure starting from `/` (root).

### Important Directories

| Directory | Purpose |
|----------|--------|
| /        | Root directory |
| /home    | User home directories |
| /root    | Root user home |
| /etc     | Configuration files |
| /var     | Logs and variable data |
| /tmp     | Temporary files |
| /bin     | Essential binaries |
| /sbin    | System binaries |
| /usr     | User programs |
| /opt     | Optional software |
| /mnt     | Temporary mounts |
| /media   | External devices |

---
## detailed image : https://i.redd.it/j2k4k1j6f1x71.jpg
## youtube video reference : https://www.youtube.com/watch?v=HbgzrKJvDRw
## filesystem navigation : https://www.youtube.com/watch?v=Aqx97d4NSbg&list=PLd3UqWTnYXOloH0vWBs4BtSbP84WcC2NY&index=4 
## types of files in linux : https://www.youtube.com/watch?v=-Y4bjL-fBMY&list=PLd3UqWTnYXOloH0vWBs4BtSbP84WcC2NY&index=3

## 🔍 Check Filesystem Information

```bash
df -h        # Disk usage (human readable)
lsblk        # List block devices
blkid        # Show filesystem UUID
