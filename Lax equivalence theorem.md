[[Numerics for differential equations]]
FDM: [[Finite Difference Method (FDM)]]


## Main statement
A linear finite diff./finite volume scheme converges if and only if it is consistent and stable.
Proof: see lecture 4, Tornberg


## Convergence
... if the numerical approximation $u_h$ of $u$ vanishes as the step length $h$ goes to $0$:
$$\Vert u_h - u\Vert \xrightarrow{h\rightarrow 0} 0$$


## Consistency (order)
If the num. scheme is
$$u_{h}^{n+1} = \Psi(u_h^n) $$
Then the local truncation error is then
$$\epsilon^{n+1} = \Psi(u_h^n) - u(t^{n+1})$$
and consistency is given if
$$\frac{\epsilon}{h}\xrightarrow{h\rightarrow 0}0$$
The scheme is of order $p$ if
$$\epsilon =\mathcal{O}(h^{p+1})$$

#todo big TODO tornberg, schlatter, faustmann, https://math.stackexchange.com/questions/1921554/local-vs-global-truncation-error
schlatter: study question 22 order of scheme
tornberg HW2 ex2.2
#todo ignore the stuff above and just add my summary of lec4 with the adv. equ example!

[[Consistency finite differences vs finite elements]]


## Stability
A method is numerically stable, if "local errors are not amplified too much".

Several different approaches, e.g. 
1. [[CFL condition]] (necessary condition) 
2. [[Von Neumann stability analysis]] (sufficient condition, constant coefficients) 
3. Energy method (sufficient condition, variable coefficients)

Von Neumann analysis can only handle periodic boundary conditions or no boundaries. The energy method can handle more general boundary conditions.


## Source:
- Prof. Tornberg - Numerical solutions of differential equations, KTH lecture notes 2022
- https://en.wikipedia.org/wiki/Numerical_methods_for_ordinary_differential_equations