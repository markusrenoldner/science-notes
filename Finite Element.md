
[[Finite Element Method (FEM)]]


## Definition from Ciarlet
A finite element is a triple $(T, V_T, \Psi_T)$ where
- $T$ is a bounded set of points (e.g. an interval, a triangle, or tetrahedron) 
- $V_T$ is a finite dimensional function space in which functions can be interpolated
- $\Psi_T=\{\psi_1, ...\}$ is a set of linearly independent functionals from $V_T\rightarrow \mathbb{R}$ called "degrees of freedom"

#todo 
## Basis functions on $V_T$
The linear functionals in ΨT allow the definition of a local nodal basis {ϕ 1 T . . . ϕ NT T } (also called local shape functions) of VT via ψ i T (ϕ j T ) = δij . The local nodal interpolation operator IT : C m(T) → VT is defined by IT v := X NT j=1 ψ j T (v)ϕ j T . It is a projection, i.e., for all v ∈ VT there holds IT v = v.


## Reference element
![[Pasted image 20230614092310.png]]