
[[0_UNLINKED]]


## Equilibrium models and quadratic functionals
Solutions of certain physical problems like e.g.
- Shape of elastic membranes
- Static electric fields
fulfil equilibrium conditions. The mentioned cases both minimize a certain energy. In case of the membrane, this is the potential energy, defined as a quadratic functional
$$J[u]:= \int_\Omega \frac{1}{2}\sigma(x) ||\operatorname{grad} u(x)||^2 - f(x)u(x) dx$$
with $x\in \mathbb{R}^n$ being the position, $u$ the vertical displacement of the membrane, $\sigma$ the stiffness coefficient, the squared gradient of $u$ is the elastic energy and the second term is the potential energy in the force field $f$.

The solution is then
$$u = \operatorname{argmin}_{v\in \hat{V}} J[v]$$
where $\hat{V}$ is the "configuration space" (space of possible solutions)
$$\hat{V} := \{u:\overline{\Omega} \mapsto \mathbb{R}, u\text{ continuous }, u|_{\partial \Omega}=g \}$$


## Quadratic minimization problems with bilinearforms
$J$ can be reformulated:
$$J[u] := \frac{1}{2} a(u,u) - l(u) + c $$
with $u\in V_0$, $a$ being a symm. bilinearform, and $l$ being a linearform. Finding the solution of such a functional in a vector space $V$ is a quadratic minimization problem. For this class of problems, unique solutions exist for certain types of $J$.


## Affine space and offset function trick
The fact that the boundary condition $u|_{\partial \Omega}$ has to be fulfilled implies that the zero function is not element of the space $\hat{V}$, which is therefore not a vector space. It is an [[Affine space]].

One can recover a proper quadr. min. probl. from the membrane problem:
For a quadr. functional $J:=\frac{1}{2}a(v,v)-l(v)$ defined on a vector space we have:

![[quadr-functional-affine-space.png]]

therefore, the minimizer of $J$ over the affine subspace $u_0 + V_0$, with $V_0 \subset V$ can be computed like this:
$$\operatorname{argmin}_{u\in u_0+V_0} J[u] = u_0 + \operatorname{argmin}_{v\in V_0} J[v+u_0] $$
with $J[v+u_0] = \frac{1}{2} a(v,v) + \tilde{l}(v) + \tilde{c}$. This is a quadr. min. problem over a proper vector space $V_0$. This is great, as the technique allows to have non-zero boundary conditions while using the solution theory of quadratic functionals.

Because
$$u = u_0 + v$$
you get
$$\operatorname{argmin}_{u} J[u] = u_0 + \operatorname{argmin}_{v} J[v+u_0]$$
#TODO why add u_0 to argmin AND add u_0 to v inside J ?


## Positive definite bilinearforms => unisolvence
See: [[Unisolvence of quadratic minimzation problem]]


## The offset function $u_0$
... can be any function satisfying the boundary condition:
$$u_0 |_{\partial \Omega} = g$$
so we might as well chose the simplest function: For a scalar problem, this is an affine linear function.


## Source
- Prof. Hipmair - Numerical Methods for Partial Differential Equations