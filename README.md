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




