# Modules
Python has a lot of built-in functions, which are typically obtained by importing the _module_ that contains the function.
- You can import the module with its full name, or with a shorthand name. 
- You can also import just the function you need.

Once you import a module in your program/shell/notebook, you can use functions from that module without importing again.

After importing the module, you can access the functions it contains with the syntax 
`
<module name>.<function>
`

For example, For example: to compute $\cos(0)$ we use the `cos` function from the _NumPy_ module, which we import with the name `np`:
```
import numpy as np
np.cos(0)
```
**Important:** There are several different modules that include functions like cosine, sine, etc. In these notes we almost exclusively use _NumPy_, which we alway import as `np`.