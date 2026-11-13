# Position-control-of-a-DC-Motor-
Cascaded control design for a DC Motor Drive in PLECS. Features an inner current loop (PI), intermediate speed loop (Symmetrical Optimum), and outer position loop (P). Includes reference pre-filter optimization and parametric robustness analysis under inertial variations and load torque disturbances.

# Electric-Drives-DC-Motor-Control / Controllo Azionamenti Elettrici

<p align="center">
  <b>[ <a href="#english">English</a> ] | [ <a href="#italiano">Italiano</a> ]</b>
</p>

---

<a name="english"></a>
## English Version

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


# Controllo in Cascata di Velocità e Posizione per Azionamento a Motore in CC

Repository ufficiale per il progetto avanzato del corso di **Advanced Electric Drives and Power Converter Systems** (Laurea Magistrale in Digital Automation Engineering).

* **Candidato:** Antonio Iodice (Matricola: 213260)[cite: 47]
* **Anno Accademico:** 2025/2026[cite: 47]

---

## Panoramica del Progetto
Questo progetto descrive la progettazione completa, la simulazione dinamica e l'analisi delle prestazioni di un sistema di controllo in cascata per un azionamento a motore in CC, sviluppato all'interno dell'ambiente software **PLECS**[cite: 48]. La metodologia adottata segue un'architettura a cascata *bottom-up*, partendo dall'anello interno di corrente, passando per l'anello intermedio di velocità e concludendo con l'anello esterno di posizione angolare[cite: 48].

## Architettura di Controllo e Metodologia
1. **Anello di Corrente (Regolatore PI):** Regola la corrente d'armatura e la coppia elettromagnetica[cite: 50, 51]. Tarato per ottenere un tempo di salita rapido ($\approx 1\text{ ms}$) e una larghezza di banda ad anello chiuso di $50\text{ rad/s}$ per un profondo disaccoppiamento in frequenza[cite: 51].
2. **Anello di Velocità (Ottimo Simmetrico):** Regola la velocità meccanica utilizzando un regolatore PI ricavato analiticamente tramite il criterio dell'Ottimo Simmetrico, puntando a un margine di fase ottimale ($\approx 54.9^\circ$) e imponendo rigidi limiti di saturazione di sicurezza della corrente ($\pm 8.7\text{ A}$)[cite: 52, 53].
3. **Anello di Posizione (Regolatore Proporzionale):** Implementa un regolatore P esterno ($K_p = 4$) per tracciare la posizione angolare senza introdurre una seconda azione integrale destabilizzante, garantendo un transitorio a smorzamento critico[cite: 54, 55].

## Ottimizzazioni Avanzate e Robustezza
* **Pre-filtraggio del Riferimento:** Introduzione di un filtro passa-basso del primo ordine ($\tau = 0.5\text{ s}$) sul riferimento di posizione per smussare i gradienti netti, prevenendo con successo i picchi di saturazione della corrente e riducendo lo stress termico e meccanico sull'hardware[cite: 58, 59].
* **Reiezione dei Disturbi e Analisi di Robustezza:** Testato sotto gradini di coppia di carico nominale ($T_L = 1\text{ Nm}$) e severe condizioni di disallineamento parametrico (triplicando il momento d'inerzia del rotore, $J_{new} = 3 \cdot J_{nom}$), dimostrando la tolleranza ai guasti e la stabilità dell'azionamento anche in condizioni di ridotto margine di fase[cite: 52, 55, 60].


### Repository Structure
```text
├── docs/                # Technical project report (PDF)
├── models/              # PLECS simulation schematics (.plecs)
└── README.md            # Project documentation
