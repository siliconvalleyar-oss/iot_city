---
name: iot-city
description: IoT City Platform — FastAPI backend, Zigbee mesh simulator, MQTT integration, interactive map frontend, and admin panel with customizable color palettes
---

## Project overview
IoT City is a smart city device management platform with a simulated Zigbee mesh network. It consists of a FastAPI backend (port 5062), a Python mesh simulator, MQTT integration via Mosquitto, an interactive Canvas 2D map frontend, and an admin panel for system configuration.

## Key files
- `backend/main.py` — FastAPI server with REST endpoints, WebSocket, MQTT client, admin API
- `scripts/control_system.sh` — Start/stop/restart/status/lifecycle management
- `scripts/install_system.sh` — Full system installation (venv, deps, Mosquitto, icons)
- `scripts/fix_iot_paho_error.sh` — Fixes paho-mqtt ModuleNotFoundError by recreating venv
- `simulator/mesh_simulator.py` — Zigbee network activity simulator
- `mqtt/gateway_simulator.py` — Raspberry Pi gateway simulator
- `frontend/index.html` — Interactive map UI with admin panel
- `analytics/metrics_engine.py` — Energy metrics engine for MRF24J40 nodes
- `energy/optimizer.py` — Energy optimization algorithms (duty cycling, TX power, aggregation)
- `data/devices.json` — Device state persistence
- `data/settings.json` — Admin settings (palette, MQTT host, etc.)

## Common commands
```bash
# Install
./scripts/install_system.sh

# Start/stop/restart
./scripts/control_system.sh {start|stop|restart|status|logs}

# Add device via CLI
./scripts/add_device.sh LAMP_001 120 300 router "Av. Mitre"
```

## Architecture
- **Backend**: FastAPI on port 5062, WebSocket at `/ws`, REST API at `/api/*`
- **Admin API**: `GET/PUT /api/admin/settings`, `GET /api/admin/palettes`, `POST /api/admin/reset`, `GET /api/admin/export`
- **Palettes**: 5 presets (cyberpunk, neon, nature, ocean, sunset) applied dynamically via CSS variables
- **MQTT**: Mosquitto on port 1883, topics under `iot/city/#`
- **Frontend**: Canvas 2D map with device drag, zoom, mesh overlay, coverage rings
- **Data**: Device state in `data/devices.json`, settings in `data/settings.json`

## Admin features
- **Color palette**: 5 themes applied in real-time via CSS custom properties
- **Settings**: MQTT host, simulation interval, default zoom
- **Data management**: Export full JSON, reset to demo city

## Error troubleshooting
- **paho-mqtt not found**: Run `sudo ./scripts/fix_iot_paho_error.sh` or `./scripts/install_system.sh`
- **Port 5062 in use**: `lsof -ti:5062 | xargs kill`
- **Backend fails**: Check `logs/backend.log` for traceback
- **pip externally-managed**: Must use venv (auto-created by control_system.sh if missing)
