# Linear, polynomial and exponential functions in log-log plots

[[Overview of errors and complexity of numerical methods]]


## Log log
![[loglog1.png]]
here, power functions like $x^2, x^3, ...$ are linear

## x axis linear, y axis log
![[loglog3.png]]
here, exponential functions like $e^x$ are linear

## x axis log, y axis linear
![[loglog2.png]]
here, $ln(x)$ is linear


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
plt.show()
```

## Python code for convergence plots
```
import numpy as np
import matplotlib.pyplot as plt

stepsize = np.array([10,1,0.1,0.01,0.001])
errors = np.array([20.01,1.98,0.21,0.0201,0.00203])
const = 1.5 # choose such that trendlines fit the error values
order1 = const*stepsize
order2 = const*stepsize**2
order3 = const*stepsize**3

plt.plot(stepsize,errors,label="error")
plt.plot(stepsize,order1, "k--",label="order 1")
plt.plot(stepsize,order2, "k--",label="order 2")
plt.plot(stepsize,order3, "k--",label="order 3")
plt.legend()

plt.xscale("log")
plt.yscale("log")
plt.xlabel("stepsize")
plt.ylabel("error")
plt.grid()
plt.show()
```