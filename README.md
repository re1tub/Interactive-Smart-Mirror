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

### Code snippets

## Custom System Health Module (node_helper.js):

getSystemData: function () {
  exec("cat /sys/class/thermal/thermal_zone0/temp", (error, tempOut) => {
    const cpuTemp = (tempOut / 1000).toFixed(1) + " °C";
    exec("top -bn1 | grep 'Cpu(s)'", (error, cpuOut) => {
      const idleMatch = cpuOut.match(/(\d+\.\d+)\s*id/);
      const idle = idleMatch ? parseFloat(idleMatch[1]) : 0;
      const cpuUsage = (100 - idle).toFixed(1) + " %";
      this.sendSocketNotification("SYSTEM_DATA", { cpuTemp, cpuUsage });
    });
  });
}

## Frontend Display (MMM-SystemHealth.js):

getDom: function () {
  const wrapper = document.createElement("div");
  wrapper.innerHTML = `
    <div class="${this.getCpuTempClass()}">CPU Temp: ${this.systemData.cpuTemp}</div>
    <div class="${this.getCpuUsageClass()}">CPU Usage: ${this.systemData.cpuUsage}</div>
    <div>Uptime: ${this.systemData.uptime}</div>
  `;
  return wrapper;
}


## Installation

```bash
# Clone repo
git clone https://github.com/reltub/Interactive-Smart-Mirror.git
cd Interactive-Smart-Mirror/MagicMirror

# Install dependencies
npm install --engine-strict=false

# Start MagicMirror
npm run start

