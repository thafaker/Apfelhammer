Hello ArchPOWER Linux for PPC64

In a nice [comment from Matias](https://apfelhammer.de/hello-t2linux-2504---i-switched-back-to-1224.html#isso-20), he told me he is using ArchPOWER Linux, an unofficial
Build of Arch Linux for PowerPC, PPC64, PPC and PPCle for the Power8 Architecture
etc. pp.; If I remember correctly, I stumbled across this Linux Distro while I
researched for the best Linux for my Powermac G5, but maybe because I was at
the beginning of my Linux journey on these machines, I found it to heavy or 
something else told me not to try. I don't know but it is not important anymore,
because I installed ArchPOWER Linux current on my NVMe-SSD in the Powermac, 
multi-booting with T2 Linux, Debian 12 SID, Adelie Linux and Fienix Linux. :-)

![](/images/fastfetch_arch.png)

---

## How to install ArchLinux PowerPC on PowermacG5 (ppc64)

First of all, I am a newbie to ArchLinux and I never sit on one. So I need to
come behind the psychology of this linux, but I think with a good knowledge of
quite ususal linux aspects, it should not be harder than to play with T2 Linux
or something similar.

The ArchPOWER documentation is quite good, there is no need for my tutorial. 
But I have some special things, so I want to write it down for myself. 
First, my setup:

* I have a typically SATA-SSD (128 GB) with <code>grub</code> installed. This is the <code>/boot/grub/</code> partition. Than 
* I have a NVMe-SSD in the PCIe-Slot of the Powermac, there is the SWAP-Drive
and all the Linux-Paritions. Also the /home Partition.

With this setup I do the following:

1. I create a bootable USB Stick via macOS and boot from it. [How to boot from USB?](https://apfelhammer.de/how-to-boot-powermac-from-usb.html)
2. On the powermac, I create a new partition on the nvme drive for the new linux
3. I install everything in that partition, I do not mount /boot from the ssd 
because I don't want to break anything. So the whole new linux goes to the
new partition on that nvme drive.
4. If everything is done, I boot from my initial Debian SID Installation, update
the <code>/etc/grub.d/40_custom</code> file and create a new section with my new linux.
5. I mount the new linux partition and the old ssd-boot partition and copy the
new linux kernel and the new initrd disk image to the boot partition on the sata-ssd
6. <code>update-grubd</code>
7. I now reboot and can select my newly installed Linux in grub from the SSD and 
because the kernel is loading, the rest of the Linux now can be loaded from the
NVMe-SSD and there I am. In one of my Linuxes on tha Powermac G5. 
8. This is the way also installed ArchPOWER Linux on that Powermac.
9. use it :-)

So I booted ArchPOWER off the USB Stick. You are logged in 
as root without password. So I set a password for root 
with <code>passwd</code> because I want to install SSH Server 
to login from my Mac Mini to perform the next steps from there:

	pacman -Sy openssh

Pacman should install openssd, now we start it:

	systemctl start sshd

and we check the IP of our powermac:

	ip addr

Now we can connect to the powermac live system via ssh.
Really good, isn't it?

![](/images/ssh_arch.png)
<small>Terminal connection ssh to my powermac g5.</small>

At this point of the install-process, we can follow the [ArchPOWER Setupguide]() to 
create an apple scheme partition map to install all the things like
grub, the kernel, the base system and than we need to take several tasks
to get network etc. done but then we should boot into our new arch linux
distribution. Great, huh?

![](/images/install_base.png)
<small>pacman is installing the base system to my powermac</small>

Next is the official [Setup Guide from ArchLinux](https://wiki.archlinux.org/title/Installation_guide) itself to get things done.

### a small update

Here you can see my graphical environment on arch linux ppc64 while running 
some tools like glxgears, htop and archticfox for websites.

[![](/images/archlinux_arcticfox.jpg)](/images/archlinux_arcticfox.jpg)
<small>Powermac G5 real running LXQt</small>

### Ressource

* [Installer ISOs: /iso/ (powerpc64le, powerpc64 & powerpc)](https://archlinuxpower.org/iso/)
* [Install PowerPC Powermac Arch POWER](https://github.com/kth5/archpower/wiki/Installation-%7C--NewWorld-PowerMac-with-Grub)
* [enable SSH on Arch LINUX](https://medium.com/@pythonaugust/enable-ssh-on-arch-linux-8f1ede0d9c88)
* [ArchPOWER Wiki](https://github.com/kth5/archpower/wiki)

Tags: powermacg5, linux, archpower, archlinux
