Linux Storage Capacity Expansion

 Project Overview

This project demonstrates Linux storage management using Logical Volume Manager (LVM), filesystem resizing, and backup and recovery techniques.

 Objective

To increase storage capacity on a Linux system while preserving existing user data.

 Technologies Used

* Ubuntu Linux
* Oracle VirtualBox
* Logical Volume Manager (LVM)
* ext4 filesystem
* Linux command-line tools

Concepts Learned

* Disk partitioning using fdisk
* Physical Volumes (PV)
* Volume Groups (VG)
* Logical Volumes (LV)
* Filesystem creation and mounting
* Logical volume expansion
* Filesystem resizing
* Backup and recovery

 Important Commands

1. Inspect Storage

lsblk
sudo pvs
sudo vgs
sudo lvs
df -Th

2. Prepare a Partition for LVM

sudo pvcreate /dev/sdb1

3. Create a Volume Group

sudo vgcreate myvg /dev/sdb1

4. Create a Logical Volume

sudo lvcreate -L 3G -n data_lv myvg

5. Create a Filesystem

sudo mkfs.ext4 /dev/myvg/data_lv

6. Mount the Filesystem

sudo mkdir -p /mnt/lvmdata
sudo mount /dev/myvg/data_lv /mnt/lvmdata

7. Expand Storage and Resize the Filesystem

sudo lvextend -r -L +1G /dev/myvg/data_lv

 Backup and Recovery

The project includes basic file backup, restoration, and verification exercises.

 Safety Notes

* Verify disk names before modifying partitions.
* Never format a volume containing data you want to preserve.
* Back up important files before making storage changes.
* Commands and device names must be adapted to the actual system configuration.

 Project Status

In Progress — documenting and validating the practical implementation.

 Learning Outcomes

* Understanding LVM architecture.
* Expanding storage while preserving existing data.
* Managing Linux filesystems.
* Performing basic backup and recovery.
