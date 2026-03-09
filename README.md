![Python](https://img.shields.io/badge/Python-Scientific%20Computing-blue)
![Type](https://img.shields.io/badge/Type-Academic%20Project-green)
![Field](https://img.shields.io/badge/Field-Computational%20Neuroscience-purple)
![Topic](https://img.shields.io/badge/Topic-Stochastic%20Resonance-orange)

# Stochastic Resonance in a LIF Neuron
## BSc Artificial Intelligence - Brain Modeling Project

Computational neuroscience simulation investigating **stochastic resonance in Leaky Integrate-and-Fire neurons** and its role in enhancing weak signal detection and spike–signal synchronization.
The project investigates how stochastic noise can enhance the detection of weak subthreshold signals and improve spike–signal synchronization at both **single-neuron and population levels**.

## Project Overview
Neural systems operate in intrinsically noisy environments. While noise is often traditionally considered detrimental to signal processing, nonlinear threshold systems such as neurons can exploit noise to enhance weak signal detection.
This phenomenon is known as **Stochastic Resonance (SR)**.

In this project, we simulate a **Leaky Integrate-and-Fire (LIF) neuron** receiving a weak sinusoidal input that remains below firing threshold. By introducing stochastic fluctuations in the input current, we study how noise enables threshold crossings and enhances **temporal signal encoding**.

The analysis investigates both **single neuron dynamics** and **population-level robustness**.

## Research Questions
This project explores the following hypotheses:

**H1 — Optimal noise level**  
Spike-signal synchronization is maximized at an intermediate noise intensity.

**H2 — Signal amplitude dependence**  
Increasing the signal amplitude shifts the optimal noise level toward lower values.

**H3 — Operating point dependence**  
Increasing the bias current brings the neuron closer to threshold, reducing the noise level required for stochastic resonance.

**H4 — High-noise degradation**  
Excessive noise increases firing activity but degrades temporal precision.

**H5 — Population robustness**  
Pooling spikes across multiple neurons produces more stable signal representations.

## Model
The neuron is modeled using a **Leaky Integrate-and-Fire (LIF) model**, which describes membrane potential dynamics as a threshold system integrating incoming current.

Subthreshold membrane dynamics:
```
τₘ dV/dt = −(V − Eₗ) + I(t)/gₗ
```
A spike occurs when the membrane potential reaches the threshold \(V_{th}\), after which the neuron resets and enters a refractory period.

The neuron receives a weak periodic input:
```
I(t) = I_bias + A sin(2πft)
```
Noise is introduced as **Gaussian white noise** added to the input current

## Methods
The simulation pipeline consists of several steps:

**LIF neuron simulation**  
The membrane dynamics are simulated using numerical integration.

**Noise injection**  
Gaussian noise is added to the input current with varying noise intensity.

**Stochastic resonance analysis**  
Noise intensity is systematically varied to identify the optimal noise level.

**Spike synchronization measurement**  
Spike–signal synchronization is quantified using **Vector Strength**, a phase-locking metric.

**Parameter sweeps**  
The analysis explores how stochastic resonance depends on:

- signal amplitude
- bias current
- noise intensity

**Population simulation**  
The model is extended to a population of **N = 50 independent neurons** receiving identical signals but independent noise realizations.

## Results

The results reveal the characteristic **stochastic resonance curve**.
![Stochastic Resonance Curve](figures/sr_curve.png)  
The analysis shows that synchronization between spikes and the input signal is strongest at an intermediate noise level. Too little noise prevents threshold crossings, while excessive noise disrupts temporal precision.

**Population response**
To investigate robustness at the network level, the model was extended to a population of independent neurons receiving the same signal, but different noise realizations.  
![Population SR Readout](figures/population_sr.png)  
The raster plot and pooled PSTH show how population activity reflects the input signal. At intermediate noise levels, spikes become temporally aligned with the periodic stimulus, producing clear oscillatory structure in the pooled population response.

**Low noise levels**
- spiking is rare and synchronization is weak.

**Intermediate noise levels**
- spike timing becomes strongly phase-locked to the input signal, maximizing synchronization.

**High noise levels**
- firing activity increases but temporal precision degrades due to noise-dominated spike timing.

## Tech Stack
**Language**  
Python

**Libraries**  
- numpy  
- scipy  
- matplotlib  
- tqdm  

**Techniques**  
Computational neuroscience modeling  
Stochastic simulations  
Phase-locking analysis  
Population neural coding  

## Reproducibility
To reproduce the results of this project:  
1. Clone the repository
2. Install the required Python libraries
3. Open the simulation notebook and run all cells

Running the notebook will reproduce the simulations, figures, and analysis presented in this project.

## Repository Structure
```
brain-modeling-stochastic-resonance
│
├── README.md
├── BM_report.pdf
├── Project_Brain_modeling.ipynb
│
├── figures
│ ├── sr_curve.png
│ └── population_sr.png
│
└── requirements.txt
```  
The repository contains the simulation notebook, the project report, and the figures used to illustrate the main results of the analysis.
## Project Materials
Additional materials for this project are available below

**Project report**
Full methodological description and results.  
[Read the report](BM_report.pdf)

**Simulation notebook**
Python notebook containing the full simulation and analysis pipeline.
[View the notebook](Project_Brain_modeling.ipynb)

## Authors
Sabina Gallo  
Beatrice Camera  
Irene Marrali  

BSc in Artificial Intelligence 
University of Pavia - University of Milano Statale - University of Milano-Bicocca


