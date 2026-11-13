# Position-control-of-a-DC-Motor-
Cascaded control design for a DC Motor Drive in PLECS. Features an inner current loop (PI), intermediate speed loop (Symmetrical Optimum), and outer position loop (P). Includes reference pre-filter optimization and parametric robustness analysis under inertial variations and load torque disturbances.

# Electric-Drives-DC-Motor-Control / Controllo Azionamenti Elettrici

<p align="center">
  <b>[ <a href="#english">English</a> ] | [ <a href="#italiano">Italiano</a> ]</b>
</p>

---

<a name="english"></a>
## 🇬🇧 English Version

# Cascaded Position and Speed Control of a DC Motor Drive

Official repository for the advanced project in **Advanced Electric Drives and Power Converter Systems** (Master's Degree in Digital Automation Engineering).

* **Candidate:** Antonio Iodice (Student ID: 213260)
* **Academic Year:** 2025/2026

### Project Overview
This project details the comprehensive design, dynamic simulation, and performance analysis of a cascaded control system for a DC Motor Drive, developed within the **PLECS** software environment. The adopted methodology follows a bottom-up cascade architecture, starting with the inner current control loop, followed by the intermediate mechanical speed loop, and concluding with the outermost angular position loop.

### Control Architecture & Methodology
1. **Inner Current Loop (PI Controller):** Regulates armature current and electromagnetic torque. Tuned via trial-and-error to achieve a fast rise time ($\approx 1\text{ ms}$) and a closed-loop bandwidth of $50\text{ rad/s}$ for deep frequency decoupling.
2. **Speed Loop (Symmetrical Optimum):** Regulates mechanical speed using an analytically derived PI controller based on the Symmetrical Optimum criterion, targeting an optimal phase margin ($\approx 54.9^\circ$) and enforcing strict current safety saturation limits ($\pm 8.7\text{ A}$) to prevent overloads.
3. **Position Loop (Proportional Controller):** Implements an outer P-regulator ($K_p = 4$) to track angular positions without introducing secondary integral destabilization, ensuring critically damped exponential settling.

### Advanced Optimizations & Robustness
* **Reference Pre-Filtering:** Implementation of a first-order low-pass filter ($\tau = 0.5\text{ s}$) on the position reference to smooth out sharp mathematical gradients, successfully preventing current saturation spikes and reducing thermal/mechanical stress on hardware.
* **Disturbance Rejection & Robustness Analysis:** Tested under nominal load torque steps ($T_L = 1\text{ Nm}$) and severe parametric mismatch conditions (tripling the rotor moment of inertia, $J_{new} = 3 \cdot J_{nom}$), proving the drive's fault tolerance and stability under degraded phase margin conditions.

### Repository Structure
```text
├── docs/                # Technical project report (PDF)
├── models/              # PLECS simulation schematics (.plecs)
└── README.md            # Project documentation
