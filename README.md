# Heap Implementation in Python

This repository contains an implementation of a **Min-Heap** and **Max-Heap** in Python using a class-based approach. The heap supports insertion, deletion, and heap property maintenance.

## Class: `Heap`

The `Heap` class provides an implementation of a priority queue, supporting both **Min-Heap** and **Max-Heap** functionality.

### **Attributes:**
- `_heap`: A list used to store heap elements (1-based index, first element is `None` for easy calculations).
- `_pos`: Tracks the number of elements currently in the heap.
- `_minheap`: Boolean flag (`True` for Min-Heap, `False` for Max-Heap).

### **Methods:**
#### `__init__(isMinHeap=True)`
Initializes a heap instance.
- **Parameters:**
  - `isMinHeap` (bool): Determines if the heap is a **Min-Heap** (`True`) or **Max-Heap** (`False`).

#### `size() -> int`
Returns the number of elements in the heap.

#### `is_empty() -> bool`
Checks if the heap is empty.

#### `left(x: int) -> int`
Returns the index of the left child of a node.

#### `right(x: int) -> int`
Returns the index of the right child of a node.

#### `father(x: int) -> int`
Returns the index of the parent of a node.

#### `getTop() -> int`
Returns the top element of the heap (**minimum for Min-Heap, maximum for Max-Heap**).

#### `compare(a, b) -> bool`
Compares two elements based on heap type:
- Returns `True` if `a < b` (Min-Heap)
- Returns `True` if `a > b` (Max-Heap)

#### `insert(x: int)`
Inserts an element into the heap while maintaining the heap property.

#### `_sift_up(idx: int)` (Private)
Moves an element up to restore the heap property after insertion.

#### `deleteTop() -> int`
Removes the top element from the heap and reorders to maintain heap property.

#### `_sift_down(idx: int)` (Private)
Moves an element down to restore heap property after deletion.

#### `buildHeap(arr: list)`
Builds a heap from an existing list using heapify.

## Features
- Supports both **Min-Heap** and **Max-Heap**
- Insert elements and maintain heap property
- Delete the top element (minimum or maximum)
- Build a heap from an existing list
- Check heap size and if it's empty

## Files
- `Heap.ipynb` - Jupyter Notebook containing the heap implementation
- `test_heap.py` - Python script with unit tests for validating heap operations

## Usage
To use the heap class, import and initialize it:
```python
from heap import Heap

# Create a Min-Heap
min_heap = Heap(isMinHeap=True)
min_heap.insert(5)
min_heap.insert(3)
min_heap.insert(8)
print(min_heap.getTop())  # Output: 3

# Create a Max-Heap
max_heap = Heap(isMinHeap=False)
max_heap.insert(5)
max_heap.insert(3)
max_heap.insert(8)
print(max_heap.getTop())  # Output: 8
```

## Running Tests
Ensure you have Python installed, then run the test script:
```sh
python test_heap.py
```

