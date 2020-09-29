# Java Cheatsheet for Algorithms and Data Structures

## Arrays
### Initializing new array
```
int[] arr = new int[15];
```

### For loops
```
for (int i = 0; i < arr.length; i++) {}

// for each value in array
for (int val : arr) {}
```

### Copying Arrays
```
arr.clone();
```

### Sorting 
```
Arrays.sort(arr);
```

### Call by reference

### Integer limits
```
Integer.MIN_VALUE
Integer.MAX_VALUE
```

## Lists
```
List<Integer> nodes = new ArrayList<Integer>();
```

## Linked Lists
### Singly Linked List
```
public class Node {
    int val;
    Node next;
    Node(int x) { val = x; }
}
```

### Doubly Linked List
```
public class Node {
    int val;
    Node next, prev;
    Node(int x) { val = x; }
}
```
### Two Pointer LL Template
#### Java
```
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
## Built in Linked List Library


## Queues
Queue Implementation using dynamic array
```
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
        if (q.isEmpty() == false) {
            System.out.println(q.Front());
        }
    }
}
```
### Built in Queue Library
```
Queue<Integer> q = new LinkedList(); // Initialize new queue

q.offer(5); // Queue new element
q.poll(); // Dequeue
q.peek(); // Get first element, return null if queue is empty
q.size(); // Get size of queue
```
