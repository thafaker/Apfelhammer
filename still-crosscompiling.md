Still crosscompiling

I own this late and great *Powermac11,2* **Powermac G5** Dual Core 2,0 GHz and 
I love this machine for being what it is: a great *retrobattle station* 
and also a sexy *workstation*. It is so clean, no cables, 
everything can be accessed easily. 

![Powermac G5 late 2005](/images/late_2005.jpg)

<hr>

Even the PowerPC 970MP [^1] Processors are
known for getting really hot, the machine fans are not loud even under
heavy load while compiling latest e.g. Firefox Version 133 for PPC64. 
And this is the moment were I want to setup something to crosscompile. 
Because I don't want to run the Powermac all day and all night with 78 degree 
Celcius all the time while compiling and I don't want to consump so much 
electrical energy.

![Powermac G5 Front-USB](/images/powermacg_g5_usb_front.jpg)

And here is why I decided this way. An <code>./t2 upgrade</code> command will 
last for complete 7 days and 14 hours. It is a command were I first updated 
the SVN Tree with <code>svn up</code> and than did that upgrade, 
like <code>apt-get dist-upgrade</code>. But in T2/Linux, there are no binary 
packages. Everything is built from scrath like in Gentoo Linux. 
That's good. That's bad. :-)

![Powermac G5 T2/SDE Linux Upgrade Time](/images/worscht.png)

So I setupped my **Mac Mini M4** (Standard) to crosscompile for 
PPC64 - and I tried a lot of different things to get this done. 
But nothing worked from start to the end yet. 

![Powermac G5 Front-USB](/images/cpu.png)

I installed QEMU and installed a PPC64 Distro. There are not a lot of PPC64
capable Linux Distros outside, all the main ones dropped support. But there
is a an inofficial version of DEBIAN for PPC64 [^3] or one from ARCH Linux and
also SUSE. So I decided to install DEBIAN on both my Powermac G5 and in
a QEMU virtualiziation on that M4. But that ran not good, I often got 
hard locked kernel errors so I moved forward and install a UBUNTU for ARM64 
in a Docker Container with only crosstool-ng software to crosscompile from 
there to ppc64. I tried with Firefox. But there are a lot of problems 
regarding the BIG ENDIANess of PPC64, all the other CPUs (Architectures) like 
x86 or ARM are using *Littel Endian*. But that also does'nt work and I 
decided to install **T2/SDE Linux** from famous Kernel Hacker *Rene Rebe* into 
qemu and later into a Parallels Installation as both PPC64 and then ARM64.

![T2/SDE is crosscompiling](/images/crosscompiling.png)

PPC64 in QEMU is the same as in real hardware and no crosscompiling is needed, 
which is easier to maintain, slower but fewer problems while compiling, but it 
is really slow (even when you not emulate a PPC 970 Processor from 2004 but a 
Power9 from 2015) and also there were that HARD LOCKED KERNEL Errors, but 
arm64 crosscompiling is to complex to get it work properly. Not to talk about 
the try to install crosstool-ng (wich I had success with) with HomeBrew in 
macOS directly, but had the problem of the endianesses again :( So nothing of 
that worked and I tried to install another ARM64 version of T2/Linux in 
**VirtualBox**. This because in VirtualBox there are no restrictions if you 
use a free plan version like me with Parallels, regarding the numbers of cpus 
or the amount of ram (only 4 Processors, only 8 GB of Ram).

But... also here I have problems and I am not smart enough to figure out how
to crosscompile from the Start to the End in a way with T2/SDE that my Packages are working on the 
Powermac G5. I want to compile complex things like GNome or Firefox or a whole updated PPC64 Distro-ISO File. 
I compiled a whole Desktop / X.Org / PPC64 G5 optimizied World but in the End
I am unable to compile sysfsutils (actually) and the process breaks, 
I always get the folling error:

<code>
bash-5.2# ./t2 build-target --cfg system

Removing old error logs ...
Removing var/adm/logs/2-sysfsutils.err ...

15:22:34 Building 2-filesystem/sysfsutils (2.1.0) ~9s
  Building in src.sysfsutils.system.241215.152233.11505, with 8 threads
  Writing output to $root/var/adm/logs/2-sysfsutils.out
  Corrected ./ltmain.sh
! checking whether build environment is sane... yes
! checking for gawk... gawk
! checking whether make sets $(MAKE)... yes
! checking for powerpc64-t2-linux-gnu-strip... powerpc64-t2-linux-gnu-strip
! checking build system type... Invalid configuration `aarch64-nocross-linux ..
! configure: error: /bin/sh ./config.sub aarch64-nocross-linux-gnu failed
! Due to previous errors, no 2-sysfsutils.log file!
! (Try enabling xtrace in the config to track an error inside the build syst ..
  +00:00:03 Aborted building filesystem/sysfsutils
  Unmounting loop mounts ...
</code>

It remains exciting.

Tags: vintage computing, powermacg5, crosscompiling

### Ressources

* [^1]: This is Footnote Number One.
* [^2]: T2/Linux is especially for cross compiling.
* [^3]: Download: [debian](https://cdimage.debian.org/cdimage/ports/current/)
