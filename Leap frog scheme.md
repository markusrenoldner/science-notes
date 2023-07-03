
An easy example of [[Numerics for differential equations]] that solves a 2nd order ODE (see [[Differential equations]]. It is symplectic ([[Symplectic ODE integrators]] and conserves the energy of the system.

These 2nd order ODEs arise a lot in [[Classical mechanics]] due to Newtons second law.
There are multiple similar formulations:

kick-drift form:
$$
\begin{aligned}
v_{i+1 / 2} & =v_i+a_i \frac{\Delta t}{2} \\
x_{i+1} & =x_i+v_{i+1 / 2} \Delta t \\
v_{i+1} & =v_{i+1 / 2}+a_{i+1} \frac{\Delta t}{2}
\end{aligned}
$$
velocities at integer steps:
$$
\begin{aligned}
& x_{i+1}=x_i+v_i \Delta t+\frac{1}{2} a_i \Delta t^2 \\
& v_{i+1}=v_i+\frac{1}{2}\left(a_i+a_{i+1}\right) \Delta t
\end{aligned}
$$


## Sources: 
https://de.wikipedia.org/wiki/Leapfrog-Verfahren
https://en.wikipedia.org/wiki/Leapfrog_integration