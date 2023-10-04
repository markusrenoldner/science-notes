also: de Rham complex

#unlinked 


## Main idea:
It holds that:
$$
\begin{array}{cccccccc}
H^1(\Omega) & \stackrel{\nabla}{\longrightarrow} & H(\operatorname {curl},\Omega) & \stackrel{\operatorname{curl}}{\longrightarrow} & H(\operatorname{div},\Omega) & \stackrel{\operatorname{div}}{\longrightarrow} & L^2(\Omega) \\
\text{ }\downarrow^{I^{P1}} & & \downarrow^{I^{ND}} & & \downarrow^{I^{RT0}} & & \text{ }\downarrow^{I^{P0}} \\
X^{P1}(\Omega) & \stackrel{\nabla}{\longrightarrow} & X^{ND}(\Omega) & \stackrel{\operatorname{curl}}{\longrightarrow} & X^{RT0}(\Omega) & \stackrel{\operatorname{div}}{\longrightarrow} & X^{P0}(\Omega)
\end{array}
$$
For simply-connected domains:
- Gradients of $H^1(\Omega)$-functions are element of $H(\operatorname{curl},\Omega)$, as the curl of any gradient is $0$ and therefore square-integrable and therefore also element of $H(\operatorname{curl},\Omega)$.
- Curls of $H(\operatorname{curl},\Omega)$ functions are element of $H(\operatorname{div},\Omega)$ as the divergence of any curl is $0$ and therefore also square-integrable and hence an element of $H(\operatorname{div},\Omega)$.
- By definition the divergence of an $H(\operatorname{div},\Omega)$ function is square integrable, which is the last property of the de Rham squence.

A simply connected domain has the property that any path between two endpoints is completely inside of the domain and can be transformed into any other path on the domain by a continuous map while preserving the endpoints.


## Summary in 1 sentence:
This can be summarized: The kernel of the right differential operator is exactly the range of the left one.


## Range and kernel
As an example:
$$\operatorname{range}(\nabla) = \operatorname{ker}(\operatorname{curl})$$
with 
$$\begin{aligned}
\operatorname{range}(\nabla)&:=\{\boldsymbol{u}\in H(\operatorname{curl},\Omega):\boldsymbol{u}= \nabla p, p \in H^1(\Omega)\},\\
\operatorname{ker}(\operatorname{curl}) &:= \{\boldsymbol{u}\in H(\operatorname{curl},\Omega):\operatorname{curl}\boldsymbol{u}=0\}.
\end{aligned}
$$


## De Rham sequence with essential boundary conditions
$$
\textcolor{red}{H}^1_{\textcolor{red}{0}}(\Omega) \stackrel{\nabla}{\longrightarrow}\textcolor{red}{H_0}(\operatorname{curl} , \Omega) \stackrel{\operatorname{curl}}{\longrightarrow}\textcolor{red}{H_0}(\operatorname{div} , \Omega) \stackrel{\operatorname{div}}{\longrightarrow} \textcolor{red}{L}^2_{\textcolor{red}{0}}(\Omega)$$
Source: S. Zaglmayr, “High Order Finite Element Methods for Electromagnetic Field Com-  
putation”, 2006



