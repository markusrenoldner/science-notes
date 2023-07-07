We consider charged particles, relevant in [[Plasma, Magnetohydrodynamics (MHD)]].
For motion in static, uniform B-fields: [[Particle motion in static uniform magnetic fields]]


## $E,B$ constant
We want to solve a Newton equation with forces due to constant $E$ and $B$ fields:$$m \partial_t v = q (e + v\times B)$$
- Parallel to $B$-field (indicated with index $p$): $m \partial_t v = qE_p \implies$ uniform acceleration
- Normal to $B$-field (indicated with index $n$): $m\partial_T v = q(E_n + v_n \times B )$ 

Qualitatively, this will happen:
![[particle-drift.png]]
While moving against the $E$ field, the positive particle will slow down and the Lamor/cyclotron radius will decrease locally, therefore the drift (and vice versa for the negative particle).
But: both positively and negatively charged particles will drift in the same direction!

Lets compute the drift: we average over one gyroperiod (denoted with brackets)
for that we take the equation for the normal velocity and set the acceleration to $0$, as we assume the drift is constant (otherwise one would have to solve the diff-equ for $v_n$ and show that this assumption is allowed)
$$\left \langle m \partial_t v \right \rangle = 0 = q \left \langle E_n + v_n \times B  \right \rangle \implies \left \langle v_n \right \rangle\times B = -E_n$$
we cross with $B$ and use some vector algebra to get an expression for $v_n$:
$$\left \langle v_n \right \rangle\times B \times B = - \left \langle v_n \right \rangle B^2 = -E_n \times B \implies \left \langle v_n \right \rangle =:v_e = \frac{E_n\times B}{B^2},$$
which does not depend on the charge and is normal to $E$ and $B$.

Now lets find the gyromotion:
We write
$$\begin{align}
    v_n = v_e + v_n' \implies \partial_t (v_e + v_n') &= m \partial v_n' = q(E_n+ v_e \times B + v_n' \times B) \\
    &= qE_n + q\underbrace{\frac{e_n\times B}{B^2}}_{-q E_n} \times B + q v_n' \times B \\
    &= q v_n' \times B
\end{align}$$

Here $v_n'$... difference between $v_n$ and $v_e$

Conclusion:
- drift is $v_e = \frac{E_n \times B}{B^2}$ and is called $E cross B drift"
- the "EcrossB drift" is independent of $q$
- particle motion is along isocontour lines of electrostatic potential (=normal to $E$)

Qualitatively (isocontourlines of electrostat. potential in orange):
![[particlemotion-potential-isocountour.png]]

We extend this result to general external forces $F$ (e.g. the gravity force), and get $$m\partial_t v = f+ qv\times B \implies v_e = \frac{F\times B}{qB^2}$$ which is now dependent on $q$!


## Application: gravity
Will the particle follow the direction of the gravity force? 
It seems, no they dont. Like before the velocity is normal to $F$ and $B$. But, positive and negative particles will drift in different directions, which itself will create an electric field, as visisble below. This electric field is the reason why the particles will still follow the direction of the gravitational field!
![[plasma-under-gravity.png]]
## Application: curvature drift
Assume a "curved" $B$-field. Particles will follow field line. The centrifugal force is $$F_C = \frac{m v_p^2}{R^2_B} R_B$$ and therefore the drift is $$v_d = \frac{F_C\times B}{q B^2}=\frac{m v_p^2}{qB^2 R_B^2}(R_B\times B)$$ it is called "curvature drift".



## Non-uniform $B$-field with $\nabla B \perp B$ ("grad-B drift")
Assume $\nabla B \perp B$. 
Qualitatively, we will have this motion (due to the non-uniform B-field, the cyclotron radius varies):
![[grad-B-drift.png]]
Without derivation, we get $$v_{\nabla B} = \frac{m}{2B^3} \frac{v_0^2}{q} (B\times \nabla B)$$ it is known as the "grad-B drift".
It holds under the assumption, that "the characteristic scale over which $B$ varies is much larger than the cyclotron radius": $\frac{B}{\nabla B}>>\rho$
Further, $v_0$ is the part of the velocity, that satisfies the equation of motion under the dominating, constant part of the $B$ field.


## Conclusion:
Particle motion in electromagnetic field is superposition of a drift and a gyromotion.


## Sources
- EPFL - Introduction to Plasma Physics, lecture 1e)