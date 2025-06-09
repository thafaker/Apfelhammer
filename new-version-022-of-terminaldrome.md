New Version 0.2.2 of TerminalDrome

I just finished the work on TerminalDrome 0.2.2 and I am really proud of it,
because I don't know nothing about Rust but the Terminal NaviDrome Client is
running very well :-) 

![](/images/terminaldrome_cover_here.png)
<small>TerminalDrome started, Cover Art, no artist or album chosen</small>

### Whats is new?

* Implemented cover art: terminaldrome is downloading the cover art of the album
if available and convert it to ASCII :-)
* Album Scrolling: while in album pane, there were no scrolling implemented and
when there were more than 5 albums, you would not see them.
* fixed mute button
* updated splash screen :-)
* a lot of other improvements and fixes

### What else?

Tested on:

* Powermac G5 (Debian, Arch, T2 Linux ppc64)
* Arm64 MacMini M4
* Macbook Pro 2016 with x86 Intel CPU
* ArmHF Device (Raspberry Pi like)
* ...

If you download and test it, please let me now if it works. Bug reports straight
to this blog here. Thank you.

## Build Instructions (short)

In this early stage, but TerminalDrome runs on a daily basis here, it is a good
idea to let it run via <code>cargo run</code>. Short build instructions as follows:

### 🔧 Build with Cargo

	git clone https://github.com/thafaker/termnavi.git TerminalDrome

After the, change to TerminalDrome directory:

	cd TerminalDrome

and create a file <code>config.toml</code>:

	[server]
	url = "https://YourNaviDromeServer.de"
	username = "yourUser"
	password = "yourPass"

than:

	#either (prefered)
	cargo run
	# or
	cargo build --release

Thats all, that should build and run TerminalDrome and let it run, connected
to your NaviDrome Server.

### Ressources
* [TerminalDrome Github Repo](https://github.com/thafaker/termnavi/tree/main)

Tags: ppc64, aarch64, arm64, navidrome, rust, terminal, powermacg5, linux, termnavi, terminaldrome
