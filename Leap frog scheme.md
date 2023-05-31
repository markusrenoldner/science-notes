
An easy example of [Numerics for differential equations](Numerics%20for%20differential%20equations.md) that solves a 2nd order [ODE](ODE.md). It is symplectic ([Symplectic ODE integrators](Symplectic%20ODE%20integrators.md)) and conserves the energy of the system.

These 2nd order ODEs arise a lot in [Classical mechanics](Classical%20mechanics.md) due to Newtons second law.
There are multiple similar formulations:



kick-drift form:
![leapfrog-kickdrift.png](leapfrog-kickdrift.png)


velocities at integer steps:
![leapfrog-intvelocity.png](leapfrog-intvelocity.png)



### Sources: 
https://de.wikipedia.org/wiki/Leapfrog-Verfahren
https://en.wikipedia.org/wiki/Leapfrog_integration