Allow Apps From Anywhere macOS 15.2 Sequoia

So, the other day [I installed a **media server** to *stream* my long lost MP3-Archive](https://thahipster.de/navidrome-mein-eigenes-spotify/) 
like it's Spotfiy, over the air to my Smartphone while I wear Headphones etc. pp
and therefore I tested a lot of apps. I ran into the issue that macOS 15 does not
let you device to open an unverified app like on the macOS releases before, it is a way
harder. But the easiest solution I found is this, type in the terminal:

<code>xattr -d com.apple.quarantine /path/to/app</code>

Replace <code>/path/to/app</code> with the app, the easiest way is to drag the app into the
terminal, it will complete the path automatically. After that, the app will start.

Tags: macos, apple
