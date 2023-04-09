

[[Mathematics]]

#notes 
my (long) notes on the topic: [[numerics.pdf]]
and the short version (ohne EV, CG) : [[numerics-short.pdf]]

errors of numerical schemes, see here: [[Errors and complexity of numerical methods]]



## Content
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
- Least Squares (see als [[Least squares vs. minimum norm solution of LSE]])
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
	- Krylov subspaces, see also [[Krylov methods - paper about idea and background]]
	- GMRES

## Source:
- Prof. Melenk - Numeric Computations https://www.asc.tuwien.ac.at/~melenk/teach/computernumerik_WS2122/