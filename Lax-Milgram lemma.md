# Lax-Milgram lemma
Shows unisolvence of continuous and discrete [[Variational problem]]s with continuous and coercive bilinearform. 
See [[Solvability of variational problems]].

## Definitions

A bilinearform $a(.,.)$ is coercive,     if $\exists \alpha_1 \in \mathbb{R}$, s.t. $a(u,u)\geq \alpha_1 \Vert u\Vert ^2 \quad \forall u.$ 
A bilinearform $a(.,.)$ is continuous if $\exists \alpha_2 \in \mathbb{R}$, s.t. $a(u,v) \leq \alpha_2 \Vert u\Vert \Vert v \Vert\quad \forall u,v.$

Continuity of a blf can usually be shown using the Cauchy Schwarz inequality.


## Main statement
Let $V$ be Hilbert space, $a(.,.)$ coercive and continuous bilinearform, $f(.)$ cont. Then the problem to find $u$ s.t. 
$$a(u,v)=f(v) \quad \forall v$$
is unisolvent. Moreover:
$$\|u\| \leq \alpha_1^{-1}\|f\|$$
where $f$ is measured in the dual norm $\|f\| \equiv \sup _{v} \frac{l(v)}{\|v\|}$.

See proof in faustmann


## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021

