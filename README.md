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


## Footage

![Mirror Motion Sensor](IMG_9283.gif)
![PIR Motion Sensor Wiring](IMG_9283.gif)
![System Health](SystemHealth.gif)

## Hardware Requirements
- HDMI Monitor or mirror display
- PIR motion sensor
- Raspberry Pi 4(Or compatible)

## Tools & Technologies
- **Node.js** – Main runtime for MagicMirror and modules
- **MagicMirror² framework** – Core display framework
- **JavaScript** – Custom modules
- **Python (optional)** – For GPIO motion control
- **Linux commands** – To get system health
- **Raspberry Pi GPIO** – Motion detection hardware

## How it works
- The system health module gathers CPU temperature, CPU usage, and uptime using Linux commands.
- PIR sensor detects motion via GPIO pins. The mirror wakes on motion, dims after inactivity, and turns off after extended inactivity.
- Modules dynamically update and reflect system state visually with color-coded thresholds.

## Installation

```bash
# Clone repo
git clone https://github.com/reltub/Interactive-Smart-Mirror.git
cd Interactive-Smart-Mirror/MagicMirror

# Install dependencies
npm install --engine-strict=false

# Start MagicMirror
npm run start
