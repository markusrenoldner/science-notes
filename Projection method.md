# Projection method
[[Fluid Dynamics]]



>If you know the velocities, you can find an equation for the pressure by taking the divergence of the momentum equations, giving a Poisson equation to solve for the pressure field.
>In numerical simulations of the Navier-Stokes equations (e.g. if you're not solving a textbook problem), a common approach is to take a "tentative" momentum step with an approximate pressure (the last timestep's pressure, or even 0), then solve for the pressure required to make the new time level's velocities divergence free. This is commonly known as the projection method, see https://en.wikipedia.org/wiki/Projection_method_(fluid_dynamics)


wikipedia also mentions :

- the relationship to the splitting method
- the reason why a poisson problem has to be solved for the pressure

https://www.reddit.com/r/CFD/comments/nrphxs/comment/h0jm0h4/