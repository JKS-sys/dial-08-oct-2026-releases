# Dial release notes

Newest first. Downloads: https://github.com/JKS-sys/dial-08-oct-2026-releases/releases/latest · https://ipconfig.co.network/dial

## Dial 1.0.9 — 17 Oct 2026

- **Noise while Dial processed an app.** On outputs that hand audio over as one mono buffer per channel (many USB interfaces and some combined outputs), Dial copied the app's left/right pairs straight into a mono buffer, so the app played as loud noise. Dial now processes every channel layout properly (left and right go to their own channels). The equalizer also no longer slows down on near-silent sound on Intel Macs, which could cause crackle.
- **Notifications in the notification centre.** Alerts now go to the system's notification centre even while Dial's window is in front (Settings → Notifications → "Also while Dial is in front" turns that off).
- **Your choices stay after a relaunch.** Pausing the System Monitor, its Overview / Processes tab, sort, kind filter and search, the Displays tab and the display you picked, the menu bar mixer's Output / Input tab and its CPU / Memory sort, and the AI panel's tab now come back as you left them. Settings saved by the main window are no longer overwritten by the mini mixer window.
- **Display settings come back by themselves.** Dial already saved HiDPI and the software picture, but put them back only once, 3 seconds after launch — a display that wasn't ready yet (at login, asleep, slow to answer) lost them, and macOS quietly resetting the colour table (wake, Night Shift, True Tone) undid dimming, warmth and contrast. Dial now retries, watches the colour table and puts it back, re-applies everything when a display is reconnected, and also restores brightness, contrast and volume on monitors that forget them (DDC). It never brings a display back darker than 5 %. Mirroring onto a Dial virtual screen is now for the session only, so a restart never mirrors to a screen that is gone.
- **More for Displays.** A new **Presets** tab: Night, Reading, Movie, Presentation and Default for one display or all; **Match brightness** on every display; a **Day and night** schedule (times, day and night brightness, night warmth); **Reset display settings** for one display or all. The Picture tab adds a **Gamma** slider, and Info shows the colour space, connection, preset and whether Dial keeps settings for it. Every action is in the display's right-click menu, with its own sound and animation.
- **Correct temperatures on Apple Silicon.** Thermals, the menu bar and alerts used macOS's averaged sensors (one of them is a fixed calibration value), so CPU temperatures looked wrong. Dial now reads every temperature sensor straight from the Mac's SMC, the way Stats does: each CPU efficiency / performance core, each GPU cluster, battery, SSD, memory, Wi-Fi and palm rest, with friendly names for M1–M5. The menu bar and mini mixer show the CPU core average.
- **Much more Auto Boost.** Presets (Silent, Balanced, Performance, Max cooling), a fan curve with draggable points, which sensor drives it (CPU, GPU, hottest, battery), hysteresis and ramp speed, boost while charging, boost while chosen apps run, mains power only, quiet hours, and fans back to automatic when Dial quits. Thermals also gains per-sensor sparklines, today's min / average / max, a throttling indicator and new animations and sounds.
- **App Tamer and Thermals alerts reach the notification centre.** CPU / memory hogs, memory pressure, swap growth, a full graphics memory, blocks, idle quits, overheating, fan problems and throttling now all send system notifications (each app separately), and a click opens the right page.
- **More App Tamer.** Presets (Battery saver, Quiet fans, Focus, Gaming), per-app rules that pause an app after some minutes in the background or lower its priority, a schedule (on battery only, certain hours), snooze, automatic taming of new hogs, a never-tame list, a "tamed now" list with Undo, a "front app only" button, an energy-impact ranking, memory pressure / swap / graphics memory charts, per-app history, rules export and import, and right-click menus everywhere.
- **More Battery.** Presets (Desk 60 %, Daily 80 %, Travel 100 % until unplugged), "full by" a chosen time, time to the limit / full / empty, a long-term health chart with the date it is likely to reach 80 %, an Adapter tab (watts, volts, the cable or port limiting power), alerts for low battery, limit reached, heat and health, and right-click menus on every card. A damaged settings file no longer resets your limit to 100 %.

## Dial 1.0.8 — 16 Oct 2026

- **Apps going silent when several play at once.** When a second app started playing, the first one's audio path could keep running but receive nothing — so that app went silent while only the other one played. Dial now notices an app that is playing but whose path delivers only silence for 2.5 seconds, and rebuilds that path; it also re-checks every other app whenever a new app's path is built. If an app ever does go quiet, right-click the menu bar icon → Tools → **Fix Silent Apps** (also in the Dock menu and the window's right-click menu) restarts the sound engine.
- **The mini mixer over full-screen apps.** macOS hides the menu bar in a full-screen app, so the icon can't be clicked. Rest the pointer in the **top-right corner** of the screen and the mini mixer opens there (Settings → Lives in → Full-screen apps: top right, top left or off; also in the menu bar and Dock menus). The ⌃⌥⌘M hotkey still opens it anywhere. A click on the menu bar icon now always opens the mixer on the screen and Space you are looking at — if it had been left open on another Space, the click used to close that one instead.
- **Battery helper no longer shows an error after every update.** Dial treated the helper as out of date whenever its version number differed from the app's, so after each update the Battery view and Settings showed "press Repair". A helper that speaks the same protocol does every job, so it now counts as up to date. The helper log only shows the helper's current run, with clock times, and normal probe lines are no longer shown as errors.
- **Menu bar animations.** Each icon style has its own click animation (the wave flows, the bars dance, the speaker's waves grow, the knob turns); closing the mini mixer turns the knob back; right-click bursts sparks; picking any menu item draws a check mark; applying a sound profile slides a card in (with its own sound); switching the equalizer moves three sliders.
- **New sounds with pictures:** the hot corner, the sound engine restarting, and a silent app playing again.
- **More in the menus.** The Dock menu now has Volume ▸ (10–100 %, up, down), Apps ▸ (mute or unmute each app, ♪ on the ones playing), Auto-pause music and Auto-switch output, like the menu bar menu. The window's right-click menus gain Fix silent apps, Sound profiles ▸ (apply any profile) and Test tone ▸ (left, right or both) — also on the master volume, apps and engine menus.

## Dial 1.0.7 — 16 Oct 2026

**Battery that works on current Macs, an idle cleaner, Block, Windows, accounts, and a menu bar that works over full-screen apps**

- **Battery fixed for current Macs.** Dial now detects which of Apple's three charging-firmware generations your Mac has and uses the method that still works: the firmware's own limit (macOS 26.4+ firmware), the classic charging switch (older firmware), turning the power adapter off at the limit (the newest firmware, which blocks the old keys — as AlDente does), or macOS's own 80–100 % limit. The Battery view says which method is in use and why. The helper now verifies itself after installing, keeps a log, shows launchd's real error, and has a Repair button.
- **Several apps playing at once.** Stopping one app no longer silences the others: Dial keeps each app's audio path when it pauses, re-checks the others after any change, rebuilds a stalled path within half a second, and never leaves an app muted without a working path.
- **Menu bar dropdown over full-screen apps.** The dropdown and the volume pop-up now open on top of a full-screen app without switching Space.
- **New menu bar dropdown.** Rows sit tightly together. It has dropdowns for outputs, inputs, each app's device and EQ, a brightness slider and HiDPI switch for every display, fan speed and the hottest temperature with a fan menu (Auto / Quiet / Boost / Max), CPU, memory, a battery menu, the apps and services using the most CPU or memory with Slow / Pause / Quit / Block, and Clean idle.
- **Idle cleaner.** Quits or hides apps you haven't used for a while (countdowns, a never-quit list, quit when the last window closes, a daily reset), never the front app or an app playing sound. Lists idle background services and leftover command-line tools in memory — forgotten dev servers, orphaned language servers, idle `ollama serve`, `caffeinate` — and cleans them with one click, or automatically.
- **Block.** Quits an app or service (force-quits if needed), switches its launchd job off where macOS allows, and stops it every time it starts again. Unblock any time from the Blocked list.
- **Notifications that open Dial.** Clicking one opens the right page. Per-kind switches and a Test button in Settings → Notifications.
- **Lives in.** Dock and menu bar, Dock, menu bar, or background. Closing the last window quits Dial whenever it is in the Dock; in the menu bar or background it keeps running only while Run in background is on.
- **Accounts.** Sign in with an email code or a password; your licence is tied to this computer, works offline for up to 14 days, and lists your computers so you can free a seat. Older codes and subscriptions carry over by themselves. The Owner Panel stays connected to the dashboard on its own.
- **Windows.** Per-app volume with real per-app levels, device switching, system-sound recording, screen recording, display modes, brightness and EDID; a system-wide EQ with Equalizer APO.
- **Installers built on the Mac.** `update.sh` builds macOS, Windows, Linux (incl. ChromeOS) and FreeBSD installers locally. Haiku isn't possible: Tauri has no web view for Haiku.
- **Finder.** 20 right-click services: play, add to the library, trim, fix sound, apply an EQ preset, normalize loudness, convert to MP3/AAC/M4A/WAV/FLAC, extract audio, compress video, make a ringtone, audio info, record the screen into a folder, set the Screen Studio folder, free memory, block, open. A File jobs drawer shows their progress.
- **Everywhere.** A Controls menu and bigger Dock and menu bar menus; right-click menus on nearly everything; 8 layouts per list; 27 new sounds, each with a small animation; no overlaps or sideways scrolling from 480 × 360 up; more colour, never pink.
- **Sound Profiles.** Save your whole sound — volumes, every app, EQ, enhancers, fixer, output and input — as a profile and bring it back with one click, a hotkey or the menu, crossfaded in 0.4 s. Profiles can switch by themselves when headphones connect, when an app starts playing or at a time of day. Per app: lower the others while it plays, a volume cap, and its own volume for every output. Listening stats show which apps played today, this week and this month.
- **Menu bar clicks come alive.** The menu bar icon animates on clicks, mute, volume, output switches and recording, with a soft click sound. On macOS the right-click menu has a coloured symbol on every item, a header with the current output and volume, and a Now Playing list. The dropdown opens with a small drop-in animation, and its sections have their own live glyphs (a fan spinning at the real speed, a thermometer, battery fill, sun rays, a flame, a sleepy moon).
- **Windows and FreeBSD builds fixed.** The Windows app links (a WinRT library name was wrong; the Windows builds keep their own Cargo folder so a home folder with spaces can't break the linker), ARM64 uses cargo-xwin's clang mode for ring, and FreeBSD builds without the updater permission it doesn't have. The Windows installers no longer depend on Tauri's own short-timeout download of its NSIS plugin: the release script fetches it with retries beforehand.
- **Releases.** The build board redraws in place instead of scrolling, a drawing error can no longer stop a release, and a failed build shows its log straight away.
- **Smaller.** Trimmed Tauri features and a size-optimised, stripped audio engine. (A Tauri app can't reach 3 MB: about 8 MB on Linux.)

## Dial 1.0.6 — 16 Oct 2026

**Battery that works on current Macs, an idle cleaner, Block, Windows, accounts, and a menu bar that works over full-screen apps**

- **Battery fixed for current Macs.** Dial now detects which of Apple's three charging-firmware generations your Mac has and uses the method that still works: the firmware's own limit (macOS 26.4+ firmware), the classic charging switch (older firmware), turning the power adapter off at the limit (the newest firmware, which blocks the old keys — as AlDente does), or macOS's own 80–100 % limit. The Battery view says which method is in use and why. The helper now verifies itself after installing, keeps a log, shows launchd's real error, and has a Repair button.
- **Several apps playing at once.** Stopping one app no longer silences the others: Dial keeps each app's audio path when it pauses, re-checks the others after any change, rebuilds a stalled path within half a second, and never leaves an app muted without a working path.
- **Menu bar dropdown over full-screen apps.** The dropdown and the volume pop-up now open on top of a full-screen app without switching Space.
- **New menu bar dropdown.** Rows sit tightly together. It has dropdowns for outputs, inputs, each app's device and EQ, a brightness slider and HiDPI switch for every display, fan speed and the hottest temperature with a fan menu (Auto / Quiet / Boost / Max), CPU, memory, a battery menu, the apps and services using the most CPU or memory with Slow / Pause / Quit / Block, and Clean idle.
- **Idle cleaner.** Quits or hides apps you haven't used for a while (countdowns, a never-quit list, quit when the last window closes, a daily reset), never the front app or an app playing sound. Lists idle background services and leftover command-line tools in memory — forgotten dev servers, orphaned language servers, idle `ollama serve`, `caffeinate` — and cleans them with one click, or automatically.
- **Block.** Quits an app or service (force-quits if needed), switches its launchd job off where macOS allows, and stops it every time it starts again. Unblock any time from the Blocked list.
- **Notifications that open Dial.** Clicking one opens the right page. Per-kind switches and a Test button in Settings → Notifications.
- **Lives in.** Dock and menu bar, Dock, menu bar, or background. Closing the last window quits Dial whenever it is in the Dock; in the menu bar or background it keeps running only while Run in background is on.
- **Accounts.** Sign in with an email code or a password; your licence is tied to this computer, works offline for up to 14 days, and lists your computers so you can free a seat. Older codes and subscriptions carry over by themselves. The Owner Panel stays connected to the dashboard on its own.
- **Windows.** Per-app volume with real per-app levels, device switching, system-sound recording, screen recording, display modes, brightness and EDID; a system-wide EQ with Equalizer APO.
- **Installers built on the Mac.** `update.sh` builds macOS, Windows, Linux (incl. ChromeOS) and FreeBSD installers locally. Haiku isn't possible: Tauri has no web view for Haiku.
- **Finder.** 20 right-click services: play, add to the library, trim, fix sound, apply an EQ preset, normalize loudness, convert to MP3/AAC/M4A/WAV/FLAC, extract audio, compress video, make a ringtone, audio info, record the screen into a folder, set the Screen Studio folder, free memory, block, open. A File jobs drawer shows their progress.
- **Everywhere.** A Controls menu and bigger Dock and menu bar menus; right-click menus on nearly everything; 8 layouts per list; 27 new sounds, each with a small animation; no overlaps or sideways scrolling from 480 × 360 up; more colour, never pink.
- **Sound Profiles.** Save your whole sound — volumes, every app, EQ, enhancers, fixer, output and input — as a profile and bring it back with one click, a hotkey or the menu, crossfaded in 0.4 s. Profiles can switch by themselves when headphones connect, when an app starts playing or at a time of day. Per app: lower the others while it plays, a volume cap, and its own volume for every output. Listening stats show which apps played today, this week and this month.
- **Menu bar clicks come alive.** The menu bar icon animates on clicks, mute, volume, output switches and recording, with a soft click sound. On macOS the right-click menu has a coloured symbol on every item, a header with the current output and volume, and a Now Playing list. The dropdown opens with a small drop-in animation, and its sections have their own live glyphs (a fan spinning at the real speed, a thermometer, battery fill, sun rays, a flame, a sleepy moon).
- **Windows and FreeBSD builds fixed.** The Windows app links (a WinRT library name was wrong; the Windows builds keep their own Cargo folder so a home folder with spaces can't break the linker), ARM64 uses cargo-xwin's clang mode for ring, and FreeBSD builds without the updater permission it doesn't have.
- **Releases.** The build board redraws in place instead of scrolling, a drawing error can no longer stop a release, and a failed build shows its log straight away.
- **Smaller.** Trimmed Tauri features and a size-optimised, stripped audio engine. (A Tauri app can't reach 3 MB: about 8 MB on Linux.)

## Dial 1.0.5 — 12 Oct 2026

**Battery care, displays with HiDPI, memory taming and a menu bar you choose**

- **Battery (an AlDente-style charge manager):**
  - Charge limit and Discharge are free. With Pro: Automatic Discharge, Top Up, Sailing Mode, Heat Protection, Calibration Mode, MagSafe LED colours, stop charging while asleep or when Dial is closed, stay awake until the limit, Low Power Mode, and schedules with catch-up and a task history.
  - A live Power Flow diagram shows where the watts go, and you see the hardware battery percentage next to the one macOS shows.
  - On Linux you get the charge limit, sailing, top up and schedules (on laptops that support charge thresholds).
- **Displays (a BetterDisplay-style manager):**
  - Flexible HiDPI renders any display at 2× for crisp text at any size (Pro).
  - Resolution and refresh rate, favourite modes, brightness for the built-in screen and for external monitors (DDC), software dimming down to black, contrast, colour temperature (Night Shift for TVs), DDC volume and input, rotation, mirroring, main display, arrangement, disconnect and reconnect, virtual screens and EDID export.
- **One-time helper:** install the Dial helper once, with one password, and fan control, charging and memory cleanup stop asking for your password.
- **App Tamer for memory:**
  - Cap an app's memory (Linux sends the rest to swap; macOS pauses it above the limit while it's in the background), pause it in the background or move it to the efficiency cores.
  - Free memory now, plus warnings for RAM, swap and VRAM hogs.
  - Per-app RAM, swap, compressed memory and VRAM.
  - CPU taming now catches Safari's page processes and resumes every held app even if Dial is force-quit.
- **Menu bar items:** pick any mix: CPU, temperature, fan rpm, memory, swap, Macintosh HD free space (e.g. 249.05 GB), network, battery, power, GPU, VRAM, App Tamer, the main display mode and uptime. You can show the icon, the text or both.
- **Screen Studio:** recordings can run with no time limit (Pro). A new Camera mode records your webcam full screen with your microphone.
- **Run in background:** closing the last window quits Dial, unless Run in background is on, or the Dock icon is off and the menu bar icon is on.
- **Fixed:** turning the Dock icon or the menu bar icon on or off could crash Dial.
- **Right-click everywhere:** much more in the app (every view, sidebar item, title bar button and status bar segment), in the Dock menu, in a new Tools menu and in the menu bar menu. There are also `dial://` links for battery, displays and memory.
- **Fits any size:** with 12 views the sidebar folds the extra ones into a More button, and nothing scrolls or overlaps down to 480 × 360.
- More colour (still no pink), more vector animations and new sounds throughout. The startup animation shows all 12 views.
- **FreeBSD:** the build is fixed.

## Dial 1.0.4 — 12 Oct 2026

**Screen Studio, a system monitor, an app tamer and thermals** — Dial now looks after your whole Mac, not only its sound.

- **Screen Studio:** record your screen with your microphone and a floating camera bubble for tutorials and YouTube videos, up to 30 minutes (5 minutes free). Watch your recordings inside Dial, trim them, rename them, show them in Finder or delete them.
- **Sound recordings:** every recording now has Open in Finder (Show in Files on Linux), and Copy path really copies the path.
- **Monitor:** CPU per core, memory and pressure, disks, network, battery and GPU with live charts, the busiest apps, and an optional readout next to the menu bar icon.
- **App Tamer:** slow down or pause apps while you're not using them, move busy background work onto the efficiency cores, and get a warning when something hogs the CPU. There's also a Time Machine speed-up (2 apps free, unlimited with Pro).
- **Thermals:** every temperature sensor with its highest reading, fan speeds, fan control (Auto, Manual or Max) and Auto Boost rules (Pro). It also shows hardware health and the last shutdown cause, and offers temperature alerts by notification and email plus CSV logs.
- **Closing the last window quits Dial.** If you'd rather keep Dial in the menu bar, turn on Settings → Keep running in the menu bar.
- **Right-click everywhere:** many more right-click options in the app, a fuller Dock menu, and Open With → Dial plus Quick Actions in Finder. On Linux you get actions in Files, Dolphin and Nemo.
- **Fits any window size:** no overlapping and no page scrolling, down to a small 480 × 360 window.
- More colour (still no pink), smoother vector animations and new sounds throughout.
- Apple Developer signing and Mac App Store packaging (`npm run apple-sign`) for when the Apple Developer Program is joined.

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

- **macOS, Linux, ChromeOS and FreeBSD** — with Pour: `curl -fsSL https://ipconfig.co.network/pour/install | sh` then `pour install --cask dial`
- **Windows** (x64 and ARM64) — get Pour (`pour-windows-x86_64.exe` or `pour-windows-arm64.exe` from https://ipconfig.co.network/pour/dl/), then `pour install --cask dial`; or run `Dial_<version>_x64-setup.exe` / `_arm64-setup.exe` from this release.
- **Linux** packages: `.deb` (Debian, Ubuntu, Mint), `.rpm` (Fedora, openSUSE) and the AppImage — each for x86_64 and ARM64.
- **ChromeOS** = the Linux `.deb`: turn on the Linux development environment, then install it (or use Pour) in its Terminal.
- **FreeBSD** 14.x (amd64): the `_freebsd_amd64.tar.gz` (`tar -xzf … && sudo sh install.sh`), or Pour.
- **Haiku**: not possible — Tauri has no WebView backend for Haiku.

First launch on macOS after a manual DMG install: `xattr -cr /Applications/Dial.app` (Dial is self-signed, not notarized). Per-app volume and the equaliser on macOS need macOS 14.4 or later.
