# Java Algorithms and Data Structures 

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
  * Dynamic Programming
  * Greedy Algorithms

## Common Functions

```java
// Power
Math.pow(n, 2); // n squared

// Max, Min Integer
Integer.MAX_VALUE;
Integer.MIN_VALUE;

// Convert binary integer to string
Integer.toBinaryString(n); 

// Rounding
Math.round(5.8); // Round to nearest integer
Math.ceil(5.3); // Round up
Math.floor(5.8); // Round down

// XOR
0 ^ 1 = 1;
1 ^ 1 = 0;

// Comparator
(e1, e2) -> e1.getValue() - e2.getValue();

arr.clone(); // deepcopy array

// Ternery operator
return (isEven) ? (median + prev)/2.0 : median;

// Generate random number
Random rand = new Random();
int rand_int = rand.nextInt(1000); // rand int between 0 and 1000
double rand_doub = rand.nextDouble();

Math.random(); // get random integer between 0.0 and 1.0

// Casting
int a = (int) someFloat; // cast float to int
```

## Built-in Libraries

### Arrays

```java
// Instantiating
int[] a = new int[5]; // declare and allocate memory to array
int[] b = {1,2,3}; // Declare array literal

List<Integer> table = new ArrayList[n]; // Instantiate array of arraylist

// Operations
a.length;

Arrays.copyOfRange(arr, 0, 2); // Splicing Array
Arrays.sort(a); // Quicksort, O(n log n) time
Arrays.sort(intervals, (a, b) -> a[0] - b[0]); // Sort intervals based a, b, where a[0] < b[0]


// Checker to empty array
if (arr.length == 0) return new int[0];

// Static Initialization, return
return new int[] {map.get(nums[i]), i};
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

#### Character

Useful character functions

```java
Character.isLetter(char ch); // Returns true if character is a letter
Character.isLetterOrDigit(char ch); // Returns true if letter or digit
Character.toUpperCase(char ch); // Converts character to uppercase

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

v1.toArray(new int[v1.size()]); // Convert arraylist to array
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
q.isEmpty(); // Returns true if queue is empty
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

pq.isEmpty(); // Check if pq is empty
pq.size(); // Returns size of pq
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
set.size(); // Get number of elements in hashset
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
h.size(); // Get size of map (number of key-value pairs)
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

### Operators

```java
// Bitwise Operators
a | b // OR
a & b // AND
a ^ b // XOR
~a // NOT Complement of a (~0101 = 1010)

// Shift Operators - Used to shift bits left or right
// Equivalent to multiplying or dividing by 2

// Shift Right - fills 0 in void on left
a >> 1 // Divides a by 2 (Preserves sign)

// Unsigned right shift - fills 0 in void on left
a >>> 1 // Shifts right, does not preserve sign bit

// Shift left
a << 1 // Shifts bits of number to left, fills 0 in void - Multiplies with some power of 2

a << 1 // a = 5, a << 1 = 10
a << 2 // = 20

```

XOR useful functions

* a ^ 0 = a
* a ^ a = 0
* a ^ b ^ a = b



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

### Divide and Conquer

Recursively breaks down problem into 2 or more subproblems until subproblem can be solved directly

Steps:

1. **Divide** into set of subproblems
2. **Conquer** Solve each subproblem recursively
3. **Combine** results of each subproblem

Important to figure out the **recurrence relationship** between subproblems and the original problem

#### Mergesort

Time complexity is O(N log N). Space complexity is O(N)

```java
private int[] merge(int[] left, int[] right) {
    int[] merged = new int[left.length + right.length];
    int leftPtr = 0;
    int rightPtr = 0;
    int mergedPtr = 0;

    while (leftPtr < left.length && rightPtr < right.length) {
        if (left[leftPtr] < right[rightPtr]) merged[mergedPtr++] = left[leftPtr++];
        else merged[mergedPtr++] = right[rightPtr++];
    }

    // Add whats left to array
    while (leftPtr < left.length) merged[mergedPtr++] = left[leftPtr++];
    while (rightPtr < right.length) merged[mergedPtr++] = right[rightPtr++];

    return merged;
}

public int[] sortArray(int[] nums) {
    if (nums.length <= 1) return nums;

    int pivot = nums.length / 2;

    // divide
    int[] left = sortArray(Arrays.copyOfRange(nums, 0, pivot));
    int[] right = sortArray(Arrays.copyOfRange(nums, pivot, nums.length));

    // Merge back
    return merge(left, right);
}

```

#### Quicksort

Steps:

1. **Partitioning** Pick a pivot to divide list into 2 sublists, all values left of pivot is lower than pivot. Choose 1st element, or randomly pick element
2. Recursively sort sublists. Base case is when input list is empty or contains just 1 element.
3. Concatenate sorted sublists

```java
public void quickSort(int [] lst) {
    /* Sorts an array in the ascending order in O(n log n) time */
    int n = lst.length;
    qSort(lst, 0, n - 1);
}

private void qSort(int [] lst, int lo, int hi) {
    if (lo < hi) {
        int p = partition(lst, lo, hi);
        qSort(lst, lo, p - 1);
        qSort(lst, p + 1, hi);
    }
}

private int partition(int [] lst, int lo, int hi) {
    /*
        Picks the last element hi as a pivot
        and returns the index of pivot value in the sorted array */
    int pivot = lst[hi];
    int i = lo;
    for (int j = lo; j < hi; ++j) {
        if (lst[j] < pivot) {
        int tmp = lst[i];
        lst[i] = lst[j];
        lst[j] = tmp;
        i++;
        }
    }
    int tmp = lst[i];
    lst[i] = lst[hi];
    lst[hi] = tmp;
    return i;
}

```

#### Master Theorem

Finds asymptotic analysis of many recursive algorithms

### Backtracking

"Generate All", "Compute All" type qns - normally exponential time
Choice - Defining decision space
Constraints - Directing recursion
Goals - When recursion bottoms out

### Dynamic Programming

Bottom-up approach to recursion. Template (building iteratively):

```java

// Fibonacci number
if (nums.length == 0) return 0;

int dp[] = new int[nums.length + 1];
dp[0] = 1;
dp[1] = 1;

for (int i = 2; i < dp.length; i++) {
    dp[i] = dp[i - 1] + dp[i - 2];
}

return dp[nums.length];

```

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

#### Backtracking

Builds candidates to solution and abandons candidate as soon as solution cannot be valid.

```python
 backtrack_nqueen(row = 0, count = 0):
    for col in range(n):
        # iterate through columns at the curent row.
        if is_not_under_attack(row, col):
            # explore this partial candidate solution, and mark the attacking zone
            place_queen(row, col)
            if row + 1 == n:
                # we reach the bottom, i.e. we find a solution!
                count += 1
            else:
                # we move on to the next row
                count = backtrack(row + 1, count)
            # backtrack, i.e. remove the queen and remove the attacking zone.
            remove_queen(row, col)
    return count

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

```java
/*
 * Return true if there is a path from cur to target.
 */
boolean DFS(Node cur, Node target, Set<Node> visited) {
    return true if cur is target;
    for (next : each neighbor of cur) {
        if (next is not in visited) {
            add next to visted;
            return true if DFS(next, target, visited) == true;
        }
    }
    return false;
}

```


