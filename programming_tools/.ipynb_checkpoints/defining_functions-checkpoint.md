# Defining functions
Functions show up in two very different contexts in these notes:
- _Mathematical functions_ used to describe differential equations, systems of differential equations, vector fields, etc.
- _Programming functions_ used to accomplish programming tasks.

Both types of functions are defined with the same construction:
```
def <function name>( <inputs> ):
    <actions>
    return <outputs>
```
**Important:** The actions and return part of the function are indented!

**Note:** If you only want the function to accomplish some task, then the function doesn't need to return anything. Similarly, a function doesn't need to have any inputs.

Here are a lot of examples.

## Example: Simple mathematical function
A function that, given the radius, computes the area of a circle.
```
def circle_area(radius):
    area = np.pi*radius**2
    return(area)
```
Try it out with the command `circle_area(3)`.

Since this is a simple function, we can also combine the 'action' with the 'output':
```
def circle_area2(radius):
    return(np.pi*radius**2)
```

## Example: Simple (and silly) programming function
A function that, given a number of cookies, tells me how many cookies I have.
```
def cookie( ct ):
    string = "I have {:g} cookies!".format(ct)
    print(string)
```
Try it out with the command `cookie(4)`.<br>
Note that this function doesn't return anything.


## Example: Function of single variable $f(x)$
We create the function $f(x)= x(1-x)$ with
```
def f(x):
    return x*(1-x)
```

## Example: Function of single variable, with a parameter
Suppose we have the function $f(x) = x(1-x) - h$, where $h$ is some parameter.
We define
```
def f(x,h):
    return x*(1-x) - h
```
When using the function, we put the appropriate number in the second entry.

## Example: Single ODE given by $f(t,x)$
Suppose we have the differential equation
$$
\frac{dy}{dt} = \underbrace{-3y + \cos(t)}_{f(t,y)}.
$$
We describe the right side of the equation with the function
```
def f(t,y):
    return -3*y + np.cos(t)
```

## Example: Another single ODE given by $f(t,x)$
Suppose we have the differential equation
$$
\frac{dx}{dt} = \underbrace{x(1-x)}_{f(t,x)}.
$$
The `solve_ivp` solver (discussed elsewhere) wants to describe the right side as a function of $t$ and $x$, even though $t$ is not explicitly present.
Thus we use the function
```
def f(t,x):
    return x*(1-x)
```

## Example: Vector field $V(x,y)$
Consider the vectorfield given by
$$
V(x,y) = \langle x- xy , -y + 2xy \rangle.
$$
When plotting this, we use the following function, which returns a list:
```
def V(x,y):
    return [x - x+y , -y + 2*x*y]
```

## Example: System of ODEs given by $F(t,x,y)$
Consider the system of differential equations corresponding to the vector field above.
We can write this as
$$
\frac{d}{dt}\begin{pmatrix} x \\ y \end{pmatrix},
$$
where
$$
F(t,\underbrace{x,y}_\text{var})
= \begin{pmatrix} x- xy \\ -y + 2xy\end{pmatrix}.
$$
For the purposes of using the `solve_ivp` solver (discussed elsewhere), we want to define a function `F` that has only two inputs: $t$ and the variables $(x,y)$, which are considered as a single object that we call `var`.
Here is one way to do this
```
def F(t,var):
    x,y = var
    return [x - x+y , -y + 2*x*y]
```



