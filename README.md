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

- ### 06_deutsch_algorithm.ipynb
- **Description:** 
Deutsch Algorithm: First Quantum Speedup.
1. First, we import numpy for linear algebra. We define the Hadamard gate (H) using its normalization factor (1/√2) and the Identity matrix (I) to represent a "do-nothing" operation.
2. We initialize the system in the state |01) (represented by the vector psi_0). The second qubit is set to |1) to enable the Phase Kickback effect later.
3. We use np.kron (Kronecker product) to expand 2x2 matrices into 4x4 matrices. H2 applies Hadamard to both qubits, while H_final applies it only to the first qubit to perform interference.
4. We define a Balanced Oracle using the CNOT matrix. This matrix acts as a "black box" that flips the second qubit if the first one is |1).
5. psi_1: Create a superposition (The "Mist").
psi_2: Pass the state through the Oracle (Phase information is transferred).
final_state: Apply the final Hadamard to resolve the phase into a measurable state.
6. We calculate prob_1 by summing the squares of the amplitudes where the first qubit is |1) (indices 2 and 3). A result of 1.0 confirms the function is Balanced in just one single run.

- ### 07_deutsch_jozsa_scaling.ipynb
- **Description:**
- Title: Scaling the Deutsch-Jozsa Algorithm to N-Qubits
- Today, I mastered matrix scaling for quantum systems. I developed a universal function to generate Hadamard portals for any number of qubits (in this example, 3 query qubits and 1 helper qubit).
- This implementation demonstrates how a Quantum Computer identifies whether a 'Black Box' (Oracle) is Constant or Balanced in just a single run (one query), regardless of the input size. This is a clear example of exponential quantum speedup."
