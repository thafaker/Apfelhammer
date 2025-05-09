Status of Firefox on PPC64 Big Endian

So yesterday was the release ouf **24.12 T2/Linux** and the maintainer, creator
and mastermind behind, René Rebe, were at a lifestream on youtube and twitch.
So I played around with T2 on my Powermac G5 and listened to the stream and 
had a small chat with him. The most important part is an actual browser on 
that machine so I asked for the actual status of firefox.

René replied that the problems with big endian still exist and  occours so there is no
Firefox for Big Endian Machines at the moment. Firefox builts well on all little endian
processors, but not on the big ones. There is no better answer at this time,
but I hope he can do something when he have the time. Because to make that
clear: there is not a big audience who is working on big endian ppc64 processors 
like my 970MP is in the world and I believe he get's not enough feedback and 
attention for his work for the open source community. But this is another part.

Debian also faces the problem of [not building firefox for ppc/64](https://buildd.debian.org/status/package.php?p=firefox&suite=sid), but they have
other important things to do than to fix that. 

I know there were patches from oracle for big endian firefox but I cant find 
the repository anymore. Maybe these patches and the Void Patches could do some
important thing? [**UPDATE**] I found the [patches for firefox](https://github.com/oracle/solaris-userland/tree/master/components/desktop/firefox/patches).

I bet biggest problem are the people at firefox who doesnt care about big endian
firefox builts for ppc64 because it is not important.

### Ressources

* [New Release Of T2/Linux](/new-release-of-t2linux.html)
* [Oracle Patches for Firefox](https://github.com/oracle/solaris-userland/tree/master/components/desktop/firefox/patches)
* [PPC 750 Void Linux Firefox Patches](https://github.com/void-ppc/void-packages-ppc750/tree/master/srcpkgs/firefox/patches)
* [void-packages-ppc750/srcpkgs/firefox/patches/big-endian-image-decoders.patch](https://github.com/void-ppc/void-packages-ppc750/blob/master/srcpkgs/firefox/patches/big-endian-image-decoders.patch)
* [Debian Build Status Firefox](https://buildd.debian.org/status/package.php?p=firefox&suite=sid)

Tags: t2linux, powermacg5, linux, firefox
