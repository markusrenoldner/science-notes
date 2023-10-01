interestingly, [[Minima of functionals solve variational problems]]


## Energy minimzation in physics
Solutions of certain physical problems like e.g.
- Shape of elastic membranes
- Static electric fields
minimize a certain energy. In case of the membrane, this is the potential energy, defined as a quadratic functional
$$J[u]:= \int_\Omega \frac{1}{2}\sigma(x) ||\operatorname{grad} u(x)||^2 - f(x)u(x) dx$$
with $x\in \mathbb{R}^n$ being the position, $u$ the vertical displacement of the membrane, $\sigma$ the stiffness coefficient, the squared gradient of $u$ is the elastic energy and the second term is the potential energy in the force field $f$. The solution is then
$$u = \operatorname{argmin}_{v\in \hat{V}} J[v]$$
where $\hat{V}$ is the "configuration space" (space of possible solutions)
$$\hat{V} := \{u:\overline{\Omega} \mapsto \mathbb{R}, u\text{ continuous }, u|_{\partial \Omega}=g \}$$


## Generalization with bilinearforms
$J$ can be reformulated:
$$J[u] := \frac{1}{2} a(u,u) - l(u) + c $$
with $u\in V_0$, $a$ being a symm. bilinearform, and $l$ being a linearform. Finding the solution of such a functional in a vector space $V$ is a quadratic minimization problem. For this class of problems, unique solutions exist for certain types of $J$.


## Offset function trick for quad. min. problem
The fact that the boundary condition $u|_{\partial \Omega}$ has to be fulfilled implies that the zero function is not element of the space $\hat{V}$, which is therefore not a vector space. It is an [[Affine space]].

One can recover a proper quadr. min. probl. from the membrane problem:
For a quadr. functional $J:=\frac{1}{2}a(v,v)-l(v)$ defined on a vector space we have:

![[quadr-functional-affine-space.png]]
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


## Necessary cond. for existence of minimizer
$a$ is pos semidefinite, if
$$a(u, u) ≥ 0 \quad∀u ∈ V_0$$
The quadr. func 
$$J[v]=\frac{1}{2}a(v,v)-l(v)$$
on a vector space V is bounded from below only if $a$ is positive semidefinite.


## Uniqueness of solution
$a$ is pos definite if
$$u ∈ V_0 \backslash \{0\} ⇐⇒ a(u, u) > 0 $$

![[unisolvence-quadrminprobl.png]]


## Boundedness condition on linear form
The following shows that the linear form $l$ has to match the bilinear form $a(·, ·)$ to make the existence of a minimizer of $J$ possible. The functional 
$$J[v]=\frac{1}{2}a(u,u)-l(u)+c \quad u\in V_0$$
based on a symm. pos. def. blf. $a$ is bounded from below if and only if ($\iff$) 
$$\exists C>0 : \quad \vert l(u)\vert<C\Vert u\Vert_a \quad \forall u \in V_0$$
where $\Vert u\Vert_a$ is the [[Energy norm]]. This is a necessary condition for $l$.



## Existence of unique sol in finite dimensions
![[minimizer-existence-finitedim.png]]


## Source
- Prof. Hipmair - Numerical Methods for Partial Differential Equations