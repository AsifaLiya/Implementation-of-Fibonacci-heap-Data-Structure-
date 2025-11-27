# Implementation-of-Fibonacci-heap-Data-Structure-
This is my project on Fibonacci heap of Data Structure

# Project Report: Implementation of Fibonacci Heap

## Abstract
This project report outlines the implementation of a **Fibonacci Heap** in C.  
A Fibonacci Heap is a collection of heap-ordered trees that satisfies the **minimum heap property** (key of a node ≥ key of its parent).  
It supports efficient operations in terms of **amortized time complexity**, making it suitable for algorithms like **Dijkstra’s** and **Prim’s**.

---

## Introduction
Fibonacci Heaps are advanced data structures used to improve the running time of network optimization algorithms.  
**Primary operations** include:
- Insertion
- Finding minimum
- Extracting minimum
- Union
- Decrease key
- Delete

This report describes the implementation and complexities of these operations.

---

## Data Structure
- **NODE**: Represents each node with key, degree, parent, children, siblings, and markers.  
- **FIB_HEAP**: Represents the heap with number of nodes, pointer to minimum node, and auxiliary fields.

---

## Functions Implemented
1. `make_fib_heap` – Initialize an empty Fibonacci Heap  
2. `insertion` – Insert a new node  
3. `find_min_node` – Return the minimum node  
4. `unionHeap` – Merge two heaps  
5. `extract_min` – Remove and return the minimum node  
6. `consolidate` – Maintain heap properties after extraction  
7. `fib_heap_link` – Link nodes during consolidation  
8. `decrease_key` – Decrease key of a node  
9. `cut` – Cut a node and add to root list  
10. `cascading_cut` – Recursive cuts to maintain heap properties  
11. `find_node` – Find a node with a specific key  
12. `Delete_Node` – Delete a node by decreasing its key and extracting

---

## Key Structures

### Node Structure
```c
#typedef struct _NODE {
  int key;
  int degree;
  struct _NODE *left_sibling;
  struct _NODE *right_sibling;
  struct _NODE *parent;
  struct _NODE *child;
  bool mark;
  bool visited;
} NODE;

#Fibonacci Heap Structure
typedef struct fibanocci_heap {
  int n;
  NODE *min;
  int phi;
  int degree;
} FIB_HEAP;

#Key Functions
make_fib_heap
FIB_HEAP *make_fib_heap() {
  FIB_HEAP *H = (FIB_HEAP *)malloc(sizeof(FIB_HEAP));
  H->n = 0;
  H->min = NULL;
  H->phi = 0;
  H->degree = 0;
  return H;
}

#insertion
void insertion(FIB_HEAP *H, NODE *new, int val) { 
  // Node allocation and insertion logic
}

#extract_min
NODE *extract_min(FIB_HEAP *H) { 
  // Extract minimum and consolidate
}

#consolidate
void consolidate(FIB_HEAP *H) {
  // Ensure heap properties after extract_min
}
```

Helper Functions: 
-fib_heap_link, cut, cascading_cut, decrease_key, find_node, Delete_Node

# Test and Results

The program provides a menu-driven interface for testing heap operations:

Create Fibonacci heap

Insert nodes

Find minimum node

Union of heaps

Extract minimum

Decrease key

Delete node

Print heap

Exit

# Sample Interaction:

Creating heap → Insert nodes → Find min → Extract min → Print heap

# Conclusion

The Fibonacci Heap implementation in C demonstrates efficiency and correctness of heap operations.
Maintaining heap properties ensures optimal performance for algorithmic tasks.
Future work: Optimization and testing with larger datasets.

# References

Cormen, T. H., Leiserson, C. E., Rivest, R. L., & Stein, C. (2009). Introduction to Algorithms.
