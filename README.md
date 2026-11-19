# AudioPi releases

AudioPi turns a Raspberry Pi into a network music player: your own music
library, Spotify Connect, AirPlay, Bluetooth, SoundCloud, Bandcamp and
internet radio, controlled from a web app on phones and desktops.

This repository only holds AudioPi's releases.

## Install

1. Flash **Raspberry Pi OS Lite (64-bit, Trixie)** with Raspberry Pi Imager.
   In its settings, set a user and password, enable SSH and set the Wi-Fi.
2. Boot the Pi and log in (`ssh <user>@<hostname>.local`).
3. Run:

   ```sh
   curl -fsSL https://github.com/federicopasquarelli/audiopi-releases/releases/latest/download/install.sh | sudo bash
   ```

4. Open `http://<hostname>.local` on a phone or computer and follow the setup.

Run the same command again to update. Settings, library and plugins stay.

Supported boards: Raspberry Pi 5, 4, 3B+ and Zero 2 W.

## Uninstall

```sh
sudo /opt/audiopi/uninstall.sh           # keeps /data (settings, library, plugins' data)
sudo /opt/audiopi/uninstall.sh --purge   # deletes /data and the packages AudioPi added too
```

## What it changes

AudioPi's programs live in `/opt/audiopi` and its data in `/data`. It adds
the packages it needs from Raspberry Pi OS (PipeWire, WirePlumber, MPD and a
few network helpers), an `audiopi` system user, and its config files and
units in `/etc`. The uninstaller undoes all of it.

AudioPi is in development: expect rough edges.

## License

MIT OR Apache-2.0.
