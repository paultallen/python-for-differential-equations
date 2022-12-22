# NumPy arrays (1d)
The NumPy module (always imported as `np`) provides the `np.array` framework, which is more sophisticated than the list framework.
In particular, one can apply a function to every value in the array all at once; see the example at the end of this page.

First, we list several ways to construct NumPy arrays; see the [NumPy documentation](https://numpy.org/doc/stable/reference/routines.array-creation.html) for more array construction routines.



## Construct using `np.linspace`
The `np.linspace` command creates a array of values, determined by
- starting value
- ending value
- the number of desired points

Examples: 
- To create an array containing the values 0,1,2,3,...,10 we use
```
    my_array = np.linspace(0,10,11)
    print(my_array)
```
- The array that starts at 0, ends at 10, and has 1000 points is determined by
```
    np.linspace(0,10,1000)
```
Do not print out this array. :)

## Construct from a list
We can convert any Python list to a NumPy array. The contents of the array are the same as the list, but we can apply NumPy functions to the array (in a way that we can't for lists).
```
my_list = [ k**2 for k in range(5) ]
my_array = np.array( my_list )
print(my_array)
```

## Construct using `np.zeros`
To create an array full of zeros, use `zeros()` and specify the length of the array:
```
my_array = np.zeros(5)
print(my_array)
```
## Construct using `np.ones`
To create an array full of ones, use `ones()` and specify the length of the array:
```
my_array = np.ones(5)
print(my_array)
```


## Functions acting on arrays
One advantage of NumPy arrays is that we can easily apply a function to every element in the array:
```
my_array = np.linspace(0,10,11)
print( np.sqrt(my_array) )
```


For a list of mathematical functions that can act on arrays, see the [NumPy documentation](https://numpy.org/doc/stable/reference/routines.math.html).



