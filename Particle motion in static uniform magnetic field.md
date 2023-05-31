Here, $v$ and $B$ are vector quantities.


## Circular motion
Motion of particle in static, uniform $B$ field, i.e. we want to solve
$$m \frac{dv}{dt} = q (v \times B),$$
the non relativistic limit case. Instead of solving the equation directly, lets understand the equation "qualitatively".
Variation of kinetic energy.
$$\frac{d}{dt}\left( \frac{mv^2}{2}\right) = mv \cdot \frac{dv}{dt}=mv\cdot \frac{q(v\times B)}{m}=0$$
due to orthogonality of the Lorentz force $q(v\times B)$ and $v$. Therefore
$$\vert v\vert^2=const$$
Useful decomposition of velocity:
$$v=v_p + v_n$$
where $v_p$ is parallel to $B$ and $v_n$ is normal to $B$. This gives three results:

1. Lets take the equation of motion and project it into the B-parallel direction:$$m\frac{dv}{dt}\cdot \frac{B}{\vert B\vert}=m\frac{dv_p}{dt}=q(v\times B)\cdot\frac{B}{\vert B\vert}=0 \implies v_p = const$$ again due to orthogonality.
2. Morover$$\vert v \vert^2 = \vert v_p\vert^2 +  \vert v_n\vert^2 \implies v_n=const$$
3. $\displaystyle \frac{dv_n}{dt}$ is normal to $v_n$ and $v_n$ is constant, which implies uniform motion $$\frac{m\vert v_n\vert^2}{r}=q\vert v_n\vert  \vert B\vert $$(due to "force balance"), where $r$ is the cyclotron radius (or "Larmor radius"), and where $\displaystyle\omega = \frac{v_n}{r}=\frac{q\vert B\vert}{m}$ is the cyclotron frequency.



## Magnetic moment
A charged particle moving in a $B$ field produces a current loop (current: $I$), and therefore a magnetic moment $\mu$:
$$\mu := I A = \frac{q \omega}{2\pi} \cdot \pi r^2= \frac{m \vert v_n \vert^2}{2B} = \frac{E_{kin,n}}{B}$$
The magnetic moment is defined analogous to the electric dipole moment, see [Electrostatic basics](Electrostatic%20basics.md). 
Direction is opposite to $B$. If $q>0$ movement follows left-hand-rule, and vice-versa for $q<0$.
![B-field-particlemotion-magneticmoment.png](B-field-particlemotion-magneticmoment.png)
Consequence: because of the particle motion, the external $B$ field will be reduced. This is called "diamagnetic property".

Morover, $\mu$ is an "adiapatic invariant". Consider the following: Analytical mechanics, tells us that the action, $\displaystyle J=\oint p dq$, of a coordinate q and momentum p, is constant (=adiabatic invariant) under a "slow" change in an external parameter (e.g. $B$).  




#todo reformulate that
We assumed that the motion is periodic if there is no change of an external parameter, and  $\displaystyle\oint$ is the integral over one period.
This is valid under the assumption that the motion is periodic if
there is no change of an external parameter
and we have indicated with this integral,
the integral over one period.
What does it mean?
Let's suppose that we have a motion of a particle that is periodic, for example, the motion of this particle in the presence of a magnetic field. Then we evaluate this integral, and we find that this integral is constant, even when you change slowly an external parameter that could be, for example, the magnetic field. Even when you change this external parameter slowly, then what you find is that although the trajectory of the particles can change because the magnetic field is changing, then this parameter, the action, will remain constant.
What we say is that that is an adiabatic invariant in the sense
that it will be constant if the change of the external parameter
is slow in comparison to the period, to the frequency of the
motion.




#TODO or do we check that $\mu$ is const?
Lets apply this to the particle motion and check if $J$ is constant: $q:=x$ , $p:=mv_x$ 
$$\begin{align}
J&=\oint mv_x dx = \oint m v_x \frac{dx}{dt}dt = \oint m v_x^2 dt \\&= \int_0^{2\pi/ \omega} m v_n^2 \sin^2(\omega t+ \phi) dt = \frac{\pi m v_n^2}{\omega} = \frac{2\pi m}{\vert q \vert} \frac{m v_n^2}{2B} = \frac{2\pi m}{\vert q\vert}\mu
\end{align}$$
which is $\mu$ times a constant factor.

Remark on how this is useful:
As $\mu$ is adiab. inv. and $\mu = m\vert v_n\vert^2 / 2B$ , one can e.g. predict an increase in $v_n$ if $B$ increases "slowly".




## Wikipedia definition
Wikipedia definition of "adiapatic invariant"
>A property of a physical system, such as the entropy of a gas, that stays approximately constant when changes occur slowly is called an adiabatic invariant. By this it is meant that if a system is varied between two end points, as the time for the variation between the end points is increased to infinity, the variation of an adiabatic invariant between the two end points goes to zero. See https://en.wikipedia.org/wiki/Adiabatic_invariant


## Sources
- EPFL - Introduction to Plasma Physics