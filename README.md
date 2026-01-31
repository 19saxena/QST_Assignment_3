# QST_Assignment_3
# Assignment 3 — Scalable Quantum Tomography Pipelines

## Overview
This project extends earlier quantum tomography work to study scalability, serialization, and benchmarking.
A lightweight surrogate quantum model is used to evaluate how fidelity and runtime scale with the number of qubits.

The focus is on reproducibility, clean serialization, and clear performance trends rather than full tomography training.

---

## Tasks Completed

### 1. Serialization
- Model parameters and metadata are serialized using Python `pickle`.
- Checkpoints are stored under `models/` using the format:
  `model_<track>_<nqubits>.pkl`
- A round-trip save/load test is included to verify correctness.

### 2. Scalable n-qubit Model
- Implemented a configurable `QuantumModel` class supporting arbitrary qubit counts.
- The model generates normalized complex statevectors.
- Fidelity is computed against randomly sampled target pure states.

### 3. Scalability Study
- Benchmarked fidelity and runtime for increasing qubit counts.
- Multiple random trials were run per qubit count.
- Results are aggregated and saved to CSV for plotting.

### 4. Visualisation
- Generated a plot of mean fidelity vs number of qubits with error bars.
- Runtime trends are shown on a secondary axis.
- The plot highlights the onset of scaling limitations as qubits increase.

### 5. Ablation Study
- Performed a simple ablation on model depth (number of layers).
- Observed trade-offs between expressibility and stability.

---

## Repository Structure
# Assignment 3 — Scalable Quantum Tomography Pipelines

## Overview
This project extends earlier quantum tomography work to study scalability, serialization, and benchmarking.
A lightweight surrogate quantum model is used to evaluate how fidelity and runtime scale with the number of qubits.

The focus is on reproducibility, clean serialization, and clear performance trends rather than full tomography training.

---

## Tasks Completed

### 1. Serialization
- Model parameters and metadata are serialized using Python `pickle`.
- Checkpoints are stored under `models/` using the format:
  `model_<track>_<nqubits>.pkl`
- A round-trip save/load test is included to verify correctness.

### 2. Scalable n-qubit Model
- Implemented a configurable `QuantumModel` class supporting arbitrary qubit counts.
- The model generates normalized complex statevectors.
- Fidelity is computed against randomly sampled target pure states.

### 3. Scalability Study
- Benchmarked fidelity and runtime for increasing qubit counts.
- Multiple random trials were run per qubit count.
- Results are aggregated and saved to CSV for plotting.

### 4. Visualisation
- Generated a plot of mean fidelity vs number of qubits with error bars.
- Runtime trends are shown on a secondary axis.
- The plot highlights the onset of scaling limitations as qubits increase.

### 5. Ablation Study
- Performed a simple ablation on model depth (number of layers).
- Observed trade-offs between expressibility and stability.

---

## Repository Structure
├── notebook.ipynb # Assignment 3 notebook (executed)
├── models/
│ ├── model_test_3.pkl # Example trained model checkpoint
│ └── test_roundtrip.pkl # Serialization round-trip test
├── scalability_results.csv # Fidelity and runtime benchmarks
├── screenshots/
│ └── scalability_plot.png # Mean fidelity vs qubits plot
└── README.md


---

## How to Run
1. Open the notebook.
2. Run all cells from top to bottom.
3. Generated checkpoints and CSV files will appear automatically.

---

## Reflection
Scalability is fundamentally limited by the exponential growth of the Hilbert space.
While surrogate models are useful for benchmarking and pipeline validation, more advanced techniques such as classical shadows or learned reconstructions will be required for larger systems.
Future work will explore these methods and hardware-aware noise models.


