# Integration with `scipy.integrate.quad`

For numerical integration, we use the `quad` function from the `scipy.integrate` module.
Rather than import the whole module, we only import the `quad` function:
```
from scipy.integrate import quad
```
The `quad` function requires three inputs:
- the function being integrated
- the left endpoint
- the right endpoint

The `quad` function returns two outputs:
- a numerical approximation of the integral
- an estimate of the size of the error

## Example
In order to approximate the integral
$$
\int_0^1 x^2\,dx
$$
we need to define the function, and then apply `quad`:
```
def f(x):
    return x**2
quad(f, 0, 1)
```
The result is two numbers:
- `0.33333333333333337` is the approximation of the integral
- `3.700743415417189e-15` is the estimate of the error size (in absolute value)

In order to just obtain the approximation of the integral, we use
```
def f(x):
    return x**2
quad(f, 0, 1)[0]
```

## Example with an anonymous function
In many cases, we don't want/need to give the function being integrated a name.
Functions without a name are called _anonymous_.
Anonymous functions can be defined with the command `lambda`.
The code
```
lambda x: x**2
```
is shortcut for the function with input `x` and output `x**2`.

Thus we can compute the integral
$$
\int_0^1 x^2\,dx
$$
using the code
```
quad(lambda x: x**2, 0, 1)
```

## Example with cosine
We know that
$$
\int_0^\pi \cos(t)\,dt =0.
$$
The numerical integral
```
quad(lambda t: np.cos(t), 0, np.pi)
```
returns a value of `4.402786869117102e-17` with error estimated at `2.2102239425853306e-14`. 
The computer is not wrong: the true value of zero is well within the range $4.4\times 10^{-17}\pm 10^{-14}$. 
