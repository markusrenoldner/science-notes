[[Numerics for differential equations]]
FDM: [[Finite Difference Method (FDM)]]

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



## Stability
the method is stable, if

#todo complete, add source



## Condition

#todo add




see also [[Von Neumann stability analysis]]


## The same analysis for Finite Element method:
[[Consistency finite differences vs finite elements]]



## Source
- https://en.wikipedia.org/wiki/Numerical_methods_for_ordinary_differential_equations