# Interview Preparation Topics

## 📌 Core Topics to Prepare

### 1. Object-Oriented Programming (OOP)
- **Classes & Objects**
- **Inheritance, Polymorphism, Abstraction, Encapsulation**
- **Interfaces** 
- **Virtual Functions & Abstract Classes**
- **Association and its Types**

---

### 2. Data Structures & Algorithms (DSA)
#### **Data Structures**:
- Arrays, Strings, Linked Lists
- Stacks, Queues
- Trees (Binary Trees, BST, AVL, Heaps)
  - Tree Balancing & Sorting
- Graphs (BFS, DFS, Dijkstra’s, MST)

#### **Algorithms**:
## Data Structures & Algorithms (DSA)

### Searching Algorithms
- Linear Search
- Binary Search
- Depth First Search (DFS)
- Breadth First Search (BFS)

### Sorting Algorithms
- Insertion Sort
- Heap Sort
- Selection Sort
- Merge Sort
- Quick Sort
- Counting Sort
- Bubble Sort
- Bucket Sort
- Radix Sort

### Graph Algorithms
- Dijkstra's Algorithm
- Bellman-Ford Algorithm
- Floyd-Warshall Algorithm
- Topological Sort
- Kruskal's Algorithm

### Array Algorithms
- Floyd's Cycle Detection
- Quick Select

### Advanced Algorithms
- Huffman Coding (Compression)

### Others
- Recursion & Backtracking
- Dynamic Programming
- Greedy Algorithms

---

### 3. Database Management (DB)
- **SQL Queries** (Joins, Subqueries, Aggregations)
- **Normalization** (1NF, 2NF, 3NF, BCNF)
- **Indexing & Transactions** (ACID Properties)
- **NoSQL vs SQL** (MongoDB vs PostgreSQL)

---

### 4. Computer Networks (CN)
- **OSI & TCP/IP Models**
- **HTTP vs HTTPS, DNS, REST APIs**
- **TCP vs UDP** (Connection-oriented vs Connectionless)
- **IP Addressing** (IPv4, Subnetting)

---

### 5. Coding & Problem-Solving
- **Time & Space Complexity** (Big-O Notation)
- **Problem Patterns**:
  - Two Pointers
  - Sliding Window
  - Tree/Graph Traversals
- **Git Basics** (Commit, Branching, Merge Conflicts)

---
---



# 📘 Interview Preparation Guide

---

# 1. 🧠 Object-Oriented Programming (OOP)

Object-Oriented Programming (OOP) is a programming paradigm based on the concept of **“objects”**, which can contain data and code to manipulate the data. It aims to model real-world entities using classes and objects.

---

## 🔹 Classes & Objects

### 🔸 Explanation

- **Class**: A user-defined blueprint or prototype from which objects are created.
- **Object**: An instance of a class. It holds actual values for the attributes defined in the class.

### 🔸 Example:
```cpp
class Car {
public:
    string brand;
    void start() {
        cout << brand << " is starting!" << endl;
    }
};

int main() {
    Car myCar;
    myCar.brand = "Toyota";
    myCar.start();  // Output: Toyota is starting!
}
```

---

## 🔹 Inheritance

### 🔸 Explanation

Inheritance is the process by which one class (child/derived class) acquires the properties and behavior (methods) of another class (parent/base class).

### 🔸 Example:
```cpp
class Animal {
public:
    void sound() {
        cout << "Animal makes a sound" << endl;
    }
};

class Dog : public Animal {
public:
    void bark() {
        cout << "Dog barks" << endl;
    }
};

int main() {
    Dog d;
    d.sound();  // Inherited method
    d.bark();
}
```

---

## 🔹 Polymorphism

### 🔸 Explanation

Polymorphism allows one interface to be used for a general class of actions. The specific action is determined by the exact nature of the situation.

### 🔸 Example:

**Compile-Time Polymorphism (Function Overloading)**:
```cpp
class Print {
public:
    void show(int i) {
        cout << "Integer: " << i << endl;
    }

    void show(string s) {
        cout << "String: " << s << endl;
    }
};
```

**Run-Time Polymorphism (Virtual Functions)**:
```cpp
class Base {
public:
    virtual void print() {
        cout << "Base class print" << endl;
    }
};

class Derived : public Base {
public:
    void print() override {
        cout << "Derived class print" << endl;
    }
};

int main() {
    Base* b = new Derived();
    b->print();  // Output: Derived class print
}
```

---

## 🔹 Abstraction

### 🔸 Explanation

Abstraction hides complex implementation details and shows only the necessary features of an object.

### 🔸 Example:
```cpp
class AbstractDevice {
public:
    virtual void operate() = 0;  // Pure virtual function
};

class Fan : public AbstractDevice {
public:
    void operate() override {
        cout << "Fan is spinning" << endl;
    }
};
```

---

## 🔹 Encapsulation

### 🔸 Explanation

Encapsulation is the process of wrapping data and code into a single unit. Access modifiers control visibility.

### 🔸 Example:
```cpp
class Account {
private:
    int balance;

public:
    void setBalance(int b) {
        if (b >= 0) balance = b;
    }

    int getBalance() {
        return balance;
    }
};
```

---

## 🔹 Virtual Functions & Abstract Classes

### 🔸 Virtual Functions:
Used to achieve run-time polymorphism by overriding functions in derived classes.

### 🔸 Abstract Classes:
Contain at least one pure virtual function. Cannot be instantiated.

### 🔸 Example:
```cpp
class Shape {
public:
    virtual void draw() = 0;  // Abstract method
};

class Circle : public Shape {
public:
    void draw() override {
        cout << "Drawing Circle" << endl;
    }
};
```

---

## 🔹 Interfaces

### 🔸 Explanation:
In C++, an interface is implemented using an abstract class with only pure virtual functions.

### 🔸 Example:
```cpp
class IPrintable {
public:
    virtual void print() = 0;
};

class Document : public IPrintable {
public:
    void print() override {
        cout << "Printing document" << endl;
    }
};
```

---

## 🔹 Association and its Types

### 🔸 Explanation:
Association represents relationships between classes.

### 🔸 Types:

| Type          | Description | Example |
|---------------|-------------|---------|
| Association   | General link between objects | A Doctor and a Patient |
| Aggregation   | "Has-a" - child can exist without parent | A Library has Books |
| Composition   | Strong "Has-a" - child cannot exist without parent | A House has Rooms |

### 🔸 Code Example for Aggregation:
```cpp
class Engine {
public:
    void start() {
        cout << "Engine starting..." << endl;
    }
};

class Car {
private:
    Engine* engine;  // Aggregation
public:
    Car(Engine* e) : engine(e) {}
    void startCar() {
        engine->start();
    }
};
```

### 🔸 Code Example for Composition:
```cpp
class Brain {
public:
    void think() {
        cout << "Thinking..." << endl;
    }
};

class Human {
private:
    Brain brain;  // Composition
public:
    void useBrain() {
        brain.think();
    }
};
```

# 📚 Data Structures & Algorithms (DSA) Guide

## 🏗️ Data Structures

---

### 🔹 Arrays
**Description:**  
Contiguous memory locations storing elements of the same type.

**Operations:**
- Access: O(1)
- Search: O(n)
- Insertion/Deletion: O(n)

```cpp
int arr[5] = {1, 2, 3, 4, 5};
cout << arr[2];  // Output: 3
```


### 🔹 Linked Lists
**Description:**  
Linear collection where elements (nodes) contain data + pointer to next node.

**Types:**
- Singly Linked
- Doubly Linked
- Circular

```cpp
struct Node {
    int data;
    Node* next;
};

Node* head = new Node{1, new Node{2, nullptr}};
```


# 📘 Data Structures & Algorithms (DSA)

---

## 🧱 Data Structures

### 1. Arrays
**Description**: Arrays are a collection of elements stored at contiguous memory locations. They allow fast access using an index.

**Example**:
```cpp
int arr[5] = {1, 2, 3, 4, 5};
cout << arr[2]; // Output: 3
```

---

### 2. Strings
**Description**: Strings are arrays of characters ending with a null character (`\0`). C++ provides the `string` class for dynamic strings.

**Example**:
```cpp
string s = "Hello";
cout << s.length(); // Output: 5
```

---

### 3. Linked Lists
**Description**: A linear data structure where elements are stored in nodes and each node points to the next.

**Example**:
```cpp
struct Node {
    int data;
    Node* next;
};
```

---

### 4. Stacks
**Description**: Follows Last In First Out (LIFO) principle.

**Example**:
```cpp
stack<int> st;
st.push(10); st.pop();
```

---

### 5. Queues
**Description**: Follows First In First Out (FIFO) principle.

**Example**:
```cpp
queue<int> q;
q.push(20); q.pop();
```

---

### 6. Trees (Binary, BST, AVL, Heap)
**Description**: Hierarchical structure. BST keeps data ordered, AVL is self-balancing, and heaps maintain a heap property.

**Example** (BST Insertion):
```cpp
struct Node {
    int data;
    Node *left, *right;
    Node(int val): data(val), left(NULL), right(NULL) {}
};
```

---

### 7. Graphs
**Description**: Consists of nodes (vertices) and edges. Can be directed/undirected.

**Example**:
```cpp
vector<int> graph[100];
graph[0].push_back(1);
```

---

## 🔍 Searching Algorithms

### 1. Linear Search
**Description**: Search each element until match is found.

**Example**:
```cpp
for (int i = 0; i < n; i++)
    if (arr[i] == x) return i;
```

---

### 2. Binary Search
**Description**: Efficient search on sorted array by dividing into halves.

**Example**:
```cpp
int binarySearch(int arr[], int l, int r, int x);
```

---

### 3. DFS (Depth First Search)
**Description**: Explore as far as possible along each branch.

**Example**:
```cpp
void DFS(int v) {
    visited[v] = true;
    for (int u : adj[v])
        if (!visited[u]) DFS(u);
}
```

---

### 4. BFS (Breadth First Search)
**Description**: Explore neighbor nodes level by level.

**Example**:
```cpp
queue<int> q;
q.push(start);
visited[start] = true;
```

---

## 📊 Sorting Algorithms

### Insertion Sort
```cpp
for (int i = 1; i < n; i++) {
    int key = arr[i], j = i - 1;
    while (j >= 0 && arr[j] > key) arr[j + 1] = arr[j--];
    arr[j + 1] = key;
}
```

### Heap Sort
**Uses heap to extract elements in sorted order.**

### Selection Sort
**Selects minimum and places in correct position.**

### Merge Sort
**Divide and conquer sorting technique.**

### Quick Sort
**Choose pivot, partition, and sort recursively.**

### Counting Sort
**Used for small range integers.**

### Bubble Sort
```cpp
for (int i = 0; i < n-1; i++)
    for (int j = 0; j < n-i-1; j++)
        if (arr[j] > arr[j+1]) swap(arr[j], arr[j+1]);
```

### Bucket Sort & Radix Sort
**Used for integer or floating-point sorting with known range.**

---

## 🌐 Graph Algorithms

### Dijkstra's Algorithm
**Finds shortest paths from source to all nodes.**

### Bellman-Ford Algorithm
**Handles negative weights too.**

### Floyd-Warshall Algorithm
**All-pairs shortest paths.**

### Topological Sort
**Ordering of vertices in DAG.**

### Kruskal's Algorithm
**Minimum Spanning Tree using Union-Find.**

---

## 📈 Array Algorithms

### Floyd’s Cycle Detection
**Detects loop in linked list.**

### Quick Select
**Find kth smallest/largest element.**

---

## 🔁 Advanced Algorithms

### Huffman Coding
**Greedy compression algorithm.**

---

## 🧠 Other Topics

### Recursion & Backtracking
**Recursive solutions exploring all possibilities.**

### Dynamic Programming
**Solving problems by combining subproblem results.**

### Greedy Algorithms
**Locally optimal choice aiming for global optimum.**




