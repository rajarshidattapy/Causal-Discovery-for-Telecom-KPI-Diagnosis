Here is the **README.md** in clean Markdown format:

````markdown
# Causal Discovery for Telecom KPI Diagnosis

This project demonstrates how classical causal discovery algorithms can recover underlying causal structure in telecom network KPIs and how such structure enables meaningful counterfactual reasoning for network automation.

---

## Overview

Modern telecom networks generate high-dimensional, interconnected KPIs (latency, jitter, congestion, packet drops, throughput, etc.). Understanding **causal relationships** between these KPIs is essential for:

- Root-cause analysis  
- Automated troubleshooting  
- Predictive/prescriptive maintenance  
- Simulation of “what-if” scenarios  

This notebook builds a controlled environment where the ground-truth causal graph is known, allowing rigorous evaluation of causal discovery approaches.

---

## Key Components

### 1. Synthetic Telecom Causal Graph
A hand-designed DAG capturing realistic KPI interactions:
- CPU load → queue buildup → packet drop  
- Packet drop + throughput → latency  
- Congestion → packet drop & latency  
- Latency → jitter  

### 2. Data Generation (SEM)
Data is simulated using a linear Structural Equation Model with noise, making the benchmark repeatable and measurable.

### 3. Causal Discovery Algorithms
The project evaluates:

- **PC Algorithm** (constraint-based)  
- **DirectLiNGAM** (linear non-Gaussian)  
- **NOTEARS** (optimization-based)  

### 4. Evaluation Metrics
Recovered graphs are compared against ground truth using:

- Precision  
- Recall  
- F1-score  

### 5. Counterfactual Analysis
Performs a simple do-operation (e.g., reducing CPU load) and measures downstream effects on latency using the SEM.

---

## Installation

```bash
pip install lingam
pip install git+https://github.com/cdt-causality/causallearn.git
pip install git+https://github.com/xunzheng/notears.git
````

---

## Notes

* This is a **toy research prototype** for benchmarking causal discovery.
* Real telecom data involves latent confounders, temporal dependencies, and complex non-linear relationships.
* Counterfactual reliability depends strongly on the accuracy of the learned structural equations.

---
