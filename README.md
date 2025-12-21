# learning-quantum
My path to becoming a Quantum Engineer at 16.
I am learning Quantum Computing from scratch. Here I explore basic gates and state transformations.

 My Quantum Journey 2025
This repository contains my daily progress in Quantum Computing.

## Contents:

- ### 01_cnot_train_relocation.ipynb
**Description:** 
In this experiment, I use the "Train Analogy" to understand Matrix Multiplication (Linear Algebra).

**How it works:**
* **Entrance (Top):** The columns represent the starting "stations" (Input States).
* **The Path:** The state travels down the column like a train on a track.
* **Exit (Left):** When the train hits a "1" (the switch), it turns left and arrives at a new station (Output State).

**Physical meaning:**
This shows how the CNOT gate relocates quantum information from one state to another based on the control qubit.

- ### 03_qutip_matplotlip.ipynb
**Description:** 
My first encounter with the qutip library and adding real physics to the graph. Before, there were only "photographs" (static gates); now it's a "film strip", where the graph shows the qubit's life over time. I have also added friction and noise to simulate how quantum information decays in the real world.

- ### 04_damped_quantum_dynamics.ipynb
**Description:** 
Moving from static gates to Time Dynamics. This project uses the mesolve solver from the qutip library to simulate the life of a qubit over time.
Key Concepts:
Quantum Dynamics (The Film Strip): Instead of a single result, we observe the continuous evolution of the quantum state using tlist.
Lindblad Master Equation: Modeling an "Open Quantum System" that interacts with its environment.
Simulating Noise (Decoherence):
Relaxation: Using qt.destroy(2) to simulate energy loss (falling from state 1 to 0).
Dephasing: Using qt.sigmaz() to simulate the loss of phase information.
Analogy:
This is the "Tired Train" experiment. On a perfect track, the train (qubit) oscillates forever. But here, we added "friction" and "wind" (noise). The graph shows the train's motion slowly dying out until it stops completely.

- ### 05_quantum_dynamics_and_3d_sphere.ipynb
- **Description:** 
Theory: Lindblad Master Equation for open systems.
Physics: Competition between coherent driving (Rabi oscillations) and environmental noise (relaxation/dephasing).
Visuals: 3D Bloch Sphere trajectory showing the "death" of a qubit as it spirals into the center.
