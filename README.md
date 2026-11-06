# roadamium-gps-bridge
Roadarium GPS Bridge is an experimental project that connects Roadarium's virtual driving simulation to Android devices. It converts live vehicle coordinates into real-world GPS locations and transfers them over Wi-Fi using a Tampermonkey userscript and an Android companion app.

# 🚗 Roadarium GPS Bridge

**Connect your Roadarium driving experience to real-world GPS coordinates!**

Roadarium GPS Bridge is an experimental project that transfers your vehicle's virtual GPS position from [Roadarium](https://roadarium.com/) to an Android device.

Drive through virtual cities in Roadarium and send your vehicle's location to your phone, allowing compatible location-based applications such as Google Maps to receive the simulated position.

## ✨ Features

- 🌍 **Live GPS Position:** Reads your vehicle's current position from Roadarium.
- 📍 **Coordinate Conversion:** Converts Roadarium map coordinates into geographic latitude and longitude.
- 📱 **Android Companion App:** Receives location updates from your computer.
- 🧩 **Tampermonkey Integration:** Uses a custom userscript to communicate with Roadarium.
- ⚙️ **Automatic City Detection:** Retrieves city origin information from Roadarium.
- 🎯 **Manual Calibration:** Supports manual coordinate calibration as a fallback.
- 🔄 **Adjustable Update Interval:** Configure how frequently location updates are sent.

## 🏗️ Architecture

The project consists of two main components:

### 1. Roadarium GPS Bridge Userscript

A Tampermonkey userscript that:
- Detects the Roadarium driving simulation.
- Reads live vehicle coordinates from `drivingSim.car`.
- Converts local map coordinates into GPS coordinates.
- Sends location data to the Android application over Wi-Fi.

### 2. Android Companion App

The Android application:
- Receives GPS coordinate updates.
- Processes incoming location information.
- Provides the bridge between Roadarium and Android location simulation.

## 📦 Project Components

| Component | Description |
|---|---|
| Userscript | Roadarium position extraction |
| Android APK | GPS bridge receiver |
| Coordinate Converter | Map-to-GPS conversion |
| Manual Calibration | Alternative coordinate mapping |

## 🚀 Installation

### Requirements

- A Windows PC
- Google Chrome or another supported browser
- Tampermonkey extension
- Roadarium account / access
- Android device
- Both devices connected to the same Wi-Fi network

### Step 1 — Install the Userscript

1. Install Tampermonkey in your browser.
2. Create a new userscript.
3. Import the Roadarium GPS Bridge userscript.
4. Open [Roadarium](https://roadarium.com/).
5. Start a driving session.

### Step 2 — Install the Android App

1. Download the latest APK from the GitHub Releases section.
2. Install it on your Android device.
3. Open the application.
4. Find the receiving URL or IP address.

### Step 3 — Connect Both Devices

1. Open the Roadarium GPS Bridge userscript panel.
2. Enter your Android phone's receiving URL.
3. Check the detected vehicle object.
4. Press **Start Sending**.
5. Monitor incoming GPS updates on your phone.

## 🛠️ Technical Details

The project uses Roadarium's vehicle data:

`window.drivingSim.car`

Relevant vehicle properties include:

- `x` — Local X coordinate
- `y` — Local Y coordinate
- `heading` — Vehicle direction
- `speedKmh` — Vehicle speed

The userscript converts the local coordinates into geographic coordinates using the city's origin information and a local projection calculation.

## ⚠️ Important Notes

- This is an experimental community project.
- GPS simulation requires appropriate Android configuration and permissions.
- Some applications may detect or reject mock locations.
- Google Maps behavior may vary depending on Android version and device configuration.
- The project is not affiliated with or endorsed by Roadarium or Google.

## 🔐 Privacy

Location data is transferred between your own computer and Android device over your local network.

No cloud GPS tracking service is required by the bridge itself.

## 📋 Project Status

<code>Experimental Development</code>

The userscript and Android APK have been built. Real-device testing and compatibility verification may vary.

## 👨‍💻 Developer

**Created by Sefa**

An experimental project combining browser scripting, Android development, GPS coordinate conversion and driving simulation.

---

⭐ If you find this project interesting, consider starring the repository!

**Roadarium GPS Bridge — From Virtual Roads to Real-World Coordinates.**
