# IQM-Pulse-Optimization
## Instructions 
There are two noteboooks **pulse_width_optimization.ipynb** and **iqm_pulse_optimization_task5.ipynb**.

### *pulse_width_optimization.ipynb*:
Contains the task 4 of the assignement:
- Building the GaussianSquare pulse 
- Convert the pulse into a control signal
- defining the system Hamiltonian
- Creating the solver
- defining the objective function with optimization parameters as input
- optimzing the pulse width by maximizing the gate fidelity (minimizing: 1-fid) using the *minimize_scalar* function
### *iqm_pulse_optimization_task5.ipynb*:
- Building the raised-cosine pulse and following the same pipeline as in Task 4
- building a parameter-agnostic objective function, that receives only the optimization variables, reconstructs the full set of physical pulse parameters, builds the pulse, simulates the dynamics, and returns the cost.
- creating a flexible environment in which pulse types and optimized/fixed parameters can be interchanged easily


To change the optimization parameters (e.g. optimizing both `sigma` and `width` for the GaussianSquare pulse), move `sigma` from `fixed_param` to `optimize_param` and set `pulse_type = "GaussianSquare"`.

At the moment, only GaussianSquare and RaisedCosine pulses are implemented, but this setup provides a clear baseline and can be easily extended to additional pulse families.
### What I learned:
- how to formulate pulse-shape optimization as control problem
- the effective RWA Hamiltonian equation
- how to identify and optimize the shape parameters of a pulse
- how crucial pulse optimization is for qubit fidelity
- the distinction between plotting the pulse envelope, the physical control signal, and state or population dynamics.
- how important my 'Communication Systems' class was in my undergraduate degree


### Next steps:
- simulate the model with more energy levels to include leakage by including higher excited states in the static Hamiltonian ($H_0=\hbar \sum_{n=1}^{n=N}\omega_n|n><n|$)
- include decoherence models to study pulse robustness under realistic noise
- constrain or penalize solutions that rely on extensively long pulse shapes
- explore other optimization methods as the number of pulse parameters increases

### Challenges I faced:
- understand which parameters can be optimized symbolically or externally
- identifying the appropriate raised-cosine envelope expression for control pulses
- designing an objective function that maps optimizer variables to physical pulse parameters without mixing optimization logic with pulse construction
- understanding optimization behavior that was physically correct but initially non-obvious, such as monotonic fidelity improvement due to under-rotation at fixed drive amplitude

### What interested me the most:
- how seemingly small design choices have strong consequences for optimization behavior
- combining Hamiltonian equations with concrete numerical simulations and visualizations
- how concepts from signal processing—such as smooth turn-on/off and bandwidth control—naturally reappear in quantum control
- modifying pulse parameters and immediately analyzing their effect on system dynamics and gate fidelity


## install

The notebook was tested with Python 3.10.

### setup
```bash
conda create -n pulse-opt python=3.10
conda activate pulse-opt
pip install numpy scipy matplotlib qiskit qiskit-dynamics
```
### run
```bash
jupyter notebook
```
- open *pulse_width_optimization.ipynb* to run the notebook containing the part 4 of the assignment (optimize GaussianSquare pulse width to maximize X-gate fidelity)
- open *iqm_pulse_optimization_task5.ipynb* to run the task 5 of the assignement (simulate RaisedCosine pulse, optimze its width to maximize X-gate fidelity, optimize all shape parameters of either GaussianSquare of RaisedCosine according to instructions for task 5.) 
