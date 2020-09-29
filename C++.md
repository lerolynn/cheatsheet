# C++ Cheatsheet for Algorithms and Data Structures

## Arrays
### Initializing new array
```

```

### For loops
```
for (int i = 0; i < arr.length; i++) {}
```

### Copying Arrays
```

```

### Sorting 
```

```

### Call by reference

### Integer limits
```

```

## Lists
```

```

## Linked Lists
### Singly Linked List
```
sturct Node {
    int val;
    Node *next;
    Node(int x) : val(x), next(NULL) {}
}
```

### Doubly Linked List
```
sturct Node {
    int val;
    Node *next, *prev;
    Node(int x) : val(x), next(NULL),prev(NULL) {}
}
```
### Two Pointer LL Template

## Built in Linked List Library


## Queues
Queue Implementation
```
#include <iostream>

class MyQueue {
    private:
        // store elements
        vector<int> data;       
        // a pointer to indicate the start position
        int p_start;            
    public:
        MyQueue() {p_start = 0;}
        /** Insert an element into the queue. Return true if the operation is successful. */
        bool enQueue(int x) {
            data.push_back(x);
            return true;
        }
        /** Delete an element from the queue. Return true if the operation is successful. */
        bool deQueue() {
            if (isEmpty()) {
                return false;
            }
            p_start++;
            return true;
        };
        /** Get the front item from the queue. */
        int Front() {
            return data[p_start];
        };
        /** Checks whether the queue is empty or not. */
        bool isEmpty()  {
            return p_start >= data.size();
        }
};

int main() {
    MyQueue q;
    q.enQueue(5);
    q.enQueue(3);
    if (!q.isEmpty()) {
        cout << q.Front() << endl;
    }
    q.deQueue();
    if (!q.isEmpty()) {
        cout << q.Front() << endl;
    }
    q.deQueue();
    if (!q.isEmpty()) {
        cout << q.Front() << endl;
    }
}
```
### Built in Queue Library
```
queue<int> q; // Initialize new queue

q.push(5); // Enqueue
q.pop() // Dequeue
q.empty(); // Boolean Check if queue is empty
q.front() // Get first element of queue
q.size() // Get size of queue
```

