# ASUS Dolby EasyEffects Presets

A set of EasyEffects output presets recreating the four **Dolby Audio** modes found on ASUS laptops — ported and corrected for **EasyEffects 8.x**.

## Presets

| Preset | Description |
|--------|-------------|
| `ASUS-Dolby-Dynamic` | Balanced everyday profile with moderate compression — good all-rounder |
| `ASUS-Dolby-Movie` | Lighter compression tuned for dialogue clarity and cinematic range |
| `ASUS-Dolby-Music` | Higher compression ratio for consistent loudness across music |
| `ASUS-Dolby-Voice` | Gentle compression optimised for speech, podcasts and video calls |

All four share the same 23-band equalizer curve (high-pass at 100 Hz, bass warmth boost around 141 Hz, presence lift around 2.25 kHz, and a progressive high-frequency roll-off above 4.5 kHz). The compressor and limiter settings differ per preset to suit each use case.

## Signal Chain

```
Equalizer (23-band IIR, APO DR) → Compressor (Downward) → Limiter (Herm Thin)
```

## Requirements

- [EasyEffects](https://github.com/wwmm/easyeffects) **8.x**
- PipeWire audio backend

> If you are on EasyEffects 6.x–7.x (GTK), these presets will **not** load correctly due to format differences.

## Installation

1. Clone or download this repository:
   ```bash
   git clone https://github.com/YOUR_USERNAME/ASUS-Dolby-EasyEffects.git
   ```

2. Copy the preset files to your EasyEffects output presets folder:

   **Native install:**
   ```bash
   cp *.json ~/.local/share/easyeffects/output/
   ```

   **Flatpak install:**
   ```bash
   cp *.json ~/.var/app/com.github.wwmm.easyeffects/data/easyeffects/output/
   ```

3. Open EasyEffects, click the **Presets** menu, and load whichever profile you want.

## Background

ASUS ships Dolby Audio processing on many of its laptops for Windows, but there is no official Linux equivalent. These presets were reverse-engineered from the Dolby Audio profiles and converted to the EasyEffects JSON format so Linux users can get a similar tuned sound on their ASUS hardware.

The JSON structure follows the EasyEffects 8.x Qt format — bands are nested under `left` / `right` channel objects, each band includes a `width` field (computed from the Q value), and legacy GTK-era keys (`right-ch`, `split-channels`) have been removed.

## License

[MIT](LICENSE)
