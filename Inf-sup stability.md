# Inf-sup stability
Shows unisolvence of continuous and discrete [[Variational problem]]s with an inf-sup stable bilinearform .
See [[Solvability of variational problems]].


## Motivation: 
there are bilinearforms, that are not coercive and continuous and still yield a unisolvent [[Variational problem]]. 
Example: $$B(u,v)=u_1 v_1 - u_2 v_2 $$ is not coercive, but there is a unique solution to $$B(u,v)=f\cdot v \quad \forall v,$$which is: $$u=(f_1, -f_2)^\intercal.$$

## Inf-sup condition
General (non-coercive) bilinearforms, denoted by $B(.,.)$, are called "inf-sup stable" if$$\inf_u \sup_v \frac{B(u,v)}{\Vert u\Vert_V \Vert v\Vert_W}\geq \beta \quad u\in V,v\in W.$$Coercivity implies inf-sup stability.

Reformulate this as operator $B:V\rightarrow W^*$ with $\langle B u,v\rangle_{W^*\times W}=B(u,v)$, which yields the inf-sup condition as $$\sup_v \frac{\langle Bu,v\rangle}{\Vert v\Vert}\geq \beta \Vert u\Vert  \quad \forall u$$
We can see that an inf-sup stable $B$ is injective:
- by definition there holds $Bu=0 \implies u=0$
- and therefore, we get the following: $B(a)=B(b)\implies B(a)-B(b)=0\implies B(a-b)=0 \implies a=b$
The second relation is injectivity.

To get an invertible/unisolvent problem, we would like to have $B$ being bijective. 


We could turn around the inf-sup condition ("sup-inf"), or we ask for the (less restrictive) "non-degeneracy condition"/NDC: $$\sup_u\frac{B(u,v)}{\Vert u\Vert\Vert v\Vert}> 0\quad \forall v$$Coercivity also implies NDC.

The result is: inf-sup stable and NDC fulfilling bilinearforms yield a unisolvent [[Variational problem]] and we have continuous dependence on the data $$\Vert u\Vert \leq \beta^{-1} \Vert f\Vert$$

## Discrete inf-sup condition
Solvability is not inherited into discrete setting (!!!)
so we pose a discrete inf-sup condition:$$\inf_{u_h} \sup_{v_h} \frac{B(u_h,v_u)}{\Vert u_h\Vert\Vert v_h\Vert}\geq \beta_{1h}$$ We dont need a discrete NDC. ("On a finite dimensional space, one to one is equivalent to onto, and therefore the discrete inf-sup condition already implies the non-degeneracy condition.")
The discrete inf-sup cond., like before, implies unisolvence.


## Sources
- Section 6.1 of Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
- https://math.stackexchange.com/questions/2030380/proof-that-a-linear-transformation-is-injective-iff-its-null-space-is-trivial
- https://math.stackexchange.com/questions/3977138/why-is-linear-map-injectivity-defined-solely-using-the-null-space
