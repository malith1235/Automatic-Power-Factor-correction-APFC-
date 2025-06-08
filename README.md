# ⚡ Automatic Power Factor Correction (APFC) System

This project presents the design, simulation, and analysis of an **Automatic Power Factor Correction (APFC)** system specifically developed for industrial applications. The system addresses poor power factor caused by inductive loads (e.g., motors, compressors, HVACs) using a **hybrid capacitor bank** and a **microcontroller-based control algorithm**. All modeling and simulations were implemented using **MATLAB/Simulink**.

---

## 📌 Objectives

- ✅ Improve power factor to ≥ 0.95 across all operational stages.
- ✅ Automatically switch capacitors based on real-time load conditions.
- ✅ Reduce energy losses and utility penalties.
- ✅ Provide a cost-effective, scalable correction solution.
- ✅ Simulate real-world 24-hour industrial load behavior.

---

## 🔧 Tools & Technologies

- MATLAB/Simulink
- Simscape Electrical Toolbox
- Embedded MATLAB Function Blocks
- RL Load Modeling
- Hysteresis-based control logic

---

## 🏗️ System Overview

### ⚙️ Hybrid Capacitor Bank Configuration

| Type        | kVAR Rating |
|-------------|-------------|
| Fixed       | 25          |
| Switched 1  | 11          |
| Switched 2  | 7           |
| Switched 3  | 9           |
| **Total**   | **52**      |

### 🧠 Control Logic

- Uses hysteresis thresholds:  
  - **On Threshold:** 0.93  
  - **Off Threshold:** 0.97
- Prevents frequent switching and overcompensation.
- Implements step-wise capacitor activation/deactivation.

---

## 📊 Load Profile Summary

Six load stages representing 24 hours of operation:

| Stage | Time        | Real Power (kW) | Reactive Power (kVAR) | PF (Before) |
|-------|-------------|------------------|------------------------|-------------|
| 1     | 06:00–08:00 | 65               | 58                     | 0.746       |
| 2     | 08:00–11:00 | 85               | 64                     | 0.799       |
| 3     | 11:00–14:00 | 120              | 90                     | 0.800       |
| 4     | 14:00–17:00 | 110              | 88                     | 0.781       |
| 5     | 17:00–21:00 | 75               | 68                     | 0.741       |
| 6     | 21:00–06:00 | 45               | 40                     | 0.747       |

---

## 📈 Results Summary

### 📌 Power Factor Improvement

| Stage | PF (Before) | PF (Fixed Only) | PF (With APFC) |
|-------|-------------|------------------|----------------|
| 1     | 0.746       | 0.9217           | 0.9699         |
| 2     | 0.799       | 0.9308           | 0.9694         |
| 3     | 0.800       | 0.8969           | 0.9655         |
| 4     | 0.781       | 0.8878           | 0.9506         |
| 5     | 0.741       | 0.8947           | 0.9603         |
| 6     | 0.747       | 0.9760           | 0.9502         |

- ✅ **Target PF of 0.95+ achieved in all stages with APFC**
- ✅ Avoided overcompensation and reduced voltage instability
- ✅ Significantly reduced apparent power demand


## 🧪 Simulation Setup

- Each load stage simulated using RL elements
- Pulse generators switch between 6 load stages over 60s
- MATLAB Function Block implements hysteresis logic
- Capacitors modeled using Simscape blocks


