# `for` loops

The `for` loop allows us to repeatedly accomplish a task that is applied to a list of items (or any other iterable object).
The basic syntax is
```
for <item> in <iterable object>:
    <task>
```
**Important:** the code for 'task' can be multiple lines, each of which must be intented.

## Silly example
In this example
- the 'list of items' is a list of strings,
- the 'task' is to print a sentence involving that string.

Here is the code:
```
sweets = ['cookies', 'cake', 'pie']
for food in sweets:
    print('Paul loves '+food+'!')
```
Note: we used the fact that strings can be added together in order form longer strings.

## Mathematical example
Here is a mathematical example where the 'item' is a number (0,1,2,3), and where the 'task' is to raise 2 to that power.
```
powers = [0,1,2,3]
for n in powers:
    print(2**n)
```

## Mathematical example with `range`
If the 'item' is a sequence of integers, as in the previous example, it is easy to use the `range` function.
```
for n in range(4):
    print(2**n)
```
**Note:** here `range(4)` means to start at 0 and end before 4. 

For a different starting point, use `range(<start>,<end before>)`. For example:
```
for n in range(1,4):
    print(2**n)
```

## Example: array of factorials
Here is a more complicated example that creates an array containing the values $0!, 1!, \dots, 5!$.
The plan is the following:
- Create an array, called `fact`, with 6 entries, all zeros
- Since $0!=1$, set `fact[0]` equal to 1.
- For index `k` starting at 1, and ending before 6, we set `fact[k]` equal to `fact[k-1]*k`.

Here is the code:
```
fact = np.zeros(6)
fact[0] = 1
for k in range(1,6):
    fact[k] = fact[k-1]*k
print(fact)
```

Note: we explicitly typed in `6`, the length of the array `fact`, in two different places. 
This makes it difficult to change the code to compute a different number of factorials.
One way to address this is to declare a variable `ct` that is the number of factorials we want to compute:
```
ct = 6
fact = np.zeros(ct)
fact[0] = 1
for k in range(1,ct):
    fact[k] = fact[k-1]*k
print(fact)
```
Another option is to use `len(fact)` to compute the length of the array `fact`, and use that in the `range` command:
```
fact = np.zeros(6)
fact[0] = 1
for k in range(1,len(fact)):
    fact[k] = fact[k-1]*k
print(fact)
```