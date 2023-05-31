[Numerics for differential equations](Numerics%20for%20differential%20equations.md)
[Lagrangian and Eulerian specification, coordinates](Lagrangian%20and%20Eulerian%20specification,%20coordinates.md)


## Visual explanation
https://www.youtube.com/watch?v=kvBRFxRIJuY


## Summary 
(for the simple advection problem in the video)

Initial wave is known at discrete points
The wave is advected/displaced without deformation by a distance $u \Delta t$ per time step. The discrete solution values should now change to represent the updated solution

1. The exact solution of the advected wave after $\Delta t$ would be the blue line: ![semilag1.png](semilag1.png)
2. We can imagine the values at gridpoints are particles, and we trace them back to were they come from ($x^*$ in the image) ![semilag2.png](semilag2.png)
3. The values $x^*$ dont correspond to gridpoints, so the black (initial) values are interpolated to approximate the blue values. I.e., we evaluate the interpolation of the previous solution at $u\Delta t$ against the advection direction resulting in the green values: ![semilag3.png](semilag3.png)
4. The green values are then advected forward by $u\Delta t$ to update the black values on the grid: ![semilag4.png](semilag4.png)

