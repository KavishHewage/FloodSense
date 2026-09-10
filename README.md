# FloodSense
FloodSense

A low-cost, solar-powered flood monitoring system designed to replace painted water-level rulers on Sri Lankan bridges and riversides. FloodSense uses a modular 3-unit stacking enclosure with discrete water-sensing chambers to detect rising water levels, trigger local LED warnings, and transmit alerts to authorities via LoRa radio — no internet infrastructure required.

How it works

Each node is a vertical stack of three 3D-printed PETG units, each housing five water-inlet chambers. As floodwater rises, it fills successive chambers and activates resistive probes inside. An ESP32 microcontroller reads the chamber states, drives LED indicators on the side wall (one LED per two chambers on the base and middle units, one per chamber on the top unit), and fires a LoRa packet over 433 MHz whenever water crosses a unit boundary. A flexible solar panel recessed into the gabled roof keeps a LiPo battery charged indefinitely. Units snap together with cantilever clips and seal with EPDM O-ring cord for weatherproofing.

A LoRa gateway node — installed at a high point such as a rooftop or bridge parapet — receives alerts from multiple sensor nodes across a coverage area and forwards water-level data to a monitoring dashboard operated by flood response authorities.

Repository contents
/dashboard — Interactive live operations dashboard (HTML/JS) simulating a 12-node Colombo canal network with real-time water level trends and alert feed
/fusion360 — Fusion 360 Python API script (v2.1) that auto-generates all three snap-fit units with correct geometry, chamber pockets, LED holes, PCB trays, snap-fits, O-ring grooves, solar recess, gabled roof, and SMA antenna boss
/firmware — ESP32 Arduino firmware for chamber polling, LED logic, LoRa packet formatting, and deep-sleep power management (in progress)
/hardware — PCB schematics and BOM for the sensor breakout and main ESP32+LoRa board (in progress)
Built with

ESP32 · SX1278 LoRa (433 MHz) · PETG 3D print · Fusion 360 Python API · CN3791 MPPT · TP4056 · Arduino IDE

Status

Active development. Dashboard and 3D model complete. Firmware and PCB design in progress.
