# Algorithms and Data Structures

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

* Techniques
  * Bit Manipulations
  * Recursion
  * BFS (Breadth First Search)
  * DFS (Depth First Search)

## Common functions

```java
// Square
Math.pow(n, 2); // n squared
Integer.MAX_VALUE;

// Comparator
(e1, e2) -> e1.getValue() - e2.getValue();
```

## Built-in Libraries

### Arrays

```java
// Instantiating
int[] a = new int[5]; // declare and allocate memory to array
int[] b = {1,2,3}; // Declare array literal

// Operations
a.length;

Arrays.copyOfRange(arr, 0, 2); // Splicing Array
Arrays.sort(a); // Quicksort, O(n log n) time

// Checker to empty array
if (arr.length == 0) return new int[0];
```

### Strings

Strings are IMMUTABLE, so CANNOT compare strings using "==". Any changes to strings takes o(n) time.

```java
// Initialize
String s1 = "Hi";

// Reference 
String s2 = s1; // s2 == s1 -> Same object

// Get string length
s1.length();
s1.charAt(0); // Get character at index 0

s1.equals(s3); // Compare string value
s1.compareTo(s3);

s1 += "!"; // s1 becomes "Hi!" // Concatenate Strings - O(N) time per concatenation
s1.indexOf("i"); // position of 1st occurrence of i
s1.lastIndexOf("i", 4); // position of last i, starting at position 4
s1.substring(3,8); // Splice from position 3 inclusive to 8 (non inclusive)

// Casting
int a = s1.charAt(0) - '0' // Get number from digits 0 - 9 based off ascii characters
```

#### Char Array

Convert strings to char array to become mutable

```java 
// Convert strings to char ARRAY - same properties as array
char[] str = s1.toCharArray();
str[2] = '.';
```

#### StringBuilder

Use StringBuilder to if have to concatenate strings often. Runs concatenation in O(N) time overall,

```java
StringBuilder str = new StringBuilder();
str.append("hello");

// Convert StringBuilder to string object after concatenation is done
String s = str.toString();
char[] ch = s.toCharArray();
String s = String.valueOf(arr); // Convert character array to string

str.setLength(0); // clear string builder

// Split string - (n < 0 - don't remove empty string; n > 0; split max n times)
String[] arr = s.split("," 0); // Split into array of max size, remove trailing empty strings
s.trim(); // Eliminate trailing whitespaces

// Convert String to Integer
int A = Integer.parseInt(a);
int A = Integer.parseInt(a, 2); // Convert string to binary Integer

// Convert Integer to String
String a = Integer.toString(A);
String a = Integer.toBinaryString(A); // Convert to binary in string format
```

### Dynamic Arrays

```java
// Constructor
List<Integer> v0 = new ArrayList<>(); // Initialize new array
List<Integer> v1 = new ArrayList<>(Arrays.asList(a)); // Cast array a to vector

List<Integer> v2 = v1; // Reference to v1
List<Integer> v3 = new ArrayList<>(v1) // Make actual copy of v1

// Operations
v1.size(); // Get length
v1.get(0); // Get element at index 0
v1.set(1, 2); // Set element at index 1 to be 2
v1.add(4); // Add element 4 to end of vector
v1.add(1, 3); // Add element 3 at index 1 
v1.remove(v1.size() - 1); // Remove element at last index

// Sorting
collections.sort(v1); // Sort array v1
```

### Linked List

```java
// Constructor
LinkedList<String> ll = new LinkedList<String>();

// Operations
ll.size(); // Get length
ll.add("A"); // Add element at end of linked list
ll.addFirst("A"); // Add to start of linked list
ll.add(0, "E"); // Add element E at index 0

ll.set(1, "B"); // Change element at index 1 to B

ll.remove("A"); // Remove 1st occurrence of element A
ll.remove(0); // Remove element at index 0
ll.removeFirst(); // Removes 1st element
ll.removeLast(); // Removes last element

ll.contains("A"); // Return true if ll contains element A

// Cast
ll.toString(); // Cast to string
```

## Stacks and Queues

### Stacks

Last-in-first-out (LIFO). Newest element added to stack processed first
Push, pop

```java
// Constructor
Stack<Integer> stack = new Stack<>();

// Operations
stack.push(1); // Push element to top of stack
stack.peek(); // Returns element at top of stack, null if stack is empty
stack.pop(); // Returns element at top of stack, removes element, returns null if stack is empty

stack.search(); // Returns position of element from top of stack, -1 if not in stack
stack.empty(); // Returns true if stack is empty

```

### Queues

First-in-first-out (FIFO), First element added to queue processed first
Enqueue, Dequeue

```java
// Constructor
Queue<Integer> q = new LinkedList(); // Initialize new queue

// Operations
q.offer(5); // Queue new element
q.poll(); // Dequeue
q.peek(); // Get first element, return null if queue is empty
q.size(); // Get size of queue
```

### Priority Queue

PriorityQueue in Java implements a min heap.

```java
// Constructor
PriorityQueue<E> pq = new PriorityQueue<E>();
PriorityQueue<E> pq = new PriorityQueue<E>(Collection<E> c);

// Operations
pq.add(10); // Add items
pq.peek(); // get min item of pq
pq.poll(); // get and remove item

```

Implementing **max heap**

```java
// Constructor
PriorityQueue<E> pq = new PriorityQueue<E>(original.size(), Collections.reverseOrder());
Queue<Map.Entry<Integer,Integer>> heap = new PriorityQueue<>((a, b) -> b.getValue() - a.getValue());
```

## Hash Tables

Types of hashtables used are `HashSet` and `HashMap`. Used for quick insertion and search. 

### Hash Sets

Implementation of `set` data structure to store **no repeated values**.
One common use of hashset is to **check if a value has ever appeared before**

```java
// Constructor
HashSet<String> set = new HashSet<>(); // Initialize new empty HashSet
HashSet<String> set = new HashSet<String>(Arrays.asList(list)); // Convert elements of list into hashset

// Operations
set.add("Hi"); // Adds new string element to set if elementis not already present - return false if otherwise
set.contains("Hi") // Output: True - Check if key is in hashset
set.remove(2); // Remove key from set
set.clear(); // Clear hashset
set.isEmpty(); // Check if hashset is empty
for (String i : set) {} // Iterate through hashset
```

### Hash Maps

Implementation of `map` data structure to store `(key, value)` pair. Similar to Python `dict` structure.

Often used for **memoization** in recursion. 
**memoization**: Store results in cache to prevent calculating a value multiple times

```java
// Constructor
HashMap <Integer, String> h = new HashMap<>();

// Operations
h.putIfAbsent(0, "H"); // Insert if key does not already exist
h.put(3, "Hi"); // Insertion, or update value - returns existing key, null if existing key does not exist
h.size(); // Get size of map
h.get(3); // Gets value associated with key
h.getOrDefault(key, defaultValue); // get value, return default if key not in hashmap
h.remove(3); // Delete key

h.containsKey(3); // Check if hashmap contains key
h.containsValue("Hi");

h.isEmpty(); // Check if hashtable is empty
h.clear() // clear hashtable

// Iterate over hashmap
for (Map.Entry<Integer, Integer> entry : hashmap.entrySet()) {
    entry.getKey();
    entry.getValue();
}
```

## Trees

### Binary Tree

Preorder Traversal root, left, right

```java
traverse(root.left);
nodes.add(root.val);
traverse(root.right);
```

Inorder Traversal - left, root, right

```java
traverse(root.left);
nodes.add(root.val);
traverse(root.right);
```

Postorder Traversal - left, right, root

```java
traverse(root.left);
nodes.add(root.val);
traverse(root.right);
```

Level-order Traversal - level by level
Use BFS

### Binary Search Tree

Special form of binary tree, satisfies binary search property.

* Value of each node > value in left subtree
* Value of node < value in right subtree
Inorder traversal will be in ascending order

### N-ary Tree

Can be traversed in:

1. Preorder - Root, children
2. Inorder
3. Postorder - Children, root
4. Level order - Level by Level - BFS

#### Recursion on N-ary Tree

Top-down Recursion

Bottom-up Recursion

### Trie

Type of N-ary tree, normally used to store strings.

Insertion

```java
// pseudocode
1. Initialize: cur = root
2. for each char c in target string S:
3.      if cur does not have a child c:
4.          cur.children[c] = new Trie node
5.      cur = cur.children[c]
6. cur is the node which represents the string S
```

Searching

```java
// pseudocode
1. Initialize: cur = root
2. for each char c in target string S:
3.      if cur does not have a child c:
4.          search fails
5.      cur = cur.children[c]
6. search successes
```

## Graphs



## Common Techniques

## Bit Manipulation

* a XOR 0 = a
* a XOR a = 0
* a XOR b XOR a = b

```java
i ^= x; // XOR operation
```

## Recursion

Steps:

1. Write down **recurrence relationship**
2. Find base case
3. Apply **memoization** when possible

**Tail Recursion** - exempted from extra space due to recursion calls

* Recursive call is the final instruction in recursion function. Only 1 recursive call in function.

## Searching

### Binary Search

Steps:

1. Sort if unsorted
2. Use loop/recursion to divide search space in half after each comparison
3. Determine viable candidates in remaining space

```java
int binarySearch(int[] nums, int target){
  if(nums == null || nums.length == 0)
    return -1;

  int left = 0, right = nums.length - 1;
  while(left <= right){
    // Prevent (left + right) overflow
    int mid = left + (right - left) / 2;
    if(nums[mid] == target){ return mid; }
    else if(nums[mid] < target) { left = mid + 1; }
    else { right = mid - 1; }
  }

  // End Condition: left > right
  return -1;
}
```

### BFS (Breadth First Search)

```java
/**
 * Return the length of the shortest path between root and target node.
 */
int BFS(Node root, Node target) {
    Queue<Node> queue;  // store all nodes which are waiting to be processed
    int step = 0;       // number of steps neeeded from root to current node
    // initialize
    add root to queue;
    // BFS
    while (queue is not empty) {
        step = step + 1;
        // iterate the nodes which are already in the queue
        int size = queue.size();
        for (int i = 0; i < size; ++i) {
            Node cur = the first node in queue;
            return step if cur is target;
            for (Node next : the neighbors of cur) {
                add next to queue;
            }
            remove the first node from queue;
        }
    }
    return -1;          // there is no path from root to target
}
```

### DFS (Depth First Search)
