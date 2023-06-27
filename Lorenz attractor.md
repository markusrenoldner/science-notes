
one very nice example of a dynamic system (see [[Dynamical systems]]) is the lorenz attractor. Its formulated as follows:
$$\begin{align}
\frac{\partial x}{\partial t} &= \sigma (y-x) \\
\frac{\partial y}{\partial t} &= x (\rho-z) -y \\
\frac{\partial z}{\partial t} &= xy-\beta z
\end{align}$$
define:
$$v := (x,y,z)^T$$
and follow:
$$\frac{d v}{dt} = f(x,y,z,\sigma,\rho,\beta)$$




## python code:

```
import numpy as np
import matplotlib.pyplot as plt
from mpl_toolkits.mplot3d import Axes3D

# sim parameters
N = 100000
T = 0
dt = 0.0005

# system parameters
rho = 28
sig = 10
beta = 8/3

# solution array
v = np.zeros([N,3])

# rhs of system
def f(x,y,z,sig,rho,beta):
    a = sig*(y-x)
    b = x*(rho-z)-y
    c = x*y-beta*z
    return np.array([a,b,c])

# initial condition
v[0] = [1,1,1]

# time loop
for i in range(N-1):
    
    # extract components of v
    xi = v[i,0]
    yi = v[i,1]
    zi = v[i,2]

    # time integration
    v[i+1] = v[i] + dt*f(xi,yi,zi,sig,rho,beta)
    T = i*dt

fig = plt.figure()
ax = fig.add_subplot(111,projection="3d")
ax.plot(v[:,0],v[:,1],v[:,2], "b")
```

