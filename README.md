# COMSOL Reproduction of SnO₂/rGO NO₂ Gas Sensor

**Thermal–Electrical Behavior and Base Resistance Validation**

## Overview

This repository contains a **partial but validated reproduction** of the results reported in:

> *COMSOL-Based Modeling and Simulation of SnO₂/rGO Gas Sensor for Detection of NO₂*
> Scientific Reports, 2018

The focus of this reproduction is on the **thermal–electrical coupling of the sensor**, specifically:

* Heater-induced **temperature variation**
* **Base resistance** of the SnO₂/rGO sensing layer
* **Resistance modulation with temperature**

The work intentionally excludes chemical reaction kinetics and transfer-function fitting, concentrating instead on **physics-consistent validation of the thermal and electrical domains**.

<img width="615" height="622" alt="image" src="https://github.com/user-attachments/assets/6c7832fb-416f-40f9-8b91-e10dd597b575" />

---

## Scope of Reproduction

### ✔ Successfully Reproduced

The following aspects of the original paper have been implemented and validated in **COMSOL Multiphysics**:

1. **Heat Transfer Model**

   * Joule heating using RuO₂ heater
   * Temperature rise as a function of applied voltage
   * Near-isothermal behavior of the active sensing layer

2. **Electrical Model of the Sensing Layer**

   * Base resistance of SnO₂/rGO composite
   * Temperature-dependent resistance variation
   * Poisson-based electrical formulation

3. **Thermal–Electrical Coupling**

   * Resistance modulation driven purely by temperature
   * Physically consistent trends matching published data

This validates the **core physical backbone** of the sensor model before introducing gas exposure dynamics.

---

## Model Description

### Sensor Stack

The simulated structure follows the original device architecture:

* **Active Layer:** SnO₂/rGO nanocomposite
* **Electrodes:** Au interdigitated contacts
* **Heater:** RuO₂ resistive heater
* **Substrate:** Al₂O₃ (alumina)

Geometrical dimensions are reconstructed from published figures and scaled consistently.

---

### Physics Interfaces Used

* **Heat Transfer in Solids**

  * Conduction-dominated heat flow
  * Convection and radiation boundary losses
* **Electric Currents**

  * Poisson equation–based electrical modeling
  * Temperature-dependent material properties
* **Multiphysics Coupling**

  * Joule heating → temperature rise → resistance change

---

## Key Results

### 1. Temperature vs Heater Voltage

* The heater produces a **monotonic temperature increase**
* Near-room-temperature operation achieved at low bias
* Active layer exhibits **minimal spatial temperature variation**

This confirms:

* Correct heater modeling
* High thermal conductivity of the substrate
* Valid isothermal assumption used in the original paper

---

### 2. Base Resistance of SnO₂/rGO Layer

* Electrical resistance extracted directly from COMSOL
* Resistance magnitude matches reported order of values
* Confirms correctness of:

  * Material parameters
  * Boundary conditions
  * Electrical domain formulation

---

### 3. Resistance Variation with Temperature

* Resistance decreases with increasing temperature
* Behavior consistent with **Efros–Shklovskii variable-range hopping (ES-VRH)** conduction
* Confirms rGO-dominated transport behavior

This validates the **temperature dependence assumed later in gas-sensing transfer functions**.

---

## Validation Strategy

Instead of matching final sensing curves directly, this reproduction validates:

* Governing equations
* Boundary conditions
* Thermal uniformity assumptions
* Electrical response consistency

This makes the repository suitable as a **foundation model** for:

* Extending to gas exposure simulations
* Implementing concentration-dependent transfer functions
* Exploring alternative materials or geometries

---

## Software & Versions

* **COMSOL Multiphysics:** 6.2
* **Physics Modules:**

  * Heat Transfer in Solids
  * Electric Currents
  * Multiphysics (Joule Heating)

---

## How to Use This Repository

1. Open the COMSOL model file
2. Apply heater voltage sweep
3. Observe:

   * Temperature distribution
   * Average sensing-layer temperature
   * Electrical resistance variation
4. Use results as:

   * Baseline validation
   * Input to time-dependent sensing models

---

## Intended Audience

This repository is intended for:

* Researchers working on **MOS / rGO gas sensors**
* COMSOL users validating **multiphysics sensor models**
* Graduate students reproducing **Scientific Reports–level work**
* Designers optimizing sensor heaters and substrates

---

## Citation
Yaghouti Niyat, F., & Shahrokh Abadi, M. H. (2018).
COMSOL-Based Modeling and Simulation of SnO₂/rGO Gas Sensor for Detection of NO₂.
Scientific Reports, 8, 2149.

---

