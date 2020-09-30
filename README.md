# Java Cheatsheet for Algorithms and Data Structures

## Built in Libraries
### Arrays
```java
// Initialize
int[] a = new int[5];
int[] b = {1,2,3};

// Accessing
a.length;

//Sorting
Arrays.sort(a);
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
ll.toArray(); // Cast ll to array
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

### Sets
```java
HashSet<String> set new HashSet<String>(); // Initialize new empty Set
HashSet<String> set new HashSet<String>(Arrays.asList(list)); // Convert elements of list into hashset
set.add("Hi"); // Adds new string element to set
set.contains("Hi") // Output: True - Checks for "Hi" in set
```

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