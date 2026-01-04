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
Used Pure NumPy

- ### 08_deutsch_jozsa_balanced_scaling.ipynb
- **Description:**
Today I learned how to automate quantum systems. I created a universal function to build portals for any number of qubits. I also built a Balanced Oracle by swapping rows in a matrix. This code can handle 3, 10, or even more qubits in one click, proving that quantum algorithms are faster than classical ones.

- ### 09_bb84_perfect.ipynb
- **Description:**
- Title: Quantum Key Distribution (QKD) — Perfect Channel
Description: Implementation of the BB84 protocol on pure NumPy. This project simulates a secure communication between Alice and Bob. It demonstrates random basis selection (Z and X), quantum state preparation, and the sifting process. The result is a 100% identical secret key shared between both parties.

- ### 10_bb84_eves_fake.ipynb
- **Description:**
- Title: Detecting Eavesdropping (Eve) in BB84 Protocol
Description: A simulation of a "Man-in-the-Middle" attack (Intercept-Resend). I introduced a spy (Eve) who intercepts qubits and measures them in random bases. Due to the No-Cloning Theorem, this intervention introduces a ~25% error rate, making the spy's presence immediately detectable by Alice and Bob.

- ### 11_bell_states_pure_numpy.ipynb
- **Description:**
Title: Complete Bell Basis Generator (Pure NumPy)
After using entanglement in previous algorithms (Deutsch, BB84), I decided to perform a "Deep Dive" into the source of quantum correlations. In this project, I implemented a universal generator for all four Bell States
|Φ+⟩ = 1/√2 (|00⟩ + |11⟩)
|Ψ+⟩ = 1/√2 (|01⟩ + |10⟩)
|Φ-⟩ = 1/√2 (|00⟩ - |11⟩)
|Ψ-⟩ = 1/√2 (|01⟩ - |10⟩)
using only Linear Algebra.

- ### 12_grover_full_scaling.ipynb
- **Description:**
Title: Universal Grover's Search Algorithm (N-Qubit Scaling)
Implementation of the Grover's search algorithm from scratch using pure NumPy. This project demonstrates quantum speedup in unstructured database searching.
Technical Highlights:
Dynamic Scaling: The algorithm works for any number of qubits (n) by dynamically constructing 2ⁿ dimensional operators.Oracle Design: Implemented a phase-inversion
Oracle that marks the target state with a negative phase.
Diffuser Construction: Built the "Inversion about the mean" operator using outer products and Hadamard transforms.
Probability Boost: Successfully demonstrated amplitude amplification, achieving ~78% probability of finding the target state |101) (index 5) in a single iteration for 3 qubits.

- ### 13_quantum_teleportation.ipynb
- **Description:**
Title: Quantum Teleportation Protocol
Implementation of the teleportation circuit on 3 qubits using Pure NumPy. The goal is to move a quantum state from Qubit 0 to Qubit 2 using entanglement as a "bridge".
Key Steps:
Entanglement: Creating a Bell Pair between Alice and Bob.
Bell Measurement: Alice entangles the "Secret" with the bridge and collapses the state.
Correction: Bob uses X and Z gates to restore the original information.
Why it matters:
It’s the foundation of the Quantum Internet. We prove that while you can't clone a qubit, you can move its state across space using entanglement and classical bits.

- ### 14_quantum_fourier_transform_qft.ipynb
- **Description:**
- Title: Quantum Fourier Transform (QFT) from Scratch
Building a universal Quantum Fourier Transform (QFT) engine from scratch. This project moves away from searching and focuses on "Quantum Phase Dynamics" — the ability to detect rhythms and periods in data.
Хow it works: Phase Rotation:
Instead of simple 0s and 1s, I used complex exponents (np.exp) to rotate qubit phases.
Universal Generator: I wrote a manual double-loop matrix generator that scales to any number of qubits by calculating the phase shift for every cell.
The Detector: I tested the algorithm with periodic signals (like [1, -1, 1, -1]). The QFT successfully identified the "rhythm" and converted it into a sharp peak at a specific position. Why it matters:QFT is the "engine" behind Shor's Algorithm. While Grover searches for a needle in a haystack, QFT finds the hidden frequency of the hay itself. It is the key to breaking modern RSA encryption.

- ### 15.bit.flip.correction.ipynb
- **Description:**
I am trying to learn English so that I can practice writing descriptions myself, without the help of AI or a translator. Therefore, I will simply state what I did in this code:
1. Created a logical qubit: Encoded the state of one qubit into three.
2. Simulated a physical error: Injected noise (Bit-Flip) into a specific qubit of the system.
3. Wrote a syndrome decoder: Created the check_error function, which analyzes binary indices and finds the "guilty" one using the majority voting method.
4. Implemented correction (Recovery): Wrote a universal function that returns the system to its original state.
