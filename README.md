# Quantum Algorithms: The Deutsch-Jozsa Algorithm
**By Karolis Bandziulis** <br>
**Student ID:** G00417529 <br>
**Module:** Emerging Technologies <br>
**Language:** Python 3.12.5 <br>

## Project Overview
This repository contains an project submission for the Emerging Technologies module at Atlantic Technological University. The work focuses on understanding and implementing the Deutsch-Jozsa algorithm, one of the earliest demonstrations of quantum computational advantage over classical computation. All work is completed in a single Jupyter notebook [problems.ipynb](problems.ipynb) featuring five structured challenges that bridge the gap between traditional computing and quantum computing. The project scales up from generating standard classical Boolean logic to designing and simulating a complete quantum circuit with Qiskit and the Qiskit Aer simulator.

## Core Problems
### Problem 1: Generating Random Boolean Functions
The first stage of this project involved creating a reliable "Black Box" or Oracle for testing. We developed a classical Python generator designed to produce functions that are strictly constant (returning the same value for every input) or balanced (returning 0 for exactly half the inputs and 1 for the other half). By analysing 16 unique input combinations for a 4-bit domain, we verified the generator through statistical trials, ensuring it consistently produced valid test cases for the quantum algorithms.

### Problem 2: Classical Testing for Function Type
To establish a performance baseline, we implemented a classical tester and analysed its query complexity using the Pigeonhole Principle. We demonstrated that for a 4-bit function, a classical algorithm requires up to 9 queries to be 100 per cent certain of the result. By using an OracleQueryTracker, we successfully showcased the worst-case scenario where a classical computer is forced to check more than half of the possible inputs before it can make a definitive claim.

### Problem 3: Quantum Oracles
This step involved translating classical logic into reversible quantum gates. As quantum operations must be reversible, we built Quantum Oracles using ancilla qubits and XOR operations. This approach allowed the function output to be encoded into the quantum state without destroying the input data. This prepared the qubits for the Phase Kickback phenomenon, which is the underlying mechanism used to achieve speedup in quantum query algorithms.

### Problem 4: Deutsch's Algorithm
We implemented the full Deutsch's Algorithm using Qiskit to solve the 1-bit parity problem in a single attempt. By orchestrating a sequence of Hadamard gates, we created an interference pattern where constructive interference yields a 0 state for constant functions and destructive interference yields a 1 state for balanced functions. This provided a clear demonstration of quantum advantage, solving in one query what classical logic requires two queries to finish.

### Problem 5: Scaling to the Deutsch–Jozsa Algorithm
The final challenge involved scaling the logic from 1 bit to 4 bits, where the performance gap between classical and quantum systems becomes exponential. We developed a Minterm Expansion encoder to automatically compile arbitrary classical Python functions into Multi-Controlled-X gates. The final circuit successfully identified the function type in just one query, demonstrating the power of quantum parallelism and providing a massive speedup compared to the 9 queries required by classical methods.

## Code Quality & Linting
This project is linted and formatted using [Ruff](https://docs.astral.sh/ruff/), the modern standard for Python code quality.

## Prerequisites
- [Git](https://git-scm.com/)
- [Python 3.12.5 Recommended](https://www.python.org/downloads/release/python-3125/)

## How To Run
**It is recommended to run this project in a virtual environment to avoid dependency conflicts.**

1. **Clone this repository**
````text
git clone https://github.com/KarolisBz/emerging-technologies-assessment-g00417529.git
cd emerging-technologies-assessment-g00417529
````

2. **Create and Activate a Virtual Environment** <br>
Run the following commands based on your operating system:

Windows PowerShell:
````
python -m venv venv
.\venv\Scripts\activate
````

macOS/Linux:
````
python3 -m venv venv
source venv/bin/activate
````

3. **Install dependencies**
````
python -m pip install -r requirements.txt
````

4. **Launch Jupyter notebook**
````
python -m jupyter notebook
````

5. **Execute the Project**
- Open problems.ipynb from the interface and run all cells sequentially from top to bottom.

## References
All references are mentioned inline or in markdown at problems.ipynb to provide the context in which they are used in.
- [Deutsch's Algorithm Explainer Video (YouTube)](https://www.youtube.com/watch?v=QcK0GK7DUh8&t=655s)
- [Deutsch–Jozsa algorithm (IBM Quantum Learning)](https://quantum.cloud.ibm.com/learning/en/modules/computer-science/deutsch-jozsa)
- [Boolean inputs & outputs (Real Python)](https://realpython.com/python-boolean/)
- [Basics of Quantum Information: Single Systems (IBM Quantum Learning)](https://quantum.cloud.ibm.com/learning/en/courses/basics-of-quantum-information/single-systems/introduction)
- [Python Closures (GeeksforGeeks)](https://www.geeksforgeeks.org/python/python-closures/)
- [Deutsch's algorithm (IBM Quantum Learning)](https://quantum.cloud.ibm.com/learning/en/courses/fundamentals-of-quantum-algorithms/quantum-query-algorithms/deutsch-algorithm)
- [John Preskill Explains Quantum Supremacy (Quanta Magazine)](https://www.quantamagazine.org/john-preskill-explains-quantum-supremacy-20191002/)
- [The query model of computation (IBM Quantum Learning)](https://quantum.cloud.ibm.com/learning/en/courses/fundamentals-of-quantum-algorithms/quantum-query-algorithms/query-model-of-computation)
- [The Deutsch-Jozsa algorithm (IBM Quantum Learning)](https://quantum.cloud.ibm.com/learning/en/courses/fundamentals-of-quantum-algorithms/quantum-query-algorithms/deutsch-jozsa-algorithm)
- [Introduction to Quantum Algorithms (IBM Quantum Blog)](https://www.ibm.com/quantum/blog/group-theory)
- [Quantum Superposition Explained (Caltech Science Exchange)](https://scienceexchange.caltech.edu/topics/quantum-science-explained/quantum-superposition)
- [Global Properties & Entanglement (Stanford Encyclopedia of Philosophy)](https://plato.stanford.edu/archives/fall2008/entries/qt-entangle/#5)
- [Quantum Oracles (Quantum Computing Stack Exchange)](https://quantumcomputing.stackexchange.com/a/4626)
- [Unitary Operations (IBM Quantum Learning)](https://quantum.cloud.ibm.com/learning/en/courses/basics-of-quantum-information/single-systems/quantum-information#unitary-operations)
- [Qiskit Framework (IBM Quantum)](https://www.ibm.com/quantum/qiskit)
- [Quantum Circuits Introduction (IBM Quantum Learning)](https://quantum.cloud.ibm.com/learning/en/courses/basics-of-quantum-information/quantum-circuits/introduction)
- [Python 3: `random` library](https://docs.python.org/3/library/random.html)
- [Python 3: `random.choice`](https://docs.python.org/3/library/random.html#random.choice)
- [Python 3: `itertools` library](https://docs.python.org/3/library/itertools.html)
- [Python 3: `itertools.product`](https://docs.python.org/3/library/itertools.html#itertools.product)
- [Python 3: `typing` library](https://docs.python.org/3/library/typing.html)
- [Python 3: `statistics` library](https://docs.python.org/3/library/statistics.html)
- [Python 3 Data Model: `object.__call__`](https://docs.python.org/3/reference/datamodel.html#object.__call__)
- [Qiskit API: `QuantumCircuit`](https://quantum.cloud.ibm.com/docs/en/api/qiskit/qiskit.circuit.QuantumCircuit)
- [Qiskit API: `QuantumRegister`](https://quantum.cloud.ibm.com/docs/en/api/qiskit/1.0/qiskit.circuit.QuantumRegister)
- [Qiskit API: `ClassicalRegister`](https://quantum.cloud.ibm.com/docs/en/api/qiskit/1.0/qiskit.circuit.ClassicalRegister)
- [Qiskit Aer Simulator](https://qiskit.org/documentation/aer/)
- [IPython Display API](https://ipython.readthedocs.io/en/stable/api/generated/IPython.display.html)