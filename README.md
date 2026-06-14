
# Industrial Batch Counter System using ESP32

An automated industrial-grade item counting system engineered to minimize human counting errors and optimize production batch management. 

## 🛠️ Hardware Components
- **ESP32 Dev Module** (Main DAQ Node)
- **Industrial IR Photoelectric Sensor** (Connected to pin D4)
- **Push Button** (System Reset - Connected to pin D5)
- **Piezo Buzzer** (Audio Alarm - Connected to pin D18)
- **RGB LED Indicator** (Visual Alert - Connected to pins D19 & D21 with 220Ω resistors)

## ⚙️ System Logic (Industrial Batch Limit)
1. **Normal State (Scanning):** The RGB LED lights up **Green**. The system reads digital pulses from the IR sensor, increments the count, and logs live data to the Serial Monitor.
2. **Alert State (Batch Full):** Once the counter reaches the preset limit (`BATCH_LIMIT = 10`), the system triggers an alarm. The RGB LED turns **Red** and the **Buzzer sounds continuously** to alert operators to halt the packaging line.
3. **System Reset:** Pressing the Push Button resets the counter back to 0, silences the buzzer, and restores the system back to the Green scanning mode.

## ⚠️ LabVIEW Integration Note
The original system structure intended to pull live data streams via the **NI-VISA Resource Library** for HMI monitoring. However, live software integration faced a connection barrier due to an **NI-VISA Driver port corruption** caused by **Ground Loop & AC Ripple Noise** from an unisolated laptop charger during live tests. The hardware remains 100% operational via the native UART Serial Monitor (115200 baud).


https://github.com/user-attachments/assets/7769566f-6b12-4eda-87d4-de0be92c9360



https://github.com/user-attachments/assets/9e9c4f39-0e26-4697-9949-71e7556f41b1

