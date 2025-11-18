
# M1 – Bench Bring-Up (Compute + Display + Audio)

## 1. Hardware Baseline

- Raspberry Pi 5 (8 GB)
- PCM5122 DAC HAT (HiFiBerry DAC+ compatible)
- DSI display (model: Hoysond 7 inch DSI powered touchscreen) - subject to change
- Powered desktop speakers - testing purposes only

## Photos
![Hardware laid out for M1](img/m1/supplies_s0.jpg)
![DAC top view](img/m1/DACTop.jpg)
![Components mounted to display](img/m1/DACMount.jpg)

## 2. OS Flashing & First Boot

- Flashed Raspberry Pi OS Lite (64-bit) with Raspberry Pi Imager.
- Hostname set to `lx470-hu`, SSH enabled.
- First boot successful on DSI display.

## 3. Audio Bring-Up

- Enabled `dtoverlay=hifiberry-dacplus` in `/boot/firmware/config.txt`.
- DAC detected as `card 2: snd_rpi_hifiberry_dacplus`.
- `speaker-test` played clean tone on both channels.
- Hiss only at max speaker gain; inaudible at normal listening levels.


## Build Notes & Gotchas

- Display standoff mounts come with stickers covering the threads; these must be removed before installing standoffs.
- DSI connectors require the latch to be fully lifted before inserting the ribbon; partial insertion gives a black screen but no error.
- The display requires a +/- pin contact forcing the pi to be mounted; a workaround would be required to have the Pi mounted elsewhere.

