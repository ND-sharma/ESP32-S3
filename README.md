# 🏠 ESP32-S3 Smart Home Touch Panel (4.3" Waveshare + LVGL)

A modern, touch-enabled **home automation control panel** built using **ESP32-S3**, **LVGL**, and a **4.3" Waveshare RGB display**.

Designed for real-world usage with smooth UI, MQTT integration, and a clean, extensible architecture.

---

## ✨ Features

* 📱 **800×480 Touch UI (LVGL v8)**
* 🧭 **Launcher-based Navigation (Tile UI)**
* ❄️ AC Control (On/Off, Temp, Mode, Fan)
* 🌪️ Fan Control (Speed levels)
* 💡 Light Control (Multiple switches + master)
* 🪟 Curtain Control (Slider + actions)
* 🔆 **Display Backlight Control (PWM)**
* 📡 MQTT Integration (Home Assistant compatible)
* 📶 WiFi + Weather + Clock display
* ⚡ Optimized for ESP32-S3 performance

---

## 🧱 Hardware

* 🧠 ESP32-S3
* 🖥️ Waveshare ESP32-S3 4.3" LCD Touch
* Touch Controller (GT911 - I2C)
* Backlight via PWM (LEDC)

---

## 🛠️ Tech Stack

* **Framework**: Arduino (ESP32 Core)
* **UI Library**: LVGL v8
* **Display Driver**: esp_lcd (RGB panel)
* **Communication**: MQTT
* **Architecture**: Modular UI + Screen API

---

## 📁 Project Structure

```bash
bedroom_panel/
├── bedroom_panel.ino          # Entry point
├── bedroom_screen.cpp        # UI API layer (DO NOT REMOVE)
├── bedroom_screen.h
├── mqtt_handler.cpp          # MQTT logic
├── lvgl_v8_port.cpp          # LVGL + display driver (unchanged)
├── ha_theme.cpp              # Styles
│
├── ui/                       # Modular UI components
│   ├── ui_launcher.cpp
│   ├── ui_ac.cpp
│   ├── ui_fan.cpp
│   ├── ui_light.cpp
│   ├── ui_curtain.cpp
│   ├── ui_backlight.cpp
```

---

## 🧠 Architecture Overview

```
MQTT / Logic Layer
        ↓
bedroom_screen.cpp  (API / Bridge Layer)
        ↓
UI Modules (/ui/*.cpp)
        ↓
LVGL Rendering Engine
```

> ⚠️ `bedroom_screen.cpp` acts as a **contract layer** — do not remove required functions used by MQTT.

---

## 🚀 Getting Started

### 1. Install Dependencies

* ESP32 Arduino Core
* LVGL v8
* Required Waveshare panel libraries

---

### 2. Configure Board

* Board: **ESP32-S3**
* PSRAM: Enabled
* Flash: 8MB or higher recommended

---

### 3. Upload

```bash
Arduino IDE → Select Port → Upload
```

---

## ⚙️ Configuration

Update the following as needed:

### 📡 WiFi & MQTT

Edit in:

```bash
mqtt_handler.cpp
```

---

### 🏠 Home Assistant Topics

Update topic mappings in:

```bash
HA/casa_blanca_bedroom_panel_package.yaml
```

---

## 🎨 UI Design

* Dark theme optimized for wall panels
* Large touch targets (finger-friendly)
* Card-based layout
* Minimal redraw for performance

---

## 🔆 Backlight Control

* PWM-based brightness control via LEDC
* Adjustable from UI
* Can be extended with:

  * Auto-dimming (time-based)
  * Ambient light sensor

---

## ⚡ Performance Notes

* Uses **double buffering**
* Optimized object count
* Minimal style duplication
* Avoids full screen redraws

---

## 🧪 Known Issues / TODO

* [ ] Replace placeholder UI with full card views
* [ ] Add smooth animations (LVGL anim)
* [ ] Implement stack navigation (no screen wipe)
* [ ] MQTT → UI async updates (lv_async_call)
* [ ] Add scene presets (Sleep / Away / Relax)

---

## 🤝 Contributing

Pull requests are welcome!
For major changes, please open an issue first to discuss.

---

## 📸 Preview (Coming Soon)

*Add screenshots or demo video here*

---

## 🧑‍💻 Author

**Navendu Sharma (ND)**
DevOps Architect | System Design Enthusiast

---

## ⭐ If you like this project

Give it a star ⭐ — helps a lot!

---

## 📜 License

MIT License (or your choice)
