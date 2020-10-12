# Java Cheatsheet for Algorithms and Data Structures

## Common functions
```java
// Square
Math.pow(n, 2); // n squared
Integer.MAX_VALUE;
```

## Built in Libraries
### Arrays
```java
// Initialize
int[] a = new int[5];
int[] b = {1,2,3};

// Accessing
a.length;

//Sorting
Arrays.sort(a); // Quicksort, O(n log n) time

// Checker to empty array
if (arr.length == 0) return new int[0];
```

### Strings
Strings are IMMUTABLE, so CANNOT compare strings using "=="

```java
// Initialize
String s1 = "Hi";

// Reference 
String s2 = s1; // s2 == s1 -> Same object

// Get string length
s1.length();

// Accessing
s1.charAt(0); // Get character at index 0

// Compare string value
s1.equals(s3);
s1.compareTo(s3);

// Concatenate Strings - O(N) time per concatenation
s1 += "!"; // s1 becomes "Hi!"

// Find position
s1.indexOf("i"); // position of 1st occurrence of i
s1.lastIndexOf("i", 4); // position of last i, starting at position 4

// Splicing
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
str.append("hello") // O(N) time no matter how many concatenations are done

// Convert StringBuilder to string object after concatenation is done
String s = str.toString();
char[] ch = s.toCharArray();
String s = String.valueOf(arr); // Convert character array to string

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
// Initialize
List<Integer> v0 = new ArrayList<>(); // Initialize new array
List<Integer> v1 = new ArrayList<>(Arrays.asList(a)); // Cast array a to vector

List<Integer> v2 = v1; // Reference to v1
List<Integer> v3 = new ArrayList<>(v1) // Make actual copy of v1

// Access
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
// Initialize
LinkedList<String> ll = new LinkedList<String>();

// Access
ll.size(); // Get length
ll.add("A"); // Add element
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

### Queues
```java
Queue<Integer> q = new LinkedList(); // Initialize new queue

q.offer(5); // Queue new element
q.poll(); // Dequeue
q.peek(); // Get first element, return null if queue is empty
q.size(); // Get size of queue
```


## Hash Tables
Types of hashtables used are `HashSet` and `HashMap`. Used for quick insertion and search. 

### Hash Sets
Implementation of `set` data structure to store **no repeated values**.
One common use of hashset is to **check if a value has ever appeared before**

```java
// Initialize
HashSet<String> set = new HashSet<>(); // Initialize new empty HashSet
HashSet<String> set = new HashSet<String>(Arrays.asList(list)); // Convert elements of list into hashset

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
// Initialize
HashMap <Integer, String> h = new HashMap<>();

// Methods
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
- Recursive call is the final instruction in recursion function. Only 1 recursive call in function.

## Arrays
### Initializing new array
```java
int[] arr = new int[15];
```

### For loops
```java
for (int i = 0; i < arr.length; i++) {}

// for each value in array
for (int val : arr) {}
```

### Copying Arrays
```java
arr.clone();
```

### Sorting 
```java
Arrays.sort(arr);
```

### Call by reference

### Integer limits
```java
Integer.MIN_VALUE
Integer.MAX_VALUE
```

## Lists
```java
List<Integer> nodes = new ArrayList<Integer>();
```

## Linked Lists
### Singly Linked List
```java
public class Node {
    int val;
    Node next;
    Node(int x) { val = x; }
}
```

### Doubly Linked List
```java
public class Node {
    int val;
    Node next, prev;
    Node(int x) { val = x; }
}
```
### Two Pointer LL Template
#### Java
```java
// Initialize slow & fast pointers
ListNode slow = head;
ListNode fast = head;
/**
 * Change this condition to fit specific problem.
 * Attention: remember to avoid null-pointer error
 **/
while (slow != null && fast != null && fast.next != null) {
    slow = slow.next;           // move slow pointer one step each time
    fast = fast.next.next;      // move fast pointer two steps each time
    if (slow == fast) {         // change this condition to fit specific problem
        return true;
    }
}
return false;   // change return value to fit specific problem
```
## Queues
Queue Implementation using dynamic array
```java
// "static void main" must be defined in a public class.

class MyQueue {
    // store elements
    private List<Integer> data;         
    // a pointer to indicate the start position
    private int p_start;            
    public MyQueue() {
        data = new ArrayList<Integer>();
        p_start = 0;
    }
    /** Insert an element into the queue. Return true if the operation is successful. */
    public boolean enQueue(int x) {
        data.add(x);
        return true;
    };    
    /** Delete an element from the queue. Return true if the operation is successful. */
    public boolean deQueue() {
        if (isEmpty() == true) {
            return false;
        }
        p_start++;
        return true;
    }
    /** Get the front item from the queue. */
    public int Front() {
        return data.get(p_start);
    }
    /** Checks whether the queue is empty or not. */
    public boolean isEmpty() {
        return p_start >= data.size();
    }     
};

public class Main {
    public static void main(String[] args) {
        MyQueue q = new MyQueue();
        q.enQueue(5);
        q.enQueue(3);
        if (q.isEmpty() == false) {
            System.out.println(q.Front());
        }
        q.deQueue();
        if (q.isEmpty() == false) {
            System.out.println(q.Front());
        }
        q.deQueue();
        if (q.isEmpty() chungha== false) {
            System.out.println(q.Front());
        }
    }
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