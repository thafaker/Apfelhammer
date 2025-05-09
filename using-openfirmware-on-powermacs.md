Using OpenFirmware on Powermacs

There is always the discussion around if the Powermacs are able to boot from USB or 
not and I can say: every Powermac G5 is able to boot from USB Thumbdrive. So it
is quite easy to dd an ISO of Linux or Leopard to an USB-Drive and boot-up the
Powermac G5 with it. But also older Macs. Older Roms. Older Edlers.
<hr>
## Some OpenFirmware Commands

### Accessing Open Firmware

**Method I**: At the chime, hold down the Option key. The Boot Picker comes up. Press Control + Z to switch to Open Firmware.
**Method II**: At the chime, hold down Command + Option + O + F until you've arrived at the Open Firmware prompt.

### Running System Diagnostics

- To reset the system NVRAM, enter reset-nvram
- To reset all changes made to Open Firmware, enter set-defaults
- To reset the machine, enter reset-all
- To display a list of all central device aliases, enter devalias
- To display information for a device, enter dev <device alias> .properties ( i.e. dev /cpus .properties | dev screen .properties | dev /memory .properties etc. )
( Note: The capacity values output by dev /memory .properties are saved in the hexadecimal format and will need to be converted to be understood by most. )
- To display a list of all utilities, enter printenv ( WARNING, DO NOT RUN setenv little-endian? true ! This will brick your machine beyond trivial repair! )
- To check the system hard disk and its partitions without extracting it from the machine, enter target-mode into the prompt. Target Disk Mode comes up. Connect a FireWire cable from the subject machine to another compatible machine. The subject machine's partitions will appear on the other machine, ready for review or remote boot.

### Accessing Open Firmware

**Method I**: At the chime, hold down the Option key. The Boot Picker comes up. Press Control + Z to switch to Open Firmware.
**Method II**: At the chime, hold down Command + Option + O + F until you've arrived at the Open Firmware prompt.

### Running System Diagnostics

- To reset the system NVRAM, enter reset-nvram
- To reset all changes made to Open Firmware, enter set-defaults
- To reset the machine, enter reset-all
- To display a list of all central device aliases, enter devalias
- To display information for a device, enter dev <device alias> .properties ( i.e. dev /cpus .properties | dev screen .properties | dev /memory .properties etc. ) ( Note: The capacity values output by dev /memory .properties are saved in the hexadecimal format and will need to be converted to be understood by most. )
- To display a list of all utilities, enter printenv (WARNING, DO NOT RUN setenv little-endian? true ! This will brick your machine beyond trivial repair! )
- To check the system hard disk and its partitions without extracting it from the machine, enter target-mode into the prompt. Target Disk Mode comes up. Connect a FireWire cable from the subject machine to another compatible machine. The subject machine's partitions will appear on the other machine, ready for review or remote boot.

### Booting an Operating System

- To automatically enter Open Firmware upon boot, enter setenv auto-boot? false (Enter setenv auto-boot? true to revert to default. )
- To set a default boot volume, enter setenv boot-device <volume>:<partition ID>,<path> (i.e. setenv boot-device hd:1,\\:tbxi | setenv boot-device cd:,\\yaboot | setenv boot-device ud:,ofwboot | etc. ) ( If no partition ID is provided, the system will look for the first available OS on the specified volume. If none are found, the system will either revert back to Open Firmware, or display a "do not cross" symbol. )
- To boot between locally installed operating systems, enter multi-boot into the prompt. The Boot Picker comes up.

<small>**Note**: The utility's interface and control methods may vary between versions.</small>

To boot from a USB disk, enter one of the following depending on the targeted OS (OF V. 4.9 / 5.2 Only) -

* Mac OS X: <code>boot ud:,\\:tbxi</code>
* Linux (YABOOT): <code>boot ud:,\\yaboot</code>
* Linux (GRUB): <code>boot ud:,\\grub.img</code>
* OpenBSD: <code>boot ud:,ofwboot</code>

**MERKE**: You need to adjust these settings, because grub and grub2 are different and sometimes
the grub.img is laying somewhere else. On [Adelie Linux PPC64](https://www.adelielinux.org) you can boot from 
USB on a Powermac G5 with the following command <code>boot ud:,\\boot\grubcore.img</code>

- To boot from a USB disk on OF V. 4.8 / 5.1 and lower, replace 'ud:,' with 'usb0/disk@1:'. Increase the digit immediately following 'usb' incrementally until successful. Alternatively, also increase the digit immediately following 'disk@' until successful, depending on the OS chosen.

If you are unable to boot Mac OS X using the provided methods, try replacing ':tbxi' with ':3,\System\Library\CoreServices\BootX'.

Tags: powermacg5, openfirmware, usb
