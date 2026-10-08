<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="icon-512.png">
    <source media="(prefers-color-scheme: light)" srcset="icon-512-light.png">
    <img src="icon-512-light.png" width="160" height="160" alt="Dial icon">
  </picture>
</p>

<h1 align="center">Dial</h1>

<p align="center"><b>An AI sound mixer — for macOS, Linux, ChromeOS and FreeBSD</b></p>

<p align="center">
  Version <b>1.0.0</b> · released 08 Oct 2026 ·
  <a href="https://github.com/JKS-sys/dial-08-oct-2026-releases/releases/latest">Download</a> ·
  <a href="https://ipconfig.co.network/dial">Website</a> ·
  <a href="RELEASE-NOTES.md">Release notes</a>
</p>

<p align="center">
  <img src="icon-512.png" width="96" height="96" alt="Dial icon, dark">&nbsp;&nbsp;
  <img src="icon-512-light.png" width="96" height="96" alt="Dial icon, light">
</p>

Dial gives every app its own volume, puts an equaliser on everything you hear, switches your speakers,
headphones and microphone, and fixes sound that is lopsided, too quiet or too harsh. Set it by hand, or just say
what you want — *“quieter music”, “more bass”, “calls to my headphones”* — and Dial AI moves the sliders.
A native desktop app of a few megabytes.

## Features

✓ = in Dial Free · ★ = Dial Pro

| | Feature | Free | Pro |
|---|---|:---:|:---:|
| 🔊 | **Master volume and mute**, output and input device switching, per-device volume | ✓ | ✓ |
| 🎚️ | **Per-app volume 0–100 % and mute**, for every app — remembered per app | ✓ | ✓ |
| 🚀 | **Per-app boost above 100 %**, up to 400 % | — | ★ |
| 🎛️ | **10-band graphic equaliser** with 14 built-in presets (Bass Boost, Vocal / Podcast, Late Night…) | ✓ | ✓ |
| 📈 | **Parametric equaliser** — up to 16 bands, type / frequency / gain / Q | — | ★ |
| 💾 | **Custom presets** — save, rename, delete, import and export as JSON | 1 slot | ★ unlimited |
| 🎧 | **Per-app EQ** — one app gets its own curve (macOS) | — | ★ |
| 🔀 | **Per-app output device** — one app to headphones, another to speakers | — | ★ |
| 🩺 | **Sound fixer:** balance and preamp | ✓ | ✓ |
| 🛡️ | **Sound fixer:** mono, left/right swap, limiter | — | ★ |
| 🌈 | **Spectrum visualiser** — bars, ring, wave, mirror | ✓ | ✓ |
| ✨ | **AI:** Dial AI (free, built in), offline quick fixes, GitHub Copilot CLI, GitHub Models, every local server (Ollama, LM Studio, Jan, llama.cpp, GPT4All, KoboldCpp, vLLM, text-generation-webui, Msty, AnythingLLM) and any OpenAI-compatible service | ✓ | ✓ |

Keyboard: Mixer ⌘1 · Equaliser ⌘2 · Devices ⌘3 · Visualiser ⌘4 · Sound Fixer ⌘5 · AI panel ⌘J.

## Screenshots

Each screenshot follows your theme (dark or light).

| | |
|---|---|
| <picture><source media="(prefers-color-scheme: dark)" srcset="screenshots/mixer-dark.png"><img src="screenshots/mixer-light.png" alt="Dial mixer"></picture> <br> *Mixer — a volume, mute and output for every app* | <picture><source media="(prefers-color-scheme: dark)" srcset="screenshots/eq-dark.png"><img src="screenshots/eq-light.png" alt="Dial equaliser"></picture> <br> *Equaliser — graphic or parametric, with presets* |
| <picture><source media="(prefers-color-scheme: dark)" srcset="screenshots/devices-dark.png"><img src="screenshots/devices-light.png" alt="Dial devices"></picture> <br> *Devices — speakers, headphones, Bluetooth and the microphone* | <picture><source media="(prefers-color-scheme: dark)" srcset="screenshots/visualizer-dark.png"><img src="screenshots/visualizer-light.png" alt="Dial visualiser"></picture> <br> *Visualiser — bars, ring, wave and mirror* |
| <picture><source media="(prefers-color-scheme: dark)" srcset="screenshots/fixer-dark.png"><img src="screenshots/fixer-light.png" alt="Dial sound fixer"></picture> <br> *Sound fixer — balance, preamp, mono, swap, limiter* | <picture><source media="(prefers-color-scheme: dark)" srcset="screenshots/ai-chat-dark.png"><img src="screenshots/ai-chat-light.png" alt="Dial AI"></picture> <br> *Dial AI — say what you want to hear* |

## Install

One line in a terminal works on **macOS, Linux, ChromeOS and FreeBSD**:

```bash
curl -fsSL https://ipconfig.co.network/updates/dial/install.sh | bash
```

**macOS** (Apple silicon and Intel, macOS 10.15+) — the installer picks the right build, copies **Dial.app** to
`/Applications` and clears the quarantine flag. If you install from the DMG by hand instead, run this once
before the first launch (Dial is ad-hoc signed, not notarized):

```bash
xattr -cr /Applications/Dial.app
```

Per-app volume, per-app EQ and the equaliser use Core Audio process taps, which need **macOS 14.4 or later**
and the **System Audio Recording Only** permission (System Settings → Privacy & Security) — Dial asks once.
On older macOS, Dial controls the master volume and devices.

**Linux** (x86_64) — works with **PipeWire** and **PulseAudio**; Dial uses `pactl` / `parec` from
`pulseaudio-utils` (the packages pull it in, and the installer adds it when `pactl` is missing).

- Debian / Ubuntu / Mint: the installer uses the `.deb`, or download `Dial_1.0.0_amd64.deb` and
  `sudo apt install ./Dial_1.0.0_amd64.deb`.
- Fedora: `sudo dnf install ./Dial_1.0.0_x86_64.rpm` · openSUSE:
  `sudo zypper install --allow-unsigned-rpm ./Dial_1.0.0_x86_64.rpm`.
- Any distribution: `Dial_1.0.0_amd64.AppImage` — `chmod +x Dial_*.AppImage && ./Dial_*.AppImage`
  (needs `libfuse2`), or `… | bash -s -- --appimage` to install it to `~/.local/bin/dial`.

**Linux ARM64** (Raspberry Pi 4/5 with a 64-bit OS, ARM laptops) — Debian / Ubuntu: the same one-liner, or
download `Dial_1.0.0_arm64.deb` and `sudo apt install ./Dial_1.0.0_arm64.deb`.
ARM64 Linux has a `.deb` only — there is no ARM AppImage or `.rpm`.

**ChromeOS** — Dial runs in the Linux development environment (a Debian container), on Intel/AMD and ARM Chromebooks:

1. **Settings → Advanced → Developers → Linux development environment → Turn on** (a few minutes the first time).
2. Open the **Terminal** app and run the one-liner above — it detects ChromeOS and picks the right package.
   Or by hand: `dpkg --print-architecture` says `amd64` (Intel/AMD) or `arm64` (ARM). Download
   `Dial_1.0.0_amd64.deb` or `Dial_1.0.0_arm64.deb`, move it to **Linux files** and double-click it —
   or run `sudo apt install ./Dial_1.0.0_<arch>.deb`.
3. Open Dial from the launcher (**Linux apps**). It mixes the sound of the apps in the Linux container.

**FreeBSD** (amd64, FreeBSD 14 or later, with a desktop) — as root:

```sh
pkg install pulseaudio webkit2-gtk_41 bash curl
curl -fsSL https://ipconfig.co.network/updates/dial/install.sh | bash
```

Or download `Dial_1.0.0_freebsd_amd64.tar.gz` and, in the download folder,
`tar -xzf Dial_1.0.0_freebsd_amd64.tar.gz && sudo sh install.sh` — it installs to `/usr/local/bin/dial`
with a menu entry and icon (`sh install.sh --uninstall` removes them). With PulseAudio running Dial mixes every
app; without it, Dial controls the OSS master volume.

**Haiku** — not possible: Haiku isn't supported because Dial's window engine (Tauri/WebKit) has no Haiku port.

**Windows** — not available yet.

Dial updates itself on macOS and Linux (AppImage, `.deb` and `.rpm`; x86_64 and ARM64): when a new version is
out it offers to install it and restart, and checks the update's signature first. A `.deb` or `.rpm` update asks
for your password, like any package install. On FreeBSD, run the installer again to update.

## Platforms

| System | CPU | Download | Updates itself |
|---|---|---|---|
| macOS 10.15+ (per-app audio: 14.4+) | Apple silicon | `Dial_1.0.0_aarch64.dmg` | yes |
| macOS 10.15+ (per-app audio: 14.4+) | Intel | `Dial_1.0.0_x64.dmg` | yes |
| Linux, any distribution | x86_64 | `Dial_1.0.0_amd64.AppImage` | yes |
| Debian / Ubuntu / Mint | x86_64 · ARM64 | `Dial_1.0.0_amd64.deb` · `Dial_1.0.0_arm64.deb` | yes |
| Fedora / openSUSE | x86_64 | `Dial_1.0.0_x86_64.rpm` | yes |
| ChromeOS (Linux development environment) | x86_64 / ARM64 | the `.deb` for the Chromebook's CPU | yes |
| FreeBSD 14+ | amd64 | `Dial_1.0.0_freebsd_amd64.tar.gz` | no — rerun the installer |
| Windows | — | not available yet | — |
| Haiku | — | not possible | — |

## Pricing

| Free | Pro monthly | Pro yearly |
|---|---|---|
| ₹0 | **₹20 / month** | **₹220 / year** |
| Per-app volume, the graphic EQ and presets, devices, balance and preamp, the visualiser and all the AI | Boost to 400 %, parametric and per-app EQ, per-app outputs, mono / swap / limiter, unlimited presets | Everything in Pro — two months cheaper |

After paying you get an activation code at once, and Pro turns on by itself if you bought from inside Dial.

[Get Dial Pro →](https://ipconfig.co.network/dial/buy?plan=monthly) · [yearly](https://ipconfig.co.network/dial/buy?plan=yearly)

## Links

- Releases and downloads: https://github.com/JKS-sys/dial-08-oct-2026-releases/releases
- Website: https://ipconfig.co.network/dial
- Release notes: [RELEASE-NOTES.md](RELEASE-NOTES.md)
- Update feed: [latest.json](latest.json)

## Creator

Made by Jagadeesh Kumar S, creator — [youtube.com/@JKS-sys](https://www.youtube.com/@JKS-sys)

## Licence

Proprietary. © 2026 Jagadeesh Kumar S. All rights reserved.
The installers are free to download and use; the source code is not published, and copying,
modifying or redistributing Dial is not permitted without written permission.
