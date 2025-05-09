Hello Chimera Linux for PPC64

**Q66**, one of the maintainer of *VOID Linux* Project left the project and created a new
Linux Distribution named **Chimera Linux**. The good thing is, there are PowerPC
and PPC64, LE, EL Kernel and software packages available. So I will give this
distro a try on my Powermac G5. It uses musl as its libc implementation, userland tools from FreeBSD, and dinit as its init system.

For package management it uses apk-tools from Alpine Linux, but Chimera does 
not re-use Alpine packages, but instead uses its own novel package build system.

### Other features
* LLVM as the toolchain of choice (instead of the GCC toolchain)
* musl with mimalloc as the system C library (instead of glibc)
* dinit as the init system (instead of systemd)
* FreeBSD userland (instead of GNU coreutils)
* GNOME desktop environment using Wayland for display and PipeWire for the audio stack

First of all, I download an ISO and dd it to my usb thumb drive. This is the 
beginning of every linux installation I do on my ppc mac. :-)

Tags: powermacg5, linux, chimera
