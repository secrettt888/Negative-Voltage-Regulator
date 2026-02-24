# Discrete Negative Voltage Regulator

A fully discrete negative voltage regulator built entirely from transistors and passive components (no integrated circuits). This repository contains the complete design pipeline, including the OrCAD schematic, PSpice simulation, and PCB layout.

![NVR](https://github.com/user-attachments/assets/f2c9e9a7-7a85-4173-bb19-38afb6e4c80a)

## ⚡ Specifications
* **Input Voltage (Vin):** -40V to -37V
* **Output Voltage (Vout):** -34V to -32V (Adjustable)
* **Max Output Current:** 44mA
* **Output Resistance:** <= 4Ω
* **Stability Factor:** > 60

## 📂 Repository Contents
* **/Hardware/OrCAD_Source:** OrCAD source files and PDF schematics.
* **/Hardware/Fabrication:** Board layout files, 3D models, and production-ready Gerbers.
* **/Simulation:** PSpice `.sim` files and waveform plots.
* **/Docs:** Component datasheets and the Bill of Materials (BOM).

## 🛠️ Theory of Operation

<img width="1130" height="618" alt="image" src="https://github.com/user-attachments/assets/c737fb3e-1f31-4a8a-a676-5c2eec945175" />


The circuit relies entirely on discrete components to achieve stable voltage regulation and fault protection:

1. **Voltage Reference:** A 10V Zener diode establishes the baseline stable voltage.
2. **Current Source:** A current mirror, taking the Zener diode as its reference, provides stable biasing.
3. **Error Amplifier:** A PNP differential pair compares the 10V reference to the scaled output voltage provided by the feedback network.
4. **Negative Feedback Network:** Formed by a resistor divider and a trimmer potentiometer, allowing the user to precisely vary and set the output voltage.
5. **Pass Element:** A Darlington transistor configuration is used to efficiently regulate the current delivered to the load.
6. **Overvoltage Protection (OVP):** Implemented using a combination of a Darlington transistor and multiple diodes to clamp unsafe voltage spikes.
7. **Overcurrent Protection (OCP):** Features a foldback current limiting circuit to safely reduce power dissipation in the pass element during a short circuit or heavy overload.

## 📈 Simulation Results
**OCP:** <img width="1257" height="502" alt="Overcurrent_protection" src="https://github.com/user-attachments/assets/098c4f2b-6f0d-4ebb-9fb4-b029d3d0fcdc" />
**OVP:** <img width="1862" height="680" alt="Overvoltage_protection" src="https://github.com/user-attachments/assets/fd935441-2e70-49f4-a5fe-04d0b27565a2" />

## 🚀 Quick Start
1. **Simulate:** Open the files in `/Hardware/OrCAD_Source` in PSpice to view the transient response, line/load regulation, and foldback protection behavior. 
2. **Fabricate:** Use the Gerber files located in `/Hardware/Fabrication` to order your printed circuit boards.
3. **Build:** Populate the components according to the `BOM.pdf` found in the `/Docs` folder.

