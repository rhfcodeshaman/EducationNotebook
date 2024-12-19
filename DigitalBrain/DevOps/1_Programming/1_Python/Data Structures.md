#note
# Subject Overview
[Roadmap](https://roadmap.sh/datastructures-and-algorithms)
[Youtube](https://www.youtube.com/playlist?list=PLkZYeFmDuaN2-KUIv-mvbjfKszIGJ4FaY)
## Array Data Structure
- An array is normally a fixed-sized list
- Python needs to use the `array` module or NumPy to do a traditional array, otherwise it will do dynamic arrays
- When a Python list grows beyond its current capacity in the memory, it allocates a new, larger block of memory and copies the existing elements--this **does** have performance implications in some cases
- The `array` module provides a more basic array type that is more memory-efficient than lists when dealing with large sequences of numeric data of the same type
	- These arrays can only store objects of the same data type, which is specified by a type code
- NumPy is the standard for numerical computing
	- Homogenous
	- Optimized for numerical operations
	- Supports multidimensional arrays like matrices and tensors
## Linked List Data Structure
- Uses 'nodes' that contain the data and a reference(or 'pointer') to the next node in the sequence
- Linked lists advantage is with inserting and deleting data
- Each node contains an address to where the next node is located
- Last node has the address 'null' to indicate there is no next node
- The head of the linked list is a reference to the first node. If the list is empty, the head is 'None'
- This setup makes inserting and deleting data far less complex than with standard arrays
- There are singly and doubly linked lists - downside of doubly linked lists is that they take more memory
- Circular linked lists also exist, where the last node points back to the head
## Stack Data Structure
- LIFO = Last-In First-Out
- Think of a stack of plates
- Common stack uses
	- Function calls: When you call functions in a program, the function calls are pushed onto a stack. When a function returns, it's popped off the stack. This manages the flow of execution.
	- Undo/Redo functionalities
	- Expression evaluation(think evaluating an expression with parantheses)
	- Backtracking Algorithms, just like undo/redo
	- Browser history: your back button uses a stack to store pages you've visited
- Python most commonly uses the `collections` module, specifically `collections.deque` (double-ended queue) for efficient stack operations, especially for large stacks
- In Python it is best practice to use a Class to build a stack
	- Encapsulation of data and the operations that can be performed on it
	- Abstraction of the interface for using the stack
	- Reusability of the blueprint for the rest of your code
	- Using a class with descriptive method names makes the code more self-documenting and easier to understand than just using list methods directly
## Queue Data Structure
- FIFO data structure
- Collection designed for holding elements prior to processing--linear data structure
- Think of a grocery store line
- Dequeuing is removing an object from a queue, enqueuing is adding an object to a queue
- Using `collections.deque` is the standard and most efficient way to implement queues in Python for most use cases. Avoid using lists for queues when performance matters, especially with large datasets.
## Hash Table Data Structure
- List of fruits and prices
- Customer comes in and asks for price of 'kiwi'
- What if we have 1000 items?
- Hash tables make complexity constant; mainly used for key-value lookup
- Each key is assigned a hash code/index in the array
- Python Dictionaries automatically generate the hash, this is why the key in a Python dictionary has to be immutable, this makes it hashable(the hash has to change if the key changes)
- Prior to 3.7, Python dicts did not preserve the order of insertion, but now they do(by default). JS Map() objects always maintain order.
## Tree Data Structure
Trees have:
- Nodes: individual elements in your tree, each holding a piece of data.
- Root: the topmost node in your tree, where everything starts.
- Parent-Child Relationships: Nodes are connected to each other in a parent-child relationship. A parent node can have multiple children, but each child only has one parent.
- Branches: the connections between nodes.
- Leaves: Nodes at the very bottom of the tree, with no children.

Trees are used for:
- Hierarchical representation
- Efficient searching
- Ordered data
- Flexibility

Types of trees:
- Binary Tree
- Binary Search Tree
- AVL Tree
- Heap Tree

To set up a tree, you must create the Node class, create the Root Node, and add Child Nodes, then build the rest of the tree by continuing to add Nodes. In Python that looks like this:
```python
Class Node:
    def __init__(self,data,children):
        self.data = data
        self.children = []

# Create the root
root = Node("A")

# Create some children
node_b = Node("B")
node_C = Node("C")

# Add the children to the root as children of the root
root.children.append(node_b)
root.children.append(node_c)
```
## Heap Data Structure
A specialized tree-based data structure that satisfies the heap property. It is like a binary tree where the nodes are arranged according to their values. THere are two main types of heaps:
1. Min Heap: the value of each node is less than or equal to the value of its children. This means the smallest element is always the root of the tree.
2. Max heap: the value of each node is greater than or equal to the value of its children, which means the largest element is always the root.
**Key Properties of a Heap**:
- Complete Binary Tree: all levels of the tree are completely filled, except possibly the last level, which is filled from left to right, which makes heaps efficient to represent using arrays.
- Heap Property: the value of each node must either by less than or equal to(min heap) or greater than or equal to(max heap) its children's values
**Why Are Heaps Useful?**
Heaps are particularly eefficient for:
- Finding the minimum or maximum element: the root always holds the min or max element so you can access it in O(1) time.
- Priority queues: heaps are the foundation of priority queues, where elements are processed based on their priority
- Heapsort algorithm: a sorting algorithm that uses the heap data structure
**Python**:
Python has a module `heapq` that provides functions to create and manipulate min heaps(**only**).
```python
import heapq

# Create a list (that we'll treat as a heap)
data = [5, 3, 8, 6, 7, 2]

# Convert the list into a min heap (in-place)
heapq.heapify(data)
print(data)  # Output (or similar, order may vary slightly): [2, 6, 3, 5, 7, 8]

# Add an element to the heap
heapq.heappush(data, 1)
print(data)  # Output: [1, 6, 2, 5, 7, 8, 3]

# Remove and return the smallest element (the root)
smallest = heapq.heappop(data)
print(smallest)  # Output: 1
print(data)  # Output: [2, 6, 3, 5, 7, 8]

# Get the smallest element without removing it (less efficient than just accessing the root directly in a min heap)
smallest_element = heapq.nsmallest(1, data)[0]
print(smallest_element) # Output: 2

# Get the largest element without removing it
largest_element = heapq.nlargest(1, data)[0]
print(largest_element) # Output: 8
```
**Representing Heaps with Arrays**:
- The root is index 0
- For any node at index `i`:
	- It's left child is at index `2 * i + 1`
	- It's right child is at index `2 * i + 2`
	- It's parent is at index `(i - 1) // 2`(using floor division)
**Creating a Max Heap Without `heapq`**
```python
import heapq

data = [5, 3, 8, 6, 7, 2]

# Create a max heap (simulated using negation)
max_heap = [-x for x in data]
heapq.heapify(max_heap)

# Get the maximum element (negate to get the original value)
max_element = -heapq.heappop(max_heap)
print(max_element)  # Output:
```
## Graph Data Structure
Graphs are a fundamental data structure in computer science, used to represent relationships between objects. Think of a social network, a map, or the internet itself - these all can be modeled as graphs.

**Key Components of a Graph**:
- Vertices(nodes): individual entities or objects in the graph. In a social network, vertices would be users.
- Edges(connections): these represent the relationships between vertices or nodes. In a social network, an edge between two uses might indicate that they are friends.
**Types of Graphs**:
- Directed Graph: Edges have a direction, indicating a one-way relationship. For example, on Twitter, use A might follow user B, but user B doesn't necessarily follow user A.
- Undirected Graph: Edges have no direction, representing a mutual relationship. For example in a network of roads, an edge between two cities means you can travel in either direction.
- Weighted Graph: Edges have weights associated with them, often representing distance, cost, or strength of a relationship.
**Representing Graphs in Python**:
There are two main ways to represent graphs in python--
1. Adjacency Matrix
```python
adjacency_matrix = [
    [0, 1, 0], 
    [1, 0, 1], 
    [0, 1, 0]
]
```
2. Adjacency List
```python
adjacency_list = {
    'A': ['B'],
    'B': ['A', 'C'],
    'C': ['B']
}
```
**Building a Graph Class in Python**:
```python
class Graph:
    def __init__(self, directed=False):
        self.graph = {}
        self.directed = directed

    def add_vertex(self, vertex):
        if vertex not in self.graph:
            self.graph[vertex] = []

    def add_edge(self, vertex1, vertex2):
        self.add_vertex(vertex1)
        self.add_vertex(vertex2)
        self.graph[vertex1].append(vertex2)
        if not self.directed:
            self.graph[vertex2].append(vertex1)

    def print_graph(self):
        for vertex, neighbors in self.graph.items():
            print(f"{vertex}: {neighbors}")

# Create an undirected graph
graph = Graph()
graph.add_edge('A', 'B')
graph.add_edge('B', 'C')
graph.print_graph()
```
**Python Graph Libraries**:
- `NetworkX`
- `igraph`
## Big-O Notation - Time Complexity
- Big-O notation is used to say "How code slows as data grows."
	- Describes the performance of an algorithm as the amount of data increases
	- Machine independent
	- Ignores smaller operations O(n+1) -> O(n)
	- n = amount of data