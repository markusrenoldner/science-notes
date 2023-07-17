A method from [[Numerics for differential equations]]. 


## Motivation: deriving a suitable PDE problem for BEM
Problem: find G for
$$-\Delta u=\delta$$
with $\delta$ being the Dirac distribution. Then the fundamental solution/Greens function is
$$G(x,z)=\begin{cases}
-\frac{1}{2\pi}log(x-z),& d=2\\
\frac{1}{4\pi} \frac{1}{|x-z|},& d=3
\end{cases}$$
depending on the dimension $d$ of the domain.

Solution formula (without derivation here) for $u$:
$$u(x)=\underbrace{\int G(x-z)f(z) dz}_{=:Nf} + \underbrace{\int_{\partial\Omega} G(x-z) \overbrace{\partial_N u(z)}^{\phi} ds}_{=:V\phi} + \underbrace{\int_{\partial\Omega} \partial_n G(x-z) u(z) ds}_{=:Ku (=Kg)}$$
The second integral contains the Neuman BC., the third one the Dirichlet BC.
$N,V,K$ are integral operators and $\phi$ is the Neuman data.

Only now, assume its a Dirichlet problem, we know the Dirichlet BC: $u\vert_{\partial\Omega} = g$. So we know the third integral, but not the Neuman data/the second integral.

Now take the trace of this formula:
$$g=u\vert_{\partial\Omega} = \left(Nf+V\phi+Kg\right)\vert_{\partial\Omega}$$
or putting all known objects to the right (called $\hat g$):
$$V\phi\vert_{\partial\Omega}\equiv\operatorname{tr} V\phi = \hat g$$
Or written as an integral equation, the problem is to find $\phi$ st.
$$\int_{\partial\Omega} G(x-z)\phi(z)ds = \hat g$$
We have reformulated the PDE to an integral equation. Applying [[Finite Element Method (FEM)]] to this problem is called Boundary Element Method (BEM).


## BEM:
Take the problem from above, multiply with testfunctions $\psi$ and integrate over ${\partial\Omega}$:
$$\underbrace{\int_{\partial\Omega} V\phi \psi ds}_{=:A(\phi,\psi)} = \int_{\partial\Omega} \hat g \psi ds$$
the right function space would be the dual space $(V:= H^{\frac{1}{2}})^*$. We can even apply the [[Lax-Milgram lemma]] to show unisolvence.
Now we use a mesh on ${\partial\Omega}$ and use e.g. piecewise constant polynomials:
$$A(\phi_h,\psi_h) = (f,\psi_h)\quad \forall \psi_h\in V_h$$


## Error estimate (no proof):
we get
$$\vert\vert\vert\phi-\phi_h\vert\vert\vert\leq Ch^{\frac{3}{2}}\vert\vert\nabla \phi\vert\vert_{L^2}$$
where the first norm is the canonical [[Energy norm]] for the unknown $\phi$. This convergence is better than the order-1 convergence that is achieved in regular FEM.


## Summary:
Use properties from fundamental solutions of a PDE to change a PDE to an integral equation.
For this we can then use the [[Finite Element Method (FEM)]].

Benefits are:
+ better convergence order
+ dimension reduction by 1 (from $\Omega\subset\mathbb{R}^d$ to $\partial\Omega\subset\mathbb{R}^{d-1}$)
+ we can deal with unbounded problems! Huge benefit! Example: wave scattering problems, like Radar signals that are incoming from "infinity", reflecting at a boundary of an object and wave goes back to infinity. We reduce the problem to what happens on the boundary of the object

Drawbacks are:
- Really complicated to compute $$\left\langle V\phi_h,\psi_h \right\rangle=\int_{\partial\Omega} \left(\int_{\partial\Omega} G(x-z)\phi(z)ds \right) \psi(x)ds$$ as 1) it is a double integral and 2) $G$ can be inifinite, so we need very elaborate numerical integration techniques
- $V$ is a "nonlocal" operator, which implies $A$ is dense, that means we can not compute as many degrees of freedom as in classical FEM


## Overcoming the drawbacks:
Approximate $A$ by a sparse matrix $A_h^r$:
- which should be cheaply computable and invertible.
- and the error should be "exponential", i.e.: $\Vert A-A_t^r\Vert \leq e^{-br}$

This is done by decomposing $A$ into submatrix blocks ("block decomposition"). The diagonal is computed exactly (i.e. we compute the double integral), but the offdiagonal blocks are approximated by interpolationg of $G$. Prof. Faustmann proved, that this decomposition also works for $A^{-1}$.


## Source:
- Prof. Faustmann
