# 1DV027 IoT Assignment Submission

**Student:** Mattias Ubbesen  
**Student ID:** mu222cu  
**Course:** 1DV027 - Web as Application Platform

## Project Summary

This project implements a complete IoT sensor data pipeline using the TIG stack (Telegraf, InfluxDB, Grafana) with custom hardware sensors. Instead of using the provided university MQTT broker, I built my own end-to-end IoT solution with physical sensors, automated deployment, and production-grade infrastructure.

### Architecture Overview
- **Hardware**: Raspberry Pi Pico 2 WH with DHT-21 (temperature/humidity) and SGP30 (TVOC/eCO2) sensors
- **Data Pipeline**: Custom sensors → WiFi → Mosquitto MQTT → Telegraf → InfluxDB → Grafana
- **Infrastructure**: Multi-tier deployment across home and university networks using Docker and Tailscale VPN

## Live Dashboard

**Public Dashboard Access:**  
[https://cscloud6-198.lnu.se/iot/d/bev7oshi0qtj4d/1dv027-iot-assignment-dashboard](https://cscloud6-198.lnu.se/iot/d/bev7oshi0qtj4d/1dv027-iot-assignment-dashboard)

## Project Repositories

### 1. Hardware Repository: iot-hardware
**URL:** [https://gitlab.lnu.se/mu222cu/iot-hardware](https://gitlab.lnu.se/mu222cu/iot-hardware)

Contains MicroPython code for Raspberry Pi Pico 2 WH with sensor integration. See repository README for detailed overview.

**Deliverables:**
- [`deliverables/hardware-setup.md`](https://gitlab.lnu.se/mu222cu/iot-hardware/-/blob/main/deliverables/hardware-setup.md) - Complete hardware setup documentation including pin configuration, software setup, and data collection features

### 2. Development Infrastructure Repository: iot-dev
**URL:** [https://gitlab.lnu.se/mu222cu/iot-dev](https://gitlab.lnu.se/mu222cu/iot-dev)

Contains TIG stack infrastructure with automated deployment and configuration management. See repository README for detailed overview.

**Deliverables:**
- [`deliverables/technical-overview.md`](https://gitlab.lnu.se/mu222cu/iot-dev/-/blob/main/deliverables/technical-overview.md) - Complete technical architecture documentation covering data flow, infrastructure distribution, and time-series optimization strategies
- [`deliverables/setup-documentation.md`](https://gitlab.lnu.se/mu222cu/iot-dev/-/blob/main/deliverables/setup-documentation.md) - Step-by-step setup instructions for local and remote deployment with automated scripts
- [`deliverables/dashboard-url.md`](https://gitlab.lnu.se/mu222cu/iot-dev/-/blob/main/deliverables/dashboard-url.md) - Dashboard access information and feature summary
- [`deliverables/dashboards/`](https://gitlab.lnu.se/mu222cu/iot-dev/-/tree/main/deliverables/dashboards) - Grafana dashboard export files and screenshots

## Key Features

### Hardware Implementation
- Real-time sensor data collection every 2 seconds
- WiFi connectivity with automatic reconnection
- NTP time synchronization for accurate timestamps
- SGP30 baseline calibration with flash persistence
- Comprehensive error handling and LED status indicators

### Infrastructure
- Multi-environment deployment (local home server + university cloud)
- Secure cross-network connectivity via Tailscale VPN
- HTTPS-enforced public dashboard with nginx reverse proxy
- Automated configuration management using templates and CI/CD
- Service-oriented architecture with separated MQTT broker

### Data Pipeline Optimizations
- InfluxDB v2 for time-series data optimization
- Telegraf data type conversion ensuring proper float formatting
- Organized data structure with measurements containing all sensor values
- High-precision timestamp handling with timezone consistency

### Dashboard Features
- Real-time temperature, humidity, TVOC, and eCO2 monitoring
- Calculated metrics including dew point and absolute humidity
- Historical data exploration with time range selection
- Public access for examiner review without authentication

## Technical Highlights

This implementation demonstrates:
- End-to-end IoT solution development from hardware to visualization
- Production-ready infrastructure with automation and monitoring
- Security best practices with VPN connectivity and secret management
- Scalable architecture supporting multiple sensors and locations
- Professional DevOps practices with CI/CD and configuration templates

The project goes beyond the basic assignment requirements by implementing a complete IoT ecosystem with custom hardware, automated deployment, and production-grade infrastructure suitable for real-world applications.