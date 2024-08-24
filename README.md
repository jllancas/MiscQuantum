# Quantum computing odds and ends

This is a running collection of half-baked things.

## Multipartite non-locality

This is based on the experiments described in 

- Ya-Li Mao <i>et al.</i>, <i>Phys. Rev. Lett.</i> <b>129</b>, 150401 (2022). ([arXiv:2201.12753](https://arxiv.org/abs/2201.12753))

- H. Cao <i>et al.</i>, <i>Phys. Rev. Lett.</i> <b>129</b>, 150402 (2022). ([arXiv:2201.12754](https://arxiv.org/abs/2201.12754))

There are two copies of a Jupyter notebook to probe entanglement in the $n$-qubit GHZ state

$$|\mbox{GHZ}_{n}\rangle = \frac{1}{\sqrt{2}}\left(|00\cdots0\rangle + |11\cdots1\rangle\right)$$

1. [MultipartiteEntanglementSim.ipynb](MultipartiteEntanglementSim.ipynb) uses Qiskit's circuit simulator 
  
2. [MultipartiteEntanglementIBM.ipynb](MultipartiteEntanglementIBM.ipynb) sends the circuit for execution on IBM Quantum hardware (Qiskit Runtime required)

Both versions make use of [Qiskit](https://www.ibm.com/quantum/qiskit) 1.1.1. The ```Estimator``` primitive is used to obtain expectation values with an adjustable level of error mitigation (see: [resilience level](https://docs.quantum.ibm.com/guides/configure-error-mitigation)).

## Quantum contextuality and the Peres-Mermin square

The following two references are some useful:

- C. Budroni <i>et al.</i>, <i>Rev. Mod. Phys.</i> <b>94</b>, 045007 (2022). ([arXiv:2102.13036](https://arxiv.org/abs/2102.13036))
  
- A. Laghaout <i>et al.</i>, <i>Eur. J. Phys.</i> <b>43</b>, 055401 (2022). ([open access](https://iopscience.iop.org/article/10.1088/1361-6404/ac79e0/meta))

The Peres-Mermin square is the following arrangement of operators such that all operators in each row commute with each other. The operators in each column also commute.

$$\left(\begin{array}{ccc} \hat{A} & \hat{B} & \hat{C}\\ \hat{a} & \hat{b} & \hat{c} \\ \hat{\alpha} & \hat{\beta} & \hat{\gamma} \end{array}\right)$$

Each row and each column is said to form a "context" in which all three observables may be measured simultaneously. Assigning a sense of "reality" to each of the nine quantities is possible if nature is "non-contextual." Note that observables from different contexts do <i>not</i> commute. Each quantity is assumed to take measure values of $\pm 1$. Assuming the simultaneous "reality" of all nine quantities, one can argue

$$\langle \hat{A}\hat{B}\hat{C} \rangle + \langle \hat{a}\hat{b}\hat{c} \rangle  + \langle \hat{\alpha}\hat{\beta}\hat{\gamma} \rangle  + \langle \hat{A}\hat{a}\hat{\alpha} \rangle  + \langle \hat{B}\hat{b}\hat{\beta} \rangle  - \langle \hat{C}\hat{c}\hat{\gamma} \rangle \leq 4$$

The notebook [ContextualitySquare.ipynb](ContextualitySquare.ipynb) uses Qiskit's circuit simulator to explore contextuality for the specific representation

$$\left(\begin{array}{ccc} \hat{A} & \hat{B} & \hat{C}\\ \hat{a} & \hat{b} & \hat{c} \\ \hat{\alpha} & \hat{\beta} & \hat{\gamma} \end{array}\right) = \left(\begin{array}{ccc} \hat{I}\otimes\hat{\sigma}^{z} & \hat{I}\otimes\hat{\sigma}^{z} & \hat{\sigma}^{z}\otimes\hat{\sigma}^{z} \\ \hat{I}\otimes\hat{\sigma}^{x} & \hat{\sigma}^{x}\otimes\hat{I} & \hat{\sigma}^{x}\otimes\hat{\sigma}^{x} \\ \hat{\sigma}^{z}\otimes\hat{\sigma}^{x} & \hat{\sigma}^{x}\otimes\hat{\sigma}^{z} & \hat{\sigma}^{y}\otimes\hat{\sigma}^{y} \end{array}\right)$$

This is a pedagogical take that works through the subtlety of treating the operators $\hat{A},\cdots, \hat{\gamma}$ as fundamental rather than the implied representation in terms of two-qubit measurements (e.g., $\hat{\sigma}^{z}\otimes\hat{\sigma}^{z}$).
