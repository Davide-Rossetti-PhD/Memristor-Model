# Extended Memristor Modeling and Machine Learning-Based Parameter Optimization

This repository provides a **Python–LTSpice framework** for the calibration of memristor models using experimental data.  

## 🚀 Overview
Accurate modeling of memristive devices is essential for capturing **asymmetric, nonlinear, and history-dependent behaviors** observed in real devices.  
This project introduces:
- A **SPICE-compatible extended memristor model**, derived from seminal Chua’s framework and enhanced with nonlinear passive components.  
- A **machine learning–driven optimization pipeline** combining:
  - Latin Hypercube Sampling (LHS)  
  - Bayesian Optimization (BO)  
  - Gradient-based refinement
 
<p align="center">
<img width="611" height="796" alt="Workflow_optimization" src="https://github.com/user-attachments/assets/c1f5add9-b755-4188-9e7d-f41e2ef2cb3b" />
</p>


This workflow enables **automated fitting** of model parameters to experimental I–V data, achieving high predictive accuracy across different waveforms and frequencies.

## ⚙️ Requirements
- **Python ≥ 3.8**
- Dependencies:
  - `numpy`
  - `scipy`
  - `matplotlib`
  - `scikit-optimize`
  - `pyDOE`
  - `ltspice`
- **LTSpice XVII or later**, callable from the command line

## 🔄 Workflow
1. **Parameter Sampling**  
   Generate initial parameter sets via Latin Hypercube Sampling (LHS).
2. **Netlist Update**  
   Modify the LTSpice netlist with candidate parameters and simulation settings.
3. **Simulation**  
   Run LTSpice in batch mode to obtain simulated I–V curves.
4. **Post-Processing**  
   Interpolate experimental and simulated data onto a common time base.  
   Compute error metrics (RMSE, relative error, area between curves).
5. **Optimization Loop**  
   - Bayesian Optimization to explore parameter space.  
   - Gradient-based refinement (e.g. L-BFGS-B) to fine-tune.
6. **Validation**  
   Compare optimized models against experimental data across different waveforms and frequencies.


## 📊 Results

- The extended memristor model reproduces:
  - Flux accumulation  
  - Conductance saturation  
  - Lobe asymmetry in pinched hysteresis loops  

- The hybrid ML optimization pipeline (LHS + BO + gradient refinement) significantly reduces error compared to baseline parameters.  
- The calibrated model demonstrates **predictive accuracy** across unseen excitation waveforms and frequencies.  
- Simulation vs. experimental I–V curves show strong alignment.  
- The resulting parameter set provides physical insight into device behavior and supports neuromorphic and in-memory computing applications.
<img width="5201" height="5615" alt="Train_Figure_08" src="https://github.com/user-attachments/assets/9f6ce4ed-d3d6-4551-9c00-1d3775d85602" />
