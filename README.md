# Extend-root-partition-using-unallocated-space

#GParted - Create a PV on top of that partition (/dev/sda1) with ext4 format for example.

#vgdisplay to see the name of your volume group, in this case is "fedora"

#vgextend fedora /dev/sda1

#Then list lvdisplay to see all the logical volumes, then select the lv that you want to increase the size, in this case we want to add more space to home directory (/dev/fedora/home)

#lvextend -l+100%FREE /dev/fedora/home or in case you want a fixed size use -L option

#lvextend -L 10G /dev/fedora/home and the name of your logical volume.

#e2fsck -f /dev/fedora/home
#resize2fs /dev/fedora/home
#e2fsck -f /dev/fedora/home
