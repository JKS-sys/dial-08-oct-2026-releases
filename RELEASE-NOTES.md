# Dial release notes

Newest first. Downloads: https://github.com/JKS-sys/dial-08-oct-2026-releases/releases/latest · https://ipconfig.co.network/dial

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
