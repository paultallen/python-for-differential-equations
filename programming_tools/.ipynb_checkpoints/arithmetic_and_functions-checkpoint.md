# Simple arithmetic and built-in functions

## Simple arithmetic
The basic arithmetic operations are
```
2+3
2-3
2*3
2/3
2**3
```

Python understands the order of operations.
- `12/2/3` yields 2, computed as 12 divided by 2, then divided by 3.
- `5*3**2` yields 45.

Nevertheless, parentheses can be useful.
- Caution: `(3+4)(5+6)` will give you an error. You must explicitly include the multiplication command: `(3+4)*(5+6)`.

## Built-in functions from _NumPy_
Python has a lot of built-in functions, which are typically obtained by loading the _module_ that contains the function.
- You can load the module with its full name, or with a shorthand name. 
- You can also load just part of the module.

After loading the module, you can access the functions it contains with the syntax 
`
<module name>.<function>
`

>For example: to compute $\cos(0)$ we use the `cos` function from the _NumPy_ module, which we import with the name `np`:
>```
>import numpy as np
>np.cos(0)
>```

**Important:** There are several different modules that include functions like cosine, sine, etc. These notes use `numpy` almost exclusively, always loaded as `np`.
The reason is that we will want to apply functions to arrays of numbers.

Here are several useful _NumPy_ functions 
- cosine `np.cos()`
- sine `np.sin()`
- exponential `np.exp()`
- natural log `np.log()` For log base 10 use `np.log10()`
- square root `np.sqrt()`

For more information, see the [Mathematical Functions in the NumPy Documentation](https://numpy.org/doc/stable/reference/routines.math.html).