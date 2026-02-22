# 🌱 IoT Live Garden Monitor

Real-time plant monitoring system built for **SWE30011 – IoT Programming** at Swinburne University of Technology.

An Arduino collects temperature, humidity, and soil moisture data every second, transmits it over serial to a Raspberry Pi, which persists it to MariaDB and streams it to a Vue.js dashboard via WebSockets. The physical LED display can be toggled from the web UI or a hardware push button.

See `Individual_Assignment_Report.pdf` for full documentation including block diagrams, UML, and implementation details.

## Hardware

- **DHT11** temperature & humidity sensor (pin 8)
- **Soil moisture sensor** (pin A0)
- **Adafruit 14-segment alphanumeric display** with HT16K33 driver (I2C)
- **Push button** (pin 2, interrupt-driven)
- **Raspberry Pi** hosting the server and database

## Quick Start

```bash
# Backend (on Raspberry Pi)
cd backend && npm install && node app.js

# Frontend
cd frontend && npm install && npm run dev
```

The backend runs on port 3000, frontend on port 5173. Adjust the serial port path in `backend/app.js` if needed (default: `/dev/ttyACM0`).

## Tech Stack

Arduino (C++) · Express.js · Socket.IO · MariaDB · Vue 3 · Vite
