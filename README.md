# markov_chain_calculator - Tighe Clough and Alton Banushi
A Jupyter Notebook Project To Automate Common Markov Chain Calculations

## Goals:
We wish to differentiate between different kinds of Markov Chains, including:
1. Ergodic
2. Regular
3. Absorbing

### Ergodic Matrix Recognizer
Classifying Markov chains as ergodic was more complicated than the other tasks for this calculator. 
The approach we took was to consider the Markov chain as an unweighted directed graph, consisting of edges and nodes. 
We used a pared-down Tarjan's algorithm to check if the graph has more than one strongly connected component (SCC). 
An SCC is a section of a graph where all nodes/states can reach each other. An ergodic transition matrix should have only one SCC that contains all nodes (by definition).
If the graph was found to have an SCC at a root node other than the first node searched, then we could determine that the graph
has more than one SCC and classify it as non-ergodic. 

## Questions to Answer:
General questions we could answer are:
1. ✅ Probability to go from state **a** to state **b** in **k** steps
2. ✅ Average number of times in a state before being absorbed
3. ✅ Average number of steps before being absorbed
4. ✅ Probability that we are absorbed by state **b** if we start in state **a** (be absorbed)
5. ✅ Find the fixed vector of a matrix
6. ✅ Mean First Passage Time of ergodic matrix
7. ✅ Mean first return time for state **a**

In the current version, functions to answer each of these have been implemented and tested for correctness.

### Right vs. Left Stochastic Matrix
Our calculator works on right stochastic matrices as input (where the rows sum to 1), 
and not left stochastic matrices (where the columns sum to 1).

### Multiple Fixed Vectors of any Matrix
An equilibrium distribution can be thought of as a special eigenvector with eigenvalue 1 (wT = 1w).
We found the fixed vectors through finding the vectors in the E1 space with non-negative components that sum to 1.

## Interactive Calculator
At the bottom of the notebook, a REPL (Read-Eval-Print-Loop) style calculator has 
been implemented. If this were to be developed furhter, we may decide to treat the 
functions as a separate project, instead opting to develop some API. Doing so would
allow  for use in other languages and mediums, such as an interactive website for
example.
