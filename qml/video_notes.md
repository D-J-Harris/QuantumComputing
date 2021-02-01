# Welcome to QHack [here](https://www.youtube.com/watch?v=WBVnE8ChGX8&ab_channel=Xanadu)

- Quantum Computing
  - Wires and gates model
  - Evaluate functions which are classically intractable
- ML
  - Differentiable programming
  - Optimisation to train models that are built with free parameters
- QML
  - Circuit ansatz defines a quantum circuit architecture with free parameters (an educated guess)
  - Linear algebraic transformation of gates are differentiable

# QML with Pennylane [here](https://www.youtube.com/watch?v=eShyPOLIfYk&ab_channel=Xanadu)

- Quantum Leverage
  - Hardware advancements (QPUs)
  - Algorithms (quantum-aware backpropogation)
- Variational Circuits
  - Primary method for near-term quantum devices (limit of fewer qubits, max 1k)
  - VQE (find ground state hamiltonians) and QAOA first popular methods
  - Basic architecture is a quantum subroutine that leads to classical measurements and statistic, which feed back into training free parameters
    - Circuit ansatz defines state preparation and circuit parameters
    - Key to remember that smooth differentiability makes optimisation techniques feasible (c.f. ML)
- Parameter Shift Method
  - Backpropagation optimisation loops inform how parameters should be shifted to improve model
  - quantum hardware -> evaluate its own gradients
    - Gradient can be computed by *same* circuit, with *shifted parameters*
    - c.f. analytic derivatives as in formal definition of differentiation (negligible magnitude shifts in parameters to calculate gradient)
- Hybrid Computation
  - Pennylane is able to harness using classical and quantum models in series and parallel
  - e.g. photonic model for output to the input of a qubit model
- Scaling of Pennylane
  - Designed to be analogous to how NNs are trained (Pytorch, TensorFlow)
  - Designed to naturally grow alongside the power of near-term devices on the cloud
  - Compatible with multiple quantum platforms, allows to combine best aspects of different providers
  - 
- Quantum Nodes
  - Interface between quantum computers and classical ML libraries
  - evaluate() and gradient() methods
  - @qml.qnode(device) decorators on functions to define
  -  Switching interface e.g. to Torch and Rigetti QPU is pretty straightforward
-  QNodes
- Ansatz and Templates
  - popular circuit ansatz from QML literature available from qml.templates
  - e.g. StronglyEntanglingLayers, BasisEmbedding
  - Can load circuits from other frameworks (e.g. Qiskit) as templates
  - Experimental quantum simulator (for on device gradient calculation with TF backend instead of parameter shift) available for hackathon