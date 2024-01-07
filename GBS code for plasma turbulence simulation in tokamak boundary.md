# GBS code for plasma turbulence simulation in tokamak boundary

#paper 

- Authors: Giacomin et al.
- Title: The GBS code for the self-consistent simulation of plasma turbulence and kinetic neutral dynamics in the tokamak boundary
- 2022

## abstract 
- GBS = global bragniskii solver
- with "toroidal" coordinates, they mean "cylindrical"!
- new version of GBS, (turbulence simulation code), expands to cover entire plasma volume, improving core-edge interactions and introducing toroidal coordinates for flexibility.
- efficient iterative solver for the Poisson and Ampère equations, enabling electromagnetic simulations without the Boussinesq approximation.
- Supports various magnetic configurations
- MPI parallelization
- verified using manufactured solutions and through a simulation of a TCV tokamak discharge
  
## bragniskii equations, p3
- 8 equations, with lots of strange operators and gyroviscous terms etc.
- for operator definition, see in daily notes
- derivation of bragniskii is still unclear to me. is it a fluid model or kinetic?

## implementation and optimization
- somehow neutral particles are calculated in an extra workflow
