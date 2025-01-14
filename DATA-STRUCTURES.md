# DATA STRUCTURES

## TABLE OF CONTENTS

- [General](#general)
  - Stack
  - Queue
  - Priority Queue
  - Set
  - Map
  - Linked List
  - Doubly Linked List

<a name="general" />

## General

### Stack

Is a linear data structure that follows the principle of Last in First Out (LIFO). It
means the last element inserted is the one that is be removed first. You can think it as a
pile of plates on top of another.
Possible operations could be:

1. Push
2. Pop
3. IsEmpty
4. IsFull
5. Peek (Get the value of the top element without removing it).

### Queue

Like stacks, are collection of elements. But unlike stacks, they follow the Fist in First Out (FIFO)
principle. Elements added to the queue are pushed to the end, and only the element at the front of the queue
is allowed to be removed.

Posible operations could be:

1. enqueue - add (store) an item to the queue.
2. dequeue - Remove (and access) an item from the queue.
3. peek - Get the element at the front of the queue without remove it.
4. isFull - Checkis if the queue is full
5. isEmpty - Checks if the queue is empty.

### Priority Queue

Is similar to a Queue, but in this case, every element inside the priority queue has a priority value associated
with it. The priority of the elements in a priority queue determines the order in which elements are served.
If in any case the elements have same priority, they are served in the same way as a normal Queue.

### Set

A set is a data structure that can store any number of unique values in any order you wish.

Posible operations could be:

1. has - Check if the set has an element.
2. values - Get set values.
3. add - Add a value
4. remove - Remove a value
5. size - Get the Set size.

### Map

Are data structures that store key-value pairs. It is also called "dictionary".

### Linked list

A linked list is a linear data structure, in which the elements are not stored at contigous memory locations.
The elements in a linked list are linked using pointers. Each element is called "Node", and each "Node" contains
a data field and a reference (link) to the next node.

Possible operations could be:

1. add - Insert an element
2. remove - Remove an element
3. addAt - Add an element at given position
4. removeAt - Remove an element at given position.
5. reverse - Reverse a linked list.
6. isEmpty - Check if a linked list is empty.

### Doubly Linked list

Is a Linked List but this one contains an extra pointer used to point a previous element in a Node.
