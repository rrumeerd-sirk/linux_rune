# LINUX-RUNE

A custom version of the GMS LTS runner for running DELTARUNE on Linux natively.

This was made for personal usage, support will **not** be provided. You are *much* better off playing the Windows version of the game under Proton.

**This project is UNOFFICIAL. This software is NOT affiliated with nor endorsed by Toby Fox, Fangamer, 8-4 Ltd, YoYo Games or Opera Norway AS.**


## "Features"

* Implemented game_change trigger for chapter switching.
* Reading game files out of the executable directory, rather than `assets/`.
* Saving savegames to the home folder (/home/{user}/.config/DELTARUNE).

### Bugfixes

* Fixed video support on modern Linux distros .
* Fixed the game becoming blurry after playing a video on older versions of the game.
* Fixed Flowery intro crashing the game 

## Usage

You need to own [DELTARUNE](https://store.steampowered.com/app/1671210/DELTARUNE/) on Steam, or the [Chapter 1&2 free demo](https://store.steampowered.com/app/1671210/DELTARUNE/).

1. Download DELTARUNE on Steam.
    * For the Chapter 1&2 demo on Steam, switch to the `chapter1.2.lts.test` branch.
    * You can also download the files for the Chapter 1&2 DEMO from [itch.io](https://tobyfox.itch.io/deltarune).
2. Extract the `linux-rune` binary into your DELTARUNE game files.
3. Run `chmod +x linux-rune` to make the binary executable.
4. Launch the linux-runer binary via Steam's "Legacy Runtime 1.0 (scout)".
    * `~/.local/share/Steam/ubuntu12_32/steam-runtime/run.sh ./linux-rune`

*(Launching individual chapters can be done; e.g. `./linux-rune -gamedir chapter4_windows launcher`)*

### Video Playback

Video playback (for DELTARUNE Chapter 3 & 5) requires ffmpeg/libavcodec installed.

* **Debian 12+, Ubuntu 22.04+:** `sudo apt install ffmpeg`
* **Fedora 41+:** `sudo dnf install ffmpeg`
* **Arch Linux:** `sudo pacman -S ffmpeg`
* **SteamOS:** (coming soon)

### arm64

1. Download DELTARUNE on Steam on another computer and copy the files over.
    * You can also download the files for the Chapter 1&2 DEMO from [itch.io](https://tobyfox.itch.io/deltarune).
2. Extract the `linux-rune_arm64` binary and provided .so files into your DELTARUNE game files.
3. Run `chmod +x linux-rune_arm64` to make the binary executable
4. Launch the linux-rune binary.
    * e.g. `./linux-rune_arm64`

This should work on most modern arm64 GNU/Linux distros, including Debian 12 (untested), Fedora 42, and the Steam Linux Runtime 3.0 (sniper).

## Known Issues

**With linux-rune** - these issues only affect linux-rune or the game when running under it:

* game_change does not properly preserve window position (offset by window border size).

**With GMS LTS** - these issues affect all games using GMS's native Linux runner:

* (x86_64) Requires launching under Steam Linux Runtime 1.0 (scout) or an older distro.

Problems:

* Controller input is slightly broken.
* Saveflies save to /home/{user}/.config/DELTARUNE rather than $XDG_CONFIG_HOME.
* Runs under XWayland when the user is using Wayland.
* Does not scale to HiDPI displays.
