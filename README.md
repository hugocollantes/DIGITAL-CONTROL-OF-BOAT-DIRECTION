# ShipAttitudeController  
**Digital Control of Marine Orientation**

---

## Overview
This project develops a **digital control system for the orientation of a cargo vessel**, based on the **Nomoto second-order dynamic model**.  
The control architecture uses both **Pole-Placement** and **Truxal (Ragazzini–Guillemin)** methods to achieve **accurate heading tracking** and **robust disturbance rejection** under wind and hydrodynamic perturbations.

The implementation and simulation were carried out in **Scilab/Xcos**, focusing on system stability, discrete-time performance, and steady-state accuracy.

---

## System Description
The vessel is modeled as a nonlinear system simplified to a second-order transfer function according to Nomoto’s hydrodynamic model:

> Inputs: Rudder angle δ(s)  
> Outputs: Ship heading ψ(s)  
> Perturbations: Hydrodynamic resistance and wind torque  

Physical constraints such as rudder limits (±35°) and actuator saturation are included.  
The discrete equivalent system is obtained using a **1 s sampling period**, ensuring proper time resolution for digital control.

---

## Controller Design
Two digital controllers were designed and compared:

1. **Pole-Placement Controller**  
   - Zero steady-state error (ep = 0)  
   - Settling time Ts ≤ 200 s  
   - Overshoot Mp ≤ 5 %  
   - Discrete design via Diophantine equation and Sylvester matrix formulation  

2. **Truxal (Ragazzini–Guillemin) Controller**  
   - Equivalent closed-loop performance  
   - Simplified digital synthesis ensuring internal stability  
   - Implemented for both **reference tracking** and **disturbance rejection** in a two-degree-of-freedom structure  

---

## Simulation and Results
- Identical responses were achieved using both design methods, confirming theoretical equivalence.  
- The system exhibits **zero steady-state error** and **smooth transient response** with negligible overshoot.  
- Under external perturbations (wind and rudder torque), the controller successfully maintains orientation with less than ±5° deviation.  
- The digital and analog implementations match closely under the Tustin discretization method.  

---

## Key Features
- 🔹 Digital control design (z-domain)  
- 🔹 Implementation in Scilab/Xcos  
- 🔹 Two control strategies: Pole-Placement & Truxal  
- 🔹 Robustness against wind and hydrodynamic disturbances  
- 🔹 Validated steady-state and transient performance  

---

## Skills Demonstrated

- **Digital Control Design** – Discrete-time controller synthesis (Pole-Placement, Truxal / Ragazzini-Guillemin methods)
- **System Modeling** – Dynamic modeling using the Nomoto second-order ship model
- **Signal Processing & Discretization** – Sampling, Z-transform, and stability analysis
- **Simulation & Verification** – Implementation and validation in Scilab/Xcos
- **Mathematical Analysis** – Use of Diophantine equations, Sylvester matrices, and transient performance evaluation
- **Technical Documentation** – Full report in LaTeX/PDF with theoretical, analytical, and simulation results
