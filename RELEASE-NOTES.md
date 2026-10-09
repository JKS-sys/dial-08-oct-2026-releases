# Dial release notes

Newest first. Downloads: https://github.com/JKS-sys/dial-08-oct-2026-releases/releases/latest · https://ipconfig.co.network/dial

## Dial 1.0.3 — 09 Oct 2026

- **Quiet start at login:** when Dial opens at login it shows only its menu bar icon — no window, no Dock icon, no splash sound — until you open it. This also works for Login Items added in System Settings, and the login entry is refreshed at every launch, so it still works after you move Dial.
- **Audio enhancers (Pro):** clarity, dialogue boost, bass enhancer and air, plus a harmonic exciter and punch on macOS. They only ever add, and a warmth guard keeps the low mids full when you boost the top.
- **Echo (Pro):** a delay with mix and time controls, and feedback on macOS. On Linux you get a single repeat.
- **Auto-restore on reconnect (Pro):** when headphones or another output comes back, every app you had sent to it goes back to it with its own volume and EQ, and the device's own EQ returns too.

## Dial 1.0.2 — 09 Oct 2026

**Hotkeys, automation and smarter apps** — more of the best ideas from FineTune and Fader.

- **Intel Macs build in the cloud:** the audio engine for Intel and Apple silicon Macs is now built on GitHub's own Macs, so releasing no longer depends on your Mac being able to build the Intel version.
- **Global hotkeys:** turn the playing app up or down, mute it, change or mute the master volume, toggle the EQ, mute your microphone or open the mini mixer from anywhere — your own keys, set in Settings → Shortcuts. A small on-screen display shows what changed.
- **Choose the volume step:** coarse (10 %), normal (5 %), fine (2 %) or extra-fine (1 %) for hotkeys and the arrow keys.
- **Keyboard in the mini mixer:** ↑ ↓ to move, ← → for volume (⇧ for bigger steps), M to mute, Tab for microphones, Esc to close.
- **Pin apps:** keep an app in the mixer even when it's silent, so its volume, EQ and output are ready before it plays.
- **Ignore apps:** tell Dial to leave an app completely alone — it plays exactly as your system plays it.
- **Loudness compensation (Pro):** at low volume Dial adds back the bass and treble your ears stop hearing, so quiet listening still sounds full.
- **Menu bar icon styles:** knob, speaker (it follows your volume), wave or bars — and it flashes the new device when the output changes.
- **Automate with links:** `dial://volume?v=40`, `dial://app?name=Spotify&volume=30`, `dial://preset?name=Rock` and more — from Terminal, Shortcuts, Raycast or any script. Examples to copy in Settings → Automation.
- **Who's using the microphone:** see which apps are listening right now.
- **Alert volume (macOS):** set the volume of system alerts and notifications.
- **Device details (macOS):** sample rate (and change it), connection type and channels for every device.
- **Popup size:** compact, comfortable or spacious.
- **More colour and motion:** coloured keycaps and links, a sliding volume display, pin drops, and a dozen new sounds.
- **Releases keep the demos:** a release from a folder without the demos and screenshots no longer removes them from GitHub.

**A real menu bar mixer** — click Dial's icon and every device and app is one slider away.

- **Menu bar mixer:** click the knob in the menu bar for a compact mixer: your outputs and microphones with their volumes, every playing app with a live level meter, mute, volume, boost (Pro), its own output (Pro) and quick EQ (Pro). Right-click the icon for the full menu. On Linux it opens from the tray menu as "Mini Mixer".
- **Dial asks for the sound permission once:** updates and reinstalls no longer make macOS ask again for "System Audio Recording". Dial is now signed with one stable identity that macOS remembers (you may be asked one last time after this update).
- **The Dock icon stays off:** with "Show in Dock" off, Dial never appears in the Dock again — not at launch, not when its window opens, not after an update.
- **Microphone:** mute your mic from the menu bar, the mini mixer or Devices, set its level, and watch a live input meter.
- **Bluetooth headphones:** paired headphones and speakers that aren't connected are listed — click Connect and the sound moves to them.
- **Tidy the mixer:** in edit mode, drag outputs into your preferred order (the same order auto-switch uses) and hide devices or apps you never touch.
- **More colour and motion:** peak-hold level meters, sliders that pulse with each app's sound, boost chevrons that light up one by one, and 15 new sounds — Bluetooth connecting, mic mute, boost steps and more. Every number, unit and bracket in every window is coloured, never pink.
- **See it move:** the GitHub page now shows animated demos of every part of Dial.

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
