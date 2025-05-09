How do I run update-grub from another Partition or a LiveCD?

As you know my Setup, I will shortly explain again. In my Powermac G5 there is 
an SATA-SSD as a replacement for the old spinning Apple HDD. On this SSD I 
installed Mac OX 10.5 and also Debian SID for PPC, to get the Partition-Scheme
and GRUB installed.

I also built in a NVMe-SSD with 1 TB because the Powermac11,2 has PCI-Express
Slots like it is standard nowadays. The OpenFirmware in the Powermac doesn't 
know what an NVMe-SSD is and therefore can't recognize it or boot it. Also 
Mac OS X 10.5 doesn't *see* the device. The technic is too young and there are
no drivers, that is the reason for that.

But lucklily, Linux has the drivers for that. And that's the reason for my Setup.
Boot Grub from SSD because that can the Powermac. Than load the things you need
for NVMe and boot the linux off the NVMe-SSD.

I have 4 Linux on that NVMe-SSD and that works great. But it is a problem to 
update the Grub Bootloader everytime there is a new kernerl or something other
changed. Long story short, here I will tell (me) you, how to update grub via chroot.

---

### Update Grub from other System (or a Live CD)

Once it boots, open a terminal and mount your Debian/Ubuntu/Whatever partition 
on /mnt. I'm assuming the root partition is /dev/sdb3, but you should determine 
this yourself:

	sudo mount /dev/sdb3 /mnt

Then mount a few more directories that are needed:

	sudo mount --bind /dev /mnt/dev
	sudo mount --bind /sys /mnt/sys
	sudo mount --bind /proc /mnt/proc

Also, if you have a separate boot partition (pretty uncommon 
these days, but it may be the case):

	sudo mount /dev/sdbX /mnt/boot

<small>While X stands for your Partition Number</small>

Once these are mounted, do **chroot** to start using the mounted directory 
as the root partition:

	sudo chroot /mnt

You are now in the other partition, as you have bootet from it. You can now do
all the tasks you want and you are affecting the chroot, not your running linux
like the Live-CD or the other partition. For GRUB, it is time to edit the file
40_custom in the grub directory.

	nano /etc/grub.d/40_custom
	
There you do your things and after saving it, you need to run the command:

	sudo update-grub

and the grub-updater script is doing the rest. After that task, you can exit the
chroot environment and reboot.

*Hope that helps*.

Tags: powermacg5, linux, grub
