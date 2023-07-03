#unlinked 


For sufficiently smooth functions and the curl operator, there holds integration by parts
$$
\int_{\Omega}(\nabla \times \boldsymbol{u}) \cdot \boldsymbol{v}=\int_{\Omega} \boldsymbol{u} \cdot(\nabla \times \boldsymbol{v})-\int_{\partial \Omega}(\boldsymbol{v} \times \boldsymbol{u}) \cdot \boldsymbol{n} .
$$

Proof. We start with the following vector identity in $\mathbb{R}^3$
$$
\nabla \cdot(\boldsymbol{v} \times \boldsymbol{u})=\boldsymbol{u} \cdot(\nabla \times \boldsymbol{v})-\boldsymbol{v} \cdot(\nabla \times \boldsymbol{u}) .
$$
Integrating the above expression over the domain yields
$$
\int_{\Omega}(\nabla \times \boldsymbol{u}) \cdot \boldsymbol{v}=\int_{\Omega} \boldsymbol{u} \cdot(\nabla \times \boldsymbol{v})-\int_{\Omega} \nabla \cdot(\boldsymbol{v} \times \boldsymbol{u}) .
$$
Now one can apply Gauss' divergence theorem to the last term and get the above statement.

