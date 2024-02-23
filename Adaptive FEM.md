# Adaptive FEM
To speed up convergence for less regular solutions in the [[Finite Element Method (FEM)]], one can use graded meshes, i.e. meshes that are iteratively, locally refined.


The idea is to:
- solve the solution on a triangulation $\mathcal{T}_l$
- estimate the local error $\eta_l^T$ on each element
- mark elements with largest $\eta$
- refine the marked elements


## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021