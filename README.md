# Interactive-Smart-Mirror

A Raspberry Pi–based smart mirror with system monitoring and motion-activated display control. This project demonstrates full-stack JavaScript, hardware integration (PIR sensor), and custom MagicMirror module development.

## Features

### Custom System Health Module
- CPU temperature, usage, and system uptime
- Visual thresholds for CPU temp and usage
- Automatic updates every 5 seconds
- Built as a reusable MagicMirror module

### PIR Motion Sensor Integration
- Motion-activated wake/dim/off states
- Middle idle dimming state
- Power-aware and energy-efficient

### MagicMirror Enhancements
- Time, weather, and compliments modules fully configured
- Auto-launch on Raspberry Pi boot
- Fullscreen, kiosk-style display

## Screenshots

![System Health Module](docs/system-health-screenshot.png)
![PIR Motion Sensor Wiring](docs/pir-sensor-diagram.png)

## Installation

```bash
# Clone repo
git clone https://github.com/reltub/Interactive-Smart-Mirror.git
cd Interactive-Smart-Mirror/MagicMirror

# Install dependencies
npm install --engine-strict=false

# Start MagicMirror
npm run start
