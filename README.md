# MPPT Solar Charge Controller (24V to 12V Synchronous Buck Converter)

This repository contains the design, simulation, and PCB layout files for a Maximum Power Point Tracking (MPPT) Solar Charge Controller. The system is designed around a 100 kHz synchronous buck converter to efficiently step down a 24V solar input to a stable 12V DC output for battery charging.

## 🚀 Key Features
* **High-Frequency Switching:** Operates at 100 kHz for reduced inductor sizing and improved transient response.
* **Synchronous Rectification:** Utilizes an IR2112 gate driver and dual IRFZ44N N-Channel MOSFETs to minimize conduction losses compared to standard diode rectification.
* **Optimized PCB Layout:** Custom physical board designed in KiCad, featuring minimized switch-node loop areas to prevent parasitic ringing and 2.5mm high-current copper pours for thermal management.
* **Algorithm Modeling:** Perturb & Observe (P&O) MPPT control algorithm modeled and validated using MATLAB/Simulink.

## 🛠️ Software & Tools Used
* **Proteus:** Schematic capture and transient circuit simulation (verifying bootstrap operation, gate timing, and 12V output stability).
* **KiCad:** Professional PCB layout, footprint assignment, and 3D board rendering.
* **MATLAB / Simulink:** Mathematical modeling of the P&O algorithm for optimal solar power extraction.

## 🧰 Core Hardware Components
* **Gate Driver:** IR2112 (High and Low Side Driver)
* **Switching Devices:** IRFZ44N N-Channel Power MOSFETs
* **Passive Components:** 47uH Power Inductor, 100uF Input/Output smoothing capacitors, ultra-fast bootstrap diode (1N4148).
* **Connectors:** High-current screw terminals for 24V Input and 12V Output.

## 📁 Repository Structure
* `/Proteus_Simulation/`: Contains the `.pdsprj` file with the working schematic, digital oscilloscope setups, and analogue graph timing analyses.
* `/KiCad_PCB/`: Contains the `.kicad_sch` (schematic) and `.kicad_pcb` (board layout) files, including custom trace width configurations.
* `/MATLAB_Simulink/`: Contains the `.slx` model for the P&O control logic.

## ⚙️ How to View the Project
1. **Proteus Simulation:** Open the project file in Proteus 8+. Run the Analogue Graph simulation (set stop time to `50u`) to view the 100 kHz PWM input, 24V switch node chopping, and 12V stable DC output.
2. **KiCad PCB:** Open the project in KiCad 7+. Press `Alt+3` in the PCB Editor to view the 3D render of the board and inspect the copper pours and power routing.
