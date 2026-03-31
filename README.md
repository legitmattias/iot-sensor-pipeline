# IoT Sensor Pipeline

A complete end-to-end IoT solution for environmental monitoring — from custom hardware sensors to real-time dashboards. Built with the TIG stack (Telegraf, InfluxDB, Grafana), MQTT, and MicroPython on a Raspberry Pi Pico 2 WH.

## Architecture Overview

```
Pico 2 WH (sensors) → WiFi → Mosquitto MQTT → Telegraf → InfluxDB → Grafana
```

- **Hardware**: Raspberry Pi Pico 2 WH with DHT-21 (temperature/humidity) and SGP30 (TVOC/eCO2) sensors
- **Data Pipeline**: Custom sensors → WiFi → Mosquitto MQTT → Telegraf → InfluxDB → Grafana
- **Infrastructure**: Multi-tier deployment across home and cloud networks using Docker and Tailscale VPN

## Project Repositories

| Repository | Description |
|---|---|
| **[iot-sensor-platform](https://github.com/legitmattias/iot-sensor-platform)** | MicroPython edge device — sensor management, WiFi, MQTT publishing, auto-calibration |
| **[iot-tig-infrastructure](https://github.com/legitmattias/iot-tig-infrastructure)** | TIG stack deployment — Docker, Telegraf, InfluxDB, Grafana, Mosquitto, nginx, Tailscale VPN |

## Key Features

### Hardware
- Real-time sensor data collection every 2 seconds
- SGP30 baseline calibration with flash persistence
- WiFi auto-reconnection and NTP time synchronization
- LED status indicators and comprehensive error recovery

### Infrastructure
- Multi-environment deployment (local home server + cloud)
- Secure cross-network connectivity via Tailscale VPN
- HTTPS-enforced public dashboard with nginx reverse proxy
- Automated configuration management with CI/CD
- Service-oriented architecture with separated MQTT broker

### Data Pipeline
- InfluxDB v2 for time-series optimization
- Telegraf data type conversion ensuring proper float formatting
- High-precision timestamp handling with timezone consistency

### Dashboard
- Real-time temperature, humidity, TVOC, and eCO2 monitoring
- Calculated metrics including dew point and absolute humidity
- Historical data exploration with time range selection

## Technical Highlights

- End-to-end IoT solution from hardware to visualization
- Production-ready infrastructure with automation and monitoring
- Security best practices with VPN connectivity and secret management
- Scalable architecture supporting multiple sensors and locations
- Professional DevOps practices with CI/CD and configuration templates

## Documentation

- [Hardware Setup](https://github.com/legitmattias/iot-sensor-platform/blob/main/deliverables/hardware-setup.md) — Pin configuration, software setup, data collection features
- [Technical Overview](https://github.com/legitmattias/iot-tig-infrastructure/blob/main/deliverables/technical-overview.md) — Architecture, data flow, time-series optimization
- [Setup Guide](https://github.com/legitmattias/iot-tig-infrastructure/blob/main/deliverables/setup-documentation.md) — Step-by-step local and remote deployment
- [Dashboard Exports](https://github.com/legitmattias/iot-tig-infrastructure/tree/main/deliverables/dashboards) — Grafana dashboard JSON and screenshots
