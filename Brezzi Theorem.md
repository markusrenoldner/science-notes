The theorem provides unisolvence for mixed variational formulations (see [[Example mixed Finite Element formulations]]).

We consider $$\begin{align}
a(u,v):&V\times V\rightarrow \mathbb{R}  \\
b(u,q):&V\times Q\rightarrow \mathbb{R}\\
f(v):&V\rightarrow \mathbb{R}\\
g(q):&Q\rightarrow \mathbb{R}
\end{align}$$ with the problem to find $(u,p)$ s.t. $$\begin{align}
&a(u,v) + b(v,p) &=f(v) \quad \forall v\in V \\
&b(u,q)&=g(q)\quad \forall q\in Q
\end{align}.$$ One option to analyze this is to add the equations and view it as a problem on the space $V\times Q$: find $(u,p)$ s.t. $$\underbrace{a(u,v)+b(v,p)+b(u,q)}_{=:B((u,v),(v,q))}=f(v)+g(q).$$ But now we dont check the inf-sup condition (see [[Solvability of continuous and discrete variational problems]]) - we remember that the big bilinearform $B$ comes from a saddle point problem.


## Brezzi Theorem
Assume there holds
- $a:V\times V\rightarrow \mathbb{R}, \quad b:V\times Q\rightarrow \mathbb{R}$ are continuous
- $a$ is coercive on Ker $[b(.,.)]$
- The "LBB-condition" holds, i.e. $$\sup_u \frac{b(u,q)}{\Vert u\Vert}\geq \Vert q \Vert \quad \forall q \in Q$$
Then, the given saddle point problem is unisolvent and the solution depends continuously on the data, i.e. $\Vert u\Vert+\Vert p\Vert \prec \Vert f\Vert\Vert g\Vert$ 

(No proof.)


## Approximation of Mixed methods
Problem is to find $(u_h,p_h)$ s.t. $$B((u_h,v_h),(v_h,q_h))=f(v_h)+g(q_h)\quad \forall v_h,q_h \in V_h,Q_h.$$
The cont. inf-sup condition (see [[Solvability of continuous and discrete variational problems]]) does not imply the discrete inf-sup condition! One could check the discrete inf-sup condition. If this is fulfilled, it also implies the non-degeneracy condition and one has the Cea-type Lemma stated in [[Solvability of continuous and discrete variational problems]]. All of this implies a best-approximation property for $B$: $$\Vert u-u_h\Vert_V + \Vert p-p_h\Vert_Q  \prec \inf_{v_h,q_h} \left(\Vert u-v_h\Vert_V +\Vert p-q_h\Vert_Q \right).$$
This is all nice, but usually people prefer checking the Brezzi theorem on the discrete level, where the continuity condition is inhertied from the continuous level.
The kernel-coercivity has to be checked similarly as in the continuous setting.
The LBB condition can be checked by constructing a "Fortin operator":

Assume there exists a cont. Fortin operator $\Pi_h:V\rightarrow V_h$ with the property $b(\Pi_h v,q_h)=b(v,q_h)$, then the discrete LBB is inhertied from the cont. LBB.

Proof.$$\sup_{v_h} \frac{b(v_h,p_h)}{\Vert v_h \Vert} \leq \sup \frac{b(\Pi_h v_h,p_h)}{C\Vert \Pi_h v_h \Vert} \leq \sup \frac{b(v,p_h)}{C\Vert v\Vert} \stackrel{cont.LBB}{\prec} \Vert p_h\Vert$$
Sometimes it is easier to construct a $\Pi_h$, than to check inf-sup etc.


## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
