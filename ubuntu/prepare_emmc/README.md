#Instructions for Installing Ubuntu Filesystem on Minized eMMC 

#The Minized ships with a single FAT32 partition in the eMMC.  In order
#to install the Ubuntu filesystem, we need to format the eMMC into two
#partitions: boot (DOS) and root (EXT4)

# Prepare USB Stick with the following conditions
# 1) USB fully formatted for EXT4.  
# 2) USB files in the following directory structure
#  /
#	 prepare_emmc.sh 
#    --/boot (in tar ball)
#           -- image.ub
#			      -- wpa_supplicant.conf
# 			
#    --/ext4 (in tar ball)
#           -- /lib
#				        -- (ext4 libs)
#			      -- mkfs.ext4
#	   --/rootfs (Download https://rcn-ee.com/rootfs/eewiki/minfs/ubuntu-16.04.3-minimal-armhf-2017-10-10.tar.xz) 
#			      -- armhf-rootfs-ubuntu-xenial.tar (extract from ubuntu-16.04.3-minimal-armhf-2017-10-10.tar.xz)

#Boot Minized with built-in image, mount the usb to /mnt/usb/boot/image and run this script
#  mount /dev/sda1 /mnt/usb
#  /mnt/usb/prepare_emmc.sh