[Fluid Dynamics](Fluid%20Dynamics.md)


## Why is this the case?
For Re $\rightarrow 0$ the Navier-Stokes equations become the Stokes equations:
$$-\mu \Delta u + \nabla p = f$$
$$\nabla \cdot u = 0$$
This problem is equivalent to this variational problem: find
$$\operatorname{min}_u \frac{\mu}{2}||\nabla u||^2_2 - (f,u)$$
under the side constraint $\nabla\cdot u =0$, see [Calculus of variations](Calculus%20of%20variations.md), [Minimum of quadratic functionals](Minimum%20of%20quadratic%20functionals.md). 

An article from scicomp.stackexchange (https://scicomp.stackexchange.com/questions/7474/pressure-as-a-lagrange-multiplier) suggests that
>If you write down the Lagrangian and then the optimality conditions of this optimization problems, you will find that indeed the pressure is the Lagrange multiplier.
>This equivalence between problems is not exploited in any numerical scheme (that I know of) but it is an important tool in the analysis because it shows that the Stokes equations are essentially the Poisson equation on a linear subspace. The same holds true for the time-dependent Stokes equations (which corresponds to the heat equation on the subspace) and it can be extended to the Navier-Stokes equations.

The author of that comment also says:
>Is there a way to recast the time-dependent Stokes (or Navier-Stokes) equations as an optimization problem, possibly of a functional integrated over time?
>Not as an optimization problem - the solution of the heat equation does not minimize anything (though it's the stationary point of a Lagrangian function). But you can formulate the Stokes equations as follows: 
>Find $u\in H(div)$ st. $$(\partial_t u, \phi) + (\nabla u, \nabla \phi) = (f, \phi) \qquad\forall \phi \in \{v\in H(div): \nabla\cdot v = 0\}$$
>subject to the constraint $\nabla \cdot u = 0$.
> Note that I have chosen the test space smaller than the trial space and so the left and right hand side of the variational equation will not be equal. The difference is the pressure.


## An easier, more shallow answer:
>You have to write the KKT conditions for the optimization problem to rigorously show that pressure is the Lagrange multiplier.
https://www.reddit.com/r/CFD/comments/nrphxs/it_is_often_said_that_pressure_acts_as_a_lagrange/

>The incompressible Navier-Stokes equations (in 3D) consist of four equations: one each for u, v, and w, and the incompressibility condition. The incompressible Navier-Stokes equations also have four variables: u, v, w, and p. Four equations, four unknowns, so we should be good, right? Wrong. There is no equation for pressure. Without pressure, the Navier-Stokes equations would be overdetermined. We reconcile this by defining pressure to be "the thing that makes the incompressibility condition true." That kind of constraint, written down a bit more formally as in the Stack Exchange answer, is a Lagrange multiplier.
https://www.reddit.com/r/CFD/comments/nrphxs/comment/h0hygsm/


## A Possible derivation:
https://personalpages.manchester.ac.uk/staff/Andrew.Hazel/Numerical_computation/Numerical_Computation_slides2.pdf