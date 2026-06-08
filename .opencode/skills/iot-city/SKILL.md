---
name: iot-city
description: IoT City Platform — FastAPI backend, Zigbee mesh simulator, MQTT integration, and interactive map frontend for managing smart urban devices
---

## Project overview
IoT City is a smart city device management platform with a simulated Zigbee mesh network. It consists of a FastAPI backend (port 5062), a Python mesh simulator, MQTT integration via Mosquitto, and an interactive Canvas 2D map frontend.

## Key files
- `backend/main.py` — FastAPI server with REST endpoints, WebSocket, MQTT client
- `scripts/control_system.sh` — Start/stop/restart/status/lifecycle management
- `scripts/install_system.sh` — Full system installation (venv, deps, Mosquitto, icons)
- `simulator/mesh_simulator.py` — Zigbee network activity simulator
- `mqtt/gateway_simulator.py` — Raspberry Pi gateway simulator
- `frontend/index.html` — Interactive map UI

## Common commands
```bash
# Install
./scripts/install_system.sh

# Start services
./scripts/control_system.sh start

# Stop services
./scripts/control_system.sh stop

# Check status
./scripts/control_system.sh status

# View logs
./scripts/control_system.sh logs
./scripts/control_system.sh logs simulator

# Add device via CLI
./scripts/add_device.sh LAMP_001 120 300 router "Av. Mitre"
```

## Architecture
- **Backend**: FastAPI on port 5062, WebSocket at `/ws`, REST API at `/api/*`
- **MQTT**: Mosquitto on port 1883, topics under `iot/city/#`
- **Frontend**: Single-page canvas map served as static files
- **Data**: Device state persisted in `data/devices.json`
- **Metrics**: Auto-generated snapshots in `data/metrics/`

## Error troubleshooting
- **paho-mqtt not found**: Run `./scripts/install_system.sh` to create venv and install deps, or manually `pip install paho-mqtt`
- **Port 5062 in use**: `lsof -ti:5062 | xargs kill`
- **Backend fails**: Check `logs/backend.log` for traceback
