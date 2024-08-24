# Quantum computing odds and ends

This is a running collection of half-baked things. 

## Multipartite non-locality

This is based on the experiments described in 

 - [Ya-Li Mao <i>et al.</i>, <i>Phys. Rev. Lett.</i> <b>129</b>, 150401 (2022)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.129.150401) ([arXiv:2201.12753](https://arxiv.org/abs/2201.12753))

 - [H. Cao <i>et al.</i>, <i>Phys. Rev. Lett.</i> <b>129</b>, 150402 (2022)](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.129.150402) ([arXiv:2201.12754](https://arxiv.org/abs/2201.12754))

There are two copies of a Jupyter notebook to probe entanglement in the $n$-qubit GHZ state

$$|\mbox{GHZ}_{n}\rangle = \frac{1}{\sqrt{2}}\left(|00\cdots0\rangle + |11\cdots1\rangle\right)$$

1. [MultipartiteEntanglementSim.ipynb](MultipartiteEntanglementSim.ipynb) uses Qiskit's circuit simulator 
  
2. [MultipartiteEntanglementIBM.ipynb](MultipartiteEntanglementIBM.ipynb) sends the circuit for execution on IBM Quantum hardware (Qiskit Runtime required)

Both versions make use of [Qiskit](https://www.ibm.com/quantum/qiskit) 1.1.1. The ```Estimator``` primitive is used to obtain expectation values with an adjustable level of error mitigation (see: [resilience level](https://docs.quantum.ibm.com/guides/configure-error-mitigation)).

## Quantum contextuality and the Peres-Mermin square

