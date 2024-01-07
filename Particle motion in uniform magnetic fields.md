# Particle motion in uniform magnetic fields
We consider charged particles, relevant in [[Plasma physics]].
Here, $v$ and $B$ are vector quantities. $B$ is constant and uniform.

Non-relativistic motion of particle in static, uniform $B$ field
$$m \frac{dv}{dt} = q (v \times B),$$
Variation of kinetic energy
$$\frac{d}{dt}\left( \frac{mv^2}{2}\right) = mv \cdot \frac{dv}{dt}=mv\cdot \frac{q(v\times B)}{m}=0 \implies \vert v\vert^2=const$$
due to orthogonality. Decomposing $v$ in parallel/normal direction to $B$ gives:
1. Equation of motion projected into B-parallel direction:$$m\frac{dv}{dt}\cdot \frac{B}{\vert B\vert}=m\frac{dv_\parallel}{dt}=q(v\times B)\cdot\frac{B}{\vert B\vert}=0 \implies v_\parallel = const$$
2. Therefore $$\vert v \vert^2 = \vert v_\parallel\vert^2 +  \vert v_\perp\vert^2 \implies | v_\perp|=const$$
3. $\displaystyle \frac{dv_\perp}{dt} \perp v_\perp$ and $|v_\perp|=const$ implies uniform circular motion $$\frac{m\vert v_\perp\vert^2}{r}=m|\omega|^2 r=q\vert v_\perp\vert  \vert B\vert $$ where $r$ is the cyclotron/Larmor radius and $\omega$ the corresponding frequency.




## Sources and a more detailed derivation:
- EPFL - Introduction to Plasma Physics, lecture 1d)
- https://en.wikipedia.org/wiki/Adiabatic_invariant