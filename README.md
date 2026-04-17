# ZHA - Tuya Smart Scene Button (Knob) for Media Player (Music Assistant)

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/acdye/zha-knob-media-control/blob/main/tuya_media_knob.yaml)

Control a Media Player (like Music Assistant) with a generic Tuya Smart Scene Button (Knob) via ZHA. This blueprint is designed to bypass strict manufacturer/model filters, making it compatible with most Tuya scene buttons that feature a rotating dial.

## ⚠️ IMPORTANT: THIS DEVICE HAS TWO MODES ⚠️
Switch between modes by rapidly tapping the button **3 times**.

### 1. Normal Mode (Built-in Media Control)
- **Single Press:** Play/Pause the selected media player.
- **Rotate Left/Right:** Smoothly adjust the volume based on your chosen step percentage.

*Note: If the device does nothing when you first set it up, tap it 3 times to wake up Normal Mode!*

### 2. Remote Mode (Custom Actions)
In this mode, default volume and play/pause logic is ignored. Instead, it executes the custom actions you assign in the UI for:
- Short Press
- Double Press
- Long Press
- Rotate Right
- Rotate Left

---

## Troubleshooting & FAQ

**The button isn't doing anything when I turn it or click it.**
This specific Tuya Smart Scene Button (Knob) has two distinct operating modes: *Normal Mode* and *Remote Mode*. This blueprint's built-in play/pause and smooth volume math rely on the device being in Normal Mode. To toggle between modes, rapidly click the physical button **3 times**. Wait a second, and try testing the volume or play/pause again. 

**How do I use the custom actions at the bottom of the automation?**
If you want to map your own custom actions to the device (like skipping tracks, activating scenes, or calling specific scripts), you need to put it into *Remote Mode*. Rapidly click the button 3 times to switch modes. Once in Remote Mode, the built-in volume logic is ignored, and the device will only execute the custom actions you assign in the Home Assistant UI.

**The volume changes are too drastic or too subtle.**
Different media players scale their volume differently. If a single click of the dial jumps the volume too high, edit your automation and lower the **Volume Step** slider. The default is set to 5%, but you can adjust it anywhere from 1% to 100% to find the sweet spot for your specific speakers.
