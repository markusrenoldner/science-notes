
#extern 

one very nice example of a dynamic system (see [[Dynamical systems]]) is the lorenz attractor.

See the following [python code](C:\one\OneDrive\Bildung\dev\python\lorenzattractor.ipynb)

Its formulated as follows:


  

$$\frac{\partial x}{\partial t} = \sigma (y-x)$$

$$\frac{\partial y}{\partial t} = x (\rho-z) -y $$

$$\frac{\partial z}{\partial t} = xy-\beta z$$

  

define:

$$v := (x,y,z)^T$$

  

and follow:

$$\frac{d v}{dt} = f(x,y,z,\sigma,\rho,\beta)$$

  
