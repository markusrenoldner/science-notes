# Consistency finite differences vs finite elements
[[Finite Element Method (FEM)]]
[[Finite Difference Method (FDM)]]
[[Lax equivalence theorem]]


## Question from Stackexchange
Whether a discretisation is consistent (and the order of consistency) in the FDM setting is defined by the truncation term, e.g.:

$$\partial_{xx}u_i=\frac{1u_{i-1}-2u_i+1u_{i+1}}{h^2}+\mathcal(O)(h^2)$$
where $u_i=u(x_i)$.

For instance we cannot construct a consistent (wrt the above definition) scheme for the Laplace operator $\Delta=\nabla^2$ in 2D with a 4-stencil (=scheme that evaluates at 4 different $x_i$), and instead at least a 5-stencil is required. This is not the case for [[Finite Element Method (FEM)]], as it is perfectly fine to have P1 elements where some inner vertex has only 3 neighbours (corresponding to a 4-stencil, and one can indeed perform the Taylor expansion to verify that the scheme is not consistent wrt the definition for FDM). Instead bounds on the error can be derived per element (e.g. Larson-Bengzon) and in general guaranteeing consistency (for an appropriate mesh).

I am looking for references connecting the two, e.g. applying the FEM analysis to some "inconsistent" FDM stencils, that nevertheless lead to convergence (e.g. are consistent w.r.t. the FEM formulation)?


## Answer from Stackexchange
I think this question may lead to a lot of confusion, as there are different notions of consistency for FDM and FEM. For instance when one thinks of FEM consistency, it is often Galerkin orthogonality (see [[Finite Element Method (FEM)]]). 

The question is probably not very good. After all in FDM we do not define basis functions, and thus consistency in terms of orthogonality is probably a stretch there.


## Source
https://math.stackexchange.com/questions/4325853/consistency-finite-differences-vs-finite-elements