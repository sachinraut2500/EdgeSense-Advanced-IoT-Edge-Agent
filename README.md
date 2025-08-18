# EdgeSense — Advanced IoT Edge Agent

**EdgeSense** is a production-minded IoT edge agent implemented in Python. It reads from multiple sensors (with simulated fallback), publishes telemetry to an MQTT broker using TLS, stores data locally in SQLite if offline, exposes a small local HTTP API for control & health checks, and implements robust reconnect/backoff and OTA-update hooks.

---

## Highlights / Features

- Modular sensor abstraction (real + simulated)
- Publishes JSON telemetry to MQTT (supports TLS + username/password)
- Local buffering in SQLite for offline resilience & delivery-once logic
- Local HTTP control API for status, last telemetry, and forced sync
- Graceful shutdown, structured logging, backoff/reconnect strategy
- Configurable via `config.json` (no hardcoded credentials)
- OTA update stub + versioning support
- Unit-test friendly structure

---

## Repo layout (suggested)


----

## Hardware (optional)

- Raspberry Pi (any model with I2C/serial)
- DHT22 or BME280 (temperature/humidity/pressure)
- PMS5003 (PM2.5 particle sensor)
- PIR motion sensor (GPIO)
- USB or Pi Camera (optional for future expansion)

> The code supports simulated sensors if hardware is not present.

---

## Software / Dependencies

**Required** (for the base code in simulation mode):
- Python 3.9+

**Optional / recommended** (install with `pip`):
- `paho-mqtt` — MQTT client
- `smbus2` — I²C for BME280
- `RPi.GPIO` or `gpiozero` — GPIO (Raspberry Pi)
- `requests` — for OTA stub (optional)

Example `requirements.txt`:


