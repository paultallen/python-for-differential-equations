# Systems of equations

Constructing numerical solutions to systems of equations with `solve_ivp` is similar to the case of a single equation (see [the introduction to solve_ivp](one_variable.md)), but with a few changes:

- the function that defines the differential equation takes the form `f(t,vars)`, where `vars` represents a list of unknowns, and returns a list.

- the `y` part of output of `solve_ivp` is a NumPy array, with one row of values for each unknown.


## Example
As an example, consider the simple Lotka-Volterra system
$$\begin{aligned}
\frac{dx}{dt} &= x - xy\\
\frac{dy}{dt} &= -y + xy
\end{aligned}$$

The function determining the right side is defined by
```
def f(t,vars):
    x,y = vars
    return [x-x*y, -y + x*y]
```
The initial condition must include an initial value for $x$ and an initial value for $y$:
```
ic = [0.5, 0.5]
```
We can now run the simulation
```
t0 = 0
tmax = 20

soln = solve_ivp( f, [t0, tmax], ic, 
                 t_eval = np.linspace(0, tmax, 1000))
```
We can plot the two solutions $x$ and $y$ on the same axis:
```
plt.plot(soln.t, soln.y[0], label='x')
plt.plot(soln.t, soln.y[1], label='y')
plt.xlabel('time $t$')
plt.title('Simple Lotka-Volterra model')
plt.legend()
plt.show()
```
The result is the following image:


![Simple Lotka-Volterra](lotka-volterra.jpg)

## Complete code
Earlier in the notebook/file/console you need:
```
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp
```
Then 
```
def f(t,vars):
    x,y = vars
    return [x-x*y, -y + x*y]
    
ic = [0.5, 0.5]
t0 = 0
tmax = 20

soln = solve_ivp( f, [t0, tmax], ic, 
                 t_eval = np.linspace(0, tmax, 1000))
                 
plt.plot(soln.t, soln.y[0], label='x')
plt.plot(soln.t, soln.y[1], label='y')
plt.xlabel('time $t$')
plt.title('Simple Lotka-Volterra model')
plt.legend()
plt.show()
```
