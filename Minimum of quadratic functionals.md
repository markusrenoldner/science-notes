
... are equivalent to [Variational formulation, variational problem](Variational%20formulation,%20variational%20problem.md), as explained here [Equivalence of minimization of quadr. functional and var. problem](Equivalence%20of%20minimization%20of%20quadr.%20functional%20and%20var.%20problem.md)


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


## Reformulation/generalization with bilinearforms
$J$ can be reformulated:
$$J[u] := \frac{1}{2} a(u,u) - l(u) + c $$
with $u\in V_0$, $a$ being a symm. bilinearform, and $l$ being a linearform. Finding the solution of such a functional in a vector space $V$ is a quadratic minimization problem. For this class of problems, unique solutions exist for certain types of $J$.


## Same problem on affine space ("offset function trick")
The fact that the boundary condition $u|_{\partial \Omega}$ has to be fulfilled implies that the zero function is not element of the space $\hat{V}$, which is therefore not a vector space. It is an [Affine space](Affine%20space.md) 

One can recover a proper quadr. min. probl. from the membrane problem:
For a quadr. functional $J:=\frac{1}{2}a(v,v)-l(v)$ defined on a vector space we have:

![quadr-functional-affine-space.png](quadr-functional-affine-space.png)
Attention: "g" is called "$u_0$" in this picture.

Because of the picture above and the fact that
$$u = g + v$$
you get that theminimizer of $J$ over the affine subspace $g + V_0$, with $V_0 \subset V$ can be computed like this:
$$\operatorname{argmin}_{u\in g+V_0} J[u] = g + \operatorname{argmin}_{v\in V_0} J[v+g] $$
with $J[v+g] = \frac{1}{2} a(v,v) + \tilde{l}(v) + \tilde{c}$,

where the right argmin minimizes over v, the argument of this right argmin is u expressed in terms of v and g, but because you only minimize over v, you add u_0 so that u=g+v is fullfilled
this is why add g to argmin AND add g to v inside J.

This is a quadr. min. problem over a proper vector space $V_0$. This is great, as the technique allows to have non-zero boundary conditions while using the solution theory of quadratic functionals.

The offset function g can be any function satisfying the boundary condition. Sso we might as well chose the simplest function: For a scalar problem, this is an affine linear function.



## Solvability and uniqueness

a is pos. semi definite if
$$a(u, u) ≥ 0 \quad∀u ∈ V_0$$
a is pos definite if
$$u ∈ V_0 \backslash \{0\} ⇐⇒ a(u, u) > 0 $$
#### Necessary cond for existence of minimizer
The quadr. func 
$$J[v]=\frac{1}{2}a(v,v)-l(v)$$
on a vector space V is bounded from below only if a is positive semidefinite.

![unisolvence-quadrminprobl.png](unisolvence-quadrminprobl.png)
>In Cor. 1.2.3.26 and Thm. 1.2.3.31 we found necessary conditions on the bilinear form a for the existence of a minimizer of an abstract quadratic minimization problem. Now we answer the questions whether the linear functional ℓ also has to satisfy some conditions.
>
>The following insight demonstrates that the linear form ℓ has to match the bilinear form a(·, ·) to make possible to existence of a minimizer of J:

#### Boundedness condition on linear form
The functional 
$$J[v]=\frac{1}{2}a(u,u)-l(u)+c \quad u\in V_0$$
based on a symm. pos. def blf a is bounded from below if and only if ($\iff$) 
$$\exists C>0 : \quad \vert l(u)\vert<C\Vert u\Vert_a\vert \quad u \in V_0$$
where $\Vert u\Vert_a$ is the [Energy norm](Energy%20norm.md). This is a necessary condition for $l$.


![minimizer-existence-finitedim.png](minimizer-existence-finitedim.png)





## Source
- Prof. Hipmair - Numerical Methods for Partial Differential Equations