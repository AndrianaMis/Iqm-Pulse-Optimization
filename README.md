# IQM-Pulse-Optimization

6. Summarize what you have learned, the main challenges, what interests you the most in this problem (if anything), and what you would investigate as the
next step towards a more realistic optimization of the qubit performance with respect to the pulse. No fancy essay - bullet points are fine. Submit your
project as a public GitHub repo which contains your notebook and a readme with installation instructions and your summary.

## learned:
- how to formulate pulse-shape optimization as control problem
- the effective RWA Hamiltonian equation
- how to identify and optimize the shape parameters of a pulse
- got familiar with the qiskit dynamics library
- the distinction between plotting the pulse envelope, the physical control signal, and state or population dynamics.
- how important my 'Communication Systems' class was in my undergraduate degree


## next steps:
- simulate the model with more energy levels to include leakage ($H_0=\hbar \Sum_{n=1}^{n=N}\omega_n $)




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
