# DC-Motor-Drive-PLECS / Controllo Azionamenti Elettrici

[English Version](#english-version) | [Versione Italiana](#versione-italiana)

---

<a name="english-version"></a>
## English Version

# Cascaded Position and Speed Control of a DC Motor Drive

Official repository for the advanced project in **Advanced Electric Drives and Power Converter Systems** (Master's Degree in Digital Automation Engineering).

* **Candidate:** Antonio Iodice (Student ID: 213260)
* **Academic Year:** 2025/2026

### Project Overview
This project details the comprehensive design, dynamic simulation, and performance analysis of a cascaded control system for a DC Motor Drive, developed within the PLECS software environment. The adopted methodology follows a bottom-up cascade architecture, starting with the inner current control loop, followed by the intermediate mechanical speed loop, and concluding with the outermost angular position loop.

### Control Architecture and Methodology
1. **Inner Current Loop (PI Controller):** Regulates armature current and electromagnetic torque. Tuned to achieve a fast rise time and a closed-loop bandwidth of 50 rad/s for deep frequency decoupling.
2. **Speed Loop (Symmetrical Optimum):** Regulates mechanical speed using an analytically derived PI controller based on the Symmetrical Optimum criterion, targeting an optimal phase margin and enforcing strict current safety saturation limits (+/- 8.7 A).
3. **Position Loop (Proportional Controller):** Implements an outer P-regulator (Kp = 4) to track angular positions without introducing secondary integral destabilization, ensuring critically damped exponential settling[cite: 54, 55].

### Advanced Optimizations and Robustness
* **Reference Pre-Filtering:** Implementation of a first-order low-pass filter (tau = 0.5 s) on the position reference to smooth out sharp mathematical gradients, successfully preventing current saturation spikes and reducing thermal and mechanical stress on hardware[cite: 58, 59].
* **Disturbance Rejection and Robustness Analysis:** Tested under nominal load torque steps (TL = 1 Nm) and severe parametric mismatch conditions (tripling the rotor moment of inertia, J_new = 3 * J_nom), proving the drive's fault tolerance and stability under degraded phase margin conditions[cite: 52, 55, 60].

### Repository Structure
```text
├── docs/                # Technical project report (PDF)
├── models/              # PLECS simulation schematics (.plecs)
└── README.md            # Project documentation
