How To Boot Powermac from USB

There are many different mentions in the web. Some say it is impossible to boot
Powermacs from USB, others says: only PowermacG5 from 7,3 Revision are able to
boot from USB and the third party says: every Powermac is bootable.

And because I own this late and great Powermac G5 11,2 and I don't want to 
always burn a CD/DVD everytime I try a new Linux or something else out, I 
invesitagted a little bit further: the third statement is correct: *every Powermac
can boot from USB.*

**But** it is not so easy like we knew it from Intel/x86 Machines. Press a button
and it boots. Because this is
a Powermac with a *PowerPC CPU* and therefore it uses Open Firmware as an BIOS
alternative. Open Firmware was far ahead of it's time with great features, but
it is a cryptical terminal. :-) So far - so good.

<hr>

### Boot PowermacG5 from USB

Because I own this Powermac G5 I will test and write for it. First of all, we 
need to create the USB Stick. 

* Download the ISO of the Distribution of your choice. [T2/SDE](https://t2sde.org/download/continue.html), [Adelie-Linux](https://www.adelielinux.org/download/),
[Debian](https://cdimage.debian.org/cdimage/ports/12.0/ppc64/debian-12.0.0-ppc64-NETINST-1.iso?ref=apfelhammer.de) [FIENIX Linux](https://fienixppc.blogspot.com/p/download.html) or something completely different. Please tell me in comments about it.
* Hand out an USB Stick who is big enough to hold the ISO. I have an old USB 2.0
16 GB Stick, it is perfect. Use dd to copy the iso to the stick. On MacOS, I first
look with the command: <code>diskutil list</code> for the USB Stick. 

In my case, it is Disk14.

	/dev/disk14 (external, physical):
	#:TYPE	NAME	SIZE	IDENTIFIER
	0:APFS		*16GB	disk14

So this is my 16 GB Stick. It is important not to shred my root Partition or
something like that. :-) The command to write the Linux ISO to that dsisk14 USB
Stick as follows:

	sudo dd if=/Downloads/linux.iso of=/dev/disk14 bs=1m status=progress

This will write the file adelie-live… located in my Downloads Folder to disk14. 
Please adapt the command for your needs. if= ISO FILE and of=/dev/YOUR USB STICK.
This command does function similar on linux, but there is no diskutil tool so
you can use everything else what shows you the plugged usb devices.

The process doesn't last long because it is only 1,4 GB or sometimes a CD, 700 MB.
After that, you can plug out the stick and plug it in your Powermac G5, power up the System.
We need to boot into Open Firmware. You can press and hold the Buttons Command+Option+O+F 
or you can simply hold the button OPTION to start the boot menue. There you can
press CTRL+Y and also go to Open Firmware. Once you are there, boot the USB-Stick.

I started Debian, Adelie Linux and T2/SDE from USB:

	# to boot T2 SDE Linux from USB Stick on Powermac G5
	boot ud:,\boot\bootppc.elf

	# to boot Adelie Linux from usb on powermac g5
	boot ud:,\boot\grubcore.img

	# to boot FIENIX Linux from USB on Powermac G5
	boot ud:,\install\yaboot

	# to boot Mac OS X from usb on powermac g5
	boot ud:,\:tbxi

As you can see in the fourth line, it is also possible to boot Mac OS X Installer
from USB Stick. So if you copy your 10.5 ISO to a USB Stick with dd command above,
you are able to boot from the stick with <code>boot ud:,\:tbxi</code>.

**Hope that helps**.

*Bye, Jan*

Tags: powermacg5, linux, usb, howto
