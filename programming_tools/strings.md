# Strings

A string is a list of chacterers. Define strings with quotes (single or double).
```
text = 'The area of the square'
print(text)
```
We can include variable values in the string
```
length = 5
area = length**2
text = 'The square with side length {} has area {}.'.format(length, area)
print(text)
```
There are many ways to format a numerical values in a string.
```
p = 22/7
print( 'A poor approximation of pi is 22/7 = {}'.format(p) )
print( 'A poor approximation of pi is 22/7 = {:g}'.format(p) )
print( 'A poor approximation of pi is 22/7 = {:0.3f}'.format(p) )
print( 'A poor approximation of pi is 22/7 = {:0.3e}'.format(p) )
```
Here 
- `g` is a _general_ formatting option that does a good job in most cases
- `0.3f` displays the number with a minimum of 0 spaces with a _fixed_ number of 3 digits 
- `0.3e` displays the number with a minimum of 0 spaces using exponential (scientific) notation having 3 explicit digits

Replace `0.3f` with `10.3f` to see the effect of increasing the minimum number of spaces, etc.