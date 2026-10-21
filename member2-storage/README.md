Member 2 – Storage & Backup Administrator

 Project

Linux Storage Capacity Expansion

 Objective

To expand Linux storage capacity using Logical Volume Manager (LVM), resize filesystems, and perform backup and recovery while preserving existing user data.

 Responsibilities

* Disk and partition management using fdisk
* Physical Volume (PV) creation and management
* Volume Group (VG) creation and management
* Logical Volume (LV) creation and management
* Filesystem creation and mounting
* Storage capacity expansion
* Filesystem resizing
* Backup and recovery
* Data integrity verification

 Technologies Used

* Ubuntu Linux
* Oracle VirtualBox
* Logical Volume Manager (LVM)
* ext4 filesystem
* Bash and Linux command-line utilities

 Implementation Workflow

1. Identified available disks and partitions using lsblk.
2. Created a partition on the practice disk using fdisk.
3. Initialized the partition as an LVM Physical Volume.
4. Created a Volume Group to pool storage capacity.
5. Created a Logical Volume from the Volume Group.
6. Created an ext4 filesystem and mounted it.
7. Expanded the Logical Volume using lvextend.
8. Resized the filesystem to use the additional capacity.
9. Backed up a test file and practised restoring it.
10. Verified filesystem capacity and checked that existing data remained accessible.

Important Commands

Inspect storage

lsblk
sudo pvs
sudo vgs
sudo lvs
df -Th

Expand storage and resize the filesystem

sudo lvextend -r -L +1G /dev/myvg/data_lv

Verify data

cat /mnt/lvmdata/test.txt

Backup and recovery

mkdir -p ~/backups
sudo cp /mnt/lvmdata/test.txt ~/backups/test.txt
cat ~/backups/test.txt

 Data Safety

* Verified disk names before modifying storage.
* Avoided formatting filesystems containing data that needed to be preserved.
* Practised backup and recovery.
* Checked that existing test data remained accessible after expansion.

 Evidence

Screenshots of actual command outputs and practical results will be stored in the screenshots/ directory.

 Learning Outcomes

* Understood the relationship between PVs, VGs, and LVs.
* Practised Linux partition and filesystem management.
* Learned to expand logical volumes and resize filesystems.
* Practised backup, recovery, and data verification.

Status

Completed — Member 2 practical tasks.

This section documents my individual contribution to the Linux Storage Capacity Expansion project.
