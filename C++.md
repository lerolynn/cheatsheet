# C++ Syntax

## Contents
* Basic Syntax
  * Basic
  * Input/Output
* Operators
  * Conditional Operators
  * Arithmetic Operators
* Functions
* Pointers

## Basic Syntax

### Basic
```c++
// Comments

/* multi line
 comment */

// Importing Libraries
#include <Library> // Search in include path list first
#include "Library" // Search in current directory first

// Common Libraries
#include <iostream> // cout
#include <vector> // Resizable arrays
#include <string> // Strings
```
### Input/Output

2 types of input/output: `printf` and `scanf`, `cout` and `cin'

```c++
// printf/scanf is a input/output from C
// d - int, ld - long, c - char, f - float, lf - double

scanf("%d %ld %c %f %lf", &n, &l, &ch, &f, &d); // Read character and double type

printf("Hello, World!"); // printing
printf("%d, %ld, %c, %f, %lf", n, l, ch, f, d); // print variables

// cout/cin
// input to int then int type
std::cin >> n1 >> n2;

// Print to stdout
std::cout << n << std::endl;

```
## Operators

### Conditional Operators

```c++
if (condition1) {}
else if (condition2) {}
else {}
```

### Arithmetic Operators
`+` - Addition
`-` - Subtraction
`*` - Multiplication
`/` - Division (follows type of variables)
`*Math.pow(x, 2)` - Exponent
`%` Modulus - Returns division remainder

** Division follows type of variables
```c++
int z = 5/2 // z = 2
float f = 5/2 // f = 2
// Cast 2 to float type
float fl = 5/(float) 2; // fl = 2.5 

```

### Loops
```c++
// Loop through array (c type array)
for (int i = 0; i < sizeof(arr) / sizeof(arr[0]); i++) {}

// Loop through c++ array, resizable array (std::array, std::vector)
for (int i = 0; i < arr.size(); i++) {}
```

## Functions
```cpp
type function(int parameter) {
  return someType;
}
```

## Pointer
Used to share memory address among different context/functions. Used when functions need to modify content of variable but does not have ownership.

Note: Only use pointers when needed (mostly in these situations): 
1. Need object to outlive current scope. Make copy of object if possible.
2. Need to allocate a lot of memory.

```cpp
&val; // access memory address
int *p = &val; // assign memory address of val to pointer p

```

## Namespace

Used to organize classes.

Namespace vs class
Classes are data types - expands structures, contains data members and functions as members.

Namespaces cannot be created as object - more or a naming convention. Used to define a scope so idientifiers don't clash (same named identifiers.)