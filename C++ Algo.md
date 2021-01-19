# C++ Algorithms and Data Structures

## Table of Contents

* Common Functions
* Common Libraries
* Built-in Data Structure Libraries
  * Array
    * String
      * Char Array
      * StringBuilder
    * Dynamic Array
    * Linked List
    * Stack and Queue
      * Stack
      * Queue
    * HashTables
      * HashSet
      * HashMap
    * Trees
    * Graphs
    * Searching

## Common Functions

```cpp
// Power
#include <cmath> // Puts functions inside std namespace
#include <math.h> // Old deprecated C header - Can still be used.
std::pow(n, 2); // n squared - Returns double

// Max, Min Int
#include <climits> //
#include <limits.h>
INT_MAX;
INT_MIN;

#include <cfloat>
#include <float.h>
FLT_MIN;
FLT_MAX;

DBL_MIN;
DBL_MAX;

// Convert binary Integer to String

// Rounding
#include <cmath>
std::round(1.23);

// XOR

// Comparator

// Ternery operator
return (isTrue) ? true : false;

// Generate Random Number
#include <random>

std::random_device rd; // Obtain seed for random number engine
std::mt19937 gen(rd()); 
std::uniform_real_distribution


```

## Common Libraries (C++ Standard Library)

C standard libraries end with `.h`, but use is deprecated. Libraries from C standard libraries in cpp start with c-something.
Features from C++ std library is declared within `std` namespace.

```cpp

#include <iostream> // cout, cin
#include <stdio.h> // printf, scanf - C library (aka cstdio)

#include <cstdlib>
#include <stdlib.h> // C library

malloc(); // Allocates memory
free(); // Deallocates memory

atof(); // Converts byte string to float
atoi(); // Converts string to integer

rand(); // Generates random number
srand(); // Seeds random number generator

NULL;

#include <time.h>

#include <bitset> // Bit array

#include <iterator>
```

### Algorithms library
Functions to be used on a range of elements
```cpp
#include <algorithm>

std::sort(); // Sorts range in ascending order
std::max(); // Returns greater of given value
std::max_element(); // Returns largest element in range
std::min(); 
std::swap(); // Swaps 2 elements
std::reverse(); // Reverses order of elements in a range

std::binary_search(); // Determines if element exists
std::merge(); // Merges 2 sorted ranges
std::inplace_merge(); // Merges 2 ordered ranges in place
```

## Built-in Data Structure Libraries

### Arrays (Lists)
Either use C-style arrays, or `array` standard library.

```cpp

#include <array>

```

### Strings
#### Character

### Dynamic Array
Dynamic Array uses `std::vector` library

```cpp
#include <vector>
// Constructor
vector<int> v1; // Initialize empty vector
vector<int> v2{1, 2, 3}; 
vector<int> v3(4, 10); // Create vector size 3 with all values 10

// Operations
v1.size(); // Get size of vector
v1.at(0); // Get element at index 0
v1.push_back(4); // Add element 4 to end of vector
v1.insert(1, 3); // Insert element 3 at index 1
v1.pop_back(); // Remove element at end of vector
v1.erase(2); // Remove element at index 2

v1.clear(); // Remove all elements of vector, resize to 0

// Sorting
#include <algorithm>
std::sort (v1.begin(), v1.end()); // Sort vector v1
```

### Linked List

```cpp
#include <forward_list> // Singly linked list
#include <list> // Doubly linked list
```

## Stacks and Queues
### Stacks

```cpp
#include <stack>
```
### Queues

```cpp
#include <queue>
```
### Priority Queue

```cpp
#include <priority_queue>
```

## Hash Tables
### Hash Sets

```cpp
#include <set>
#include <unordered_set>
#include <unordered_multiset>
```
### Hash Maps

Libraries for hashtables: 

```cpp
#include <map> // Associative array
#include <multimap> // Multimap

#include <unordered_map>
#include <unordered_multimap> // hashtables
```

Hashmap:

```cpp
// Constructor
unordered_map<int, string> map;

// Inserting values
map[3] = "Hi";
map.insert(make_pair(4, "HII"));

// Check if hashmap contains key
if (m.find(3) == m.end()) // key does not exist in map

// Iterate over unordered map
for (auto x : map) {
  x.first; // get key
  x.second; // get value
}

```

## Trees
### Binary Tree
### Binary Search Tree
### N-ary Tree
#### Recursion on N-ary Tree
### Trie

## Graphs

## Common Techniques

## Bit Manipulation

### Operators
```cpp
// Bitwise Operators
a | b // OR
a & b // AND
a ^ b // XOR
~a // NOT Complement of a (~0101 = 1010)

<< // Left shift
>> // Right shift

```
