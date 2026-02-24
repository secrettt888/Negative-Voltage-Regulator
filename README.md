# Negative Voltage Regulator

A fully discrete negative voltage regulator built entirely from transistors (no ICs). This repository contains the complete design files, including the schematic, SPICE simulation, and PCB layout.

> ![NVR](https://github.com/user-attachments/assets/7ec499e1-6e0d-4d45-a963-73bf24c913a9)


## ⚡ Specifications
* **Input Voltage ($V_{in}$) ** :  -40V to -37V 
* **Output Voltage ($V_{out}$) ** : -34V to -32V
* **Max Current:** : 44mA
* **Output resistance** : <=4Ω

## 📂 Repository Contents
* **/Schematic:** KiCad/Eagle source files and PDF schematics.
* **/Simulation:** LTspice/Ngspice `.asc` files and waveform plots.
* **/PCB:** Board layout files, 3D models, and production-ready Gerbers.
* **/Docs:** Component datasheets.

## 🛠️ Theory of Operation
The circuit relies entirely on discrete components:
1. **Reference:** [e.g., 5.1V Zener diode].
2. **Error Amp:** [e.g., PNP differential pair] to compare output against the reference.
3. **Pass Element:** [e.g., TIP32 power transistor] to regulate current to the load.

## 🚀 Quick Start
1. **Simulate:** Open `/Simulation/regulator.asc` in your SPICE tool to view the transient response and line regulation.
2. **Fabricate:** Use the files in `/PCB/Gerbers` to order boards.
3. **Build:** Populate components according to the BOM (found in `/Docs/BOM.csv`). 
*Note: Ensure the pass transistor is properly heatsinked if drawing >200mA.*

## 📄 License
Licensed under the [MIT / CERN-OHL] License.
