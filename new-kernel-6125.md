New Kernel 6.12.5 for my Powermac G5

I plugged in that great **NVMe SSD** into my Powermac G5 because he supports PCI-Express (Version 1.0) and
there is a 4x Speed Port that is unused (the x16 is for the Graphicscard) and now I ran a 1 TB NVMe-SSD
in this Powermac and it is doing great. Because due the lack of drivers, Open Firmware is unable to
boot from thos NVMe-SSDs, he is able to boot from a normal 2,5" SSD on the SATA-Port. So I installed the
/boot/grub parts to that SSD and therefor it loads the Operating System from the NVMe :-) This is
working quite well and I run 

* Debian 12
* T2/SDE Linux
* Adélie Linux

for PowerPC 64 PPC64 plattform. I even write this article on that machine while on Debian 12 doing an
<code>apt update && apt upgrade</code>, running SeaLion Firefox and listening to music. Okay, it is not the 
performance of a late and great 128 Core Threadripper, but it is quite impressive what this machine
from 2005 is able to do in the end of 2024.

<code>powermac:~$ uname -a <br />
Linux powermac 6.12.5-powerpc64 #1 SMP Debian 6.12.5-1 (2024-12-15) ppc64 GNU/Linux</code>

I installed 12 GB-Ram and that NVMe-SSD in the System. It has a 2 GHz PPC970MP Dualcore CPU and
the original Apple 23" Cinema Display. I like that setup, typing is done via the famous Keycron K2
Keyboard.

Actually, I have no glue what can I do to get things crosscompiled. Firefox for PowerPC is broken and
epiphany is running with a white screen, doesnt load on Debian. There is no 
actual browser for PowerPC, what I really dislike. 
I now use SeaLion (Version 33.4) and it is surprisingly good, even github loads and a 
lot of other new websites. It is usable.

Tags: powermacg5, debian, powerpc64, ppc64

### Ressources

* Adelie Linux: [https://www.adelielinux.org/](https://www.adelielinux.org/)
* Fresh Install T2/Linux: [https://t2sde.org/kb/8/?kb/8](https://t2sde.org/kb/8/?kb/8)
* Debian 12 SID: [https://cdimage.debian.org/cdimage/ports/12.0/ppc64/](https://cdimage.debian.org/cdimage/ports/12.0/ppc64/debian-12.0.0-ppc64-NETINST-1.iso?ref=thahipster.de)
* Linux on PowerPC Computers: [https://thahipster.de/linux-auf-dem-powermac-g5/](https://thahipster.de/linux-auf-dem-powermac-g5/)
* SeaLion on Github: [https://github.com/wicknix/SeaLion/releases/tag/33.4.0](https://github.com/wicknix/SeaLion/releases/tag/33.4.0)
