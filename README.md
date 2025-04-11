# KAK Decomposition of Two-Qubit Gates via Lie Theory and Quantum Machine Learning

> Developed as supplemental material for Quantum Formalism's "[Lie Groups with Applications](https://quantumformalism.academy/lie-groups-with-applications)" course (Lecture 5).

> *See my full portfolio at: [https://bhepler.com/portfolio/](https://brainhelper.wordpress.com/data-science-portfolio/)*

## Goal

To decompose a general two-qubit gate (an $SU(4)$ matrix) into simpler components using Lie-theoretic methods (Cartan Decomposition) and, complementarily, to synthesize the same gate using a Quantum Machine Learning (QML) approach with a Variational Quantum Circuit (VQC). This project explores both exact numerical solutions rooted in Lie theory and approximate, trainable quantum circuits.

## Key Concepts & Relevance

*   **Lie Theory:** Cartan KAK Decomposition ($G = K_0 A K_1^{-1}$) of SU(4), Lie Algebras ($\mathfrak{su}(4)$), matrix logarithm/exponential.
*   **Quantum Computing:** Two-Qubit Gates (SU(4)), Gate Decomposition, Gate Synthesis, Local vs. Non-local (Entangling) Operations.
*   **Quantum Machine Learning (QML):** Variational Quantum Circuits (VQC), Parameter Optimization, Automatic Differentiation, Gradient Descent.
*   **Numerical Methods:** Root-finding algorithms for solving decomposition equations.
*   **Relevance:** Essential for understanding quantum gate structures, optimizing quantum circuits, quantum optimal control, and applying ML techniques within quantum computation.

## Implementation & Activities

*   **Implemented two distinct methods** for handling arbitrary $SU(4)$ two-qubit gates:
    *   **Exact Decomposition:** Developed a numerical solution using the Khaneja-Glaser algorithm (**NumPy, SciPy**) based on the Cartan KAK decomposition, isolating local ($K_0, K_1$) and non-local ($A$) factors. Utilized **SciPy's optimize.root** for solving intermediate steps.
    *   **Variational Synthesis (QML):** Designed and implemented a Variational Quantum Circuit (VQC) in **PennyLane**, with a structure inspired by the Cartan decomposition (parameterizing local and non-local parts).
*   **Leveraged PennyLane's automatic differentiation** capabilities to compute gradients of a fidelity cost function (comparing VQC output to the target gate).
*   **Implemented gradient descent** optimization to train the VQC parameters, learning an approximate synthesis of the target $SU(4)$ gate.
*   **Verified** the accuracy of both methods by reconstructing the original gate from the decomposed/synthesized components and calculating the approximation error (e.g., using matrix norm).
*   **Bridged** advanced Lie theory concepts with practical quantum computing frameworks (**PennyLane**) and numerical optimization techniques.

## Technologies & Skills

*   **Languages:** Python
*   **Libraries:** NumPy, SciPy (linalg, optimize), PennyLane, Matplotlib (for potential convergence plots)
*   **Concepts:** Lie Groups (SU(4)), Lie Algebras ($\mathfrak{su}(4)$), Cartan Decomposition (KAK), Matrix Logarithm/Exponential, Quantum Machine Learning (QML), Variational Quantum Circuits (VQC), Automatic Differentiation, Gradient Descent, Quantum Computing (Two-Qubit Gates, Gate Decomposition/Synthesis), Numerical Optimization, Linear Algebra.


## Theoretical Background

This project leverages the Cartan KAK decomposition, a fundamental result in Lie theory stating that any element $G$ of a semisimple Lie group (like SU(4)) can be written as $G = K_0 A K_1^{-1}$, where $K_0, K_1$ are in a maximal compact subgroup (here $SU(2) \otimes SU(2)$, representing local operations) and $A$ is in a specific abelian subgroup related to the Cartan subalgebra (representing the non-local/entangling part).
