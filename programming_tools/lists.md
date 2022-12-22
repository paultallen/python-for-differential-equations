# Lists 

Lists take the form of numbers (or any other item) in square brackets, separated by commas. For example:
```
[0,1,4,9,16]
```
**Important:** Using round braces instead of square brackets creates a different type of object, called a _tuple_, which has different properties.
In these notes, we don't use tuples.

We can give lists a variable name:
```
squares = [0,1,4,9,16]
print(squares)
```

## Creating lists
Lists can be constructed via a formula using `range()`:
```
squares = [ k**2 for k in range(5) ]
print(squares)
```
Note that `range(5)` provides 5 different values for the counter, starting at 0 and ending at 4.


## Accessing list values
We access values in a list by the index. 
Remember that computers count starting at zero.
Thus `squares[3]` gives the value in location number 3, which is the 4th item.
```
squares = [ k**2 for k in range(5) ]
print(squares[3])
```

## Changing list values
We can change the value by using the index.
```
squares = [ k**2 for k in range(5) ]
print(squares)
squares[2] = 100
print(squares)
```

## Lists of lists
The items in a list can lists. For example
```
coord = [ [1,2], [3,4], [5,6] ]
print(coord[1])
```

## Lists of strings 
The items in a list can be strings. For example:
```
colors = ['red','blue','green','purple']
print(colors[2])
```