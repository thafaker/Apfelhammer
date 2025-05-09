Backslash, German iMac Keyboard and OpenFirmware

I had problems typing the backslash "\" and bar "|" on my iMac
keyboard when in the OpenFirmware user interface.

[![iMac G3](/images/imac_g3_ppc.jpg)](/images/imac_g3_ppc.jpg)
<small>A picture of my iMac G3 while in Open Firmware</small>

<hr>

The "\" key on US iMac keyboards seems to produce keycode 57 (in X11).
There is no key on the German keyboard that produces keycode 57.
There is one with keycode 58, the "#" key.

The keycodes in OpenFirmware are different.  They are 50 for the US
"\" key and 51 for the German "#" key.  (all numbers in decimal).

Now, the OpenFirmware keymaps seem to contain the proper values for
code 50, but this doesn't help.  We want number 51 to produce "\" and
"|".  But keycode 51 is mapped to space (0x20), both shifted and
unshifted.

Add the following to your boot script to fix this:

    dev /packages/usb-hid-class
    5c key-map-lc 32 + c!
    7c key-map-uc 32 + c!
    device-end

You can then use the "#" key to produce "\" (unshifted) and "|"
(shifted).

In case you don't know how to edit your boot script:

    - boot into OpenFirmware
    - execute "nvedit"
    - type in the above line, ending each with RET.
      You will only see one line at any one time, but you can
      move around with the cursor keys.
    - end the editing session with control-C.
    - execute "nvstore"
    - execute "setenv use-nvramrc? true"
    - reboot into OpenFirmware to test

This way I was able to boot Adelie Linux off of the USB Stick I created for that case.

### Ressources
* [How To Boot Mac from USB](https://apfelhammer.de/how-to-boot-powermac-from-usb.html)
* [OpenFirmware Commands](https://mac-classic.com/articles/open-firmware-basics/)
* [How To Boot PPC Powermacs from USB](https://www.macintoshrepository.org/articles/115-how-to-boot-ppc-powermacs-g3-g4-g5-from-a-usb-stick-or-drive-)

([via](https://lists.debian.org/debian-powerpc/1999/06/msg00017.html))

Tags: imacg3, linux, openfirmware
