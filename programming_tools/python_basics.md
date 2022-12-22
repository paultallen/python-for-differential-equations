# Python basics

## Variables
Read variable assignment right-to-left.
To see the value of a variable, use `print()`:
```
x = 1+2+3
print(x)
y = x+4
print(y)
```
We can manipulate a variable, and then assign the resulting value to that same variable. Remember: read right-to-left!
```
x = 5
print(x)
x = x+7
print(x)
```

We can assign two variables at once:
```
x, y = 2, 4
print(x)
print(y)
print(x+y)
```
Arithmetic with variables
```
length = 5
width = 7
area = length*width
perimeter = 2*length + 2*width
print(area)
print(perimeter)
```