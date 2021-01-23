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

// Pointers
// Normal way to pass vectors - copy of vector is created
void func(vector<int> vect) {}

// Pass large arrays, vectors etc by reference
void func(vector<int> &vect) {}

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
// C type arrays
// Array Declaration
int arr[] = {1, 2, 3 , 4}; // Initializing elements
int arr[10]; // Initialize array of size 10

// Accessing elements
arr[2];

// Get array size
sizeof(arr)/sizeof(arr[0]);

// C++ Array Library
#include <array>

// Initialization
array<int, 5> arr{{1, 2, 3, 4, 5}};
array<int, 5> arr = {1, 2, 3, 4, 5};

// Operations
arr.size() // Get size of array
arr.empty(); // Returns true if array is empty
arr.at(2); // Returns element at index 2

// Sorting
sort(arr.begin(). arr.end());
```

### Strings

```cpp
#include <string>

// Constructor
string str ("test"); // std::string

// Operations

str.length(); // Returns length of string
str.size(); // Returns length of string
str.at(2); // Access character at index 2
str.append("some string"); // append to back of string
str.insert(2, "HI"); // Insert HI at index 2
str.substr(3, 5); // Index, Length of substring
// For loop
for (string::iterator it=str.begin(); it!=str.end(); ++it) {}
str.begin(); // Returns iterator pointing to 1st character of string
str.end(); // Returns iterator pointing to end of string
str.empty(); // Returns true if string is empty

str.compare(str2); // Compare string value
str.clear(); // Clears string

// Conversion
std::stoi("2"); // Convert string to integer
std::stoi("1001001"); // Convert binary string to integer
```
#### Character

### Dynamic Array
Dynamic Array uses `std::vector` library

```cpp
#include <vector>
// Constructor
std::vector<int> v1; // Initialize empty vector
std::vector<int> v2{1, 2, 3}; 
std::vector<int> v3(4, 10); // Create vector size 3 with all values 10

// Functions
v1.size(); // Get size of vector
v1.at(0); // Get element at index 0
v1.push_back(4); // Add element 4 to end of vector
v1.insert(v1.begin() + 2, 3); // Insert element 3 at index 2
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

// Constructor
std::stack<int> stack;

// Functions
stack.push(1); // Push to top of stack
stack.top(); // Returns reerence to top of stack
stack.pop(); // Removes element on top of stack

stack.size(); // Returns size of stack
stack.empty(); // Returns true if stack is empty
```
### Queues

```cpp
#include <queue>

// Constructor
std::queue<int> q;

// Functions
q.push(1); // Queue new element
q.pop(); // Dequeue
q.front(); // Access 1st element

q.size(); // Returns size of queue
q.empty(); // Returns true if queue is empty
```
### Priority Queue

CPP pq library impelments max heap
```cpp
#include <priority_queue>

// Constructor

std::priority_queue<int> pq;

// Functions
pq.push(10); // Add items
pq.pop(); // Removes top element of pq
pq.top(); // Get top element of pq

pq.empty(); // Returns true if priority queue is empty
pq.size(); // Returns size of pq
```

## Hash Tables
### Hash Sets
`unordered_set` library implements Java style HashSets.
```cpp
#include <unordered_set> // Stores unique elements in no particular order

// Constructor
std::unordered_set<int> set;
// Destructor
~unordered_set();

// Functions
set.insert(5); // Add new element to set
set.size(); // Returns size of set

if (set.find(5) != set.end()) // Set contains element
set.erase(5); // Removes element from set
set.empty(); // Returns true if hashset is empty
set.clear(); // Clear hashset

// Other type of hashsets
#include <set> // Stores unique elements in a specified order
#include <unordered_multiset> // Allows different elements to store the same values
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
std::unordered_map<int, std::string> map;

// Inserting values
map[3] = "Hi";
map.insert(make_pair(4, "HII"));
map.emplace(1, "Hi"); // putIfAbsent
map.size(); // Returns size of map
map.at(3); // Access mapped value

// Check if hashmap contains key
if (m.find(3) == m.end()) // key does not exist in map
map.erase(2); // Delete key-value pair

map.empty(); // Returns true if map is empty
map.clear(); // Clear map

// Iterate over unordered map
for (auto x : map) {
  x.first; // get key
  x.second; // get value
}

// C++20 
map.contains(3) // Returns true if element in map

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
