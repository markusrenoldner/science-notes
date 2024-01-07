# E cross B drift

We consider charged particles, relevant in [[Plasma physics]].
For motion in static, uniform B-fields: [[Particle motion in uniform magnetic fields]]

Constant, non-parallel $E/B$-fields cause a particle drift in the $E\times B$-direction.

Qualitatively, this will happen:
![[particle-drift.png]]
While moving against the $E$ field, the positive particle will slow down and the Lamor/cyclotron radius (see [[Particle motion in uniform magnetic fields]]) will decrease locally, therefore the drift. Both positively and negatively charged particles will drift in the same direction!

Quantitatively (derivation see in sources below):
$$v_e = \frac{E_n \times B}{B^2}$$
which is indep. of $q$ and along isocontour lines of electr. potential (=normal to $E$)
Isocontourlines of electrostat. potential in orange:
![[particlemotion-potential-isocountour.png]]

We extend this result to general external forces $F$ (e.g. the gravity force), and get $$m\partial_t v = f+ qv\times B \implies v_e = \frac{F\times B}{qB^2}$$ which is now dependent on $q$! If $F$ is the gravity force, positive and negative particles will drift in different directions creating an $E$-field, resulting in a motion along $F$
![[plasma-under-gravity.png]]

## Sources
- EPFL - Introduction to Plasma Physics, lecture 1e)
- McGreivy -General Plasma Physics, Princeton lecture notes 2017