is a numerical scheme, that conserves certain properties of the unknown. It does this by deriving a formula for the "exact cell average" of the unknown. This formula is then approximated using [[Numerical integration]].
Volume integrals in a partial differential equation that contain a divergence term are converted to surface integrals, using the divergence theorem. These terms are then evaluated as fluxes at the surfaces of each finite volume.

We will now consider the method for a 1D [[Conservation law, transport equation]]:
$$\partial_t u + \partial_x f(u)=0$$


## Scheme:
$$Q_j^{n+1}=Q_j^n-\frac{\Delta t}{\Delta x} (F(Q^n_j,Q^n_{j+1})-F(Q^n_{j-1},Q^n_j))$$


## Derivation in 1D:
1. Discretize in space:
   $N$ cells of size $\Delta x = 1/N$.
   Then $x_j = \frac{\Delta x}{2}+j\Delta x$ for all $j$.
   The spatial cell/subdomain is then $C_j:=  [x_{j-1/2}, x_{j+1/2}]=[(j-1)\Delta x, j \Delta x]$ 
2. Discretize in time:
   $t^n=n\Delta t$
3. Exact update formula:
   write down conservation law on $C_j$ scaled with $1/\Delta x$ and integrate over $C_j$:
$$
\begin{aligned}
0 & =\frac{1}{\Delta x} \int_{C_j} \partial_t u d x+\frac{1}{\Delta x} \int_{C_j} \partial_x f(u) d x \\
& =\frac{1}{\Delta x} \int_{C_j} \partial_t u d x+\frac{1}{\Delta x} \left[ f\left(u(x_{j+\frac{1}{2}}, t)\right)-f\left(u(x_{j-\frac{1}{2}}, t)\right) \right].
\end{aligned}
$$
4. Integrate in time:    $$\frac{1}{\triangle x} \int_{C_j} \mathbf{u}\left(x, t^{n+1}\right) d x=\frac{1}{\triangle x} \int_{C_j} \mathbf{u}\left(x, t^n\right) d x-\frac{1}{\triangle x} \int_{t^n}^{t^{n+1}} f\left(\mathbf{u}\left(x_{j+\frac{1}{2}}, t\right)\right)-f\left(\mathbf{u}\left(x_{j-\frac{1}{2}}, t\right)\right) dt$$
5. Define the approximation of the cell average of the quantity $u$: $$
Q_j^n \approx \frac{1}{\Delta x} \int_{C_j} \mathbf{u}\left(x, t^n\right) d x .
$$as well as the time average of the flux (depending on $Q_j^n$ and $Q_{j+1}^n$ )
$$
F\left(Q_j^n, Q_{j+1}^n\right) \approx \frac{1}{\Delta t} \int_{t^n}^{t^{n+1}} f\left(\mathbf{u}\left(x_{j+\frac{1}{2}}, t\right)\right) d t
$$
This yields the scheme shown above.
For higher dimensions, one has to use the divergence theorem after the integration over $C_j$.


## Conservation of $\int_\Omega u$
How does the approximation of the integral of $u$ over the domain $$\Delta x \sum_j Q_j^n$$ change in time?
First, denote $F_{j+1/2}^n:=F(Q_j^n,Q_{j+1}^n)$.
$$\Delta x \sum_j Q_j^{n+1} = \Delta x \sum_j Q_j^n + \Delta t \left(-\sum_j F_{j+1/2}^n + \sum_j F_{j-1/2}^n \right) $$
Now everything cancels out in the big paranthesis and we are left with:
$$\Delta x \sum_j Q_j^{n+1} = \Delta x \sum_j Q_j^n + \Delta t \left(F_{1/2}^n - F_{N+1/2}^n \right) $$
The quantity $u$ only changes if the flux across the domain boundaries is not zero.


## Different choices for the flux approximation:
- Lax-Friedrich scheme
$$F(U,V)=\frac{1}{2}\left(f(U)+f(V)-\frac{\Delta x}{\Delta t} (V-U)\right)$$
- Lax-Wendroff scheme
$$F(U,V)=\frac{1}{2}\left(f(U)+f(V)-\frac{\Delta x}{\Delta t} \frac{(f(V)-f(U))^2 }{V-U}\right)$$
- Roe scheme: #todo see HW3 of NDE lecture tornberg


## Source:
- Prof. Tornberg - Numerical solutions of differential equations, KTH lecture notes 2022, lecture 3
- https://en.wikipedia.org/wiki/Numerical_methods_for_partial_differential_equations

