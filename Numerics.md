important branch of [[Mathematics]]


#TODO split this into 1 note per chapter (yes, split up the PDFs!)


## Topics

#notes [[numerics.pdf]], [[numerics-short.pdf]] (without EV, CG), [[Errors and complexity of numerical methods]]

- Polynomial interpolation
	- Neville
	- Newton polynomials
	- Horner scheme: evaluate polynomial in $\mathcal{O}(n)$ steps
	- Cehbyshev points
	- Splines
	- Trigonometric interpol, Fouriert Transform, FFT
- Numeric integration
	- Legendre
	- Gauss Quadr.
- Conditioning and error analysis
- Gauss Elimination
	- LU
	- Cholesky
	- QR (Gram schmitt, housholder reflections, pivoting)
- Least Squares
	- [[Least squares vs. minimum norm solution of LSE]]
	- Normal equations
	- QR sol of least squares
	- Underdetermined systems: minimum norm solution
	- SVD and how to find a minimum norm solution
	- Moore Penrose Pseude-Inverse
- Nonlinear equation solutions and Newton method
	- Basics, contraction, etc.
	- Damped newton
		- Descent method (find minimum of function)
		- Use descent method to find solution of nonlinear equation: find minimum of $x\mapsto||\boldsymbol{f}(x)||^2_2$  which are the zeros of $\boldsymbol{f}$ 
	- Gauss-Newton: use Newton method to solve nonlinear least squares 
	- quasi-newton method
		- Broyden method
	- Unconstrained minimization / gradient methods
- Eigenvalue problems
	- Power method
	- QR
- Conjugate Gradient Method
	- Krylov subspaces
		- [[Krylov methods - paper about idea and background]]
	- GMRES


## Topics: Numerics for differential equations
- [[Finite Element Method (FEM)]]
- [[Symplectic ODE integrators]]
- [[Viscosity solution]]


## Main sources:
- Prof. Melenk - Numeric Computations https://www.asc.tuwien.ac.at/~melenk/teach/computernumerik_WS2122/