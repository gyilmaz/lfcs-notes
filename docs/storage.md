# Useful Command

## Device

* `lsblk`
* `fdisk` : `n` (new), `d` (delete)
* `cfdisk`
* `/etc/fstab` : auto mount
* `mkfs.xfs -L <label>` : xfs with label
* `mkfs.ex4 -N <inodes>` : ex4 with inodes
* `mount <partition> <target>` : mount (can use options with `-o`)
* `umount <target>` : un-mount
* `xfs_admin -L <label> <partition>` : change partition label
* `xfs_quota -x -c 'limit bsoft=100m bhard=500m <username>' <partition>` : `-x` (expert mode), `-c` (command)

## Swap

* `mkswap <partition>` : make partition as a swap
* `swapon --show` : show all swap
* `swapon <swap>` : activate swap
* `swapoff <swap>` : de-activate swap

## LVM

### Physical

* `pvcreate <... devices>` : make all as physical volumes
* `pvs` : Physical Volume Sizes
* `pvremove <device>` : remove device from pyhsical volumes
* `vgcreate <group name> <physical ...>` : create Volume Groups
* `vgextend <group name> <physical>` : extend VG add new Physical
* `vgreduce <group name> <physical>` : reduce VG, remove physical
* `vgs` : show VGs sizes

### Logical

* `lvcreate --size <logical size> --name <logic name> <VG name>` : create Logical
* `lvresize --size <new size> <VG>/<logical name>` : resize Logical
* `lvremove <VG>/<logical name>` : remove Logical

### Encrypt

* `cryptsetup open --type plain <disk> <mapped device name>` : open encrypted device (plain)
* `cryptsetup close <mapped name>` : close encrypted device
* `cryptsetup luksFormat <device>` : Encrypt device

## ACL

* `setfacl --modify user:<username>:<acl> <filename>` : setup/modify acl to user
* `setfacl --remove user:<username> <filename>` : remove ACL to user
* `setfacl --modify group:<groupname>:<acl> <filename>` : modify acl to group
* `setfacl --recursive --modify user:<username>:<acl> <dirname>` : setup acl to directory and all files/subdirectories on it

## Additional

* `chattr -i <filename>` : remove immutable file flag
* `/etc/exports` : NFS
* `/etc/auto.master` : Config file auto mount, format : `<source> <dest>`
* `autofs` : `/etc/auto.shares`, format: `<network name> -fstype:<fstype> <addr>:<dir>`
* `nfs-utils`
* `findmnt <dir>` : mount options

## Raid

* Type
  * level 1 - mirrored array
* `cat /proc/mdstat`
* `mdadm` : Raid with md driver
* `mdadm --create <target> --level=<level> --raid-devices=<n> <list devices ...>` : create `level` raid
* `mdadm --manage <existing> --add <new device>` : add device to existing raid
