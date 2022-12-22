# NumPy arrays (2d)

2d NumPy arrays can be viewed as either
- an array whose elements are 1d NumPy arrays, or
- as a matrix / grid of values

Let's explore this via an example.

Start by defining a 1d array called `pts`:
```
pts = np.linspace(0,4,5)
```
Now consider four different arrays: `pts**0`, `pts**1`, `pts**2`, `pts**3`.

We arrange these into a list, which we then convert into a 2d NumPy array that we call `powers`:

```
powers = np.array([pts**0, pts**1, pts**2, pts**3])
print(powers)
```
As we can see, the rows of `powers` are the four different arrays that we got by raising `pts` to various powers.

We can access the rows of `powers` via their index.
For example, `powers[2]` gives the 3rd row (remember, computers count starting at zero):
```
print(powers[2])
```
If we want item number 3 from row number 2 (meaning the 4th item in the 3rd row), we use `powers[2][3]`:
```
powers[2][3]
```
In general, `powers[i][j]` gives the value in the ith row and jth column.

We can change the value of `powers[2][3]` as follows:
```
powers[2][3] = -99
print(powers)
```

The idea of a 2d array generalizes to any dimension. Check out the [NumPy user guide](https://numpy.org/doc/stable/user/index.html) for more information.