[[Fluid Dynamics]]
[[Material derivative]]


In the Eulerian specification of a field $u$, the field i sdescribed as a function of time and position $$u(x,t)$$In the Lagrangian specification, single particles of the field $u$ are followed through time. These particles are labeled by their initial position $x_0$ at the initial time $t_0$. Therefore, the flow is then described by a function$$X(x_0, t)$$that gives the position of a particle at location $x_0$ at any time $t$. The velocity of a particle is then$$u(X(x_0,t),t)=\frac{\partial X(x_0,t)}{\partial t}$$
The relation between the Lagrangian coordinates $(x_0, t)$ and the Eulerian coordinates $(x,t)$ is$$x=X(x_0,t)\quad \text{at time } t$$The rate of change of a quantity $\phi$ "experienced" by a particle with initial location $x_0$ is then
$$\begin{aligned}
\frac{d \phi(x_0,t)}{d t} &=  \frac{\partial \phi}{\partial X}\frac{\partial X}{\partial t} + \frac{\partial \phi}{\partial t}\\
&= 
\end{aligned}$$
#todo 


## Source
- https://en.wikipedia.org/wiki/Lagrangian_and_Eulerian_specification_of_the_flow_field