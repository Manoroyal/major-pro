# 🌱 Agri Vision – ESP32 Soil Monitoring System

## 📌 Overview

This repository contains the **ESP32 firmware** for the **Agri Vision** Smart Agriculture project.

The ESP32 communicates with a **7-in-1 RS485 Soil Sensor** using the Modbus RTU protocol, collects real-time soil parameters, and hosts a lightweight web server over Wi-Fi to make the sensor data available for the Agri Vision dashboard.

This module serves as the data acquisition layer of the complete Agri Vision ecosystem.


# 🚀 Features

* Real-time soil monitoring
* ESP32 Wi-Fi connectivity
* Built-in HTTP Web Server
* Modbus RTU communication (RS485)
* Live sensor data updates
* Easy integration with web dashboards
* Suitable for Smart Farming and IoT applications

# 📊 Parameters Measured

The system reads the following soil parameters:

* 🌧 Soil Moisture (%)
* 🌡 Temperature (°C)
* ⚡ Electrical Conductivity (EC)
* 🧪 Soil pH
* 🌿 Nitrogen (N)
* 🌿 Phosphorus (P)
* 🌿 Potassium (K)

---

# 🛠 Hardware Used

* ESP32 Development Board
* MAX485 RS485-TTL Converter
* 7-in-1 Soil Sensor (NPK + Moisture + Temperature + EC + pH)
* Wi-Fi Network
* USB Cable

---

# 🔌 Wiring

| ESP32  | MAX485  |
| ------ | ------- |
| GPIO16 | RO      |
| GPIO17 | DI      |
| GPIO4  | RE & DE |
| 5V     | VCC     |
| GND    | GND     |

The MAX485 module is connected to the 7-in-1 soil sensor through the RS485 interface.

---

# 📡 Communication

Protocol: **Modbus RTU**

Baud Rate: **4800**

Request Frame:

```
01 03 00 00 00 07 04 08
```

The ESP32 requests seven registers from the sensor and converts the received data into readable values.

---

# 🌐 Web Server

After connecting to Wi-Fi, the ESP32 starts an HTTP server.

Example:

```
http://192.168.x.x/
```

The webpage displays live values of:

* Soil Moisture
* Temperature
* EC
* pH
* Nitrogen
* Phosphorus
* Potassium

---

# 📁 Project Structure

```
AgriVision-ESP32/
│
├── AgriVision_ESP32.ino
├── README.md
└── images/
```

---

# ⚙ Configuration

Update your Wi-Fi credentials before uploading the code.

```cpp
const char* ssid = "Your_WiFi_Name";
const char* password = "Your_WiFi_Password";
```

Upload the sketch using the Arduino IDE or PlatformIO.

---

# ▶ How to Run

1. Connect the ESP32 to the MAX485 module.
2. Connect the RS485 soil sensor.
3. Update Wi-Fi credentials.
4. Upload the firmware.
5. Open Serial Monitor (115200 baud).
6. Wait for Wi-Fi connection.
7. Copy the displayed IP address.
8. Open the IP address in a browser.
9. View live soil sensor readings.

---

# 🌾 Agri Vision Ecosystem

This ESP32 module is one component of the complete Agri Vision system.

Workflow:

```
7-in-1 Soil Sensor
        │
        ▼
    MAX485 Module
        │
        ▼
      ESP32
        │
        ▼
   Wi-Fi Network
        │
        ▼
  Agri Vision Website
        │
        ▼
 Crop Recommendation Model
        │
        ▼
 Recommended Crops
```

---

# 💡 Future Improvements

* Cloud database integration
* Historical sensor data logging
* Real-time dashboard graphs
* Mobile application support
* Weather API integration
* Automatic irrigation control
* Firebase/MQTT connectivity
* Alert notifications

---

# 👨‍💻 Developed By

**Manohar KS**

**Project:** Agri Vision – Smart Crop Recommendation System

**Technologies Used**

* ESP32
* Arduino IDE
* Modbus RTU
* RS485
* Embedded C++
* Wi-Fi
* IoT
* Smart Agriculture

---

# 📜 License

This project is developed for educational and research purposes as part of the **Agri Vision Smart Agriculture Project**.
