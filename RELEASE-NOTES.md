# Dial release notes

Newest first. Downloads: https://github.com/JKS-sys/dial-08-oct-2026-releases/releases/latest · https://ipconfig.co.network/dial

## Dial 1.0.1 — 08 Oct 2026

**Dial now lives in your menu bar** — plus a recorder, headphone correction and smarter outputs, ideas taken from the best open-source sound apps.

- **Menu bar app:** Dial runs from a knob icon in the menu bar (the system tray on Linux) with your volume next to it. From there: mute, volume, output device, equaliser on/off and presets, mute any app, record, and quit.
- **No Dock icon:** on macOS Dial stays out of the Dock by default (turn it back on in Settings). Closing the window keeps Dial running, so your volumes and EQ keep working.
- **Fully in the background if you like:** hide the menu bar icon too — open Dial again from Finder, Launchpad or Spotlight to bring the window back. **Open at login** starts it quietly in the background.
- **Recorder (Pro):** record everything you hear — exactly as Dial processes it — to a WAV file in Music → Dial Recordings, with a live waveform, timer and file size (⌘6).
- **Headphone correction (Pro):** search about 8,800 headphones and earphones (AutoEQ — AirPods, Sony, Sennheiser and more) and Dial flattens their sound with a measured correction curve. Tick "Use with" and it comes back whenever those headphones become the output.
- **Auto-switch output:** rank your devices and Dial moves to the best one the moment it connects — plug in headphones and the sound follows.
- **Auto-pause music (Pro):** your music pauses when a call or video starts playing and resumes when it ends (Spotify, Music, VLC; on Linux any player `playerctl` knows).
- **Sound Fixer (Pro):** stereo width (0–200 %), headphone crossfeed for less tiring listening, and Night mode, a compressor that evens out loud and quiet parts (macOS).
- **Mixer scenes:** Focus, Movie, Call and Normal in one click. Hold ⌥ while dragging any slider for fine control, or scroll on it for 1 % steps.
- **More colour everywhere:** every view, dialog and the Owner Panel now use one colour per meaning — numbers, units, brackets and shortcut keys included — checked for contrast in both themes, never pink.
- **More motion and sound:** animated sidebar bars while audio plays, bursts on presets, a spring when devices plug in, a pulsing record button and 13 new synthesised sound effects.
- **Linux fixes:** equaliser changes now apply live without a gap (some changes were silently ignored before), and the limiter works on Linux too.
- **Release builds no longer need Xcode:** the Command Line Tools are enough.
- **Room reverb (Pro):** add space to any sound, from a small room to a concert hall.
- **Warmth (Pro, macOS):** gentle tape-style saturation for thin or harsh audio.
- **Play on several outputs at once (Pro):** speakers and headphones together, or two rooms at once.
- **Software volume for HDMI and DisplayPort:** outputs with no volume control of their own now get a working volume slider and mute.
- **Remembers each device's volume:** switching to your headphones brings back their level.
- **Duck other apps during calls (Pro):** music and videos drop to the level you pick while Zoom, Teams, FaceTime, Discord, Slack and other call apps are playing, then come back.
- **Sleep timer:** fall asleep to music — Dial fades it out after 15 to 90 minutes (or your own time) and mutes or pauses.
- **Releasing from a fresh folder works:** update.sh now puts the folder's files on top of what GitHub already has instead of stopping with "rejected (fetch first)".

## Dial 1.0.0 — 08 Oct 2026

**Meet Dial — an AI sound mixer.** A volume for every app, an equaliser for everything you hear, and an AI that sets them from plain words. Free for everyday use, AI included.

- **A volume for every app:** turn one app down while another stays loud — music, calls, games, the browser — and mute any of them in one click. Dial remembers each app's settings and brings them back the next time it plays.
- **Boost quiet apps (Pro):** push a too-quiet app past 100 %, up to 400 %.
- **Master volume and devices:** switch between speakers, headphones, Bluetooth, HDMI, USB and AirPlay outputs and your microphone, and set each device's volume, all in one window.
- **Per-app output (Pro):** send one app to your headphones and another to the speakers at the same time.
- **System-wide equaliser:** a 10-band graphic EQ with 14 built-in presets — Bass Boost, Vocal / Podcast, Voice Clarity, Late Night and more — for everything you hear.
- **Parametric EQ (Pro):** up to 16 bands, each with its own type, frequency, gain and Q.
- **Per-app EQ (Pro, macOS):** give one app its own sound — warmer voices on calls, more bass in music — while the rest keeps the global curve.
- **Your own presets:** save, rename and delete EQ presets, and import or export them as JSON (Free keeps one slot, Pro unlimited).
- **Sound fixer:** balance and preamp for everyone; mono, left/right swap and a limiter that tames sudden loud peaks with Pro.
- **Live visualiser:** a colourful spectrum in four styles — bars, ring, wave and mirror.
- **Dial AI, free for everyone:** say "make the music quieter", "more bass" or "send calls to my headphones" and the sliders move for you. Built in, with no account or key — or use GitHub Copilot CLI, GitHub Models, any local model (Ollama, LM Studio, Jan, llama.cpp, GPT4All, KoboldCpp, vLLM, text-generation-webui, Msty, AnythingLLM) or any OpenAI-compatible service. Offline quick fixes work with no AI at all.
- **Keyboard first:** Mixer ⌘1, Equaliser ⌘2, Devices ⌘3, Visualiser ⌘4, Sound Fixer ⌘5, AI panel ⌘J.
- **macOS:** per-app volume and EQ use Core Audio process taps on macOS 14.4 and later — Dial asks once for the "System Audio Recording Only" permission. Older macOS gets master volume and device switching.
- **Linux:** works with PipeWire and PulseAudio (needs `pactl`, from `pulseaudio-utils`); the equaliser runs as a PipeWire filter-chain. Packages: AppImage, `.deb` (x86_64 and ARM64) and `.rpm` for Fedora and openSUSE — all update themselves.
- **ChromeOS:** runs in the Linux development environment on Intel/AMD and ARM Chromebooks; the one-line installer detects ChromeOS and installs the right `.deb`.
- **FreeBSD:** an amd64 tarball with an `install.sh` for `/usr/local` (`pkg install pulseaudio webkit2-gtk_41`). FreeBSD builds do not update themselves — rerun the installer.
- **Dial Pro:** ₹20 a month or ₹220 a year through Razorpay (UPI, cards, netbanking), or an activation code. Pro turns on by itself after paying.
- **Updates itself** on macOS and Linux, and checks every update's signature first.
- Windows isn't available yet. Haiku isn't supported: Dial's window engine (Tauri/WebKit) has no Haiku port.

### Install

- **macOS, Linux, ChromeOS and FreeBSD** — one line in a terminal: `curl -fsSL https://ipconfig.co.network/updates/dial/install.sh | bash`
- **Linux** packages: `.deb` (Debian, Ubuntu, Mint — x86_64 and ARM64), `.rpm` (Fedora, openSUSE — x86_64) or the AppImage; the installer picks the right one.
- **ChromeOS**: turn on the Linux development environment, then run the same line in its Terminal (or install the `.deb`).

First launch on macOS after a manual DMG install: `xattr -cr /Applications/Dial.app` (Dial is ad-hoc signed, not notarized). Per-app volume and the equaliser on macOS need macOS 14.4 or later.
