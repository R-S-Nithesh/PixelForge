<div align="center">

<img src="https://img.shields.io/badge/PixelForge-R.S.Nithesh-cyan?style=for-the-badge&logo=github" alt="R.S.Nithesh - PixelForge"/>
&nbsp;
<img src="https://img.shields.io/github/stars/R-S-Nithesh/PixelForge?style=for-the-badge&color=yellow" alt="Stars"/>
&nbsp;
<img src="https://img.shields.io/github/forks/R-S-Nithesh/PixelForge?style=for-the-badge&color=blue" alt="Forks"/>

<br/>
<br/>

# 🎨 PixelForge

### A fast, browser-based image-to-Arduino converter

**Transform PNG/JPG images into ready-to-use `.h` files for ESP32, STM32, Arduino, RP2040, and any RGB565 or OLED bitmap display — entirely in your browser, no server required.**

<br/>

[Features](#-features) · [Supported Libraries](#-supported-libraries) · [Getting Started](#-getting-started) · [Contributing](#-contributing)

</div>

---

## 📖 Overview

PixelForge eliminates the tedious manual work of converting images for embedded display projects. Drop in an image, configure your target format, and get a clean, PROGMEM-ready C header file in seconds. Everything runs offline in your browser — your images never leave your machine.

```
Convert → Preview → Export → Flash
```

---

## ✨ Features

### 🖼️ Image Conversion Engine

- Converts images to multiple embedded display formats:
  - **RGB565 / BGR565** — for TFT colour displays
  - **1-bit, 4-bit, 8-bit OLED bitmaps** — for monochrome and greyscale displays
- Auto-detects colour mode and handles byte-swapping automatically
- Multi-frame support for sprite sheets and animations
- Runs **100% offline** in your browser — no uploads, no servers

### 📐 Size & Scaling

- Set any custom width × height for your target display
- Built-in presets for common display resolutions:

  | Preset | Use Case |
  |--------|----------|
  | 240 × 240 | Round TFT, GC9A01 |
  | 128 × 128 | OLED, small TFT |
  | 96 × 64 | SSD1306-class OLED |
  | 64 × 48 | Tiny OLED modules |
  | 32 × 32 | Icons, sprites |
  | 16 × 16 | Small UI glyphs |

### 👁️ Live Preview System

Preview your output at every stage before exporting:

- **Original frame** — unmodified source image
- **Scaled output** — pixel-accurate resized result
- **TFT / OLED simulation** — rendered as it will appear on device
- **Animation preview** — multi-frame playback for sprite assets

### ⚙️ Output Format

Clean, production-ready C arrays with no extra fluff:

```c
// RGB565 example output
const uint16_t myImage[] PROGMEM = {
    0xF800, 0x07E0, 0x001F, ...
};

// OLED 1-bit example output
const uint8_t myBitmap[] PROGMEM = {
    0xFF, 0x81, 0xBD, ...
};
```

- `uint16_t` arrays for RGB565 colour data
- `uint8_t` arrays for OLED 1/4/8-bit bitmaps
- Auto-grouped arrays for animation frame sets

### 🌗 Interface

- GitHub-style **Light / Dark mode** toggle
- Developer-friendly layout with a large scrollable code panel
- Clean typography and fully responsive design

---

## 📦 Supported Libraries

| Display Library | Status | Notes |
|-----------------|--------|-------|
| **TFT_eSPI** | ✅ Full | RGB565 / BGR565 with optional byte-swap |
| **U8g2** | ✅ Full | 1-bit, 4-bit, 8-bit OLED modes |
| **Adafruit_GFX** | 🔜 Planned | Coming soon |

---

## 🚀 Getting Started

PixelForge is browser-based — no installation needed.

1. Open the tool in your browser
2. Upload a PNG or JPG image
3. Select your target format (RGB565, BGR565, or OLED bit depth)
4. Choose a preset or enter custom dimensions
5. Preview the output
6. Copy or download the generated `.h` file
7. Include it in your Arduino / ESP-IDF project and flash

---

## 🤝 Contributing

Contributions are welcome! Here are some ways you can help:

- 🐛 **Report bugs** — open an issue with steps to reproduce
- 🎨 **Improve colour accuracy** — better OLED/TFT dithering or quantisation
- 📐 **Add presets** — for common display modules not yet listed
- 📚 **Expand library support** — Adafruit_GFX and others are planned
- ⭐ **Star and share** — helps others discover the project

Please open an issue before submitting large pull requests so we can discuss the approach first.

---

## 📄 License

This project is open source. See the [LICENSE](LICENSE) file for details.

---

<div align="center">

Made with ❤️ by **R.S.Nithesh**

</div>
