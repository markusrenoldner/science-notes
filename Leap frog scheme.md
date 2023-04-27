
An easy method to solve a 2nd order [[ODE]] using [[Numerics]] . It is symplectic ([[Symplectic ODE integrators]]) and conserves the energy of the system.

These 2nd order ODEs arise a lot in [[Classical mechanics]] due to Newtons second law.
There are multiple similar formulations:



kick-drift form:
![[leapfrog-kickdrift.png]]


velocities at integer steps:
![[leapfrog-intvelocity.png]]



### Sources: 
https://de.wikipedia.org/wiki/Leapfrog-Verfahren
https://en.wikipedia.org/wiki/Leapfrog_integration