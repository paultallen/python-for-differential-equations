# NumPy arrays
The NumPy module (always imported as `np`) provides the more sophisticated `np.array` framework.
There are several ways to construct NumPy arrays; see the [NumPy documentation](https://numpy.org/doc/stable/reference/routines.array-creation.html) for more array construction routines.

### Convert lists to arrays
We can convert any Pythn list to a NumPy array. The contents of the array are the same as the list, but we can apply NumPy functions to the array (in a way that we can't for lists).
```
my_list = [ k**2 for k in range(5) ]
my_array = np.array( my_list )
print(my_array)
```

### Zeros
To create an array full of zeros, use `zeros()` and specify the length of the array:
```
my_array = np.zeros(5)
print(my_array)
```
### Ones
To create an array full of ones, use `ones()` and specify the length of the array:
```
my_array = np.ones(5)
print(my_array)
```



## Functions acting on arrays
One advantage of NumPy arrays is that we can easily apply a function to every element in the array:
```
print( np.sqrt(my_array) )
```


For a list of mathematical functions that can act on arrays, see the [NumPy documentation](https://numpy.org/doc/stable/reference/routines.math.html).



