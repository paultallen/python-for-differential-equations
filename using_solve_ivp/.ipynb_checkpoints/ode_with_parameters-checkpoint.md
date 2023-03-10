# Differential equations with parameters

Consider the simple logistic model with harvesting
$$\frac{dy}{dt}=y(1-y)-h$$
where $h \geq 0$ represents the harvesting rate.

In [Functions with a parameter](simple_plots/functions_with_parameters.md) we saw how to plot the function 
$$f(y)=y(1-y)-h$$
for various values of $h$.

Now we want to explore numerical solutions for different values of $h$.
In particular, we want to generate the following plot, which shows numerical solutions for varying values of the parameter $h$:


![Logistic model with harvesting](logistic_with_harvesting.jpg)


### Define the function with parameters
We start by defining the function $f$ that determines the right side of the differential equation.
The inputs need to be
- the time variable, which in this case is `t`
- the unknown variable, which in this case is `y`
- the parameter(s), which in this case is `h`

Thus our code is:
```
def f(t,y,h):
    return y*(1-y) - h
```
### Specify the evolution parameters
Specify the initial/ending times:
```
t0 = 0
tmax = 10
```
Specify the initial condition:
```
ic = [0.4]
```
Specify the various values of $h$ to consider, along with the corresponding labels:
```
hvals = [0, 0.15, 0.25, 0.4]
labels = ['$h=0$', '$0<h<1/4$', '$h=1/4$', '$h>1/4$']
```
### Construct and plot numerical solutions
For each value of $h$ we construct a numerical solution, adding the option `args=[<h value>]` to the `solve_ivp` function.
Since we are running a loop, the $h$ value is given by `hvals[k]`.

Once we have constructed the solution, we immediately plot it, using the label from our list of labels.
```
for k in range(4):
    soln = solve_ivp( f, [t0,tmax],ic, args=[hvals[k]],
                     t_eval=np.linspace(t0,tmax, 1000) )
    plt.plot(soln.t, soln.y[0], label=labels[k])
```
### Final touches
Finally, we add our finishing touches to the plot:
- we include a legend 
```
    plt.legend(title='harvesting')
```
- adjust the limits of the plot
```
    plt.ylim(0, 1.1)
```
- change the ticks on the vertical axis to reflect only the important points
```
    yplus = 0.5 + np.sqrt(0.25 - hvals[1])
    yminus = 0.5 - np.sqrt(0.25 - hvals[1])
    plt.yticks([0,yminus, 0.5, yplus,1], [0, '$y_-$', 0.5,'$y_+$', 1])
```
- include title, axes labels
```
    plt.title('Simple logistic model with harvesting')
    plt.xlabel('time $t$')
    plt.ylabel('percent habitat occupied')
```

### Full code
Earlier in the notebook/file/console you need:
```
import numpy as np
import matplotlib.pyplot as plt
from scipy.integrate import solve_ivp
```
Then the graphic above is generated by the following code:
```
def f(t,y,h):
    return y*(1-y) - h

t0 = 0
tmax = 10
ic = [0.4]

hvals = [0, 0.15, 0.25, 0.4]
labels = ['$h=0$', '$0<h<1/4$', '$h=1/4$', '$h>1/4$']

for k in range(4):
    soln = solve_ivp( f, [t0,tmax],ic, args=[hvals[k]],
                     t_eval=np.linspace(t0,tmax, 1000) )
    plt.plot(soln.t, soln.y[0], label=labels[k])

    
plt.legend(title='harvesting')

plt.ylim(0, 1.1)

yplus = 0.5 + np.sqrt(0.25 - hvals[1])
yminus = 0.5 - np.sqrt(0.25 - hvals[1])
plt.yticks([0,yminus, 0.5, yplus,1], [0, '$y_-$', 0.5,'$y_+$', 1])

plt.title('Simple logistic model with harvesting')
plt.xlabel('time $t$')
plt.ylabel('percent habitat occupied')
plt.show()
```