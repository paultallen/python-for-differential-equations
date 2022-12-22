# Math from NumPy

There are several different modules one can use to obtain built-in math functions like cosine, sine, etc. 
In these notes, we obtain these from the _NumPy_ module, which we always import as `np`. 
The reason is that we often want to apply these functions to _NumPy_ arrays.

Here are several useful _NumPy_ functions 
- square root function: `np.sqrt()`
- cosine function `np.cos()`
- sine function `np.sin()`
- exponential function `np.exp()` <br> 
This means that you compute $e^x$ using `np.exp(x)`.
- natural log function `np.log()` <br>
This means that you compute $\ln(x)$ using `np.log(x)`.<br>
For log base 10 use `np.log10()`.

For more information, and a lot more functions, see the [Mathematical Functions](https://numpy.org/doc/stable/reference/routines.math.html) in the NumPy Documentation.

Finally, note that we can obtain $\pi$ from NumPy as `np.pi`.
For example, to compute $\cos(\pi t)$ we use `np.cos(np.pi*t)`.