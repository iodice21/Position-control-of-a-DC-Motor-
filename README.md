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


<a name="versione-italiana"></a>
# Controllo in Cascata di Velocità e Posizione per Azionamento a Motore in CC

Repository ufficiale per il progetto avanzato del corso di Advanced Electric Drives and Power Converter Systems (Laurea Magistrale in Digital Automation Engineering).

* **Candidato:** Antonio Iodice (Matricola: 213260)
* **Anno Accademico:** 2025/2026

## Panoramica del Progetto
Questo progetto descrive la progettazione completa, la simulazione dinamica e l'analisi delle prestazioni di un sistema di controllo in cascata per un azionamento a motore in CC, sviluppato all'interno dell'ambiente software PLECS. La metodologia adottata segue un'architettura a cascata bottom-up, partendo dall'anello interno di corrente, passando per l'anello intermedio di velocità e concludendo con l'anello esterno di posizione angolare.

## Architettura di Controllo e Metodologia
1. **Anello di Corrente (Regolatore PI):** Regola la corrente d'armatura e la coppia elettromagnetica. Tarato per ottenere un tempo di salita rapido e una larghezza di banda ad anello chiuso di 50 rad/s per un profondo disaccoppiamento in frequenza.
2. **Anello di Velocità (Ottimo Simmetrico):** Regola la velocità meccanica utilizzando un regolatore PI ricavato analiticamente tramite il criterio dell'Ottimo Simmetrico, puntando a un margine di fase ottimale e imponendo rigidi limiti di saturazione di sicurezza della corrente (+/- 8.7 A).
3. **Anello di Posizione (Regolatore Proporzionale):** Implementa un regolatore P esterno (Kp = 4) per tracciare la posizione angolare senza introdurre una seconda azione integrale destabilizzante, garantendo un transitorio a smorzamento critico.

## Ottimizzazioni Avanzate e Robustezza
* **Pre-filtraggio del Riferimento:** Introduzione di un filtro passa-basso del primo ordine (tau = 0.5 s) sul riferimento di posizione per smussare i gradienti netti, prevenendo con successo i picchi di saturazione della corrente e riducendo lo stress termico e meccanico sull'hardware.
* **Reiezione dei Disturbi e Analisi di Robustezza:** Testato sotto gradini di coppia di carico nominale (TL = 1 Nm) e severe condizioni di disallineamento parametrico (triplicando il momento d'inerzia del rotore, J_new = 3 * J_nom), dimostrando la tolleranza ai guasti e la stabilità dell'azionamento anche in condizioni di ridotto margine di fase.


### Repository Structure
```text
├── docs/                # Technical project report (PDF)
├── models/              # PLECS simulation schematics (.plecs)
└── README.md            # Project documentation
