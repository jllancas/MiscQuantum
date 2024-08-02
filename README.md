# Measuring Multipartite Entanglement with IBM Quantum computers

There are two copies of a Jupyter notebook to probe entanglement in the $n$-qubit GHZ state

$$|\mbox{GHZ}_{n}\rangle = \frac{1}{\sqrt{2}}\left(|00\cdots0\rangle + |11\cdots1\rangle\right)$$

1. [MultipartiteEntanglementSim.ipynb](MultipartiteEntanglementSim.ipynb) uses Qiskit's circuit simulator 
  
2. [MultipartiteEntanglementIBM.ipynb](MultipartiteEntanglementIBM.ipynb) sends the circuit for execution on IBM Quantum hardware (Qiskit Runtime required)

Both versions make use of [Qiskit](https://www.ibm.com/quantum/qiskit) 1.1.1. The ```Estimator``` primitive is used to obtain expectation values with an adjustable level of error mitigation (see: [resilience level](https://docs.quantum.ibm.com/guides/configure-error-mitigation)).

