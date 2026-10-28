# ESP32 Word Clock — Classic ESP32 edition

A frozen, **one-time-install** build of the [ESP32 Word Clock](https://github.com/bgarick/esp32-word-clock) firmware (v11) for boards with the **classic ESP32 chip** (ESP32 Dev Module / ESP32-WROOM). It has **no over-the-air updates**: flash it once and it runs as installed.

The C3 edition, which keeps OTA updates and gets new features, lives in [esp32-word-clock](https://github.com/bgarick/esp32-word-clock).

## Install (one time)

1. Use **desktop Chrome or Edge** (not a phone, not Safari).
2. Plug the clock into the computer with a **USB data cable** (charge-only cables don't work).
3. Open the installer page: **https://bgarick.github.io/esp32-word-clock-classic/**
4. Click **Install**, pick the clock's serial port, and wait for it to finish.
5. Do **not** choose "Erase device" unless you want to start fresh; a normal install keeps WiFi, timezone, and layout.

Prefer the command line? The release also has a single-file image, `esp32-word-clock-classic-full.bin`, to flash at address `0x0` with esptool.

## First-time setup

Hold the board's **BOOT** button while powering it on, join the `Word Clock Setup` WiFi network, and set your WiFi, timezone, layout (Vertical / Horizontal), and Special Days.

**LEDs stay dark?** The data wire is probably on a different pin. Open the setup portal as above and choose the right **LED Data Pin** (default GPIO 4).

## What's different from the C3 edition

| | Classic (this repo) | C3 ([main repo](https://github.com/bgarick/esp32-word-clock)) |
|---|---|---|
| Chip | ESP32 Dev Module | ESP32-C3 Super Mini |
| Updates | None (reflash by USB) | OTA from GitHub |
| LED pin | GPIO 4 default, selectable in portal | GPIO 4 |
| Button | GPIO 0 (BOOT) | GPIO 9 (BOOT) |

Hardware, wiring, panel layout, and 3D-printed parts are the same as the main project; see its README and the `stl/` folder here.

## Building from source

Arduino IDE or `arduino-cli`, board **ESP32 Dev Module**, default partition scheme. Libraries: Adafruit NeoPixel, WiFiManager. Sketch: `esp32-word-clock.ino`. CI (`.github/workflows/build.yml`) builds and publishes on every push to `main`.

## License

CC BY-NC-SA 4.0. See [LICENSE](LICENSE).
