# 🌦️ EDGE WEATHER — Smart Environmental Monitoring Station

An ESP32-S3-based IoT weather and environmental monitoring station designed to monitor indoor environmental conditions and display real-time measurements locally while synchronizing data with Firebase Realtime Database.

## 🚀 Overview

EDGE WEATHER uses an ESP32-S3-WROOM-1U as the main controller and combines multiple sensors with a 0.96" SSD1306 OLED display.

The system monitors:

- 🌡️ Temperature
- 💧 Humidity
- 🌡️ Atmospheric Pressure
- 💡 Ambient Light Level
- 🌧️ Rain Detection
- 🚶 Motion / Presence

Sensor information is processed locally on the ESP32-S3, displayed through the OLED interface, and synchronized with Firebase when Wi-Fi connectivity is available.

## ✨ Key Features

- ESP32-S3 based environmental monitoring
- Real-time temperature and humidity monitoring
- Atmospheric pressure measurement
- Ambient light monitoring using an LDR
- Rain detection
- PIR-based motion detection
- Capacitive touch-based OLED navigation
- 0.96" 128×64 SSD1306 OLED display
- Local-first system operation
- Wi-Fi connectivity
- Firebase Realtime Database synchronization
- Automatic network reconnection
- Non-blocking firmware architecture
- Environmental alert system
- OLED standby and motion-based wake-up
- Delta-based Firebase synchronization
- Periodic full synchronization for data consistency

## 🧩 Hardware Components

| Component | Purpose |
|---|---|
| ESP32-S3-WROOM-1U | Main microcontroller |
| SSD1306 0.96" OLED | Local data display |
| HTU21D | Temperature & humidity sensing |
| BMP180 | Atmospheric pressure sensing |
| LDR | Ambient light monitoring |
| MH-RD Rain Sensor | Rain detection |
| TTP223 | Capacitive touch input |
| HC-SR501 PIR | Motion detection |

## 🔌 Pin Configuration

| Function | ESP32-S3 GPIO |
|---|---:|
| I2C SDA | GPIO 10 |
| I2C SCL | GPIO 11 |
| LDR | GPIO 13 |
| Rain Sensor | GPIO 48 |
| Touch Sensor | GPIO 45 |
| PIR Sensor | GPIO 9 |

## 🖥️ OLED Interface

The OLED provides multiple monitoring pages:

1. Temperature
2. Humidity
3. Barometric Pressure
4. Light Level
5. Precipitation

The display uses a centered layout with page indicators and automatically enters standby after a period of inactivity.

Touch input or detected motion wakes the display.

## ⚡ Alert System

The system provides priority-based alerts for environmental conditions such as:

- Rain detection
- High temperature
- High humidity
- Low or high atmospheric pressure
- Low light conditions

Alerts are displayed directly on the OLED.

## ☁️ Firebase Integration

The station synchronizes environmental data with Firebase Realtime Database.

Example database structure:

```text
/weather_station
├── temperature
├── humidity
├── pressure
├── light_status
├── is_raining
└── online
