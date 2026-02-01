# IQM-Pulse-Optimization
#
## learned:
- how to formulate pulse-shape optimization as control problem
- the effective RWA Hamiltonian equation
- how to identify and optimize the shape parameters of a pulse
- how crucial pulse optimization is for qubit fidelity
- the distinction between plotting the pulse envelope, the physical control signal, and state or population dynamics.
- how important my 'Communication Systems' class was in my undergraduate degree


## next steps:
- simulate the model with more energy levels to include leakage by including higher excited states in the static Hamiltonian ($H_0=\hbar \sum_{n=1}^{n=N}\omega_n|n><n|$)
- include decoherence models to study pulse robustness under realistic noise
- constrain or penalize solutions that rely on extensively long pulse shapes
- explore other optimization methods as the number of pulse parameters increases

## challenges I faced:
- understand which parameters can be optimized symbolically or externally
- find the raised cosine envelope expression
- design an objective function that maps optimizer variables to physical pulse parameters without mixing optimization logic with pulse construction
- understanding optimization behavior that was physically correct but initially non-obvious, such as monotonic fidelity improvement due to under-rotation at fixed drive amplitude

## what interested me the most:
- how seemingly small design choices have strong consequences for optimization behavior.
- working with actual hamiltonian equations and being able to play with different parameters and analyze behavior
- how ideas from signal processing—such as smooth turn-on/off and bandwidth control—naturally reappear in quantum control



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
