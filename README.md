Linux Storage Capacity Expansion

 Role: Storage & Backup Administrator

 Project Overview

This project focuses on expanding Linux storage capacity using Logical Volume Manager (LVM), resizing filesystems, and practising backup and recovery while protecting existing data.

 Objectives

* Practise Linux disk partitioning.
* Understand and configure LVM.
* Create and manage logical volumes.
* Expand storage capacity.
* Resize filesystems.
* Perform backup and recovery.
* Verify data integrity after storage operations.

 Technologies Used

* Operating System: Ubuntu Linux
* Virtualization: Oracle VirtualBox
* Storage Management: LVM
* Filesystem: ext4
* Commands: Bash and Linux command-line utilities

 Implementation Steps

1. Disk Identification

lsblk

Identify the separate practice disk before making changes.

2. Partitioning

sudo fdisk /dev/sdb

Create a partition on the verified practice disk.

3. Create Physical Volume

sudo pvcreate /dev/sdb1
sudo pvs

Initialize and verify the partition for LVM.

4. Create Volume Group

sudo vgcreate myvg /dev/sdb1
sudo vgs

Create a storage pool named myvg.

5. Create Logical Volume

sudo lvcreate -L 3G -n data_lv myvg
sudo lvs

Allocate a 3 GB logical volume.

6. Create and Mount Filesystem

sudo mkfs.ext4 /dev/myvg/data_lv
sudo mkdir -p /mnt/lvmdata
sudo mount /dev/myvg/data_lv /mnt/lvmdata
df -Th /mnt/lvmdata

Create an ext4 filesystem and mount it for use.

7. Expand Storage

sudo vgs
sudo lvextend -r -L +1G /dev/myvg/data_lv
df -Th /mnt/lvmdata

Extend the logical volume by 1 GB and resize its filesystem, provided sufficient free space is available.

8. Backup and Recovery

mkdir -p ~/backups
sudo cp /mnt/lvmdata/test.txt ~/backups/test.txt
cat ~/backups/test.txt

Create a backup copy and verify its contents before attempting a recovery exercise.

Verification

lsblk
sudo pvs
sudo vgs
sudo lvs
df -Th /mnt/lvmdata
cat /mnt/lvmdata/test.txt

 Safety Considerations

* Verify the correct disk with lsblk before partitioning.
* Never format a filesystem containing data you need to preserve.
* Check available volume-group space before extending a logical volume.
* Verify backup files before deleting originals.
* Keep important backups on a separate disk or remote storage.

 Learning Outcomes

* Understanding the PV → VG → LV storage architecture.
* Practising Linux storage administration.
* Expanding logical volumes and filesystems.
* Performing basic backup and recovery.
* Verifying storage capacity and data integrity.

 Project Status

In Progress — practical implementation, verification, and documentation.

 Contribution

Responsible for the storage management and backup/recovery component of the team project.
