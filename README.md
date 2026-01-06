# Interactive Smart Mirror

A Raspberry Pi–based smart mirror that displays real-time system information, time, weather, and compliments. The mirror also integrates a PIR motion sensor to wake, dim, or turn off based on user presence, creating an interactive and energy-efficient display.

---

### Technologies & Languages

- **Node.js**  
- **MagicMirror² framework**  
- **JavaScript** (custom modules for system health and PIR control)  
- **Python** (optional, for GPIO integration)  
- **Linux system commands**

---

### Hardware Requirements

- Raspberry Pi 4 (or compatible)  
- PIR motion sensor  
- HDMI monitor or mirror display  

---

### How It Works

 **System Health Module**  
  - Gathers CPU temperature, CPU usage, and uptime using Linux commands.  
  - Dynamically updates with color-coded thresholds.  

 **PIR Motion Sensor**  
  - Detects motion via GPIO pins.  
  - Mirror wakes on motion, dims after short inactivity, and turns off after extended inactivity.  

 **MagicMirror Modules**  
  - Time, compliments, and weather modules display dynamic content.  
  - Modules update automatically based on system state and motion detection.

---

### Media

![Magic Mirror Overview](IMG_9283.gif)  ![System Health Module](SystemHealth.gif)  

---

### Optional Enhancements

- Motion-triggered dimming with an idle state

- Visual charts or color-coded thresholds for CPU usage and temperature

- Custom system monitoring widgets

### Notes

- Fully customizable and modular using the MagicMirror² framework.

- This prjoect showcases embedded systems, hardware integration, and JavaScript development skills.
