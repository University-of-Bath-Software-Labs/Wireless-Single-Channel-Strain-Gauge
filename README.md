# Wireless Single-Channel Strain Gauge (LabVIEW)

A LabVIEW data acquisition program that **reads wireless strain gauge data from an Arduino (via serial/COM port)**, displays it live on a graph, and optionally records the data to a **CSV file** for later analysis.

---

## What it does

- Connects to an Arduino over a selected **COM port** using VISA serial communication.
- Reads incoming data formatted as: **`Time, Strain`**.
- Displays the latest **time** and **strain** as live indicators.
- Plots **Strain vs Time** on an **XY graph** (so the x‑axis is the time sent by the Arduino, not PC elapsed time).
- Records data to a **CSV file** when recording is enabled.
- Uses an improved, user-friendly workflow where acquisition starts via a **Start** action (not immediately on run), and recording can be toggled through an event-driven control.

---

## Requirements

- **LabVIEW** (this project was developed in LabVIEW as part of Electronics & Software Labs support work).
- **NI-VISA** (for serial/COM port communication).
- An Arduino-based wireless strain gauge setup that outputs serial data as **`Time, Strain`**.
- A Windows PC where the Arduino receiver appears as a **COM port**.

> Note: The baud rate must match the Arduino configuration provided with the hardware setup.

---

## How to run

1. Open the project in LabVIEW (open the `.lvproj` file).
2. Open the main VI and click the **Run** arrow.
3. Select the correct **VISA resource / COM port** on the front panel.
4. Press Confirm
5. Press Start

---

## How to use (typical workflow)

### 1) Select the COM port
- Choose the correct **VISA Resource Name** (COM port) for the Arduino device.

### 2) Confirm the COM port
- Press **Confirm** once you have selected the correct COM port.

### 3) Start acquisition
- Press **Start** to begin reading data and plotting it live.

### 4) View live data
- The program displays the latest **Time** and **Strain** values and updates the **XY graph** continuously.

### 5) Record to file (optional)
The program can save results to a CSV file for later analysis.

- Enable recording using the **Record** control (checkbox/event-driven toggle).
- A **Recording** indicator light shows when data is actively being saved.

### 6) Stop
- Press **Stop** to end acquisition and close the program cleanly.

---

## Output files

- Output format: **CSV** (`.csv`).
- The program creates a results file named using the current date/time, e.g.:  
  `Strain Readings 25Mar2025 09h30m50s.csv`
- Data headings are written to the file (e.g., `Time, Strain`) before data rows are appended.
- Files are saved into a **Results** folder located alongside the VI/project (if present).

---

## Troubleshooting

**No data / flat line graph**
- Confirm the correct **COM port** is selected.
- Confirm the Arduino is outputting data in the expected `Time, Strain` format.

**Garbage values or conversion errors**
- This usually indicates the incoming string format doesn’t match what the program expects (comma-separated time + strain).

**Recording not saving**
- Make sure recording is enabled (Record control) and the recording indicator shows active logging.
- Check the output folder exists (e.g., a `Results` folder next to the VI).

---

## Support / contact

For support or to adapt this program for a different wireless sensor setup, contact the  
**Electronics & Software Labs** team.
