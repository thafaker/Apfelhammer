Hello T2/Linux 25.04 - I switched back to 12.24

**Man**, I am a little bit frustrated right now. Everytime a new release of 
[T2/Linux](https://apfelhammer.de/release-t2-linux-254-it-only-does-everything.html)
is going online, I am really happy to try it out on my *Powermac G5*. I download
it and <code>dd</code> it to a USB Stick ([here](https://apfelhammer.de/how-to-boot-powermac-from-usb.html) 
I explain how to boot a PPC Mac from USB) and than boot the Powermac via OpenFirmware
from that USB Stick and everything works like charme. Like I exspect it.

The Install Process is straight forward and easy, thanks to *STONE*, the Installer
of T2. But with Version 25.04 there is a problem, the FANs turn to MAX rotation like
there is a kernel module not loaded or something like that and you think the G5 
will soon fly away. The next thing: X seems to be broken, I can't <code>startx</code> 
anymore. 

In **24.12** these things were okay, X works and even 3D-Acceleration works 
so I could use it in a quite usual way. But now - *all of this is gone*. 
Everytime I try, there is another problem. Something other broken. 
And I am not smart enough to fix it. I do not understand enough and there is
not enough documentation to get this done. Sure, René is a One-Man-Show with his
T2 Linux Project and he is fixing a lot of older drivers and software packages
and he earns nothing and I say thank you man. Great Job. But even in his 
documentation, I am unable to find the right solution e.g. to crosscompile not the 
whole target, just a package and all of it's depencies.

I never got *Palemoon* or *ArcticFox* compiled or crosscompiled, because there
are errors I canot solve. I installed **T2/ARM64** on my *Mac Mini M4* because this
small machine is really powerful so it is a great crosscompoling solution for
the me at home for my PPC64 Powermac. 
But it starts while compiling gcc. I am unable to compile GCC. And 
without GCC there is no way to compile anything further.

---

### How to crosscompile T2 Linux for PPC64

Maybe someone can eplain the best way to crosscompile from ARM64 to
PPC64 is, with two T2 Installs so it is nearly identical. I think it sould be
possible and meant to be that way. It would be great.

![My Powermac G5 with T2 Linux and Cinema HD 23" Display](/images/errors.jpeg)
<small>My Powermac G5 with T2 Linux and Cinema HD 23" Display</small>

And Fienix Linux is [completely broken](https://apfelhammer.de/tag_fienix.html) :-(

Tags: powermacg5, t2linux
