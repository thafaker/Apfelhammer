TerminalDrome 0.2.0 is available

I am proud to announce the release of **TerminalDrome** 0.2.0 as a feature-rich
stable version to the public. It is still alpha but it works on a daily basis
here on my Powermac G5 or the Mac Mini M4. 

![](/images/terminal_drome_splash.png)
<small>TerminalDrome Splash Screen</small>

There are [compiled binaries](https://github.com/thafaker/termnavi/releases/tag/v0.2.0) available for arm64, ppc64 and armhf. But TerminalDrome
will build on every Linux with Rust and Cargo.

## Status
* Absolute pre-alpha!!!
* Scrobbling to last.fm and listen.brainz works via Navidrome
* Track updates while playing. Once a song finishes, it automatically switches to the next one and updates the display accordingly.
* A basic full-text search is implemented: press the slash `/` key to open the search window, enter a term, and the results will appear in the third pane.
* Basic Help Screen via Shift+H Button.
* Splash Start Screen :-)
* Nice Status Bar at the bottom

![](/images/terminaldrome_powermac_playing.png)
<small>TerminalDrome is playing a song on my Powermac G5</small>

## ✨ Key Features of TerminalDrome

1. Navidrome Integration  
    * Connects to your Navidrome server (HTTPS enforced)  
    * Supports all Subsonic API endpoints (Artists, Albums, Songs)

2. TUI (Terminal UI) with 3-column layout  
    * Artists → Albums → Songs  
    * Intuitive navigation using arrow keys  
    * Colored highlights (active songs, selection, status)

3. Music Playback  
    * MPV integration (runs silently in the background)  
    * Automatic transition to the next song (playlist mode)  
    * Play/pause with spacebar  
    * Progress bar and time display

4. Last.fm Scrobbling  
    * Automatically scrobbles at ~50% of the song duration  
    * Correct timestamps (Unix milliseconds)  
    * Avoids duplicates (via `current_scrobble_sent` flag)

5. Persistence  
    * Saves last state (`state.json`)  
        * Current artist/album/song  
        * Scroll positions  
        * Now-playing index  
    * Stable MPV communication  
    * Unix socket for real-time updates (playlist position, time)  
    * Correct handling of playlist end  
    * Minimal status bar  
    * Displays current song + album/artist  
    * Clear error messages (e.g. for connection problems)

![](/images/terminaldrome_help.png)
<small>TerminalDrome Help Screen</small>

## 🔧 Technical Highlights

* Written in Rust (fast & safe)  
* Async/await for non-blocking I/O  
* Atomic operations for thread-safe state (MPV ↔ UI)  
* TOML configuration (server URL, credentials)

## 🚀 Roadmap Ideas (optional)

* Search filtering in lists  
* Shuffle/repeat modes  
* Cover art (via Sixel or ASCII art)  
* Theme support (color schemes)

### Ressources
* [TerminalDrome Release 0.2.0](https://github.com/thafaker/termnavi/releases/tag/v0.2.0)
* [TerminalDrome Github Repo](https://github.com/thafaker/termnavi/tree/main)

Tags: ppc64, navidrome, rust, terminal, powermacg5, linux, termnavi, terminaldrome

