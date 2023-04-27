
[[Overview of errors and complexity of numerical methods]]


## Log log
![[loglog1.png]]


## x axis linear, y axis log
![[loglog3.png]]


## x axis log, y axis linear
![[loglog2.png]]


## Python code:
```
import numpy as np
import matplotlib.pyplot as plt

x = np.linspace(1,10,200)

plt.plot(x,x**1,label="$x$")
plt.plot(x,x**2,label="$x^2$")
plt.plot(x,x**3,label="$x^3$")
plt.plot(x,np.exp(x),label="$e^x$")
plt.plot(x,np.log(x),label="ln(x)")
plt.legend()
plt.grid()
plt.xlabel("x")
plt.xscale("log")
plt.yscale("log")
```