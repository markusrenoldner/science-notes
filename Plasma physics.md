a field that describes ionized Fluids/Plasmas.
it incorporates indeas from [[Electrodynamics]]

## Where to find plasmas
![[MHD_plasma_paramterspace.png]]


## Definition of a plasma
Plasma is an ionized, globally neutral (="quasi neutral") gas that displays collective effects.

To understand that, we need 3 definitions:
- [[Plasma Debye length]]
- [[Plasma frequency]]
- [[Plasma collision frequency]]

The definition above implies the following:
- globally neutral $\implies$ size of plasma larger than Debye length
- collective effects
	- $\implies$ one-to-one interactions weak, $N_D>>1$ 
	- $\implies$ $\displaystyle\frac{\omega_{pe}}{\nu_{col}} = \sqrt{\frac{n_0 e^2}{\epsilon_0 m_e}} \frac{1}{n_{e} \cdot \pi b^2 \cdot  \nu_{th,e}}= \dots =16\pi N_D$  which is "large". That means, the plasma frequency is larger than the collision frequency


## Motion of single particles
In uniform B-field, particles experience gyromotion: [[Particle motion in uniform magnetic fields]]

In E field, motion is a superposition of drift and gyromotion.
- [[E cross B drift]]
- [[Curvature drift]]
- [[Grad B drift]]

Plasma confinement strategies based on the understanding of gyromotion and drifts is discussed in [1].


## Kinetic description of plasma
Instead of single particles, we have to study many particles that itself influence the $B$ and $E$-fields, using statistical methods.
- [[Kinetic plasma model, Boltzmann equation]]
- [[Vlasov equation]]

## Fluid description of plasma
the kinetic model is very accurate, but sometimes too complex.
the fluid model is 3dimensional instead of 6dimensional
its incorporates ideas from [[Fluid Dynamics]]

[[Plasma fluid models and MHD]]


## Sources
1. EPFL - Introduction to Plasma Physics
2. McGreivy -General Plasma Physics, Princeton lecture notes 2017