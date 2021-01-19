# Python3 Syntax

## Contents
* Basic Syntax
  * Basic
  * Input/Output
* Operators
  * Conditional Operators
  * Arithmetic Operators
  * Loops
* Functions

## Basic Syntax

### Basic
```python
# Comment

'''
Multiline Comment
'''

# Importing Libraries
import Math # Use math functions, but must do Math.Calculate
from Math import Calculate # Don't have to prefix
from Math import * # Don't have to prefix, not recommended
```

### Input/Output

```python
# Printing
print("Hello, World!")
print(i, end='') # Printing without newline
# Input
n = raw_input("Type input: ") # Presents prompt to user and gets input from user
```

## Operators

### Conditional
```python
if condition:
    pass
elif condition2:
    pass
else:
    pass
```

### Arithmetic Operators

`+` - Addition
`-` - Subtraction
`*` - Multiplication
`/` - Division (5/2 = 2.5))
`//` - Floor division (5/2 = 2)
`**` - Exponent
`%` Modulus - Returns division remainder

### Loops

```python
# Loop through list
for fruit in fruits:
    pass

# Loop through string
for letter in "word":
    pass

# Loop from 0 to 5
for x in range(6):
    pass
# Loop from 2 to 5
for x in range(2, 6):
    pass

# Loop from 2 to 30, increment by 3
for x in range(2, 30, 3):
    pass

# Exit loop if condition is met
for x in lis:
    if x == 1:
        break
```
## FUnctions
```python
def function_name(argument):
    return someValue
```