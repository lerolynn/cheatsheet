# Python Algorithms and Data Structures

## Table of Contents

* Common Functions
* Built-in Libraries
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

## Common Built-in Functions

```python
# Power
n ** 2 # n squared

# Max and Min value
import sys
maxVal = sys.maxsize
minVal = -sys.maxsize - 1

# Express value as binary
bin(2) # Get binary value of 2
0b01001 # Express binary literal

# Rounding
round(5.8) # Round to nearest integer

# XOR
bin(0b1111 ^ 0b1111) # Output is 0b0

# Deepcopy
import copy
copy.copy(x) # shallow copy - creates copy of objects, references of nested objects
copy.deepcopy(x) # deepcopy - creates new copy of objects, recursively adds copies of nested objects

# Generate random number
import random
random.randint(0,9) # Create random number in range 0, 9

random.random() # Generate random float between 0 and 1

# Casting
import math
f = math.floor(2.3) # Safest way to cast
f = int(2.3) # Truncates value

# Typing - Specifying data type of argument and return type
def greeting(name: str) -> str:
  pass

# Assignment
nums = foo # Rebinds name nums to same object that foo refers to
nums[:] = foo # Makes copy of contents of original object

# Data type conversion
int(1.23) # Casts to 1
float(1) # Cast to 1.0

bool(1) # Returns true unless object is empty, False, 0, None
enumerate(lis) # Takes a collection and returns as list of (index, item)
min() # Returns smallest item in iterable
pow(x, 2) # Returns x square
range(start, end, increment) # Returns sequence of numbers
reversed(lis) # Returns reversed list
sorted(lis) # Returns sorted list
str(123) # Convert to string
sum(lis) # Sums items in iterator
zip(it1, it2, ..) # Paris items in iterators into tuples
```

### String Methods

```python
s.capitalize() # Convert 1st character to uppercase
s.count("hi") # Count no of times "hi" appears in string
s.find("hi") # Returns 1st occurrence of "hi", -1 if value not found

s.isalnum() # Returns True if all characters are alphanumeric
s.isalpha() # Returns True if all characters are in alphabet
s.isdigit() # Returns True if all are digits
s.lower() # Convert to lower case
s.upper() # Convert to upper case
s.title() # Convert 1st charactr of each word to uppercase
s.swapcase() # Convert lower to uppercase, upper to lower

s.strip() # Removes any leading and trailing whitespaces
s.split() # Split string into list of words at whitespaces
s.split(",") # Split string at ","
```

## Common Libraries - Python Methods

### Built-in data types - Iterable

Python has 4 built-in collection data types: Lists, Tuples, Sets, Dictionaries

#### Lists

Lists can be of any data types, can contain different data types.

```python
# Constructor
lis = [1, 2, 3, 4, 5]
type(lis) # outputs 'list'
list((1,2,3)) # Converts type to a list

# Accessing Items
lis[1] # Access 2nd item in list
lis[-2] # Access 2nd last item in list

# Splicing
lis[2:5] # Index 2 - 4
lis[:4] # Start to index 3
lis[2:] # Index 2 to end
lis[-4:-1] # 4th last to 2nd last (not inclusive of -1 index)

# Check if item is present
if 2 in lis:
  pass # do something

# Operations
lis.append(6) # Add to end of list
lis.insert(0,1) # Insert 1 to index 0

len(lis) # Gets length of list

lis.extend(lis2) # Add any iterable to end of lis
lis3 = lis1 + lis2 # Join/Concatenates lists

lis.remove(1) # Remove 1st instance of 1
lis.pop(2) # Remove element at index 2
lis.pop() # Remove last item
del lis[0] # Remove element at index 0
del lis # Delete whole list
lis.clear() # Clear contents of list
lis.count(0) # Returns the number of times 0 appears in list

# Sorting
sorted(lis)
lis.sort() # Sorts list alphanumerically in ascending order (capital letters before lowercase)
lis.sort(reverse = True) # Sorts in descending order
def myfunc(n):
  return abs(n - 50)
lis.sort(key = myfunc) # Sorts based on some function - how close number is to 50
lis.sort(key = str.lower) # Case insensitive sort

# Copying
lis2 = lis # lis2 references lis
lis2 = lis.copy() # Copys lis
lis2 = list(lis) # Copys lis
lis2 = lis.deepcopy() # Copys lis1 recursively (including nested lists)

# Conversion
list(collection) # Convert any collection datatype to list

# Looping
for x in lis:
  pass 
range
for i in range(len(lis)): # i will give the index
  pass # lis[i] will give the item

for i, j in enumerate(lis): # i is the index, j is the value
  pass

for i in range(len(digits)-1, -1, -1): # Loop in reverse
```

#### Tuples

Ordered and immutable (unchangeable) collection. Allows duplicate values. Operations for tuples same as operations for lists. But cannot add, remove, change items.

```python
# Constructor
tup = (1, 2, 3, 4, 5)

# Operations on tuples
tuple(list(tup).append(6)) # Need to convert tuple to list to perform operations on list then convert back

# Conversion
tuple(collection) # Convert any collection datatype to tuple

# Unpacking
(a, b, *c) = tup # Assigns 1 to a, 2 to b, the rest of the tuple as a list to c

# Joining tuples
tup3 = tup1 + tup2 # Joining tup1 and tup2
tup3 = tup1 * 3 # Join 3x tup1 into tup3

```

#### Sets

Used to store multiple items in a single variable. Unordered and unindexed collection. Does not allow duplicate values.

```python
# Constructor
st = {1, 2, 3, 4, 5}

# Conversion
set(collection) # Convert any collection datatype to set

# Looping - cannot use range(len()) because no index. Use:
for x in st:
  pass

# Operations
st.add(0) # Add 0 to set


st.remove(3) # Remove element 3 from set - will raise error if item does not exist
st.discard(3) # Remove if present. 
st.pop() # Removes last (random) item from set
st.clear() # Empties set
del st # Deletes set

# Joining sets - duplicates excluded
st3 = st.union(st2) # Returns new set with items from both sets
st.update(st2) # Add items from st2 to st
st.update(lis) # Add items from any iterables to set

st.intersection_update(st2) # Update st with intersection
s3 = st.intersection(st2) # Keep intersection of sets

s3 = st.symmetric_differenct(st2) # XOR
```

#### Dictionaries

Used to store data in key value pairs. Unordered, Mutable, does not allow duplicates. Values in dict can be of any data type.

Dicts can contain dicts as nested dictionaries - json style

```python
# Constructor
dic = {
  "name" : "Lero",
  "age" : 3,
  "year" : 2005
  #"year" : 2001 will override previous year value
  "colors" : ["orange", "black", "pink"]
 }

# Accessing values
dic["name"] # Outputs Lero
dic.get("name")

if someKey in dic: # Check if key exists in dictionary

len(dic) # Prints number of items in dictionary

# Operations
dic.keys() # Returns list of all keys in dict
dic.values() # Returns list of all values in dict
dic.items() # Returns list of tuples of key-value pairs

dic.pop("age") # Remove item with key of age
dic.popitem() # Removes last inserted item
del dic["age"] # Removes item with specified key name

del dic # Deletes dectionary
dic.clear() # Empties dictionary


# Check if key is present in dictionary
if "age" in dic:
  pass

# Changing / Adding values
dic["age"] = 5 
dic.update({"age": 6}) # Updates dictionary with items

# Looping
for x in dic: # Loop through keys
for x in dic.keys(): # Loop through keys
for x in dic.values(): # Loop through values
for x in dic.items(): # Loop through both keys and values

# Copying
dic2 = dic.copy() # Shallow copy
dic2 = dict(dic)

```

## Built-in Libraries

### Arrays (Lists)
Python does not have C++/Java style fixed-sized arrays. Use Python lists instead.

### Strings

Use python built-in library for strings.


### Linked List

```python
# Creating Linked Lists
class Node:
  def __init__(self, val=None):
  self.val = val
  self.next = None

class LinkedList:
  def __init__(self):
    self.head = None

ll = LikedList()
ll.head = Node("Mon")
node2 = Node("Tue")
node3 = Node("Wed")

ll.head.next = node2
node2.next = node3

# Traversing Linked List
ptr = ll.head
while ptr is not None:
  ptr = ptr.next
```

## Stacks and Queues

### Stacks

Stacks can be implemented using built-in Lists or Deque library

```python
# Stack using list
stack = []

stack.append('a') # Push
stack.pop() # Pop
stack[-1] # Peek
len(stack) == 0 # Empty

# Stack using deque
from collections import deque
stack = deque()

stack.append('a') # Push
stack.pop() # Pop
```

### Queues

Queues can be implemented using built-in Lists, collections.deque library or queue.Queue

```python
# Queue using list
queue = []
q.append('a') # Queue
queue.pop(0) # Deque
queue[0] # Peek

# Queue using deque
from collections import deque
queue = deque()
q.append('a') # Queue
q.popleft() # Deque

# Queue using queue.Queue
queue = Queue()
q.put('a') # Queue
q.get() # Deque
q.empty() # Returns true if queue is empty
q.size()

```

### Priority Queue


## Hash Tables
### Hash Sets

Use Python's built-in set

### Hash Maps

Dictionaries are the equivalent of Hash Maps in Python.

## Trees
### Binary Tree
### Binary Search Tree
### N-ary Tree
#### Recursion on N-ary Tree
### Trie

## Graphs
