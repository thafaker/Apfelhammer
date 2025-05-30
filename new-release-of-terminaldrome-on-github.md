New Release of TerminalDrome on Github

Since I recently discovered how relaxing programming can be, I've been tinkering with my Navidrome-compatible terminal client called TerminalDrome almost every day.

I've now integrated a new feature, which I've moved to Main:

A simple search function:

* Press slash / and the search will open.
* Enter the search term, press Enter, and you'll see the search results in the right panel.
* It's neither alphabetically sorted nor otherwise organized.
* Additionally, there's a feature in the leftmost panel where you can jump directly to the beginning of the respective artist by pressing a letter of your choice. So if I press D, I'll land on D.A.F., or Q on Queens Of The Stone Age—you get it?

![](/images/terminaldrome_searchj.png)
<small>My TerminalDrome CLient in Search Mode</small>

I'm very proud.

TerminalDrome is written in Rust and can be downloaded and compiled using the following command. You'll need the Rust toolchain and mpv.

	git clone https://github.com/thafaker/termnavi.git TerminalDrome
	cd TerminalDrome
	cargo build && cargo run 

I've also explained this on my [Github repo](https://github.com/thafaker/termnavi/tree/main).

![](/images/terminaldrome_with_search.png)
<small>TerminalDrome (left) near btop (right) on my Debian 13 Sid PowerPC Powermac G5</small>

Tags: ppc64, navidrome, rust, terminal, powermacg5, linux, termnavi, terminaldrome
