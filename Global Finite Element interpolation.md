# Global Finite Element interpolation

[[Local Finite Element interpolation]] only discusses basis functions, etc. on one local element.

First we define the global interpolation operator $I_\mathcal{T}(\Omega)$ such that $$(I_\mathcal{T} u)\vert_T = I_T(u\vert_T)\quad \forall T\in \mathcal{T}$$
We define the global space $V_\mathcal{T}$ as the image of the global interpolation operator applied to smooth functions:$$V_\mathcal{T}:=\left\{ u=I_\mathcal{T}\omega:\omega\in C^m(\Omega)\right\}$$ alternatively, we can also define it as the subspace of $H^1$ (or another Sobolev space), whose elements are restricted to be polynomials of a certain degree: $$V_\mathcal{T}:=\left\{ u\in H^1(\Omega):u\vert_T \in \mathcal{P}^1(T) \quad\forall T\right\}$$
Global basis:
1. collect all linearly independent functionals $\psi_i^{T_i}$ from all elements $T_i$
2. identify functionals that coincide on element interfaces ("remove duplicates")
3. find $\phi_i$ by requiring globally: $\psi_j(\phi_i)=\delta_{ij}$ 

This is done by a so called "connectivity matrix" or a "local-global-map":
Matches indices of local and global functionals and global basis functions. This matrix/map has to be constructed once for each element.


## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021