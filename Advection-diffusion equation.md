# Advection-diffusion equation
also: "convection-diffusion equation".

An example of a [[Conservation law, transport equation]], that combines the [[Advection equation]] and [[Diffusion equation]].


The general equation is
$$
\frac{\partial c}{\partial t}=\nabla \cdot(D \nabla c)-\nabla \cdot(\mathbf{v} c)+R
$$
where
- $c$ is the variable of interest (species concentration for mass transfer, temperature for heat transfer),
- $D$ is the diffusivity (also called diffusion coefficient), such as mass diffusivity for particle motion or thermal diffusivity for heat transport,
- $\mathbf{v}$ is the velocity field that the quantity is moving with. It is a function of time and space. For example, in advection, $c$ might be the concentration of salt in a river, and then $\mathbf{v}$ would be the velocity of the water flow as a function of time and location. Another example, $c$ might be the concentration of small bubbles in a calm lake, and then $\mathbf{v}$ would be the velocity of bubbles rising towards the surface by buoyancy (see below) depending on time and location of the bubble.


## Derivation 
take the [[Conservation law, transport equation]] a flux of the form
$$f(c) = f_{conv} + f_{diff}= -D\nabla c + \boldsymbol{v}c$$
and we are done.


## Source
https://en.wikipedia.org/wiki/Convection%E2%80%93diffusion_equation