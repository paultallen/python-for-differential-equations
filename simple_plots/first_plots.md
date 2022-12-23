# First plots with pyplot

To create plots we use the `pyplot` collection of functions, which are part of the `matplotlib` module. 
Always we import these functions as
```
import matplotlib.pyplot as plt
```
In addition to the notes here, see also the [pyplot tutorial](https://matplotlib.org/stable/tutorials/introductory/pyplot.html#sphx-glr-tutorials-introductory-pyplot-py)

## Example: plotting a list of values
In this first example we 
- first create a list called `values` 
- apply the `plt.plot()` command
- apply the `plt.show()` command

Here is the code:
```
values = [k*(-1)**k for k in range(11)]
plt.plot(values)
plt.show()
```

## Example: plotting one list vs another
Often we have a list of inputs and another list of outputs, and want to plot one against the other.
```
inputs = [0.5*k for k in range(5)]
outputs = [k**2 for k in range(5)]
plt.plot(inputs, outputs)
plt.show()
```

## Example: formatting options
The `plt.plot()` function can take many optional inputs that format the plot.
For example:
```
plt.plot(values, 
         marker='o',
         color='purple',
         linestyle='dashed')
plt.show()
```
See the 
[`plot` documentation](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.plot.html) for a long list of optional parameters.