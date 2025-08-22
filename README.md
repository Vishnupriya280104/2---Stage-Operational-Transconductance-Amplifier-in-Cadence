# 2-Stage OTA (Operational Transconductance Amplifier) in Cadence

## Overview

This repository documents the end-to-end design, simulation, and analysis of a **two-stage CMOS Operational Transconductance Amplifier (OTA)** realized in Cadence Virtuoso. The focus is on robust compensation, biasing, and performance verification across DC, AC, and transient domains—all supported by real tool screenshots and methodical simulation setup.

---

## Table of Contents
- [Project Specs](#project-specs)
- [Schematic](#schematic)
- [Simulation Strategy](#simulation-strategy)
- [Results](#results)
- [Key Equations](#key-equations)
- [About](#about)

---

## Project Specs

| Parameter          | Value                 |
|--------------------|-----------------------|
| Technology         | gpdk90nm              |
| VDD                | 3.0 V                 |
| Load Capacitance   | 2 pF                  |
| I_bias             | 20u A                 |
| Output Swing       | 0.5 – (VDD–0.5) V     |

---

## Schematic

**Complete schematic of the designed two-stage OTA:**

<img width="1242" height="566" alt="sch_vpulse" src="https://github.com/user-attachments/assets/831021d6-1bfa-4765-9acd-f8f615c94508" />


---

## Simulation Strategy

**1. DC Analysis:**  
- Sweeps input voltage, checks output transfer curve and bias points.

**2. AC Analysis:**  
- Extracts open-loop gain, unity-gain bandwidth, and ensures proper dominant-pole rolloff.

**3. AC Gain & Phase vs. Frequency:**  
- Verifies stability and phase margin with Bode plot.

**4. Transient Analysis:**  
- Applies a pulse input and observes dynamic output—verifies settling, overshoot, and slew rate.

---

## Results

### 1. **DC Response**
Plots V(out) vs. input DC voltage—demonstrates input-output linearity and bias window.

<img width="1005" height="785" alt="dc_vpulse" src="https://github.com/user-attachments/assets/20a5d992-30d6-44ba-8c73-51ee8bcf9755" />



- Output follows input; shows expected linearity and range.

---

### 2. **AC Magnitude Response**
Shows frequency response: high open-loop gain, dominant pole, and roll-off.

<img width="997" height="781" alt="ac_vpulse" src="https://github.com/user-attachments/assets/8dda6cd1-9106-4379-97b3-b7e25e0e404b" />


- High gain at low frequency, single dominant pole as expected.

---

### 3. **AC Gain and Phase**
Bode plot: open-loop gain (dB) and phase vs. frequency to show phase margin and stability.

<img width="1006" height="751" alt="gain_phase_vpulse" src="https://github.com/user-attachments/assets/4ea672f1-3e73-4737-979a-15fa0d5aa604" />


- Flat phase and gain at low freq, stable roll-off and wide phase margin.

---

### 4. **Transient Response**
Pulse test: output response to square wave input, reveals amplifier’s dynamic speed and settling.

<img width="1013" height="773" alt="trans_vpulse" src="https://github.com/user-attachments/assets/be6da414-851b-4a44-b296-b1d089aae780" />


- Output steps are fast and stable, indicating good slew and settling.

---

## Key Equations

$$
A_v = g_{m1} \cdot r_{o,stage1} \cdot g_{m2} \cdot r_{o,stage2}
$$

$$
GBW = \frac{g_{m1}}{2 \pi C_c}
$$

$$
SR = \frac{I_{tail}}{C_c}
$$

Phase Margin is extracted from the Bode plot at the unity-gain point.

---


## About

**Author:** Vishnupriya V    
**Contact:** priya.venkatesh.2804@gmail.com  
**Date:** August 2025

---
